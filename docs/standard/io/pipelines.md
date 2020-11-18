---
title: Potoki we/wy — .NET
description: Dowiedz się, jak efektywnie korzystać z potoków we/wy w programie .NET i uniknąć problemów w kodzie.
ms.date: 08/27/2020
helpviewer_keywords:
- Pipelines
- Pipelines I/O
- I/O [.NET], Pipelines
author: rick-anderson
ms.author: riande
ms.openlocfilehash: 508ae0e2b854f81ee639a63063a8f6d73ae84863
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830639"
---
# <a name="systemiopipelines-in-net"></a><span data-ttu-id="1c649-103">System. IO. potoki w środowisku .NET</span><span class="sxs-lookup"><span data-stu-id="1c649-103">System.IO.Pipelines in .NET</span></span>

<span data-ttu-id="1c649-104"><xref:System.IO.Pipelines> to nowa biblioteka, która umożliwia łatwiejsze wykonywanie operacji we/wy na platformie .NET.</span><span class="sxs-lookup"><span data-stu-id="1c649-104"><xref:System.IO.Pipelines> is a new library that is designed to make it easier to do high-performance I/O in .NET.</span></span> <span data-ttu-id="1c649-105">Jest to biblioteka ukierunkowana .NET Standard, która działa na wszystkich implementacjach platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="1c649-105">It's a library targeting .NET Standard that works on all .NET implementations.</span></span>

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a><span data-ttu-id="1c649-106">Jaki problem rozwiązuje system. IO. potoki</span><span class="sxs-lookup"><span data-stu-id="1c649-106">What problem does System.IO.Pipelines solve</span></span>

<!-- corner case doesn't MT (machine translate)   -->
<span data-ttu-id="1c649-107">Aplikacje, które analizują dane przesyłane strumieniowo, składają się z kodu standardowego, który ma wiele wyspecjalizowanych i nietypowych przepływów kodu.</span><span class="sxs-lookup"><span data-stu-id="1c649-107">Apps that parse streaming data are composed of boilerplate code having many specialized and unusual code flows.</span></span> <span data-ttu-id="1c649-108">Kod standardowy i szczególny przypadek jest skomplikowany i trudny do utrzymania.</span><span class="sxs-lookup"><span data-stu-id="1c649-108">The boilerplate and special case code is complex and difficult to maintain.</span></span>

<span data-ttu-id="1c649-109">`System.IO.Pipelines` został zaprojektowany z myślą o:</span><span class="sxs-lookup"><span data-stu-id="1c649-109">`System.IO.Pipelines` was architected to:</span></span>

* <span data-ttu-id="1c649-110">Przeanalizowanie danych przesyłanych strumieniowo o wysokiej wydajności.</span><span class="sxs-lookup"><span data-stu-id="1c649-110">Have high performance parsing streaming data.</span></span>
* <span data-ttu-id="1c649-111">Zmniejsz złożoność kodu.</span><span class="sxs-lookup"><span data-stu-id="1c649-111">Reduce code complexity.</span></span>

<span data-ttu-id="1c649-112">Poniższy kod jest typowy dla serwera TCP, który odbiera komunikaty rozdzielane wierszami (rozdzielane przez `'\n'` ) od klienta:</span><span class="sxs-lookup"><span data-stu-id="1c649-112">The following code is typical for a TCP server that receives line-delimited messages (delimited by `'\n'`) from a client:</span></span>

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

<span data-ttu-id="1c649-113">Poprzedni kod zawiera kilka problemów:</span><span class="sxs-lookup"><span data-stu-id="1c649-113">The preceding code has several problems:</span></span>

* <span data-ttu-id="1c649-114">Cały komunikat (koniec wiersza) może nie zostać odebrany w jednym wywołaniu do `ReadAsync` .</span><span class="sxs-lookup"><span data-stu-id="1c649-114">The entire message (end of line) might not be received in a single call to `ReadAsync`.</span></span>
* <span data-ttu-id="1c649-115">Wynik jest ignorowany `stream.ReadAsync` .</span><span class="sxs-lookup"><span data-stu-id="1c649-115">It's ignoring the result of `stream.ReadAsync`.</span></span> <span data-ttu-id="1c649-116">`stream.ReadAsync` Zwraca ilość odczytanych danych.</span><span class="sxs-lookup"><span data-stu-id="1c649-116">`stream.ReadAsync` returns how much data was read.</span></span>
* <span data-ttu-id="1c649-117">Nie obsługuje przypadku, w którym wiele wierszy jest odczytywanych w pojedynczym `ReadAsync` wywołaniu.</span><span class="sxs-lookup"><span data-stu-id="1c649-117">It doesn't handle the case where multiple lines are read in a single `ReadAsync` call.</span></span>
* <span data-ttu-id="1c649-118">Przydziela `byte` tablicę do każdego odczytu.</span><span class="sxs-lookup"><span data-stu-id="1c649-118">It allocates a `byte` array with each read.</span></span>

<span data-ttu-id="1c649-119">Aby rozwiązać powyższe problemy, wymagane są następujące zmiany:</span><span class="sxs-lookup"><span data-stu-id="1c649-119">To fix the preceding problems, the following changes are required:</span></span>

* <span data-ttu-id="1c649-120">Buforuj dane przychodzące do momentu znalezienia nowego wiersza.</span><span class="sxs-lookup"><span data-stu-id="1c649-120">Buffer the incoming data until a new line is found.</span></span>
* <span data-ttu-id="1c649-121">Przeanalizuj wszystkie wiersze zwrócone w buforze.</span><span class="sxs-lookup"><span data-stu-id="1c649-121">Parse all the lines returned in the buffer.</span></span>
* <span data-ttu-id="1c649-122">Istnieje możliwość, że wiersz jest większy niż 1 KB (1024 bajtów).</span><span class="sxs-lookup"><span data-stu-id="1c649-122">It's possible that the line is bigger than 1 KB (1024 bytes).</span></span> <span data-ttu-id="1c649-123">Kod musi zmienić rozmiar buforu wejściowego do momentu, w którym zostanie znaleziony ogranicznik, aby dopasować cały wiersz w buforze.</span><span class="sxs-lookup"><span data-stu-id="1c649-123">The code needs to resize the input buffer until the delimiter is found in order to fit the complete line inside the buffer.</span></span>

  * <span data-ttu-id="1c649-124">Jeśli rozmiar buforu jest zmieniany, w danych wejściowych są umieszczane więcej kopii buforów.</span><span class="sxs-lookup"><span data-stu-id="1c649-124">If the buffer is resized, more buffer copies are made as longer lines appear in the input.</span></span>
  * <span data-ttu-id="1c649-125">Aby zmniejszyć ilość zajętego miejsca, należy skompaktować bufor używany do odczytywania wierszy.</span><span class="sxs-lookup"><span data-stu-id="1c649-125">To reduce wasted space, compact the buffer used for reading lines.</span></span>

* <span data-ttu-id="1c649-126">Rozważ użycie puli buforów, aby uniknąć wielokrotnego przydzielania pamięci.</span><span class="sxs-lookup"><span data-stu-id="1c649-126">Consider using buffer pooling to avoid allocating memory repeatedly.</span></span>
* <span data-ttu-id="1c649-127">Poniższy kod dotyczy niektórych z następujących problemów:</span><span class="sxs-lookup"><span data-stu-id="1c649-127">The following code addresses some of these problems:</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs" id="snippet":::

<span data-ttu-id="1c649-128">Poprzedni kod jest skomplikowany i nie dotyczy wszystkich zidentyfikowanych problemów.</span><span class="sxs-lookup"><span data-stu-id="1c649-128">The previous code is complex and doesn't address all the problems identified.</span></span> <span data-ttu-id="1c649-129">Wysoka wydajność sieci zwykle oznacza pisanie bardzo złożonego kodu w celu zmaksymalizowania wydajności.</span><span class="sxs-lookup"><span data-stu-id="1c649-129">High-performance networking usually means writing very complex code to maximize performance.</span></span> <span data-ttu-id="1c649-130">`System.IO.Pipelines` została zaprojektowana, aby ułatwić pisanie tego typu kodu.</span><span class="sxs-lookup"><span data-stu-id="1c649-130">`System.IO.Pipelines` was designed to make writing this type of code easier.</span></span>

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="pipe"></a><span data-ttu-id="1c649-131">Wodzie</span><span class="sxs-lookup"><span data-stu-id="1c649-131">Pipe</span></span>

