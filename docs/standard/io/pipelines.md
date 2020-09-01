---
title: Potoki we/wy — .NET
description: Dowiedz się, jak efektywnie korzystać z potoków we/wy w programie .NET i uniknąć problemów w kodzie.
ms.date: 08/27/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- Pipelines
- Pipelines I/O
- I/O [.NET], Pipelines
author: rick-anderson
ms.author: riande
ms.openlocfilehash: a24d7f5c22c936cd3fd3fdc51f0f3ace56386574
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271987"
---
# <a name="systemiopipelines-in-net"></a>System. IO. potoki w środowisku .NET

<xref:System.IO.Pipelines> to nowa biblioteka, która umożliwia łatwiejsze wykonywanie operacji we/wy na platformie .NET. Jest to biblioteka ukierunkowana .NET Standard, która działa na wszystkich implementacjach platformy .NET.

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a>Jaki problem rozwiązuje system. IO. potoki

<!-- corner case doesn't MT (machine translate)   -->
Aplikacje, które analizują dane przesyłane strumieniowo, składają się z kodu standardowego, który ma wiele wyspecjalizowanych i nietypowych przepływów kodu. Kod standardowy i szczególny przypadek jest skomplikowany i trudny do utrzymania.

`System.IO.Pipelines` został zaprojektowany z myślą o:

* Przeanalizowanie danych przesyłanych strumieniowo o wysokiej wydajności.
* Zmniejsz złożoność kodu.

Poniższy kod jest typowy dla serwera TCP, który odbiera komunikaty rozdzielane wierszami (rozdzielane przez `'\n'` ) od klienta:

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

Poprzedni kod zawiera kilka problemów:

* Cały komunikat (koniec wiersza) może nie zostać odebrany w jednym wywołaniu do `ReadAsync` .
* Wynik jest ignorowany `stream.ReadAsync` . `stream.ReadAsync` Zwraca ilość odczytanych danych.
* Nie obsługuje przypadku, w którym wiele wierszy jest odczytywanych w pojedynczym `ReadAsync` wywołaniu.
* Przydziela `byte` tablicę do każdego odczytu.

Aby rozwiązać powyższe problemy, wymagane są następujące zmiany:

* Buforuj dane przychodzące do momentu znalezienia nowego wiersza.
* Przeanalizuj wszystkie wiersze zwrócone w buforze.
* Istnieje możliwość, że wiersz jest większy niż 1 KB (1024 bajtów). Kod musi zmienić rozmiar buforu wejściowego do momentu, w którym zostanie znaleziony ogranicznik, aby dopasować cały wiersz w buforze.

  * Jeśli rozmiar buforu jest zmieniany, w danych wejściowych są umieszczane więcej kopii buforów.
  * Aby zmniejszyć ilość zajętego miejsca, należy skompaktować bufor używany do odczytywania wierszy.

* Rozważ użycie puli buforów, aby uniknąć wielokrotnego przydzielania pamięci.
* Poniższy kod dotyczy niektórych z następujących problemów:

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs" id="snippet":::

Poprzedni kod jest skomplikowany i nie dotyczy wszystkich zidentyfikowanych problemów. Wysoka wydajność sieci zwykle oznacza pisanie bardzo złożonego kodu w celu zmaksymalizowania wydajności. `System.IO.Pipelines` została zaprojektowana, aby ułatwić pisanie tego typu kodu.

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="pipe"></a>Wodzie

<xref:System.IO.Pipelines.Pipe>Klasy można użyć do utworzenia `PipeWriter/PipeReader` pary. Wszystkie dane zapisywane w `PipeWriter` programie są dostępne w `PipeReader` :

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet2":::

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a>Podstawowe użycie potoków

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet":::

Istnieją dwie pętle:

* `FillPipeAsync` odczytuje z `Socket` i zapisuje dane w `PipeWriter` .
* `ReadPipeAsync` odczytuje z `PipeReader` i analizuje linie przychodzące.

Nie ma żadnych jawnie przyznanych buforów. Wszystkie Zarządzanie buforem jest delegowane `PipeReader` do `PipeWriter` implementacji i. Delegowanie zarządzania buforem ułatwia wykorzystywanie kodu do skoncentrowania się wyłącznie na logice biznesowej.

