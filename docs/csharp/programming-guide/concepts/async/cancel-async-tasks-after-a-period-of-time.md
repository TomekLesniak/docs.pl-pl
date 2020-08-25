---
title: Anulowanie zadań asynchronicznych po upływie czasu (C#) "
description: Dowiedz się, jak zaplanować anulowanie wszystkich skojarzonych zadań, które nie zostały ukończone w danym okresie czasu.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: ad9064f8f45a737982ffc35ab4ea2395ddae9016
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811421"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a><span data-ttu-id="8ae1d-103">Anulowanie zadań asynchronicznych po upływie czasu (C#)</span><span class="sxs-lookup"><span data-stu-id="8ae1d-103">Cancel async tasks after a period of time (C#)</span></span>

<span data-ttu-id="8ae1d-104">Istnieje możliwość anulowania operacji asynchronicznej po upływie okresu czasu przy użyciu <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> metody, jeśli nie chcesz czekać na zakończenie operacji.</span><span class="sxs-lookup"><span data-stu-id="8ae1d-104">You can cancel an asynchronous operation after a period of time by using the <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="8ae1d-105">Ta metoda służy do planowania anulowania wszystkich skojarzonych zadań, które nie zostały ukończone w okresie wyznaczonym przez `CancelAfter` wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="8ae1d-105">This method schedules the cancellation of any associated tasks that aren't complete within the period of time that's designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="8ae1d-106">Ten przykład dodaje do kodu, który został opracowany w polu [Anuluj listę zadań (C#)](cancel-an-async-task-or-a-list-of-tasks.md) , aby pobrać listę witryn sieci Web i wyświetlić długość zawartości każdej z nich.</span><span class="sxs-lookup"><span data-stu-id="8ae1d-106">This example adds to the code that's developed in [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

<span data-ttu-id="8ae1d-107">W tym samouczku opisano następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="8ae1d-107">This tutorial covers:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="8ae1d-108">Aktualizowanie istniejącej aplikacji konsolowej .NET</span><span class="sxs-lookup"><span data-stu-id="8ae1d-108">Updating an existing .NET console application</span></span>
> - <span data-ttu-id="8ae1d-109">Planowanie anulowania</span><span class="sxs-lookup"><span data-stu-id="8ae1d-109">Scheduling a cancellation</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ae1d-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="8ae1d-110">Prerequisites</span></span>

<span data-ttu-id="8ae1d-111">Dla tego samouczka wymagane są następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="8ae1d-111">This tutorial requires the following:</span></span>

- <span data-ttu-id="8ae1d-112">Oczekiwano, że aplikacja zostanie utworzona w samouczku [anulowania listy zadań (C#)](cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="8ae1d-112">You're expected to have created an application in the [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) tutorial</span></span>
- [<span data-ttu-id="8ae1d-113">Zestaw SDK programu .NET 5,0 lub nowszego</span><span class="sxs-lookup"><span data-stu-id="8ae1d-113">.NET 5.0 or later SDK</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- <span data-ttu-id="8ae1d-114">Zintegrowane środowisko programistyczne (IDE)</span><span class="sxs-lookup"><span data-stu-id="8ae1d-114">Integrated development environment (IDE)</span></span>
  - [<span data-ttu-id="8ae1d-115">Zalecamy korzystanie z programu Visual Studio, Visual Studio Code lub Visual Studio dla komputerów Mac</span><span class="sxs-lookup"><span data-stu-id="8ae1d-115">We recommend Visual Studio, Visual Studio Code, or Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com)

## <a name="update-application-entry-point"></a><span data-ttu-id="8ae1d-116">Aktualizuj punkt wejścia aplikacji</span><span class="sxs-lookup"><span data-stu-id="8ae1d-116">Update application entry point</span></span>

<span data-ttu-id="8ae1d-117">Zastąp istniejącą `Main` metodę następującym:</span><span class="sxs-lookup"><span data-stu-id="8ae1d-117">Replace the existing `Main` method with the following:</span></span>

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");

    try
    {
        s_cts.CancelAfter(3500);

        await SumPageSizesAsync();
    }
    catch (TaskCanceledException)
    {
        Console.WriteLine("\nTasks cancelled: timed out.\n");
    }

    Console.WriteLine("Application ending.");
}
```

<span data-ttu-id="8ae1d-118">Zaktualizowana `Main` Metoda zapisuje kilka komunikatów instruktażowych w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="8ae1d-118">The updated `Main` method writes a few instructional messages to the console.</span></span> <span data-ttu-id="8ae1d-119">W ramach instrukcji [try catch](../../../language-reference/keywords/try-catch.md)należy wywołać metodę w <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> celu zaplanowania anulowania.</span><span class="sxs-lookup"><span data-stu-id="8ae1d-119">Within the [try catch](../../../language-reference/keywords/try-catch.md), a call to <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> to schedule a cancellation.</span></span> <span data-ttu-id="8ae1d-120">Spowoduje to anulowanie działania po upływie czasu.</span><span class="sxs-lookup"><span data-stu-id="8ae1d-120">This will signal cancellation after a period of time.</span></span>

<span data-ttu-id="8ae1d-121">Następnie `SumPageSizesAsync` Metoda jest oczekiwana.</span><span class="sxs-lookup"><span data-stu-id="8ae1d-121">Next, the `SumPageSizesAsync` method is awaited.</span></span> <span data-ttu-id="8ae1d-122">Jeśli przetwarzanie wszystkich adresów URL odbywa się szybciej niż zaplanowane anulowanie, aplikacja zostanie zakończona.</span><span class="sxs-lookup"><span data-stu-id="8ae1d-122">If processing all of the URLs occurs faster than the scheduled cancellation, the application ends.</span></span> <span data-ttu-id="8ae1d-123">Jeśli jednak zaplanowane anulowanie zostanie wyzwolone przed przetworzeniem wszystkich adresów URL, <xref:System.Threading.Tasks.TaskCanceledException> zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="8ae1d-123">However, if the scheduled cancellation is triggered before all of the URLs are processed, a <xref:System.Threading.Tasks.TaskCanceledException> is thrown.</span></span>

### <a name="example-application-output"></a><span data-ttu-id="8ae1d-124">Przykładowe dane wyjściowe aplikacji</span><span class="sxs-lookup"><span data-stu-id="8ae1d-124">Example application output</span></span>

```console
Application started.

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663

Tasks cancelled: timed out.

Application ending.
```

## <a name="complete-example"></a><span data-ttu-id="8ae1d-125">Pełny przykład</span><span class="sxs-lookup"><span data-stu-id="8ae1d-125">Complete example</span></span>

<span data-ttu-id="8ae1d-126">Poniższy kod jest pełnym tekstem pliku *program.cs* na przykład.</span><span class="sxs-lookup"><span data-stu-id="8ae1d-126">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/cancel-tasks/cancel-task-after-period-of-time/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="8ae1d-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8ae1d-127">See also</span></span>

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [<span data-ttu-id="8ae1d-128">Programowanie asynchroniczne z Async i Await (C#)</span><span class="sxs-lookup"><span data-stu-id="8ae1d-128">Asynchronous programming with async and await (C#)</span></span>](index.md)
- [<span data-ttu-id="8ae1d-129">Anulowanie listy zadań (C#)</span><span class="sxs-lookup"><span data-stu-id="8ae1d-129">Cancel a list of tasks (C#)</span></span>](cancel-an-async-task-or-a-list-of-tasks.md)