<span data-ttu-id="1c649-132"><xref:System.IO.Pipelines.Pipe>Klasy można użyć do utworzenia `PipeWriter/PipeReader` pary.</span><span class="sxs-lookup"><span data-stu-id="1c649-132">The <xref:System.IO.Pipelines.Pipe> class can be used to create a `PipeWriter/PipeReader` pair.</span></span> <span data-ttu-id="1c649-133">Wszystkie dane zapisywane w `PipeWriter` programie są dostępne w `PipeReader` :</span><span class="sxs-lookup"><span data-stu-id="1c649-133">All data written into the `PipeWriter` is available in the `PipeReader`:</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet2":::

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a><span data-ttu-id="1c649-134">Podstawowe użycie potoków</span><span class="sxs-lookup"><span data-stu-id="1c649-134">Pipe basic usage</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet":::

<span data-ttu-id="1c649-135">Istnieją dwie pętle:</span><span class="sxs-lookup"><span data-stu-id="1c649-135">There are two loops:</span></span>

* <span data-ttu-id="1c649-136">`FillPipeAsync` odczytuje z `Socket` i zapisuje dane w `PipeWriter` .</span><span class="sxs-lookup"><span data-stu-id="1c649-136">`FillPipeAsync` reads from the `Socket` and writes to the `PipeWriter`.</span></span>
* <span data-ttu-id="1c649-137">`ReadPipeAsync` odczytuje z `PipeReader` i analizuje linie przychodzące.</span><span class="sxs-lookup"><span data-stu-id="1c649-137">`ReadPipeAsync` reads from the `PipeReader` and parses incoming lines.</span></span>

<span data-ttu-id="1c649-138">Nie ma żadnych jawnie przyznanych buforów.</span><span class="sxs-lookup"><span data-stu-id="1c649-138">There are no explicit buffers allocated.</span></span> <span data-ttu-id="1c649-139">Wszystkie Zarządzanie buforem jest delegowane `PipeReader` do `PipeWriter` implementacji i.</span><span class="sxs-lookup"><span data-stu-id="1c649-139">All buffer management is delegated to the `PipeReader` and `PipeWriter` implementations.</span></span> <span data-ttu-id="1c649-140">Delegowanie zarządzania buforem ułatwia wykorzystywanie kodu do skoncentrowania się wyłącznie na logice biznesowej.</span><span class="sxs-lookup"><span data-stu-id="1c649-140">Delegating buffer management makes it easier for consuming code to focus solely on the business logic.</span></span>

<span data-ttu-id="1c649-141">W pierwszej pętli:</span><span class="sxs-lookup"><span data-stu-id="1c649-141">In the first loop:</span></span>

* <span data-ttu-id="1c649-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> jest wywoływana w celu uzyskania pamięci z bazowego składnika zapisywania.</span><span class="sxs-lookup"><span data-stu-id="1c649-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> is called to get memory from the underlying writer.</span></span>
* <span data-ttu-id="1c649-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> jest wywoływana w celu poinformowania o `PipeWriter` ilości danych, które zostały zapisaną w buforze.</span><span class="sxs-lookup"><span data-stu-id="1c649-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> is called to tell the `PipeWriter` how much data was written to the buffer.</span></span>
* <span data-ttu-id="1c649-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> jest wywoływana, aby udostępnić dane dla `PipeReader` .</span><span class="sxs-lookup"><span data-stu-id="1c649-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> is called to make the data available to the `PipeReader`.</span></span>

