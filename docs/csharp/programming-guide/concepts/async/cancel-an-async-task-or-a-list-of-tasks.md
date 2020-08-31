---
title: Anulowanie listy zadań (C#)
description: Dowiedz się, jak używać tokenów anulowania do sygnalizowania żądania anulowania do listy zadań.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 30bef5d1a5082fbd3757377dbedb8f9b9d17e218
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053096"
---
# <a name="cancel-a-list-of-tasks-c"></a><span data-ttu-id="d20ca-103">Anulowanie listy zadań (C#)</span><span class="sxs-lookup"><span data-stu-id="d20ca-103">Cancel a list of tasks (C#)</span></span>

<span data-ttu-id="d20ca-104">Możesz anulować asynchroniczną aplikację konsolową, jeśli nie chcesz czekać na jej zakończenie.</span><span class="sxs-lookup"><span data-stu-id="d20ca-104">You can cancel an async console application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="d20ca-105">Postępując zgodnie z przykładem w tym temacie, można dodać anulowanie do aplikacji pobierającej zawartość listy witryn sieci Web.</span><span class="sxs-lookup"><span data-stu-id="d20ca-105">By following the example in this topic, you can add a cancellation to an application that downloads the contents of a list of websites.</span></span> <span data-ttu-id="d20ca-106">Można anulować wiele zadań, kojarząc <xref:System.Threading.CancellationTokenSource> wystąpienie z każdym zadaniem.</span><span class="sxs-lookup"><span data-stu-id="d20ca-106">You can cancel many tasks by associating the <xref:System.Threading.CancellationTokenSource> instance with each task.</span></span> <span data-ttu-id="d20ca-107">Po wybraniu klawisza <kbd>Enter</kbd> anulujesz wszystkie zadania, które nie zostały jeszcze ukończone.</span><span class="sxs-lookup"><span data-stu-id="d20ca-107">If you select the <kbd>Enter</kbd> key, you cancel all tasks that aren't yet complete.</span></span>

<span data-ttu-id="d20ca-108">W tym samouczku opisano następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="d20ca-108">This tutorial covers:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="d20ca-109">Tworzenie aplikacji konsolowej .NET</span><span class="sxs-lookup"><span data-stu-id="d20ca-109">Creating a .NET console application</span></span>
> - <span data-ttu-id="d20ca-110">Pisanie aplikacji asynchronicznej, która obsługuje anulowanie</span><span class="sxs-lookup"><span data-stu-id="d20ca-110">Writing an async application that supports cancellation</span></span>
> - <span data-ttu-id="d20ca-111">Prezentowanie anulowania sygnalizującego</span><span class="sxs-lookup"><span data-stu-id="d20ca-111">Demonstrating signaling cancellation</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d20ca-112">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="d20ca-112">Prerequisites</span></span>

<span data-ttu-id="d20ca-113">Dla tego samouczka wymagane są następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="d20ca-113">This tutorial requires the following:</span></span>

- [<span data-ttu-id="d20ca-114">Zestaw SDK programu .NET 5,0 lub nowszego</span><span class="sxs-lookup"><span data-stu-id="d20ca-114">.NET 5.0 or later SDK</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- <span data-ttu-id="d20ca-115">Zintegrowane środowisko programistyczne (IDE)</span><span class="sxs-lookup"><span data-stu-id="d20ca-115">Integrated development environment (IDE)</span></span>
  - [<span data-ttu-id="d20ca-116">Zalecamy korzystanie z programu Visual Studio, Visual Studio Code lub Visual Studio dla komputerów Mac</span><span class="sxs-lookup"><span data-stu-id="d20ca-116">We recommend Visual Studio, Visual Studio Code, or Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com)

### <a name="create-example-application"></a><span data-ttu-id="d20ca-117">Tworzenie przykładowej aplikacji</span><span class="sxs-lookup"><span data-stu-id="d20ca-117">Create example application</span></span>

<span data-ttu-id="d20ca-118">Utwórz nową aplikację konsolową platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d20ca-118">Create a new .NET Core console application.</span></span> <span data-ttu-id="d20ca-119">Można go utworzyć za pomocą [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) polecenia lub z [programu Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="d20ca-119">You can create one by using the [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) command or from [Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="d20ca-120">Otwórz plik *program.cs* w ulubionym edytorze kodu.</span><span class="sxs-lookup"><span data-stu-id="d20ca-120">Open the *Program.cs* file in your favorite code editor.</span></span>

### <a name="replace-using-statements"></a><span data-ttu-id="d20ca-121">Zamień instrukcje using</span><span class="sxs-lookup"><span data-stu-id="d20ca-121">Replace using statements</span></span>

<span data-ttu-id="d20ca-122">Zastąp istniejące instrukcje using następującymi deklaracjami:</span><span class="sxs-lookup"><span data-stu-id="d20ca-122">Replace the existing using statements with these declarations:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;
```

## <a name="add-fields"></a><span data-ttu-id="d20ca-123">Dodawanie pól</span><span class="sxs-lookup"><span data-stu-id="d20ca-123">Add fields</span></span>

<span data-ttu-id="d20ca-124">W `Program` definicji klasy Dodaj następujące trzy pola:</span><span class="sxs-lookup"><span data-stu-id="d20ca-124">In the `Program` class definition, add these three fields:</span></span>

```csharp
static readonly CancellationTokenSource s_cts = new CancellationTokenSource();

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

<span data-ttu-id="d20ca-125"><xref:System.Threading.CancellationTokenSource>Służy do sygnalizowania żądanego anulowania do <xref:System.Threading.CancellationToken> .</span><span class="sxs-lookup"><span data-stu-id="d20ca-125">The <xref:System.Threading.CancellationTokenSource> is used to signal a requested cancellation to a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="d20ca-126">`HttpClient`Umożliwia użytkownikom wysyłanie żądań HTTP i odbieranie odpowiedzi HTTP.</span><span class="sxs-lookup"><span data-stu-id="d20ca-126">The `HttpClient` exposes the ability to send HTTP requests and receive HTTP responses.</span></span> <span data-ttu-id="d20ca-127">`s_urlList`Zawiera wszystkie adresy URL, które aplikacja planuje przetworzyć.</span><span class="sxs-lookup"><span data-stu-id="d20ca-127">The `s_urlList` holds all of the URLs that the application plans to process.</span></span>

## <a name="update-application-entry-point"></a><span data-ttu-id="d20ca-128">Aktualizuj punkt wejścia aplikacji</span><span class="sxs-lookup"><span data-stu-id="d20ca-128">Update application entry point</span></span>

<span data-ttu-id="d20ca-129">Głównym punktem wejścia do aplikacji konsolowej jest `Main` Metoda.</span><span class="sxs-lookup"><span data-stu-id="d20ca-129">The main entry point into the console application is the `Main` method.</span></span> <span data-ttu-id="d20ca-130">Zastąp istniejącą metodę następującym:</span><span class="sxs-lookup"><span data-stu-id="d20ca-130">Replace the existing method with the following:</span></span>

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");
    Console.WriteLine("Press the ENTER key to cancel...\n");

    Task cancelTask = Task.Run(() =>
    {
        while (Console.ReadKey().Key != ConsoleKey.Enter)
        {
            Console.WriteLine("Press the ENTER key to cancel...");
        }

        Console.WriteLine("\nENTER key pressed: cancelling downloads.\n");
        s_cts.Cancel();
    });

    Task sumPageSizesTask = SumPageSizesAsync();

    await Task.WhenAny(new[] { cancelTask, sumPageSizesTask });

    Console.WriteLine("Application ending.");
}
```

<span data-ttu-id="d20ca-131">Zaktualizowana `Main` Metoda jest teraz uważana za [asynchroniczny element główny](../../../whats-new/csharp-7-1.md#async-main), który umożliwia asynchroniczny punkt wejścia do pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="d20ca-131">The updated `Main` method is now considered an [Async main](../../../whats-new/csharp-7-1.md#async-main), which allows for an asynchronous entry point into the executable.</span></span> <span data-ttu-id="d20ca-132">Zapisuje kilka komunikatów instruktażowych w konsoli programu, a następnie deklaruje <xref:System.Threading.Tasks.Task> wystąpienie o nazwie `cancelTask` , które odczytaje klucze konsoli.</span><span class="sxs-lookup"><span data-stu-id="d20ca-132">It writes a few instructional messages to the console, then declares a <xref:System.Threading.Tasks.Task> instance named `cancelTask`, which will read console key strokes.</span></span> <span data-ttu-id="d20ca-133">Po naciśnięciu klawisza <kbd>Enter</kbd> następuje wywołanie <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="d20ca-133">If the <kbd>Enter</kbd> key is pressed, a call to <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType> is made.</span></span> <span data-ttu-id="d20ca-134">Spowoduje to anulowanie tego sygnału.</span><span class="sxs-lookup"><span data-stu-id="d20ca-134">This will signal cancellation.</span></span> <span data-ttu-id="d20ca-135">Następnie `sumPageSizesTask` zmienna jest przypisywana z `SumPageSizesAsync` metody.</span><span class="sxs-lookup"><span data-stu-id="d20ca-135">Next, the `sumPageSizesTask` variable is assigned from the `SumPageSizesAsync` method.</span></span> <span data-ttu-id="d20ca-136">Oba zadania są następnie przenoszone do <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType> , które będą kontynuowane po zakończeniu jednego z tych dwóch zadań.</span><span class="sxs-lookup"><span data-stu-id="d20ca-136">Both tasks are then passed to <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType>, which will continue when any of the two tasks have completed.</span></span>

## <a name="create-the-asynchronous-sum-page-sizes-method"></a><span data-ttu-id="d20ca-137">Tworzenie asynchronicznej metody rozmiarów stron sum</span><span class="sxs-lookup"><span data-stu-id="d20ca-137">Create the asynchronous sum page sizes method</span></span>

<span data-ttu-id="d20ca-138">Poniżej `Main` metody Dodaj `SumPageSizesAsync` metodę:</span><span class="sxs-lookup"><span data-stu-id="d20ca-138">Below the `Main` method, add the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    int total = 0;
    foreach (string url in s_urlList)
    {
        int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
        total += contentLength;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

<span data-ttu-id="d20ca-139">Metoda rozpoczyna się od utworzenia wystąpienia i uruchomienia <xref:System.Diagnostics.Stopwatch> .</span><span class="sxs-lookup"><span data-stu-id="d20ca-139">The method starts by instantiating and starting a <xref:System.Diagnostics.Stopwatch>.</span></span> <span data-ttu-id="d20ca-140">Następnie pętle przez poszczególne adresy URL w `s_urlList` wywołaniach i `ProcessUrlAsync` .</span><span class="sxs-lookup"><span data-stu-id="d20ca-140">It then loops through each URL in the `s_urlList` and calls `ProcessUrlAsync`.</span></span> <span data-ttu-id="d20ca-141">Każda iteracja `s_cts.Token` jest przenoszona do metody, `ProcessUrlAsync` a kod zwraca a <xref:System.Threading.Tasks.Task%601> , gdzie `TResult` jest liczbą całkowitą:</span><span class="sxs-lookup"><span data-stu-id="d20ca-141">With each iteration, the `s_cts.Token` is passed into the `ProcessUrlAsync` method and the code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
int total = 0;
foreach (string url in s_urlList)
{
    int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
    total += contentLength;
}
```

## <a name="add-process-method"></a><span data-ttu-id="d20ca-142">Dodaj metodę procesu</span><span class="sxs-lookup"><span data-stu-id="d20ca-142">Add process method</span></span>

<span data-ttu-id="d20ca-143">Dodaj następującą `ProcessUrlAsync` metodę poniżej `SumPageSizesAsync` metody:</span><span class="sxs-lookup"><span data-stu-id="d20ca-143">Add the following `ProcessUrlAsync` method below the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client, CancellationToken token)
{
    HttpResponseMessage response = await client.GetAsync(url, token);
    byte[] content = await response.Content.ReadAsByteArrayAsync(token);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

<span data-ttu-id="d20ca-144">W przypadku dowolnego podanego adresu URL metoda użyje `client` dostarczonego wystąpienia w celu uzyskania odpowiedzi jako `byte[]` .</span><span class="sxs-lookup"><span data-stu-id="d20ca-144">For any given URL, the method will use the `client` instance provided to get the response as a `byte[]`.</span></span> <span data-ttu-id="d20ca-145"><xref:System.Threading.CancellationToken>Wystąpienie jest przesyłane do <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync(System.Threading.CancellationToken)?displayProperty=nameWithType> metod i.</span><span class="sxs-lookup"><span data-stu-id="d20ca-145">The <xref:System.Threading.CancellationToken> instance is passed into the <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> and <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync(System.Threading.CancellationToken)?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="d20ca-146">`token`Jest używany do rejestracji w celu zażądania anulowania.</span><span class="sxs-lookup"><span data-stu-id="d20ca-146">The `token` is used to register for requested cancellation.</span></span> <span data-ttu-id="d20ca-147">Długość jest zwracana po zapisaniu adresu URL i długości w konsoli.</span><span class="sxs-lookup"><span data-stu-id="d20ca-147">The length is returned after the URL and length is written to the console.</span></span>

### <a name="example-application-output"></a><span data-ttu-id="d20ca-148">Przykładowe dane wyjściowe aplikacji</span><span class="sxs-lookup"><span data-stu-id="d20ca-148">Example application output</span></span>

```console
Application started.
Press the ENTER key to cancel...

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663
https://docs.microsoft.com/dotnet                                67,452
https://docs.microsoft.com/dynamics365                           48,582
https://docs.microsoft.com/education                             22,924

ENTER key pressed: cancelling downloads.

Application ending.
```

## <a name="complete-example"></a><span data-ttu-id="d20ca-149">Pełny przykład</span><span class="sxs-lookup"><span data-stu-id="d20ca-149">Complete example</span></span>

<span data-ttu-id="d20ca-150">Poniższy kod jest pełnym tekstem pliku *program.cs* na przykład.</span><span class="sxs-lookup"><span data-stu-id="d20ca-150">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/cancel-tasks/cancel-tasks/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="d20ca-151">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d20ca-151">See also</span></span>

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [<span data-ttu-id="d20ca-152">Programowanie asynchroniczne z Async i Await (C#)</span><span class="sxs-lookup"><span data-stu-id="d20ca-152">Asynchronous programming with async and await (C#)</span></span>](index.md)

## <a name="next-steps"></a><span data-ttu-id="d20ca-153">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="d20ca-153">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d20ca-154">Anulowanie zadań asynchronicznych po upływie czasu (C#)</span><span class="sxs-lookup"><span data-stu-id="d20ca-154">Cancel async tasks after a period of time (C#)</span></span>](cancel-async-tasks-after-a-period-of-time.md)
