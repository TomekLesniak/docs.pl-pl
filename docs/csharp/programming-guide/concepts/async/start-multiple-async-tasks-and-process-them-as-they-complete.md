---
title: Przetwarzanie zadań asynchronicznych po ich zakończeniu
description: Ten przykład pokazuje, jak używać Task. WhenAny w języku C# do uruchamiania wielu zadań i przetwarzać wyniki po zakończeniu, zamiast przetwarzać je w kolejności, w jakiej zostały uruchomione.
ms.date: 08/19/2020
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 860e94a9c3973ce56e7321741a1136f752aa3d18
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805242"
---
# <a name="process-asynchronous-tasks-as-they-complete-c"></a><span data-ttu-id="cae7a-103">Przetwarzaj zadania asynchroniczne w miarę ich ukończenia (C#)</span><span class="sxs-lookup"><span data-stu-id="cae7a-103">Process asynchronous tasks as they complete (C#)</span></span>

<span data-ttu-id="cae7a-104">Korzystając z programu <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> , można uruchomić wiele zadań w tym samym czasie i przetworzyć je w taki sposób, aby były wykonywane, a nie przetwarzane w kolejności, w której są uruchamiane.</span><span class="sxs-lookup"><span data-stu-id="cae7a-104">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they're completed rather than process them in the order in which they're started.</span></span>

<span data-ttu-id="cae7a-105">Poniższy przykład używa zapytania, aby utworzyć kolekcję zadań.</span><span class="sxs-lookup"><span data-stu-id="cae7a-105">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="cae7a-106">Każde zadanie pobiera zawartość określonej witryny sieci Web.</span><span class="sxs-lookup"><span data-stu-id="cae7a-106">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="cae7a-107">W każdej iteracji pętli while oczekiwane wywołanie <xref:System.Threading.Tasks.Task.WhenAny%2A> zwraca zadanie w kolekcji zadań, które kończą najpierw pobieranie.</span><span class="sxs-lookup"><span data-stu-id="cae7a-107">In each iteration of a while loop, an awaited call to <xref:System.Threading.Tasks.Task.WhenAny%2A> returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="cae7a-108">To zadanie jest usuwane z kolekcji i przetwarzane.</span><span class="sxs-lookup"><span data-stu-id="cae7a-108">That task is removed from the collection and processed.</span></span> <span data-ttu-id="cae7a-109">Pętla powtarza się, dopóki kolekcja nie będzie zawierać żadnych zadań.</span><span class="sxs-lookup"><span data-stu-id="cae7a-109">The loop repeats until the collection contains no more tasks.</span></span>

## <a name="create-example-application"></a><span data-ttu-id="cae7a-110">Tworzenie przykładowej aplikacji</span><span class="sxs-lookup"><span data-stu-id="cae7a-110">Create example application</span></span>

<span data-ttu-id="cae7a-111">Utwórz nową aplikację konsolową platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cae7a-111">Create a new .NET Core console application.</span></span> <span data-ttu-id="cae7a-112">Można go utworzyć przy użyciu [nowego konsoli programu dotnet](../../../../core/tools/dotnet-new.md#console) lub z [programu Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="cae7a-112">You can create one by using the [dotnet new console](../../../../core/tools/dotnet-new.md#console) command or from [Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="cae7a-113">Otwórz plik *program.cs* w ulubionym edytorze kodu.</span><span class="sxs-lookup"><span data-stu-id="cae7a-113">Open the *Program.cs* file in your favorite code editor.</span></span>

### <a name="replace-using-statements"></a><span data-ttu-id="cae7a-114">Zamień instrukcje using</span><span class="sxs-lookup"><span data-stu-id="cae7a-114">Replace using statements</span></span>

<span data-ttu-id="cae7a-115">Zastąp istniejące instrukcje using następującymi deklaracjami:</span><span class="sxs-lookup"><span data-stu-id="cae7a-115">Replace the existing using statements with these declarations:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Net.Http;
using System.Threading.Tasks;
```

## <a name="add-fields"></a><span data-ttu-id="cae7a-116">Dodawanie pól</span><span class="sxs-lookup"><span data-stu-id="cae7a-116">Add fields</span></span>

<span data-ttu-id="cae7a-117">W `Program` definicji klasy Dodaj następujące dwa pola:</span><span class="sxs-lookup"><span data-stu-id="cae7a-117">In the `Program` class definition, add the following two fields:</span></span>

```csharp
static readonly HttpClient s_client = new HttpClient
{
    MaxResponseContentBufferSize = 1_000_000
};