<span data-ttu-id="1c649-145">W drugiej pętli, `PipeReader` zużywa bufory zapisywane przez `PipeWriter` .</span><span class="sxs-lookup"><span data-stu-id="1c649-145">In the second loop, the `PipeReader` consumes the buffers written by `PipeWriter`.</span></span> <span data-ttu-id="1c649-146">Bufory pochodzą z gniazda.</span><span class="sxs-lookup"><span data-stu-id="1c649-146">The buffers come from the socket.</span></span> <span data-ttu-id="1c649-147">Wywołanie `PipeReader.ReadAsync` :</span><span class="sxs-lookup"><span data-stu-id="1c649-147">The call to `PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="1c649-148">Zwraca wartość zawierającą <xref:System.IO.Pipelines.ReadResult> dwie ważne informacje:</span><span class="sxs-lookup"><span data-stu-id="1c649-148">Returns a <xref:System.IO.Pipelines.ReadResult> that contains two important pieces of information:</span></span>

  * <span data-ttu-id="1c649-149">Dane, które zostały odczytane w postaci `ReadOnlySequence<byte>` .</span><span class="sxs-lookup"><span data-stu-id="1c649-149">The data that was read in the form of `ReadOnlySequence<byte>`.</span></span>
  * <span data-ttu-id="1c649-150">Wartość logiczna `IsCompleted` wskazująca, czy osiągnięto koniec danych (EOF).</span><span class="sxs-lookup"><span data-stu-id="1c649-150">A boolean `IsCompleted` that indicates if the end of data (EOF) has been reached.</span></span>

<span data-ttu-id="1c649-151">Po znalezieniu ogranicznika końca wiersza (EOL) i przeanalizowaniu wiersza:</span><span class="sxs-lookup"><span data-stu-id="1c649-151">After finding the end of line (EOL) delimiter and parsing the line:</span></span>

* <span data-ttu-id="1c649-152">Logika przetwarza bufor, aby pominąć operacje, które zostały już przetworzone.</span><span class="sxs-lookup"><span data-stu-id="1c649-152">The logic processes the buffer to skip what's already processed.</span></span>
* <span data-ttu-id="1c649-153">`PipeReader.AdvanceTo` jest wywoływana, aby określić ilość `PipeReader` danych, które zostały zużyte i zbadane.</span><span class="sxs-lookup"><span data-stu-id="1c649-153">`PipeReader.AdvanceTo` is called to tell the `PipeReader` how much data has been consumed and examined.</span></span>

<span data-ttu-id="1c649-154">Pętle czytnika i składnika zapisywania kończą się przez wywołanie `Complete` .</span><span class="sxs-lookup"><span data-stu-id="1c649-154">The reader and writer loops end by calling `Complete`.</span></span> <span data-ttu-id="1c649-155">`Complete` umożliwia potoku w celu zwolnienia pamięci do przydzielenia.</span><span class="sxs-lookup"><span data-stu-id="1c649-155">`Complete` lets the underlying Pipe release the memory it allocated.</span></span>

### <a name="backpressure-and-flow-control"></a><span data-ttu-id="1c649-156">Sterowanie ruchem wstecznym i przepływem</span><span class="sxs-lookup"><span data-stu-id="1c649-156">Backpressure and flow control</span></span>

<span data-ttu-id="1c649-157">Najlepiej, odczytując i przeanalizować współpracę:</span><span class="sxs-lookup"><span data-stu-id="1c649-157">Ideally, reading and parsing work together:</span></span>

* <span data-ttu-id="1c649-158">Wątek pisania wykorzystuje dane z sieci i umieszcza je w buforach.</span><span class="sxs-lookup"><span data-stu-id="1c649-158">The writing thread consumes data from the network and puts it in buffers.</span></span>
* <span data-ttu-id="1c649-159">Wątek analizy jest odpowiedzialny za konstruowanie odpowiednich struktur danych.</span><span class="sxs-lookup"><span data-stu-id="1c649-159">The parsing thread is responsible for constructing the appropriate data structures.</span></span>

<span data-ttu-id="1c649-160">Zwykle analiza zajmuje więcej czasu niż tylko kopiowanie bloków danych z sieci:</span><span class="sxs-lookup"><span data-stu-id="1c649-160">Typically, parsing takes more time than just copying blocks of data from the network:</span></span>

* <span data-ttu-id="1c649-161">Wątek odczytywania pobiera przed wątkiem analizy.</span><span class="sxs-lookup"><span data-stu-id="1c649-161">The reading thread gets ahead of the parsing thread.</span></span>
* <span data-ttu-id="1c649-162">Wątek odczytu musi spowolnić lub przydzielić więcej pamięci, aby przechowywać dane dla wątku analizy.</span><span class="sxs-lookup"><span data-stu-id="1c649-162">The reading thread has to either slow down or allocate more memory to store the data for the parsing thread.</span></span>

<span data-ttu-id="1c649-163">W celu uzyskania optymalnej wydajności istnieje równowaga między częste Wstrzymywanie i przydzielania większej ilości pamięci.</span><span class="sxs-lookup"><span data-stu-id="1c649-163">For optimal performance, there's a balance between frequent pauses and allocating more memory.</span></span>

<span data-ttu-id="1c649-164">Aby rozwiązać ten problem, program `Pipe` ma dwa ustawienia umożliwiające sterowanie przepływem danych:</span><span class="sxs-lookup"><span data-stu-id="1c649-164">To solve the preceding problem, the `Pipe` has two settings to control the flow of data:</span></span>

* <span data-ttu-id="1c649-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Określa, ile danych ma być buforowanych przed wywołaniem do <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> wstrzymania.</span><span class="sxs-lookup"><span data-stu-id="1c649-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Determines how much data should be buffered before calls to <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> pause.</span></span>
* <span data-ttu-id="1c649-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Określa, ile danych musi obserwować czytelnik przed wywołaniem `PipeWriter.FlushAsync` wznowienia.</span><span class="sxs-lookup"><span data-stu-id="1c649-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Determines how much data the reader has to observe before calls to `PipeWriter.FlushAsync` resume.</span></span>

![Diagram z ResumeWriterThreshold i PauseWriterThreshold](media/pipelines/resume-pause.png)

<span data-ttu-id="1c649-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1c649-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="1c649-169">Zwraca wartość niekompletną `ValueTask<FlushResult>` , gdy ilość danych w `Pipe` krzyżach `PauseWriterThreshold` .</span><span class="sxs-lookup"><span data-stu-id="1c649-169">Returns an incomplete `ValueTask<FlushResult>` when the amount of data in the `Pipe` crosses `PauseWriterThreshold`.</span></span>
* <span data-ttu-id="1c649-170">Kończy działanie `ValueTask<FlushResult>` , gdy zostanie ono mniejsze niż `ResumeWriterThreshold` .</span><span class="sxs-lookup"><span data-stu-id="1c649-170">Completes `ValueTask<FlushResult>` when it becomes lower than `ResumeWriterThreshold`.</span></span>

<span data-ttu-id="1c649-171">Dwie wartości są używane, aby zapobiec szybkiemu cyklowi, który może wystąpić w przypadku użycia jednej wartości.</span><span class="sxs-lookup"><span data-stu-id="1c649-171">Two values are used to prevent rapid cycling, which can occur if one value is used.</span></span>

### <a name="examples"></a><span data-ttu-id="1c649-172">Przykłady</span><span class="sxs-lookup"><span data-stu-id="1c649-172">Examples</span></span>

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a><span data-ttu-id="1c649-173">PipeScheduler</span><span class="sxs-lookup"><span data-stu-id="1c649-173">PipeScheduler</span></span>

<span data-ttu-id="1c649-174">Zazwyczaj przy użyciu `async` i `await` , kod asynchroniczny jest wznawiany na <xref:System.Threading.Tasks.TaskScheduler> lub na bieżącym <xref:System.Threading.SynchronizationContext> .</span><span class="sxs-lookup"><span data-stu-id="1c649-174">Typically when using `async` and `await`, asynchronous code resumes on either on a <xref:System.Threading.Tasks.TaskScheduler> or on the current <xref:System.Threading.SynchronizationContext>.</span></span>

<span data-ttu-id="1c649-175">Podczas wykonywania operacji we/wy należy mieć precyzyjną kontrolę nad tym, gdzie jest wykonywane wykonywanie operacji we/wy.</span><span class="sxs-lookup"><span data-stu-id="1c649-175">When doing I/O, it's important to have fine-grained control over where the I/O is performed.</span></span> <span data-ttu-id="1c649-176">Ta kontrolka umożliwia efektywne wykorzystanie pamięci podręcznych procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="1c649-176">This control allows taking advantage of CPU caches effectively.</span></span> <span data-ttu-id="1c649-177">Wydajne buforowanie ma kluczowe znaczenie dla aplikacji o wysokiej wydajności, takich jak serwery sieci Web.</span><span class="sxs-lookup"><span data-stu-id="1c649-177">Efficient caching is critical for high-performance apps like web servers.</span></span> <span data-ttu-id="1c649-178"><xref:System.IO.Pipelines.PipeScheduler> zapewnia kontrolę nad miejscem, w którym są uruchamiane asynchroniczne wywołania zwrotne.</span><span class="sxs-lookup"><span data-stu-id="1c649-178"><xref:System.IO.Pipelines.PipeScheduler> provides control over where asynchronous callbacks run.</span></span> <span data-ttu-id="1c649-179">Domyślnie:</span><span class="sxs-lookup"><span data-stu-id="1c649-179">By default:</span></span>

* <span data-ttu-id="1c649-180">Bieżąca <xref:System.Threading.SynchronizationContext> jest używana.</span><span class="sxs-lookup"><span data-stu-id="1c649-180">The current <xref:System.Threading.SynchronizationContext> is used.</span></span>
* <span data-ttu-id="1c649-181">Jeśli nie istnieje `SynchronizationContext` , używa puli wątków do uruchamiania wywołań zwrotnych.</span><span class="sxs-lookup"><span data-stu-id="1c649-181">If there's no `SynchronizationContext`, it uses the thread pool to run callbacks.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Program.cs" id="snippet":::

<span data-ttu-id="1c649-182">[PipeScheduler.](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) Threading to <xref:System.IO.Pipelines.PipeScheduler> implementacja, która kolejkuje wywołania zwrotne do puli wątków.</span><span class="sxs-lookup"><span data-stu-id="1c649-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) is the <xref:System.IO.Pipelines.PipeScheduler> implementation that queues callbacks to the thread pool.</span></span> <span data-ttu-id="1c649-183">`PipeScheduler.ThreadPool` jest to ustawienie domyślne i ogólnie najlepszym wyborem.</span><span class="sxs-lookup"><span data-stu-id="1c649-183">`PipeScheduler.ThreadPool` is the default and generally the best choice.</span></span> <span data-ttu-id="1c649-184">[PipeScheduler. inline](xref:System.IO.Pipelines.PipeScheduler.Inline) może spowodować niezamierzone konsekwencje, takie jak zakleszczenia.</span><span class="sxs-lookup"><span data-stu-id="1c649-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) can cause unintended consequences such as deadlocks.</span></span>

### <a name="pipe-reset"></a><span data-ttu-id="1c649-185">Resetowanie potoku</span><span class="sxs-lookup"><span data-stu-id="1c649-185">Pipe reset</span></span>

<span data-ttu-id="1c649-186">Często wydajnym rozwiązaniem jest ponowne użycie `Pipe` obiektu.</span><span class="sxs-lookup"><span data-stu-id="1c649-186">It's frequently efficient to reuse the `Pipe` object.</span></span> <span data-ttu-id="1c649-187">Aby zresetować potok, wywołaj <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> po zakończeniu obu `PipeReader` i `PipeWriter` .</span><span class="sxs-lookup"><span data-stu-id="1c649-187">To reset the pipe, call <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> when both the `PipeReader` and `PipeWriter` are complete.</span></span>

## <a name="pipereader"></a><span data-ttu-id="1c649-188">PipeReader</span><span class="sxs-lookup"><span data-stu-id="1c649-188">PipeReader</span></span>

<span data-ttu-id="1c649-189"><xref:System.IO.Pipelines.PipeReader> zarządza pamięcią w imieniu obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="1c649-189"><xref:System.IO.Pipelines.PipeReader> manages memory on the caller's behalf.</span></span> <span data-ttu-id="1c649-190">**Zawsze** wywołuj <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> po wywołaniu <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1c649-190">**Always** call <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> after calling <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1c649-191">Dzięki temu `PipeReader` wiadomo, kiedy obiekt wywołujący jest wykonywany z pamięcią, aby można było go śledzić.</span><span class="sxs-lookup"><span data-stu-id="1c649-191">This lets the `PipeReader` know when the caller is done with the memory so that it can be tracked.</span></span> <span data-ttu-id="1c649-192">Wartość `ReadOnlySequence<byte>` zwracana z `PipeReader.ReadAsync` jest prawidłowa tylko do momentu wywołania metody `PipeReader.AdvanceTo` .</span><span class="sxs-lookup"><span data-stu-id="1c649-192">The `ReadOnlySequence<byte>` returned from `PipeReader.ReadAsync` is only valid until the call the `PipeReader.AdvanceTo`.</span></span> <span data-ttu-id="1c649-193">Użycie po wywołaniu nie jest dozwolone `ReadOnlySequence<byte>` `PipeReader.AdvanceTo` .</span><span class="sxs-lookup"><span data-stu-id="1c649-193">It's illegal to use `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo`.</span></span>

<span data-ttu-id="1c649-194">`PipeReader.AdvanceTo` przyjmuje dwa <xref:System.SequencePosition> argumenty:</span><span class="sxs-lookup"><span data-stu-id="1c649-194">`PipeReader.AdvanceTo` takes two <xref:System.SequencePosition> arguments:</span></span>

* <span data-ttu-id="1c649-195">Pierwszy argument określa, ile pamięci zostało zużyte.</span><span class="sxs-lookup"><span data-stu-id="1c649-195">The first argument determines how much memory was consumed.</span></span>
* <span data-ttu-id="1c649-196">Drugi argument określa, jaka część buforu została zaobserwowana.</span><span class="sxs-lookup"><span data-stu-id="1c649-196">The second argument determines how much of the buffer was observed.</span></span>

<span data-ttu-id="1c649-197">Oznaczenie danych jako zużyte oznacza, że potok może zwrócić pamięć do źródłowej puli buforów.</span><span class="sxs-lookup"><span data-stu-id="1c649-197">Marking data as consumed means that the pipe can return the memory to the underlying buffer pool.</span></span> <span data-ttu-id="1c649-198">Oznaczanie danych jako obserwowanych kontroluje, jak następne wywołanie ma zostać wykonane `PipeReader.ReadAsync` .</span><span class="sxs-lookup"><span data-stu-id="1c649-198">Marking data as observed controls what the next call to `PipeReader.ReadAsync` does.</span></span> <span data-ttu-id="1c649-199">Oznaczenie wszystkiego jako zaobserwowane oznacza, że następne wywołanie `PipeReader.ReadAsync` nie zostanie zwrócone do momentu zapisania większej ilości danych w potoku.</span><span class="sxs-lookup"><span data-stu-id="1c649-199">Marking everything as observed means that the next call to `PipeReader.ReadAsync` won't return until there's more data written to the pipe.</span></span> <span data-ttu-id="1c649-200">Wszystkie inne wartości spowodują, że następne wywołanie `PipeReader.ReadAsync` zwróci natychmiast z obserwowanymi *i* nieobserwowanymi danymi, ale nie wykorzystano już danych.</span><span class="sxs-lookup"><span data-stu-id="1c649-200">Any other value will make the next call to `PipeReader.ReadAsync` return immediately with the observed *and* unobserved data, but not data that has already been consumed.</span></span>

### <a name="read-streaming-data-scenarios"></a><span data-ttu-id="1c649-201">Odczytaj scenariusze przesyłania strumieniowego danych</span><span class="sxs-lookup"><span data-stu-id="1c649-201">Read streaming data scenarios</span></span>

<span data-ttu-id="1c649-202">Istnieje kilka typowych wzorców, które nastąpiły podczas próby odczytu danych przesyłanych strumieniowo:</span><span class="sxs-lookup"><span data-stu-id="1c649-202">There are a couple of typical patterns that emerge when trying to read streaming data:</span></span>

* <span data-ttu-id="1c649-203">Przy użyciu strumienia danych Przeanalizuj pojedynczy komunikat.</span><span class="sxs-lookup"><span data-stu-id="1c649-203">Given a stream of data, parse a single message.</span></span>
* <span data-ttu-id="1c649-204">Przy użyciu strumienia danych Przeanalizuj wszystkie dostępne komunikaty.</span><span class="sxs-lookup"><span data-stu-id="1c649-204">Given a stream of data, parse all available messages.</span></span>

<span data-ttu-id="1c649-205">W poniższych przykładach użyto `TryParseMessage` metody analizowania komunikatów z `ReadOnlySequence<byte>` .</span><span class="sxs-lookup"><span data-stu-id="1c649-205">The following examples use the `TryParseMessage` method for parsing messages from a `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="1c649-206">`TryParseMessage` analizuje pojedynczy komunikat i aktualizuje bufor wejściowy, aby przyciąć przeanalizowany komunikat z bufora.</span><span class="sxs-lookup"><span data-stu-id="1c649-206">`TryParseMessage` parses a single message and update the input buffer to trim the parsed message from the buffer.</span></span> <span data-ttu-id="1c649-207">`TryParseMessage` Program nie jest częścią programu .NET. jest to metoda zapisywana przez użytkownika użyta w poniższych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="1c649-207">`TryParseMessage` is not part of .NET, it's a user written method used in the following sections.</span></span>

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a><span data-ttu-id="1c649-208">Odczytaj pojedynczy komunikat</span><span class="sxs-lookup"><span data-stu-id="1c649-208">Read a single message</span></span>