W pierwszej pętli:

* <xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> jest wywoływana w celu uzyskania pamięci z bazowego składnika zapisywania.
* <xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> jest wywoływana w celu poinformowania o `PipeWriter` ilości danych, które zostały zapisaną w buforze.
* <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> jest wywoływana, aby udostępnić dane dla `PipeReader` .

W drugiej pętli, `PipeReader` zużywa bufory zapisywane przez `PipeWriter` . Bufory pochodzą z gniazda. Wywołanie `PipeReader.ReadAsync` :

* Zwraca wartość zawierającą <xref:System.IO.Pipelines.ReadResult> dwie ważne informacje:

  * Dane, które zostały odczytane w postaci `ReadOnlySequence<byte>` .
  * Wartość logiczna `IsCompleted` wskazująca, czy osiągnięto koniec danych (EOF).

Po znalezieniu ogranicznika końca wiersza (EOL) i przeanalizowaniu wiersza:

* Logika przetwarza bufor, aby pominąć operacje, które zostały już przetworzone.
* `PipeReader.AdvanceTo` jest wywoływana, aby określić ilość `PipeReader` danych, które zostały zużyte i zbadane.

Pętle czytnika i składnika zapisywania kończą się przez wywołanie `Complete` . `Complete` umożliwia potoku w celu zwolnienia pamięci do przydzielenia.

### <a name="backpressure-and-flow-control"></a>Sterowanie ruchem wstecznym i przepływem

Najlepiej, odczytując i przeanalizować współpracę:

* Wątek pisania wykorzystuje dane z sieci i umieszcza je w buforach.
* Wątek analizy jest odpowiedzialny za konstruowanie odpowiednich struktur danych.

Zwykle analiza zajmuje więcej czasu niż tylko kopiowanie bloków danych z sieci:

* Wątek odczytywania pobiera przed wątkiem analizy.
* Wątek odczytu musi spowolnić lub przydzielić więcej pamięci, aby przechowywać dane dla wątku analizy.

W celu uzyskania optymalnej wydajności istnieje równowaga między częste Wstrzymywanie i przydzielania większej ilości pamięci.

Aby rozwiązać ten problem, program `Pipe` ma dwa ustawienia umożliwiające sterowanie przepływem danych:

* <xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Określa, ile danych ma być buforowanych przed wywołaniem do <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> wstrzymania.
* <xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Określa, ile danych musi obserwować czytelnik przed wywołaniem `PipeWriter.FlushAsync` wznowienia.

![Diagram z ResumeWriterThreshold i PauseWriterThreshold](media/pipelines/resume-pause.png)

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:

* Zwraca wartość niekompletną `ValueTask<FlushResult>` , gdy ilość danych w `Pipe` krzyżach `PauseWriterThreshold` .
* Kończy działanie `ValueTask<FlushResult>` , gdy zostanie ono mniejsze niż `ResumeWriterThreshold` .

Dwie wartości są używane, aby zapobiec szybkiemu cyklowi, który może wystąpić w przypadku użycia jednej wartości.

### <a name="examples"></a>Przykłady

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a>PipeScheduler

Zazwyczaj przy użyciu `async` i `await` , kod asynchroniczny jest wznawiany na <xref:System.Threading.Tasks.TaskScheduler> lub na bieżącym <xref:System.Threading.SynchronizationContext> .

Podczas wykonywania operacji we/wy należy mieć precyzyjną kontrolę nad tym, gdzie jest wykonywane wykonywanie operacji we/wy. Ta kontrolka umożliwia efektywne wykorzystanie pamięci podręcznych procesora CPU. Wydajne buforowanie ma kluczowe znaczenie dla aplikacji o wysokiej wydajności, takich jak serwery sieci Web. <xref:System.IO.Pipelines.PipeScheduler> zapewnia kontrolę nad miejscem, w którym są uruchamiane asynchroniczne wywołania zwrotne. Domyślnie:

* Bieżąca <xref:System.Threading.SynchronizationContext> jest używana.
* Jeśli nie istnieje `SynchronizationContext` , używa puli wątków do uruchamiania wywołań zwrotnych.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Program.cs" id="snippet":::

