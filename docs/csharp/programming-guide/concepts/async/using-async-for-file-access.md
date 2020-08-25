---
title: Asynchroniczny dostęp do plików (C#)
description: Dowiedz się, jak korzystać z funkcji asynchronicznej w celu uzyskiwania dostępu do plików w języku C#. Można wywołać metody asynchroniczne bez używania wywołań zwrotnych lub dzieląc kod w różnych metodach.
ms.date: 08/19/2020
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
ms.openlocfilehash: 9a8db6004e8fff2cb39f0c350b403b56ea619e54
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812045"
---
# <a name="asynchronous-file-access-c"></a>Asynchroniczny dostęp do plików (C#)

Do uzyskiwania dostępu do plików można użyć funkcji asynchronicznej. Za pomocą funkcji asynchronicznej można wywołać metody asynchroniczne bez używania wywołań zwrotnych lub dzieląc kod w wielu metodach lub wyrażeniach lambda. Aby przeprowadzić synchroniczne asynchroniczne kod, wystarczy wywołać metodę asynchroniczną zamiast metody synchronicznej i dodać kilka słów kluczowych do kodu.

Aby dodać asynchroniczności do wywołań dostępu do plików, należy wziąć pod uwagę następujące przyczyny:

> [!div class="checklist"]
>
> - Asynchroniczności sprawia, że aplikacje interfejsu użytkownika działają szybciej, ponieważ wątek interfejsu użytkownika uruchamiający operację może wykonać inne czynności. Jeśli wątek interfejsu użytkownika musi wykonać kod, który zajmuje dużo czasu (na przykład więcej niż 50 milisekund), interfejs użytkownika może się zamrozić do momentu zakończenia operacji we/wy, a wątek interfejsu użytkownika może ponownie przetwarzać dane wejściowe klawiatury i myszy oraz inne zdarzenia.
> - Asynchroniczności poprawia skalowalność ASP.NET i innych aplikacji opartych na serwerze, zmniejszając potrzebę wątków. Jeśli aplikacja korzysta z dedykowanego wątku na odpowiedź i jednocześnie są obsługiwane tysiące żądań, są zbędne tysiące wątków. Operacje asynchroniczne często nie muszą używać wątku podczas oczekiwania. Z chwilą korzystają z istniejącego wątku zakończenia operacji we/wy.
> - Opóźnienie operacji dostępu do pliku może być bardzo niskie w bieżących warunkach, ale opóźnienie może znacznie wzrosnąć w przyszłości. Na przykład plik można przenieść na serwer, na którym znajduje się na całym świecie.
> - Dodatkowe obciążenie związane z korzystaniem z funkcji asynchronicznej jest małe.
> - Zadania asynchroniczne można łatwo uruchomić równolegle.

## <a name="use-appropriate-classes"></a>Użyj odpowiednich klas

Proste przykłady w tym temacie pokazują <xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType> i <xref:System.IO.File.ReadAllTextAsync%2A?displayProperty=nameWithType> . W celu uzyskania ograniczonej kontroli nad operacjami we/wy pliku Użyj <xref:System.IO.FileStream> klasy, która powoduje, że asynchroniczne operacje we/wy są wykonywane na poziomie systemu operacyjnego. Korzystając z tej opcji, można uniknąć blokowania wątku puli wątków w wielu przypadkach. Aby włączyć tę opcję, należy określić `useAsync=true` argument or `options=FileOptions.Asynchronous` w wywołaniu konstruktora.

Nie można użyć tej opcji razem z <xref:System.IO.StreamReader> i, <xref:System.IO.StreamWriter> Jeśli otworzysz je bezpośrednio, określając ścieżkę pliku. Można jednak użyć tej opcji, jeśli podajesz im <xref:System.IO.Stream> , że została <xref:System.IO.FileStream> otwarta Klasa. Wywołania asynchroniczne są szybsze w aplikacjach interfejsu użytkownika, nawet jeśli wątek puli wątków jest zablokowany, ponieważ wątek interfejsu użytkownika nie jest blokowany podczas oczekiwania.

## <a name="write-text"></a>Zapisz tekst

Poniższe przykłady zapisują tekst do pliku. W każdej instrukcji Await Metoda natychmiast opuszcza. Po zakończeniu operacji we/wy pliku Metoda zostaje wznowiona przy użyciu instrukcji, która następuje po instrukcji Await. Modyfikator Async jest w definicji metod, które używają instrukcji Await.

### <a name="simple-example"></a>Prosty przykład

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleWrite":::

### <a name="finite-control-example"></a>Przykład skończonego formantu

:::code language="csharp" source="snippets/file-access/Program.cs" id="WriteText":::

Oryginalny przykład zawiera instrukcję `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);` , która jest umową obejmującą następujące dwie instrukcje:

```csharp
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);
await theTask;
```

Pierwsza instrukcja zwraca zadanie i powoduje uruchomienie przetwarzania plików. Druga instrukcja z Await powoduje, że metoda natychmiast zakończy działanie i zwróci inne zadanie. Po późniejszym zakończeniu przetwarzania plików wykonanie powraca do instrukcji, która następuje po oczekiwania.

## <a name="read-text"></a>Odczytaj tekst

Poniższe przykłady odczytują tekst z pliku.

### <a name="simple-example"></a>Prosty przykład

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleRead":::

### <a name="finite-control-example"></a>Przykład skończonego formantu

Tekst jest buforowany i, w tym przypadku, umieszczony w <xref:System.Text.StringBuilder> . W przeciwieństwie do poprzedniego przykładu, obliczanie oczekiwania powoduje utworzenie wartości. <xref:System.IO.Stream.ReadAsync%2A>Metoda zwraca <xref:System.Threading.Tasks.Task> \<<xref:System.Int32>>, więc Ocena await generuje `Int32` wartość `numRead` po zakończeniu operacji. Aby uzyskać więcej informacji, zobacz [asynchroniczne typy zwracane (C#)](async-return-types.md).

:::code language="csharp" source="snippets/file-access/Program.cs" id="ReadText":::

## <a name="parallel-asynchronous-io"></a>Równoległe asynchroniczne operacje we/wy

W poniższych przykładach pokazano przetwarzanie równoległe, pisząc 10 plików tekstowych.

### <a name="simple-example"></a>Prosty przykład

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleParallelWrite":::

### <a name="finite-control-example"></a>Przykład skończonego formantu

Dla każdego pliku <xref:System.IO.Stream.WriteAsync%2A> Metoda zwraca zadanie, które jest następnie dodawane do listy zadań. `await Task.WhenAll(tasks);`Instrukcja kończy metodę i wznawia działanie w ramach metody po zakończeniu przetwarzania plików dla wszystkich zadań.

Przykład zamyka wszystkie <xref:System.IO.FileStream> wystąpienia w `finally` bloku po zakończeniu zadań. Jeśli każdy z `FileStream` nich został utworzony w `using` instrukcji, `FileStream` może zostać usunięty przed ukończeniem zadania.

Wszelkie zwiększenia wydajności są niemal całkowicie od przetwarzania równoległego, a nie do przetwarzania asynchronicznego. Zalety asynchroniczności są takie same, że nie wiążą się z wieloma wątkami i nie wiążą się z wątkiem interfejsu użytkownika.

:::code language="csharp" source="snippets/file-access/Program.cs" id="ParallelWriteText":::

W przypadku korzystania <xref:System.IO.Stream.WriteAsync%2A> z <xref:System.IO.Stream.ReadAsync%2A> metod i można określić <xref:System.Threading.CancellationToken> , której można użyć do anulowania strumienia średniej operacji. Aby uzyskać więcej informacji, zobacz [Anulowanie w zarządzanych wątkach](../../../../standard/threading/cancellation-in-managed-threads.md).

## <a name="see-also"></a>Zobacz też

- [Programowanie asynchroniczne z Async i Await (C#)](index.md)
- [Asynchroniczne typy zwracane (C#)](async-return-types.md)