static readonly IEnumerable<string> s_urlList = new string[]
{
    "https://docs.microsoft.com",
    "https://docs.microsoft.com/aspnet/core",
    "https://docs.microsoft.com/azure",
    "https://docs.microsoft.com/azure/devops",
    "https://docs.microsoft.com/dotnet",
    "https://docs.microsoft.com/dynamics365",
    "https://docs.microsoft.com/education",
    "https://docs.microsoft.com/enterprise-mobility-security",
    "https://docs.microsoft.com/gaming",
    "https://docs.microsoft.com/graph",
    "https://docs.microsoft.com/microsoft-365",
    "https://docs.microsoft.com/office",
    "https://docs.microsoft.com/powershell",
    "https://docs.microsoft.com/sql",
    "https://docs.microsoft.com/surface",
    "https://docs.microsoft.com/system-center",
    "https://docs.microsoft.com/visualstudio",
    "https://docs.microsoft.com/windows",
    "https://docs.microsoft.com/xamarin"
};
```

<span data-ttu-id="cae7a-118">`HttpClient`Umożliwia użytkownikom wysyłanie żądań HTTP i odbieranie odpowiedzi HTTP.</span><span class="sxs-lookup"><span data-stu-id="cae7a-118">The `HttpClient` exposes the ability to send HTTP requests and receive HTTP responses.</span></span> <span data-ttu-id="cae7a-119">`s_urlList`Zawiera wszystkie adresy URL, które aplikacja planuje przetworzyć.</span><span class="sxs-lookup"><span data-stu-id="cae7a-119">The `s_urlList` holds all of the URLs that the application plans to process.</span></span>

## <a name="update-application-entry-point"></a><span data-ttu-id="cae7a-120">Aktualizuj punkt wejścia aplikacji</span><span class="sxs-lookup"><span data-stu-id="cae7a-120">Update application entry point</span></span>

<span data-ttu-id="cae7a-121">Głównym punktem wejścia do aplikacji konsolowej jest `Main` Metoda.</span><span class="sxs-lookup"><span data-stu-id="cae7a-121">The main entry point into the console application is the `Main` method.</span></span> <span data-ttu-id="cae7a-122">Zastąp istniejącą metodę następującym:</span><span class="sxs-lookup"><span data-stu-id="cae7a-122">Replace the existing method with the following:</span></span>

```csharp
static Task Main() => SumPageSizesAsync();
```

<span data-ttu-id="cae7a-123">Zaktualizowana `Main` Metoda jest teraz uważana za [asynchroniczny element główny](../../../whats-new/csharp-7.md#async-main), który umożliwia asynchroniczny punkt wejścia do pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="cae7a-123">The updated `Main` method is now considered an [Async main](../../../whats-new/csharp-7.md#async-main), which allows for an asynchronous entry point into the executable.</span></span> <span data-ttu-id="cae7a-124">Jest on wyrażony jako wywołanie `SumPageSizesAsync` .</span><span class="sxs-lookup"><span data-stu-id="cae7a-124">It is expressed a call to `SumPageSizesAsync`.</span></span>

## <a name="create-the-asynchronous-sum-page-sizes-method"></a><span data-ttu-id="cae7a-125">Tworzenie asynchronicznej metody rozmiarów stron sum</span><span class="sxs-lookup"><span data-stu-id="cae7a-125">Create the asynchronous sum page sizes method</span></span>

<span data-ttu-id="cae7a-126">Poniżej `Main` metody Dodaj `SumPageSizesAsync` metodę:</span><span class="sxs-lookup"><span data-stu-id="cae7a-126">Below the `Main` method, add the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in s_urlList
        select ProcessUrlAsync(url, s_client);

    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

    int total = 0;
    while (downloadTasks.Any())
    {
        Task<int> finishedTask = await Task.WhenAny(downloadTasks);
        downloadTasks.Remove(finishedTask);
        total += await finishedTask;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

<span data-ttu-id="cae7a-127">Metoda rozpoczyna się od utworzenia wystąpienia i uruchomienia <xref:System.Diagnostics.Stopwatch> .</span><span class="sxs-lookup"><span data-stu-id="cae7a-127">The method starts by instantiating and starting a <xref:System.Diagnostics.Stopwatch>.</span></span> <span data-ttu-id="cae7a-128">Następnie zawiera zapytanie, które po wykonaniu tworzy kolekcję zadań.</span><span class="sxs-lookup"><span data-stu-id="cae7a-128">It then includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="cae7a-129">Każde wywołanie `ProcessUrlAsync` w poniższym kodzie zwraca a <xref:System.Threading.Tasks.Task%601> , gdzie `TResult` jest liczbą całkowitą:</span><span class="sxs-lookup"><span data-stu-id="cae7a-129">Each call to `ProcessUrlAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
IEnumerable<Task<int>> downloadTasksQuery =
    from url in s_urlList
    select ProcessUrlAsync(url, s_client);