[PipeScheduler.](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) Threading to <xref:System.IO.Pipelines.PipeScheduler> implementacja, która kolejkuje wywołania zwrotne do puli wątków. `PipeScheduler.ThreadPool` jest to ustawienie domyślne i ogólnie najlepszym wyborem. [PipeScheduler. inline](xref:System.IO.Pipelines.PipeScheduler.Inline) może spowodować niezamierzone konsekwencje, takie jak zakleszczenia.

### <a name="pipe-reset"></a>Resetowanie potoku

Często wydajnym rozwiązaniem jest ponowne użycie `Pipe` obiektu. Aby zresetować potok, wywołaj <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> po zakończeniu obu `PipeReader` i `PipeWriter` .

## <a name="pipereader"></a>PipeReader

<xref:System.IO.Pipelines.PipeReader> zarządza pamięcią w imieniu obiektu wywołującego. **Zawsze** wywołuj <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> po wywołaniu <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType> . Dzięki temu `PipeReader` wiadomo, kiedy obiekt wywołujący jest wykonywany z pamięcią, aby można było go śledzić. Wartość `ReadOnlySequence<byte>` zwracana z `PipeReader.ReadAsync` jest prawidłowa tylko do momentu wywołania metody `PipeReader.AdvanceTo` . Użycie po wywołaniu nie jest dozwolone `ReadOnlySequence<byte>` `PipeReader.AdvanceTo` .

`PipeReader.AdvanceTo` przyjmuje dwa <xref:System.SequencePosition> argumenty:

* Pierwszy argument określa, ile pamięci zostało zużyte.
* Drugi argument określa, jaka część buforu została zaobserwowana.

Oznaczenie danych jako zużyte oznacza, że potok może zwrócić pamięć do źródłowej puli buforów. Oznaczanie danych jako obserwowanych kontroluje, jak następne wywołanie ma zostać wykonane `PipeReader.ReadAsync` . Oznaczenie wszystkiego jako zaobserwowane oznacza, że następne wywołanie `PipeReader.ReadAsync` nie zostanie zwrócone do momentu zapisania większej ilości danych w potoku. Wszystkie inne wartości spowodują, że następne wywołanie `PipeReader.ReadAsync` zwróci natychmiast z obserwowanymi *i* nieobserwowanymi danymi, ale nie wykorzystano już danych.

### <a name="read-streaming-data-scenarios"></a>Odczytaj scenariusze przesyłania strumieniowego danych

Istnieje kilka typowych wzorców, które nastąpiły podczas próby odczytu danych przesyłanych strumieniowo:

* Przy użyciu strumienia danych Przeanalizuj pojedynczy komunikat.
* Przy użyciu strumienia danych Przeanalizuj wszystkie dostępne komunikaty.

W poniższych przykładach użyto `TryParseMessage` metody analizowania komunikatów z `ReadOnlySequence<byte>` . `TryParseMessage` analizuje pojedynczy komunikat i aktualizuje bufor wejściowy, aby przyciąć przeanalizowany komunikat z bufora. `TryParseMessage` Program nie jest częścią programu .NET. jest to metoda zapisywana przez użytkownika użyta w poniższych sekcjach.

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a>Odczytaj pojedynczy komunikat

Poniższy kod odczytuje pojedynczy komunikat z `PipeReader` i zwraca go do obiektu wywołującego.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs" id="snippet":::

Powyższy kod ma następujące działanie:

* Analizuje pojedynczy komunikat.
* Aktualizuje zużyte `SequencePosition` i sprawdzone pod kątem `SequencePosition` początku przyciętego buforu wejściowego.

Dwa `SequencePosition` argumenty są aktualizowane, ponieważ `TryParseMessage` usuwa przeanalizowany komunikat z bufora wejściowego. Ogólnie rzecz biorąc, podczas analizowania pojedynczej wiadomości z bufora pozycja zbadana powinna mieć jedną z następujących wartości:

* Koniec komunikatu.
* Koniec odebranego buforu, jeśli nie odnaleziono komunikatu.