<span data-ttu-id="1c649-209">Poniższy kod odczytuje pojedynczy komunikat z `PipeReader` i zwraca go do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="1c649-209">The following code reads a single message from a `PipeReader` and returns it to the caller.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs" id="snippet":::

<span data-ttu-id="1c649-210">Powyższy kod ma następujące działanie:</span><span class="sxs-lookup"><span data-stu-id="1c649-210">The preceding code:</span></span>

* <span data-ttu-id="1c649-211">Analizuje pojedynczy komunikat.</span><span class="sxs-lookup"><span data-stu-id="1c649-211">Parses a single message.</span></span>
* <span data-ttu-id="1c649-212">Aktualizuje zużyte `SequencePosition` i sprawdzone pod kątem `SequencePosition` początku przyciętego buforu wejściowego.</span><span class="sxs-lookup"><span data-stu-id="1c649-212">Updates the consumed `SequencePosition` and examined `SequencePosition` to point to the start of the trimmed input buffer.</span></span>

<span data-ttu-id="1c649-213">Dwa `SequencePosition` argumenty są aktualizowane, ponieważ `TryParseMessage` usuwa przeanalizowany komunikat z bufora wejściowego.</span><span class="sxs-lookup"><span data-stu-id="1c649-213">The two `SequencePosition` arguments are updated because `TryParseMessage` removes the parsed message from the input buffer.</span></span> <span data-ttu-id="1c649-214">Ogólnie rzecz biorąc, podczas analizowania pojedynczej wiadomości z bufora pozycja zbadana powinna mieć jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="1c649-214">Generally, when parsing a single message from the buffer, the examined position should be one of the following:</span></span>

* <span data-ttu-id="1c649-215">Koniec komunikatu.</span><span class="sxs-lookup"><span data-stu-id="1c649-215">The end of the message.</span></span>
* <span data-ttu-id="1c649-216">Koniec odebranego buforu, jeśli nie odnaleziono komunikatu.</span><span class="sxs-lookup"><span data-stu-id="1c649-216">The end of the received buffer if no message was found.</span></span>

