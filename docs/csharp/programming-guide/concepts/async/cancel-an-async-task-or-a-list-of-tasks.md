---
title: Anulowanie listy zadań (C#)
description: Dowiedz się, jak używać tokenów anulowania do sygnalizowania żądania anulowania do listy zadań.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 79c9db53674182489c89d657786bf39e8bb44b21
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805255"
---
# <a name="cancel-a-list-of-tasks-c"></a>Anulowanie listy zadań (C#)

Możesz anulować asynchroniczną aplikację konsolową, jeśli nie chcesz czekać na jej zakończenie. Postępując zgodnie z przykładem w tym temacie, można dodać anulowanie do aplikacji pobierającej zawartość listy witryn sieci Web. Można anulować wiele zadań, kojarząc <xref:System.Threading.CancellationTokenSource> wystąpienie z każdym zadaniem. Po wybraniu klawisza <kbd>Enter</kbd> anulujesz wszystkie zadania, które nie zostały jeszcze ukończone.

W tym samouczku opisano następujące czynności:

> [!div class="checklist"]
>
> - Tworzenie aplikacji konsolowej .NET
> - Pisanie aplikacji asynchronicznej, która obsługuje anulowanie
> - Prezentowanie anulowania sygnalizującego

## <a name="prerequisites"></a>Wymagania wstępne

Dla tego samouczka wymagane są następujące elementy:

- [Zestaw SDK programu .NET 5,0 lub nowszego](https://dotnet.microsoft.com/download/dotnet/5.0)
- Zintegrowane środowisko programistyczne (IDE)
  - [Zalecamy korzystanie z programu Visual Studio, Visual Studio Code lub Visual Studio dla komputerów Mac](https://visualstudio.microsoft.com)

### <a name="create-example-application"></a>Tworzenie przykładowej aplikacji

Utwórz nową aplikację konsolową platformy .NET Core. Można go utworzyć za pomocą [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) polecenia lub z [programu Visual Studio](/visualstudio/install/install-visual-studio). Otwórz plik *program.cs* w ulubionym edytorze kodu.

### <a name="replace-using-statements"></a>Zamień instrukcje using

Zastąp istniejące instrukcje using następującymi deklaracjami:

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;
```

## <a name="add-fields"></a>Dodawanie pól

W `Program` definicji klasy Dodaj następujące trzy pola:

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

<xref:System.Threading.CancellationTokenSource>Służy do sygnalizowania żądanego anulowania do <xref:System.Threading.CancellationToken> . `HttpClient`Umożliwia użytkownikom wysyłanie żądań HTTP i odbieranie odpowiedzi HTTP. `s_urlList`Zawiera wszystkie adresy URL, które aplikacja planuje przetworzyć.

## <a name="update-application-entry-point"></a>Aktualizuj punkt wejścia aplikacji

Głównym punktem wejścia do aplikacji konsolowej jest `Main` Metoda. Zastąp istniejącą metodę następującym:

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

Zaktualizowana `Main` Metoda jest teraz uważana za [asynchroniczny element główny](../../../whats-new/csharp-7.md#async-main), który umożliwia asynchroniczny punkt wejścia do pliku wykonywalnego. Zapisuje kilka komunikatów instruktażowych w konsoli programu, a następnie deklaruje <xref:System.Threading.Tasks.Task> wystąpienie o nazwie `cancelTask` , które odczytaje klucze konsoli. Po naciśnięciu klawisza <kbd>Enter</kbd> następuje wywołanie <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType> . Spowoduje to anulowanie tego sygnału. Następnie `sumPageSizesTask` zmienna jest przypisywana z `SumPageSizesAsync` metody. Oba zadania są następnie przenoszone do <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType> , które będą kontynuowane po zakończeniu jednego z tych dwóch zadań.

## <a name="create-the-asynchronous-sum-page-sizes-method"></a>Tworzenie asynchronicznej metody rozmiarów stron sum

Poniżej `Main` metody Dodaj `SumPageSizesAsync` metodę:

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

Metoda rozpoczyna się od utworzenia wystąpienia i uruchomienia <xref:System.Diagnostics.Stopwatch> . Następnie pętle przez poszczególne adresy URL w `s_urlList` wywołaniach i `ProcessUrlAsync` . Każda iteracja `s_cts.Token` jest przenoszona do metody, `ProcessUrlAsync` a kod zwraca a <xref:System.Threading.Tasks.Task%601> , gdzie `TResult` jest liczbą całkowitą:

```csharp
int total = 0;
foreach (string url in s_urlList)
{
    int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
    total += contentLength;
}
```

## <a name="add-process-method"></a>Dodaj metodę procesu

Dodaj następującą `ProcessUrlAsync` metodę poniżej `SumPageSizesAsync` metody:

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client, CancellationToken token)
{
    HttpResponseMessage response = await client.GetAsync(url, token);
    byte[] content = await response.Content.ReadAsByteArrayAsync();
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

W przypadku dowolnego podanego adresu URL metoda użyje `client` dostarczonego wystąpienia w celu uzyskania odpowiedzi jako `byte[]` . <xref:System.Threading.CancellationToken>Wystąpienie jest przesyłane do <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync?displayProperty=nameWithType> metod i. `token`Jest używany do rejestracji w celu zażądania anulowania. Długość jest zwracana po zapisaniu adresu URL i długości w konsoli.

### <a name="example-application-output"></a>Przykładowe dane wyjściowe aplikacji

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

## <a name="complete-example"></a>Pełny przykład

Poniższy kod jest pełnym tekstem pliku *program.cs* na przykład.

:::code language="csharp" source="snippets/cancel-tasks/cancel-tasks/Program.cs":::

## <a name="see-also"></a>Zobacz też

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [Programowanie asynchroniczne z Async i Await (C#)](index.md)

## <a name="next-steps"></a>Następne kroki

> [!div class="nextstepaction"]
> [Anulowanie zadań asynchronicznych po upływie czasu (C#)](cancel-async-tasks-after-a-period-of-time.md)
