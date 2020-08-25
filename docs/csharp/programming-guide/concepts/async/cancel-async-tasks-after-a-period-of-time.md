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
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a>Anulowanie zadań asynchronicznych po upływie czasu (C#)

Istnieje możliwość anulowania operacji asynchronicznej po upływie okresu czasu przy użyciu <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> metody, jeśli nie chcesz czekać na zakończenie operacji. Ta metoda służy do planowania anulowania wszystkich skojarzonych zadań, które nie zostały ukończone w okresie wyznaczonym przez `CancelAfter` wyrażenie.

Ten przykład dodaje do kodu, który został opracowany w polu [Anuluj listę zadań (C#)](cancel-an-async-task-or-a-list-of-tasks.md) , aby pobrać listę witryn sieci Web i wyświetlić długość zawartości każdej z nich.

W tym samouczku opisano następujące czynności:

> [!div class="checklist"]
>
> - Aktualizowanie istniejącej aplikacji konsolowej .NET
> - Planowanie anulowania

## <a name="prerequisites"></a>Wymagania wstępne

Dla tego samouczka wymagane są następujące elementy:

- Oczekiwano, że aplikacja zostanie utworzona w samouczku [anulowania listy zadań (C#)](cancel-an-async-task-or-a-list-of-tasks.md)
- [Zestaw SDK programu .NET 5,0 lub nowszego](https://dotnet.microsoft.com/download/dotnet/5.0)
- Zintegrowane środowisko programistyczne (IDE)
  - [Zalecamy korzystanie z programu Visual Studio, Visual Studio Code lub Visual Studio dla komputerów Mac](https://visualstudio.microsoft.com)

## <a name="update-application-entry-point"></a>Aktualizuj punkt wejścia aplikacji

Zastąp istniejącą `Main` metodę następującym:

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

Zaktualizowana `Main` Metoda zapisuje kilka komunikatów instruktażowych w konsoli programu. W ramach instrukcji [try catch](../../../language-reference/keywords/try-catch.md)należy wywołać metodę w <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> celu zaplanowania anulowania. Spowoduje to anulowanie działania po upływie czasu.

Następnie `SumPageSizesAsync` Metoda jest oczekiwana. Jeśli przetwarzanie wszystkich adresów URL odbywa się szybciej niż zaplanowane anulowanie, aplikacja zostanie zakończona. Jeśli jednak zaplanowane anulowanie zostanie wyzwolone przed przetworzeniem wszystkich adresów URL, <xref:System.Threading.Tasks.TaskCanceledException> zostanie zgłoszony.

### <a name="example-application-output"></a>Przykładowe dane wyjściowe aplikacji

```console
Application started.

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663

Tasks cancelled: timed out.

Application ending.
```

## <a name="complete-example"></a>Pełny przykład

Poniższy kod jest pełnym tekstem pliku *program.cs* na przykład.

:::code language="csharp" source="snippets/cancel-tasks/cancel-task-after-period-of-time/Program.cs":::

## <a name="see-also"></a>Zobacz też

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [Programowanie asynchroniczne z Async i Await (C#)](index.md)
- [Anulowanie listy zadań (C#)](cancel-an-async-task-or-a-list-of-tasks.md)