<span data-ttu-id="1c649-217">Przypadek z pojedynczym komunikatem ma największą możliwość wystąpienia błędów.</span><span class="sxs-lookup"><span data-stu-id="1c649-217">The single message case has the most potential for errors.</span></span> <span data-ttu-id="1c649-218">Przekazanie nieprawidłowych wartości do *zbadania* może spowodować wyjątek braku pamięci lub nieskończoną pętlę.</span><span class="sxs-lookup"><span data-stu-id="1c649-218">Passing the wrong values to *examined* can result in an out of memory exception or an infinite loop.</span></span> <span data-ttu-id="1c649-219">Aby uzyskać więcej informacji, zobacz sekcję [typowe problemy związane z PipeReader](#gotchas) w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="1c649-219">For more information, see the [PipeReader common problems](#gotchas) section in this article.</span></span>

### <a name="reading-multiple-messages"></a><span data-ttu-id="1c649-220">Odczytywanie wielu wiadomości</span><span class="sxs-lookup"><span data-stu-id="1c649-220">Reading multiple messages</span></span>

<span data-ttu-id="1c649-221">Poniższy kod odczytuje wszystkie komunikaty z `PipeReader` wywołań i `ProcessMessageAsync` na każdym z nich.</span><span class="sxs-lookup"><span data-stu-id="1c649-221">The following code reads all messages from a `PipeReader` and calls `ProcessMessageAsync` on each.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection1.cs" id="snippet":::

### <a name="cancellation"></a><span data-ttu-id="1c649-222">Anulowanie</span><span class="sxs-lookup"><span data-stu-id="1c649-222">Cancellation</span></span>

<span data-ttu-id="1c649-223">`PipeReader.ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="1c649-223">`PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="1c649-224">Obsługuje przekazywanie <xref:System.Threading.CancellationToken> .</span><span class="sxs-lookup"><span data-stu-id="1c649-224">Supports passing a <xref:System.Threading.CancellationToken>.</span></span>
* <span data-ttu-id="1c649-225">Zgłasza, <xref:System.OperationCanceledException> czy element `CancellationToken` jest anulowany, gdy istnieje oczekujące odczytanie.</span><span class="sxs-lookup"><span data-stu-id="1c649-225">Throws an <xref:System.OperationCanceledException> if the `CancellationToken` is canceled while there's a read pending.</span></span>
* <span data-ttu-id="1c649-226">Obsługuje sposób anulowania bieżącej operacji odczytu za pośrednictwem <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType> , co pozwala uniknąć wywoływania wyjątku.</span><span class="sxs-lookup"><span data-stu-id="1c649-226">Supports a way to cancel the current read operation via <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, which avoids raising an exception.</span></span> <span data-ttu-id="1c649-227">Wywołanie `PipeReader.CancelPendingRead` powoduje, że bieżące lub następne wywołanie w `PipeReader.ReadAsync` celu zwrócenia elementu <xref:System.IO.Pipelines.ReadResult> z `IsCanceled` ustawionym na `true` .</span><span class="sxs-lookup"><span data-stu-id="1c649-227">Calling `PipeReader.CancelPendingRead` causes the current or next call to `PipeReader.ReadAsync` to return a <xref:System.IO.Pipelines.ReadResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="1c649-228">Może to być przydatne w przypadku zatrzymania istniejącej pętli odczytu w nieniszczącej i niewyjątkowy sposób.</span><span class="sxs-lookup"><span data-stu-id="1c649-228">This can be useful for halting the existing read loop in a non-destructive and non-exceptional way.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection.cs" id="snippet":::

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a><span data-ttu-id="1c649-229">PipeReader typowe problemy</span><span class="sxs-lookup"><span data-stu-id="1c649-229">PipeReader common problems</span></span>

* <span data-ttu-id="1c649-230">Przekazanie nieprawidłowych wartości do `consumed` lub `examined` może spowodować odczyt danych, które zostały już odczytane.</span><span class="sxs-lookup"><span data-stu-id="1c649-230">Passing the wrong values to `consumed` or `examined` may result in reading already read data.</span></span>
* <span data-ttu-id="1c649-231">Przekazanie `buffer.End` jako badane może skutkować:</span><span class="sxs-lookup"><span data-stu-id="1c649-231">Passing `buffer.End` as examined may result in:</span></span>

  * <span data-ttu-id="1c649-232">Dane wstrzymane</span><span class="sxs-lookup"><span data-stu-id="1c649-232">Stalled data</span></span>
  * <span data-ttu-id="1c649-233">Ewentualny wyjątek braku pamięci (OOM), jeśli dane nie są używane.</span><span class="sxs-lookup"><span data-stu-id="1c649-233">Possibly an eventual Out of Memory (OOM) exception if data isn't consumed.</span></span> <span data-ttu-id="1c649-234">Na przykład `PipeReader.AdvanceTo(position, buffer.End)` podczas przetwarzania pojedynczego komunikatu w czasie z buforu.</span><span class="sxs-lookup"><span data-stu-id="1c649-234">For example, `PipeReader.AdvanceTo(position, buffer.End)` when processing a single message at a time from the buffer.</span></span>

* <span data-ttu-id="1c649-235">Przekazanie nieprawidłowych wartości do `consumed` lub `examined` może skutkować pętlą nieskończoną.</span><span class="sxs-lookup"><span data-stu-id="1c649-235">Passing the wrong values to `consumed` or `examined` may result in an infinite loop.</span></span> <span data-ttu-id="1c649-236">Na przykład, `PipeReader.AdvanceTo(buffer.Start)` Jeśli `buffer.Start` nie zmieniono, spowoduje to, że następne wywołanie zostanie `PipeReader.ReadAsync` zwrócone natychmiast przed nadejściem nowych danych.</span><span class="sxs-lookup"><span data-stu-id="1c649-236">For example, `PipeReader.AdvanceTo(buffer.Start)` if `buffer.Start` hasn't changed will cause the next call to `PipeReader.ReadAsync` to return immediately before new data arrives.</span></span>
* <span data-ttu-id="1c649-237">Przekazanie nieprawidłowych wartości do `consumed` lub `examined` może spowodować nieskończone buforowanie (ostateczne OOM).</span><span class="sxs-lookup"><span data-stu-id="1c649-237">Passing the wrong values to `consumed` or `examined` may result in infinite buffering (eventual OOM).</span></span>
* <span data-ttu-id="1c649-238">Użycie `ReadOnlySequence<byte>` po wywołaniu `PipeReader.AdvanceTo` może spowodować uszkodzenie pamięci (za darmo).</span><span class="sxs-lookup"><span data-stu-id="1c649-238">Using the `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo` may result in memory corruption (use after free).</span></span>
* <span data-ttu-id="1c649-239">Niepowodzenie wywołania `PipeReader.Complete/CompleteAsync` może spowodować przeciek pamięci.</span><span class="sxs-lookup"><span data-stu-id="1c649-239">Failing to call `PipeReader.Complete/CompleteAsync` may result in a memory leak.</span></span>
* <span data-ttu-id="1c649-240">Sprawdzanie <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> i kończenie logiki odczytu przed przetworzeniem buforu powoduje utratę danych.</span><span class="sxs-lookup"><span data-stu-id="1c649-240">Checking <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> and exiting the reading logic before processing the buffer results in data loss.</span></span> <span data-ttu-id="1c649-241">Warunek zakończenia pętli powinien opierać się na `ReadResult.Buffer.IsEmpty` i `ReadResult.IsCompleted` .</span><span class="sxs-lookup"><span data-stu-id="1c649-241">The loop exit condition should be based on `ReadResult.Buffer.IsEmpty` and `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="1c649-242">Nieprawidłowe działanie może spowodować powstanie pętli nieskończonej.</span><span class="sxs-lookup"><span data-stu-id="1c649-242">Doing this incorrectly could result in an infinite loop.</span></span>

#### <a name="problematic-code"></a><span data-ttu-id="1c649-243">Problematyczny kod</span><span class="sxs-lookup"><span data-stu-id="1c649-243">Problematic code</span></span>

<span data-ttu-id="1c649-244">❌ **Utrata danych**</span><span class="sxs-lookup"><span data-stu-id="1c649-244">❌ **Data loss**</span></span>

<span data-ttu-id="1c649-245">`ReadResult`Może zwrócić końcowy segment danych, gdy `IsCompleted` jest ustawiony na `true` .</span><span class="sxs-lookup"><span data-stu-id="1c649-245">The `ReadResult` can return the final segment of data when `IsCompleted` is set to `true`.</span></span> <span data-ttu-id="1c649-246">Nie można odczytać tych danych przed wyjściem z pętli odczytu spowoduje utratę danych.</span><span class="sxs-lookup"><span data-stu-id="1c649-246">Not reading that data before exiting the read loop will result in data loss.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="1c649-247">❌**Nieskończona pętla**</span><span class="sxs-lookup"><span data-stu-id="1c649-247">❌ **Infinite loop**</span></span>

<span data-ttu-id="1c649-248">Poniższa logika może spowodować nieskończoną pętlę, jeśli `Result.IsCompleted` jest, `true` ale nigdy nie pełny komunikat w buforze.</span><span class="sxs-lookup"><span data-stu-id="1c649-248">The following logic may result in an infinite loop if the `Result.IsCompleted` is `true` but there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet2":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="1c649-249">Oto inny fragment kodu z tym samym problemem.</span><span class="sxs-lookup"><span data-stu-id="1c649-249">Here's another piece of code with the same problem.</span></span> <span data-ttu-id="1c649-250">Sprawdzanie niepustego buforu przed sprawdzeniem `ReadResult.IsCompleted` .</span><span class="sxs-lookup"><span data-stu-id="1c649-250">It's checking for a non-empty buffer before checking `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="1c649-251">Ponieważ znajduje się w `else if` , będzie ona zapętlać w nieskończoność, jeśli w buforze nigdy nie ma kompletnego komunikatu.</span><span class="sxs-lookup"><span data-stu-id="1c649-251">Because it's in an `else if`, it will loop forever if there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet3":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="1c649-252">❌**Nieoczekiwany zawieszenie**</span><span class="sxs-lookup"><span data-stu-id="1c649-252">❌ **Unexpected Hang**</span></span>

<span data-ttu-id="1c649-253">Bezwarunkowe wywoływanie `PipeReader.AdvanceTo` przy użyciu `buffer.End` w `examined` położeniu może spowodować zawieszenie podczas analizowania pojedynczego komunikatu.</span><span class="sxs-lookup"><span data-stu-id="1c649-253">Unconditionally calling `PipeReader.AdvanceTo` with `buffer.End` in the `examined` position may result in hangs when parsing a single message.</span></span> <span data-ttu-id="1c649-254">Następne wywołanie `PipeReader.AdvanceTo` nie zwróci do momentu:</span><span class="sxs-lookup"><span data-stu-id="1c649-254">The next call to `PipeReader.AdvanceTo` won't return until:</span></span>

* <span data-ttu-id="1c649-255">Więcej danych jest zapisywana w potoku.</span><span class="sxs-lookup"><span data-stu-id="1c649-255">There's more data written to the pipe.</span></span>
* <span data-ttu-id="1c649-256">Nowe dane nie były wcześniej badane.</span><span class="sxs-lookup"><span data-stu-id="1c649-256">And the new data wasn't previously examined.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet4":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="1c649-257">❌Za **mało pamięci (OOM)**</span><span class="sxs-lookup"><span data-stu-id="1c649-257">❌ **Out of Memory (OOM)**</span></span>

<span data-ttu-id="1c649-258">W następujących warunkach Poniższy kod przechowuje buforowanie do momentu <xref:System.OutOfMemoryException> wystąpienia:</span><span class="sxs-lookup"><span data-stu-id="1c649-258">With the following conditions, the following code keeps buffering until an <xref:System.OutOfMemoryException> occurs:</span></span>

* <span data-ttu-id="1c649-259">Nie ma maksymalnego rozmiaru wiadomości.</span><span class="sxs-lookup"><span data-stu-id="1c649-259">There's no maximum message size.</span></span>
* <span data-ttu-id="1c649-260">Dane zwrócone z `PipeReader` nie pełnią komunikatu.</span><span class="sxs-lookup"><span data-stu-id="1c649-260">The data returned from the `PipeReader` doesn't make a complete message.</span></span> <span data-ttu-id="1c649-261">Na przykład nie wykonuje pełnego komunikatu, ponieważ druga strona zapisuje dużą wiadomość (na przykład komunikat 4 GB).</span><span class="sxs-lookup"><span data-stu-id="1c649-261">For example, it doesn't make a complete message because the other side is writing a large message (For example, a 4-GB message).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet5":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="1c649-262">❌**Uszkodzenie pamięci**</span><span class="sxs-lookup"><span data-stu-id="1c649-262">❌ **Memory Corruption**</span></span>

<span data-ttu-id="1c649-263">Podczas pisania pomocników odczytujących bufor należy skopiować wszystkie zwrócone ładunki przed wywołaniem `Advance` .</span><span class="sxs-lookup"><span data-stu-id="1c649-263">When writing helpers that read the buffer, any returned payload should be copied before calling `Advance`.</span></span> <span data-ttu-id="1c649-264">Poniższy przykład zwróci pamięć, która `Pipe` została odrzucona i może ponownie użyć dla następnej operacji (odczyt/zapis).</span><span class="sxs-lookup"><span data-stu-id="1c649-264">The following example will return memory that the `Pipe` has discarded and may reuse it for the next operation (read/write).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippetMessage":::

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet6":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a><span data-ttu-id="1c649-265">PipeWriter</span><span class="sxs-lookup"><span data-stu-id="1c649-265">PipeWriter</span></span>

<span data-ttu-id="1c649-266"><xref:System.IO.Pipelines.PipeWriter>Zarządza buforami do zapisu w imieniu obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="1c649-266">The <xref:System.IO.Pipelines.PipeWriter> manages buffers for writing on the caller's behalf.</span></span> <span data-ttu-id="1c649-267">`PipeWriter` implementuje [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601) .</span><span class="sxs-lookup"><span data-stu-id="1c649-267">`PipeWriter` implements [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span></span> <span data-ttu-id="1c649-268">`IBufferWriter<byte>` umożliwia uzyskanie dostępu do buforów w celu wykonywania operacji zapisu bez dodatkowych kopii buforów.</span><span class="sxs-lookup"><span data-stu-id="1c649-268">`IBufferWriter<byte>` makes it possible to get access to buffers to perform writes without additional buffer copies.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet":::

<span data-ttu-id="1c649-269">Poprzedni kod:</span><span class="sxs-lookup"><span data-stu-id="1c649-269">The previous code:</span></span>

* <span data-ttu-id="1c649-270">Żąda bufora co najmniej 5 bajtów z `PipeWriter` polecenia using <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> .</span><span class="sxs-lookup"><span data-stu-id="1c649-270">Requests a buffer of at least 5 bytes from the `PipeWriter` using <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.</span></span>
* <span data-ttu-id="1c649-271">Zapisuje bajty dla ciągu ASCII `"Hello"` zwracanego `Memory<byte>` .</span><span class="sxs-lookup"><span data-stu-id="1c649-271">Writes bytes for the ASCII string `"Hello"` to the returned `Memory<byte>`.</span></span>
* <span data-ttu-id="1c649-272">Wywołania <xref:System.IO.Pipelines.PipeWriter.Advance%2A> wskazujące, ile bajtów Zapisano w buforze.</span><span class="sxs-lookup"><span data-stu-id="1c649-272">Calls <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to indicate how many bytes were written to the buffer.</span></span>
* <span data-ttu-id="1c649-273">Opróżnia `PipeWriter` , który wysyła bajty do urządzenia bazowego.</span><span class="sxs-lookup"><span data-stu-id="1c649-273">Flushes the `PipeWriter`, which sends the bytes to the underlying device.</span></span>

<span data-ttu-id="1c649-274">Poprzednia metoda pisania używa buforów dostarczonych przez `PipeWriter` .</span><span class="sxs-lookup"><span data-stu-id="1c649-274">The previous method of writing uses the buffers provided by the `PipeWriter`.</span></span> <span data-ttu-id="1c649-275">Alternatywnie <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType> :</span><span class="sxs-lookup"><span data-stu-id="1c649-275">Alternatively, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="1c649-276">Kopiuje istniejący bufor do `PipeWriter` .</span><span class="sxs-lookup"><span data-stu-id="1c649-276">Copies the existing buffer to the `PipeWriter`.</span></span>
* <span data-ttu-id="1c649-277">Wywołania `GetSpan` , `Advance` zgodnie z potrzebami i wywołania <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> .</span><span class="sxs-lookup"><span data-stu-id="1c649-277">Calls `GetSpan`, `Advance` as appropriate and calls <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet2":::

### <a name="cancellation"></a><span data-ttu-id="1c649-278">Anulowanie</span><span class="sxs-lookup"><span data-stu-id="1c649-278">Cancellation</span></span>

<span data-ttu-id="1c649-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> obsługuje przekazywanie <xref:System.Threading.CancellationToken> .</span><span class="sxs-lookup"><span data-stu-id="1c649-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> supports passing a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="1c649-280">Przekazywanie `CancellationToken` wyników w `OperationCanceledException` przypadku, gdy token zostanie anulowany, gdy istnieje oczekująca operacja opróżniania.</span><span class="sxs-lookup"><span data-stu-id="1c649-280">Passing a `CancellationToken` results in an `OperationCanceledException` if the token is canceled while there's a flush pending.</span></span> <span data-ttu-id="1c649-281">`PipeWriter.FlushAsync` obsługuje sposób anulowania bieżącej operacji opróżniania za pośrednictwem <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> bez podnoszenia wyjątku.</span><span class="sxs-lookup"><span data-stu-id="1c649-281">`PipeWriter.FlushAsync` supports a way to cancel the current flush operation via <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> without raising an exception.</span></span> <span data-ttu-id="1c649-282">Wywołanie `PipeWriter.CancelPendingFlush` powoduje, że bieżące lub następne wywołanie `PipeWriter.FlushAsync` lub `PipeWriter.WriteAsync` zwraca element <xref:System.IO.Pipelines.FlushResult> z `IsCanceled` ustawioną na `true` .</span><span class="sxs-lookup"><span data-stu-id="1c649-282">Calling `PipeWriter.CancelPendingFlush` causes the current or next call to `PipeWriter.FlushAsync` or `PipeWriter.WriteAsync` to return a <xref:System.IO.Pipelines.FlushResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="1c649-283">Może to być przydatne w przypadku zatrzymania opróżniania w sposób nieniszczący i niewyjątkowy.</span><span class="sxs-lookup"><span data-stu-id="1c649-283">This can be useful for halting the yielding flush in a non-destructive and non-exceptional way.</span></span>

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a><span data-ttu-id="1c649-284">PipeWriter typowe problemy</span><span class="sxs-lookup"><span data-stu-id="1c649-284">PipeWriter common problems</span></span>

* <span data-ttu-id="1c649-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> i <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> Zwróć bufor z co najmniej żądaną ilością pamięci.</span><span class="sxs-lookup"><span data-stu-id="1c649-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> and <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="1c649-286">**Nie** zakładaj dokładnie rozmiarów buforów.</span><span class="sxs-lookup"><span data-stu-id="1c649-286">**Don't** assume exact buffer sizes.</span></span>
* <span data-ttu-id="1c649-287">Nie ma gwarancji, że kolejne wywołania będą zwracać ten sam bufor lub bufor o takim samym rozmiarze.</span><span class="sxs-lookup"><span data-stu-id="1c649-287">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
* <span data-ttu-id="1c649-288">Należy zażądać nowego buforu po wywołaniu <xref:System.IO.Pipelines.PipeWriter.Advance%2A> , aby kontynuować zapisywanie większej ilości danych.</span><span class="sxs-lookup"><span data-stu-id="1c649-288">A new buffer must be requested after calling <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to continue writing more data.</span></span> <span data-ttu-id="1c649-289">Nie można zapisać wcześniej uzyskanego buforu.</span><span class="sxs-lookup"><span data-stu-id="1c649-289">The previously acquired buffer can't be written to.</span></span>
* <span data-ttu-id="1c649-290">Wywołanie `GetMemory` lub `GetSpan` niekompletne wywołanie do `FlushAsync` nie jest bezpieczne.</span><span class="sxs-lookup"><span data-stu-id="1c649-290">Calling `GetMemory` or `GetSpan` while there's an incomplete call to `FlushAsync` isn't safe.</span></span>
* <span data-ttu-id="1c649-291">Wywołanie `Complete` lub `CompleteAsync` nieopróżnione dane mogą spowodować uszkodzenie pamięci.</span><span class="sxs-lookup"><span data-stu-id="1c649-291">Calling `Complete` or `CompleteAsync` while there's unflushed data can result in memory corruption.</span></span>

## <a name="iduplexpipe"></a><span data-ttu-id="1c649-292">IDuplexPipe</span><span class="sxs-lookup"><span data-stu-id="1c649-292">IDuplexPipe</span></span>

<span data-ttu-id="1c649-293"><xref:System.IO.Pipelines.IDuplexPipe>Jest to kontrakt dla typów, które obsługują odczyt i zapis.</span><span class="sxs-lookup"><span data-stu-id="1c649-293">The <xref:System.IO.Pipelines.IDuplexPipe> is a contract for types that support both reading and writing.</span></span> <span data-ttu-id="1c649-294">Na przykład połączenie sieciowe będzie reprezentowane przez `IDuplexPipe` .</span><span class="sxs-lookup"><span data-stu-id="1c649-294">For example, a network connection would be represented by an `IDuplexPipe`.</span></span>

 <span data-ttu-id="1c649-295">W przeciwieństwie do `Pipe` , który zawiera `PipeReader` a `PipeWriter` i `IDuplexPipe` , reprezentuje jedną stronę połączenia pełnego dupleksu.</span><span class="sxs-lookup"><span data-stu-id="1c649-295">Unlike `Pipe`, which contains a `PipeReader` and a `PipeWriter`, `IDuplexPipe` represents a single side of a full duplex connection.</span></span> <span data-ttu-id="1c649-296">Oznacza to, że zapis w `PipeWriter` programie nie zostanie odczytany z `PipeReader` .</span><span class="sxs-lookup"><span data-stu-id="1c649-296">That means what is written to the `PipeWriter` will not be read from the `PipeReader`.</span></span>

## <a name="streams"></a><span data-ttu-id="1c649-297">Strumienie</span><span class="sxs-lookup"><span data-stu-id="1c649-297">Streams</span></span>

<span data-ttu-id="1c649-298">Podczas odczytywania lub zapisywania danych strumienia zwykle dane są odczytywane przy użyciu deserializatora i zapisu danych przy użyciu serializatora.</span><span class="sxs-lookup"><span data-stu-id="1c649-298">When reading or writing stream data, you typically read data using a de-serializer and write data using a serializer.</span></span> <span data-ttu-id="1c649-299">Większość z tych interfejsów API odczytu i zapisu ma `Stream` parametr.</span><span class="sxs-lookup"><span data-stu-id="1c649-299">Most of these read and write stream APIs have a `Stream` parameter.</span></span> <span data-ttu-id="1c649-300">Aby ułatwić integrację z tymi istniejącymi interfejsami API `PipeReader` i `PipeWriter` uwidocznić <xref:System.IO.Pipelines.PipeReader.AsStream%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="1c649-300">To make it easier to integrate with these existing APIs, `PipeReader` and `PipeWriter` expose an <xref:System.IO.Pipelines.PipeReader.AsStream%2A> method.</span></span> <span data-ttu-id="1c649-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> zwraca `Stream` implementację otaczającą `PipeReader` lub `PipeWriter` .</span><span class="sxs-lookup"><span data-stu-id="1c649-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> returns a `Stream` implementation around the `PipeReader` or `PipeWriter`.</span></span>

### <a name="stream-example"></a><span data-ttu-id="1c649-302">Przykład strumienia</span><span class="sxs-lookup"><span data-stu-id="1c649-302">Stream example</span></span>

<span data-ttu-id="1c649-303">`PipeReader``PipeWriter`wystąpienia można tworzyć przy użyciu metod statycznych, które mają `Create` <xref:System.IO.Stream> obiekt i opcjonalne odpowiednie opcje tworzenia.</span><span class="sxs-lookup"><span data-stu-id="1c649-303">`PipeReader` and `PipeWriter` instances can be created using the static `Create` methods given a <xref:System.IO.Stream> object and optional corresponding creation options.</span></span>

<span data-ttu-id="1c649-304"><xref:System.IO.Pipelines.StreamPipeReaderOptions>Zezwól na kontrolę nad tworzeniem `PipeReader` wystąpienia z następującymi parametrami:</span><span class="sxs-lookup"><span data-stu-id="1c649-304">The <xref:System.IO.Pipelines.StreamPipeReaderOptions> allow for control over the creation of the `PipeReader` instance with the following parameters:</span></span>

- <span data-ttu-id="1c649-305"><xref:System.IO.Pipelines.StreamPipeReaderOptions.BufferSize?displayProperty=nameWithType> jest minimalnym rozmiarem buforu w bajtach używanym podczas dzierżawienia pamięci z puli, a wartością domyślną jest `4096` .</span><span class="sxs-lookup"><span data-stu-id="1c649-305"><xref:System.IO.Pipelines.StreamPipeReaderOptions.BufferSize?displayProperty=nameWithType> is the minimum buffer size in bytes used when renting memory from the pool, and defaults to `4096`.</span></span>
- <span data-ttu-id="1c649-306"><xref:System.IO.Pipelines.StreamPipeReaderOptions.LeaveOpen?displayProperty=nameWithType> Flaga określa, czy źródłowy strumień pozostał otwarty po `PipeReader` zakończeniu i ma wartość domyślną `false` .</span><span class="sxs-lookup"><span data-stu-id="1c649-306"><xref:System.IO.Pipelines.StreamPipeReaderOptions.LeaveOpen?displayProperty=nameWithType> flag determines whether or not the underlying stream is left open after the `PipeReader` completes, and defaults to `false`.</span></span>
- <span data-ttu-id="1c649-307"><xref:System.IO.Pipelines.StreamPipeReaderOptions.MinimumReadSize?displayProperty=nameWithType> reprezentuje próg pozostałych bajtów w buforze przed przydzieleniem nowego buforu i wartością domyślną `1024` .</span><span class="sxs-lookup"><span data-stu-id="1c649-307"><xref:System.IO.Pipelines.StreamPipeReaderOptions.MinimumReadSize?displayProperty=nameWithType> represents the threshold of remaining bytes in the buffer before a new buffer is allocated, and defaults to `1024`.</span></span>
- <span data-ttu-id="1c649-308"><xref:System.IO.Pipelines.StreamPipeReaderOptions.Pool?displayProperty=nameWithType> jest `MemoryPool<byte>` używany podczas przydzielania pamięci, a wartość domyślna to `null` .</span><span class="sxs-lookup"><span data-stu-id="1c649-308"><xref:System.IO.Pipelines.StreamPipeReaderOptions.Pool?displayProperty=nameWithType> is the `MemoryPool<byte>` used when allocating memory, and defaults to `null`.</span></span>

<span data-ttu-id="1c649-309"><xref:System.IO.Pipelines.StreamPipeWriterOptions>Zezwól na kontrolę nad tworzeniem `PipeWriter` wystąpienia z następującymi parametrami:</span><span class="sxs-lookup"><span data-stu-id="1c649-309">The <xref:System.IO.Pipelines.StreamPipeWriterOptions> allow for control over the creation of the `PipeWriter` instance with the following parameters:</span></span>

- <span data-ttu-id="1c649-310"><xref:System.IO.Pipelines.StreamPipeWriterOptions.LeaveOpen?displayProperty=nameWithType> Flaga określa, czy źródłowy strumień pozostał otwarty po `PipeWriter` zakończeniu i ma wartość domyślną `false` .</span><span class="sxs-lookup"><span data-stu-id="1c649-310"><xref:System.IO.Pipelines.StreamPipeWriterOptions.LeaveOpen?displayProperty=nameWithType> flag determines whether or not the underlying stream is left open after the `PipeWriter` completes, and defaults to `false`.</span></span>
- <span data-ttu-id="1c649-311"><xref:System.IO.Pipelines.StreamPipeWriterOptions.MinimumBufferSize?displayProperty=nameWithType> reprezentuje minimalny rozmiar buforu, który ma być używany podczas dzierżawy pamięci z <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool> i domyślnie `4096` .</span><span class="sxs-lookup"><span data-stu-id="1c649-311"><xref:System.IO.Pipelines.StreamPipeWriterOptions.MinimumBufferSize?displayProperty=nameWithType> represents the minimum buffer size to use when renting memory from the <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool>, and defaults to `4096`.</span></span>
- <span data-ttu-id="1c649-312"><xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool?displayProperty=nameWithType> jest `MemoryPool<byte>` używany podczas przydzielania pamięci, a wartość domyślna to `null` .</span><span class="sxs-lookup"><span data-stu-id="1c649-312"><xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool?displayProperty=nameWithType> is the `MemoryPool<byte>` used when allocating memory, and defaults to `null`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c649-313">Podczas tworzenia `PipeReader` `PipeWriter` wystąpień i używania `Create` metod należy wziąć pod uwagę `Stream` okres istnienia obiektu.</span><span class="sxs-lookup"><span data-stu-id="1c649-313">When creating `PipeReader` and `PipeWriter` instances using the `Create` methods, you need to consider the `Stream` object lifetime.</span></span> <span data-ttu-id="1c649-314">Jeśli potrzebny jest dostęp do strumienia po zakończeniu czytelnika lub składnika zapisywania, należy ustawić `LeaveOpen` flagę `true` na opcje tworzenia.</span><span class="sxs-lookup"><span data-stu-id="1c649-314">If you need access to the stream after the reader or writer is done with it, you'll need to set the `LeaveOpen` flag to `true` on the creation options.</span></span> <span data-ttu-id="1c649-315">W przeciwnym razie strumień zostanie zamknięty.</span><span class="sxs-lookup"><span data-stu-id="1c649-315">Otherwise, the stream will be closed.</span></span>

<span data-ttu-id="1c649-316">Poniższy kod ilustruje tworzenie `PipeReader` `PipeWriter` wystąpień i przy użyciu `Create` metod ze strumienia.</span><span class="sxs-lookup"><span data-stu-id="1c649-316">The following code demonstrates the creation of `PipeReader` and `PipeWriter` instances using the `Create` methods from a stream.</span></span>

:::code language="csharp" source="snippets/pipelines/Program.cs":::

<span data-ttu-id="1c649-317">Aplikacja używa programu, <xref:System.IO.StreamReader> Aby odczytać plik *lorem-ipsum.txt* jako strumień.</span><span class="sxs-lookup"><span data-stu-id="1c649-317">The application uses a <xref:System.IO.StreamReader> to read the *lorem-ipsum.txt* file as a stream.</span></span> <span data-ttu-id="1c649-318"><xref:System.IO.FileStream>Jest przenoszona do <xref:System.IO.Pipelines.PipeReader.Create%2A?displayProperty=nameWithType> , który tworzy wystąpienie `PipeReader` obiektu.</span><span class="sxs-lookup"><span data-stu-id="1c649-318">The <xref:System.IO.FileStream> is passed to <xref:System.IO.Pipelines.PipeReader.Create%2A?displayProperty=nameWithType>, which instantiates a `PipeReader` object.</span></span> <span data-ttu-id="1c649-319">Aplikacja konsolowa przekazuje następnie swój standardowy strumień wyjściowy do <xref:System.IO.Pipelines.PipeWriter.Create%2A?displayProperty=nameWithType> użycia <xref:System.Console.OpenStandardOutput?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1c649-319">The console application then passes its standard output stream to <xref:System.IO.Pipelines.PipeWriter.Create%2A?displayProperty=nameWithType> using <xref:System.Console.OpenStandardOutput?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1c649-320">Przykład obsługuje [Anulowanie](#cancellation).</span><span class="sxs-lookup"><span data-stu-id="1c649-320">The example supports [cancellation](#cancellation).</span></span>