```

<span data-ttu-id="cae7a-130">Z powodu [odroczonego wykonania](../../../../standard/linq/deferred-execution-example.md) za pomocą LINQ, należy wywołać, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> Aby rozpocząć każde zadanie.</span><span class="sxs-lookup"><span data-stu-id="cae7a-130">Due to [deferred execution](../../../../standard/linq/deferred-execution-example.md) with the LINQ, you call <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> to start each task.</span></span>

```csharp
List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
```

<span data-ttu-id="cae7a-131">`while`Pętla wykonuje następujące kroki dla każdego zadania w kolekcji:</span><span class="sxs-lookup"><span data-stu-id="cae7a-131">The `while` loop performs the following steps for each task in the collection:</span></span>

1. <span data-ttu-id="cae7a-132">Oczekuje na wywołanie w `WhenAny` celu zidentyfikowania pierwszego zadania w kolekcji, które zakończyło pobieranie.</span><span class="sxs-lookup"><span data-stu-id="cae7a-132">Awaits a call to `WhenAny` to identify the first task in the collection that has finished its download.</span></span>

    ```csharp
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
    ```

1. <span data-ttu-id="cae7a-133">Usuwa to zadanie z kolekcji.</span><span class="sxs-lookup"><span data-stu-id="cae7a-133">Removes that task from the collection.</span></span>

    ```csharp
    downloadTasks.Remove(firstFinishedTask);
    ```

1. <span data-ttu-id="cae7a-134">Czeka `finishedTask` , który jest zwracany przez wywołanie metody `ProcessUrlAsync` .</span><span class="sxs-lookup"><span data-stu-id="cae7a-134">Awaits `finishedTask`, which is returned by a call to `ProcessUrlAsync`.</span></span> <span data-ttu-id="cae7a-135">`finishedTask`Zmienna to <xref:System.Threading.Tasks.Task%601> gdzie `TResult` jest liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="cae7a-135">The `finishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span> <span data-ttu-id="cae7a-136">Zadanie zostało już ukończone, ale czeka na pobranie długości pobranej witryny sieci Web, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="cae7a-136">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span> <span data-ttu-id="cae7a-137">Jeśli zadanie jest błędne, `await` program zgłosi pierwszy wyjątek podrzędny zapisany w `AggregateException` , w przeciwieństwie do odczytu <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> właściwości, która spowodowałaby wygenerowanie `AggregateException` .</span><span class="sxs-lookup"><span data-stu-id="cae7a-137">If the task is faulted, `await` will throw the first child exception stored in the `AggregateException`, unlike reading the <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> property, which would throw the `AggregateException`.</span></span>

    ```csharp
    total += await finishedTask;
    ```

## <a name="add-process-method"></a><span data-ttu-id="cae7a-138">Dodaj metodę procesu</span><span class="sxs-lookup"><span data-stu-id="cae7a-138">Add process method</span></span>

<span data-ttu-id="cae7a-139">Dodaj następującą `ProcessUrlAsync` metodę poniżej `SumPageSizesAsync` metody:</span><span class="sxs-lookup"><span data-stu-id="cae7a-139">Add the following `ProcessUrlAsync` method below the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client)
{
    byte[] content = await client.GetByteArrayAsync(url);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

<span data-ttu-id="cae7a-140">W przypadku dowolnego podanego adresu URL metoda użyje `client` dostarczonego wystąpienia w celu uzyskania odpowiedzi jako `byte[]` .</span><span class="sxs-lookup"><span data-stu-id="cae7a-140">For any given URL, the method will use the `client` instance provided to get the response as a `byte[]`.</span></span> <span data-ttu-id="cae7a-141">Długość jest zwracana po zapisaniu adresu URL i długości w konsoli.</span><span class="sxs-lookup"><span data-stu-id="cae7a-141">The length is returned after the URL and length is written to the console.</span></span>

<span data-ttu-id="cae7a-142">Uruchom program kilka razy, aby sprawdzić, czy pobrane długości nie zawsze pojawiają się w tej samej kolejności.</span><span class="sxs-lookup"><span data-stu-id="cae7a-142">Run the program several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

> [!CAUTION]
> <span data-ttu-id="cae7a-143">Można użyć `WhenAny` w pętli, jak opisano w przykładzie, w celu rozwiązania problemów obejmujących niewielką liczbę zadań.</span><span class="sxs-lookup"><span data-stu-id="cae7a-143">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="cae7a-144">Jednak inne podejścia są bardziej wydajne, jeśli masz dużą liczbę zadań do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="cae7a-144">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="cae7a-145">Aby uzyskać więcej informacji i przykładów, zobacz [Przetwarzanie zadań po ich zakończeniu](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete).</span><span class="sxs-lookup"><span data-stu-id="cae7a-145">For more information and examples, see [Processing tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete).</span></span>

## <a name="complete-example"></a><span data-ttu-id="cae7a-146">Pełny przykład</span><span class="sxs-lookup"><span data-stu-id="cae7a-146">Complete example</span></span>

<span data-ttu-id="cae7a-147">Poniższy kod jest pełnym tekstem pliku *program.cs* na przykład.</span><span class="sxs-lookup"><span data-stu-id="cae7a-147">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/multiple-tasks/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="cae7a-148">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cae7a-148">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="cae7a-149">Programowanie asynchroniczne z Async i Await (C#)</span><span class="sxs-lookup"><span data-stu-id="cae7a-149">Asynchronous programming with async and await (C#)</span></span>](index.md)