Przypadek z pojedynczym komunikatem ma największą możliwość wystąpienia błędów. Przekazanie nieprawidłowych wartości do *zbadania* może spowodować wyjątek braku pamięci lub nieskończoną pętlę. Aby uzyskać więcej informacji, zobacz sekcję [typowe problemy związane z PipeReader](#gotchas) w tym artykule.

### <a name="reading-multiple-messages"></a>Odczytywanie wielu wiadomości

Poniższy kod odczytuje wszystkie komunikaty z `PipeReader` wywołań i `ProcessMessageAsync` na każdym z nich.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection1.cs" id="snippet":::

### <a name="cancellation"></a>Anulowanie

`PipeReader.ReadAsync`:

* Obsługuje przekazywanie <xref:System.Threading.CancellationToken> .
* Zgłasza, <xref:System.OperationCanceledException> czy element `CancellationToken` jest anulowany, gdy istnieje oczekujące odczytanie.
* Obsługuje sposób anulowania bieżącej operacji odczytu za pośrednictwem <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType> , co pozwala uniknąć wywoływania wyjątku. Wywołanie `PipeReader.CancelPendingRead` powoduje, że bieżące lub następne wywołanie w `PipeReader.ReadAsync` celu zwrócenia elementu <xref:System.IO.Pipelines.ReadResult> z `IsCanceled` ustawionym na `true` . Może to być przydatne w przypadku zatrzymania istniejącej pętli odczytu w nieniszczącej i niewyjątkowy sposób.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection.cs" id="snippet":::

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a>PipeReader typowe problemy

* Przekazanie nieprawidłowych wartości do `consumed` lub `examined` może spowodować odczyt danych, które zostały już odczytane.
* Przekazanie `buffer.End` jako badane może skutkować:

  * Dane wstrzymane
  * Ewentualny wyjątek braku pamięci (OOM), jeśli dane nie są używane. Na przykład `PipeReader.AdvanceTo(position, buffer.End)` podczas przetwarzania pojedynczego komunikatu w czasie z buforu.

* Przekazanie nieprawidłowych wartości do `consumed` lub `examined` może skutkować pętlą nieskończoną. Na przykład, `PipeReader.AdvanceTo(buffer.Start)` Jeśli `buffer.Start` nie zmieniono, spowoduje to, że następne wywołanie zostanie `PipeReader.ReadAsync` zwrócone natychmiast przed nadejściem nowych danych.
* Przekazanie nieprawidłowych wartości do `consumed` lub `examined` może spowodować nieskończone buforowanie (ostateczne OOM).
* Użycie `ReadOnlySequence<byte>` po wywołaniu `PipeReader.AdvanceTo` może spowodować uszkodzenie pamięci (za darmo).
* Niepowodzenie wywołania `PipeReader.Complete/CompleteAsync` może spowodować przeciek pamięci.
* Sprawdzanie <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> i kończenie logiki odczytu przed przetworzeniem buforu powoduje utratę danych. Warunek zakończenia pętli powinien opierać się na `ReadResult.Buffer.IsEmpty` i `ReadResult.IsCompleted` . Nieprawidłowe działanie może spowodować powstanie pętli nieskończonej.

#### <a name="problematic-code"></a>Problematyczny kod

❌**Utrata danych**

`ReadResult`Może zwrócić końcowy segment danych, gdy `IsCompleted` jest ustawiony na `true` . Nie można odczytać tych danych przed wyjściem z pętli odczytu spowoduje utratę danych.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌**Nieskończona pętla**

Poniższa logika może spowodować nieskończoną pętlę, jeśli `Result.IsCompleted` jest, `true` ale nigdy nie pełny komunikat w buforze.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet2":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

Oto inny fragment kodu z tym samym problemem. Sprawdzanie niepustego buforu przed sprawdzeniem `ReadResult.IsCompleted` . Ponieważ znajduje się w `else if` , będzie ona zapętlać w nieskończoność, jeśli w buforze nigdy nie ma kompletnego komunikatu.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet3":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌**Nieoczekiwany zawieszenie**

Bezwarunkowe wywoływanie `PipeReader.AdvanceTo` przy użyciu `buffer.End` w `examined` położeniu może spowodować zawieszenie podczas analizowania pojedynczego komunikatu. Następne wywołanie `PipeReader.AdvanceTo` nie zwróci do momentu:

* Więcej danych jest zapisywana w potoku.
* Nowe dane nie były wcześniej badane.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet4":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌Za **mało pamięci (OOM)**

W następujących warunkach Poniższy kod przechowuje buforowanie do momentu <xref:System.OutOfMemoryException> wystąpienia:

* Nie ma maksymalnego rozmiaru wiadomości.
* Dane zwrócone z `PipeReader` nie pełnią komunikatu. Na przykład nie wykonuje pełnego komunikatu, ponieważ druga strona zapisuje dużą wiadomość (na przykład komunikat 4 GB).

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet5":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌**Uszkodzenie pamięci**

Podczas pisania pomocników odczytujących bufor należy skopiować wszystkie zwrócone ładunki przed wywołaniem `Advance` . Poniższy przykład zwróci pamięć, która `Pipe` została odrzucona i może ponownie użyć dla następnej operacji (odczyt/zapis).

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippetMessage":::

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet6":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a>PipeWriter

<xref:System.IO.Pipelines.PipeWriter>Zarządza buforami do zapisu w imieniu obiektu wywołującego. `PipeWriter` implementuje [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601) . `IBufferWriter<byte>` umożliwia uzyskanie dostępu do buforów w celu wykonywania operacji zapisu bez dodatkowych kopii buforów.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet":::

Poprzedni kod:

* Żąda bufora co najmniej 5 bajtów z `PipeWriter` polecenia using <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> .
* Zapisuje bajty dla ciągu ASCII `"Hello"` zwracanego `Memory<byte>` .
* Wywołania <xref:System.IO.Pipelines.PipeWriter.Advance%2A> wskazujące, ile bajtów Zapisano w buforze.
* Opróżnia `PipeWriter` , który wysyła bajty do urządzenia bazowego.

Poprzednia metoda pisania używa buforów dostarczonych przez `PipeWriter` . Alternatywnie <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType> :

* Kopiuje istniejący bufor do `PipeWriter` .
* Wywołania `GetSpan` , `Advance` zgodnie z potrzebami i wywołania <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> .

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet2":::

### <a name="cancellation"></a>Anulowanie

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> obsługuje przekazywanie <xref:System.Threading.CancellationToken> . Przekazywanie `CancellationToken` wyników w `OperationCanceledException` przypadku, gdy token zostanie anulowany, gdy istnieje oczekująca operacja opróżniania. `PipeWriter.FlushAsync` obsługuje sposób anulowania bieżącej operacji opróżniania za pośrednictwem <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> bez podnoszenia wyjątku. Wywołanie `PipeWriter.CancelPendingFlush` powoduje, że bieżące lub następne wywołanie `PipeWriter.FlushAsync` lub `PipeWriter.WriteAsync` zwraca element <xref:System.IO.Pipelines.FlushResult> z `IsCanceled` ustawioną na `true` . Może to być przydatne w przypadku zatrzymania opróżniania w sposób nieniszczący i niewyjątkowy.

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a>PipeWriter typowe problemy

* <xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> i <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> Zwróć bufor z co najmniej żądaną ilością pamięci. **Nie** zakładaj dokładnie rozmiarów buforów.
* Nie ma gwarancji, że kolejne wywołania będą zwracać ten sam bufor lub bufor o takim samym rozmiarze.
* Należy zażądać nowego buforu po wywołaniu <xref:System.IO.Pipelines.PipeWriter.Advance%2A> , aby kontynuować zapisywanie większej ilości danych. Nie można zapisać wcześniej uzyskanego buforu.
* Wywołanie `GetMemory` lub `GetSpan` niekompletne wywołanie do `FlushAsync` nie jest bezpieczne.
* Wywołanie `Complete` lub `CompleteAsync` nieopróżnione dane mogą spowodować uszkodzenie pamięci.

## <a name="iduplexpipe"></a>IDuplexPipe

<xref:System.IO.Pipelines.IDuplexPipe>Jest to kontrakt dla typów, które obsługują odczyt i zapis. Na przykład połączenie sieciowe będzie reprezentowane przez `IDuplexPipe` .

 W przeciwieństwie do `Pipe` , który zawiera `PipeReader` a `PipeWriter` i `IDuplexPipe` , reprezentuje jedną stronę połączenia pełnego dupleksu. Oznacza to, że zapis w `PipeWriter` programie nie zostanie odczytany z `PipeReader` .

## <a name="streams"></a>Strumienie

Podczas odczytywania lub zapisywania danych strumienia zwykle dane są odczytywane przy użyciu deserializatora i zapisu danych przy użyciu serializatora. Większość z tych interfejsów API odczytu i zapisu ma `Stream` parametr. Aby ułatwić integrację z tymi istniejącymi interfejsami API `PipeReader` i `PipeWriter` uwidocznić <xref:System.IO.Pipelines.PipeReader.AsStream%2A> metodę. <xref:System.IO.Pipelines.PipeWriter.AsStream%2A> zwraca `Stream` implementację otaczającą `PipeReader` lub `PipeWriter` .

### <a name="stream-example"></a>Przykład strumienia

`PipeReader``PipeWriter`wystąpienia można tworzyć przy użyciu metod statycznych, które mają `Create` <xref:System.IO.Stream> obiekt i opcjonalne odpowiednie opcje tworzenia.

<xref:System.IO.Pipelines.StreamPipeReaderOptions>Zezwól na kontrolę nad tworzeniem `PipeReader` wystąpienia z następującymi parametrami:

- <xref:System.IO.Pipelines.StreamPipeReaderOptions.BufferSize?displayProperty=nameWithType> jest minimalnym rozmiarem buforu w bajtach używanym podczas dzierżawienia pamięci z puli, a wartością domyślną jest `4096` .
- <xref:System.IO.Pipelines.StreamPipeReaderOptions.LeaveOpen?displayProperty=nameWithType> Flaga określa, czy źródłowy strumień pozostał otwarty po `PipeReader` zakończeniu i ma wartość domyślną `false` .
- <xref:System.IO.Pipelines.StreamPipeReaderOptions.MinimumReadSize?displayProperty=nameWithType> reprezentuje próg pozostałych bajtów w buforze przed przydzieleniem nowego buforu i wartością domyślną `1024` .
- <xref:System.IO.Pipelines.StreamPipeReaderOptions.Pool?displayProperty=nameWithType> jest `MemoryPool<byte>` używany podczas przydzielania pamięci, a wartość domyślna to `null` .

<xref:System.IO.Pipelines.StreamPipeWriterOptions>Zezwól na kontrolę nad tworzeniem `PipeWriter` wystąpienia z następującymi parametrami:

- <xref:System.IO.Pipelines.StreamPipeWriterOptions.LeaveOpen?displayProperty=nameWithType> Flaga określa, czy źródłowy strumień pozostał otwarty po `PipeWriter` zakończeniu i ma wartość domyślną `false` .
- <xref:System.IO.Pipelines.StreamPipeWriterOptions.MinimumBufferSize?displayProperty=nameWithType> reprezentuje minimalny rozmiar buforu, który ma być używany podczas dzierżawy pamięci z <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool> i domyślnie `4096` .
- <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool?displayProperty=nameWithType> jest `MemoryPool<byte>` używany podczas przydzielania pamięci, a wartość domyślna to `null` .

> [!IMPORTANT]
> Podczas tworzenia `PipeReader` `PipeWriter` wystąpień i używania `Create` metod należy wziąć pod uwagę `Stream` okres istnienia obiektu. Jeśli potrzebny jest dostęp do strumienia po zakończeniu czytelnika lub składnika zapisywania, należy ustawić `LeaveOpen` flagę `true` na opcje tworzenia. W przeciwnym razie strumień zostanie zamknięty.

Poniższy kod ilustruje tworzenie `PipeReader` `PipeWriter` wystąpień i przy użyciu `Create` metod ze strumienia.

:::code language="csharp" source="snippets/pipelines/Program.cs":::

Aplikacja używa programu, <xref:System.IO.StreamReader> Aby odczytać plik *lorem-ipsum.txt* jako strumień. <xref:System.IO.FileStream>Jest przenoszona do <xref:System.IO.Pipelines.PipeReader.Create%2A?displayProperty=nameWithType> , który tworzy wystąpienie `PipeReader` obiektu. Aplikacja konsolowa przekazuje następnie swój standardowy strumień wyjściowy do <xref:System.IO.Pipelines.PipeWriter.Create%2A?displayProperty=nameWithType> użycia <xref:System.Console.OpenStandardOutput?displayProperty=nameWithType> . Przykład obsługuje [Anulowanie](#cancellation).
