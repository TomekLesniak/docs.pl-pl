---
title: Przetwarzanie zadań asynchronicznych po ich zakończeniu
description: Ten przykład pokazuje, jak używać Task. WhenAny w języku C# do uruchamiania wielu zadań i przetwarzać wyniki po zakończeniu, zamiast przetwarzać je w kolejności, w jakiej zostały uruchomione.
ms.date: 08/19/2020
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 520953eaf851dc82440e39b348aa4b246255e126
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557310"
---
# <a name="process-asynchronous-tasks-as-they-complete-c"></a>Przetwarzaj zadania asynchroniczne w miarę ich ukończenia (C#)

Korzystając z programu <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> , można uruchomić wiele zadań w tym samym czasie i przetworzyć je w taki sposób, aby były wykonywane, a nie przetwarzane w kolejności, w której są uruchamiane.

Poniższy przykład używa zapytania, aby utworzyć kolekcję zadań. Każde zadanie pobiera zawartość określonej witryny sieci Web. W każdej iteracji pętli while oczekiwane wywołanie <xref:System.Threading.Tasks.Task.WhenAny%2A> zwraca zadanie w kolekcji zadań, które kończą najpierw pobieranie. To zadanie jest usuwane z kolekcji i przetwarzane. Pętla powtarza się, dopóki kolekcja nie będzie zawierać żadnych zadań.

## <a name="create-example-application"></a>Tworzenie przykładowej aplikacji

Utwórz nową aplikację konsolową platformy .NET Core. Można go utworzyć przy użyciu [nowego konsoli programu dotnet](../../../../core/tools/dotnet-new.md#console) lub z [programu Visual Studio](/visualstudio/install/install-visual-studio). Otwórz plik *program.cs* w ulubionym edytorze kodu.

### <a name="replace-using-statements"></a>Zamień instrukcje using

Zastąp istniejące instrukcje using następującymi deklaracjami:

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Net.Http;
using System.Threading.Tasks;
```

## <a name="add-fields"></a>Dodawanie pól

W `Program` definicji klasy Dodaj następujące dwa pola:

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

`HttpClient`Umożliwia użytkownikom wysyłanie żądań HTTP i odbieranie odpowiedzi HTTP. `s_urlList`Zawiera wszystkie adresy URL, które aplikacja planuje przetworzyć.

## <a name="update-application-entry-point"></a>Aktualizuj punkt wejścia aplikacji

Głównym punktem wejścia do aplikacji konsolowej jest `Main` Metoda. Zastąp istniejącą metodę następującym:

```csharp
static Task Main() => SumPageSizesAsync();
```

Zaktualizowana `Main` Metoda jest teraz uważana za [asynchroniczny element główny](../../../whats-new/csharp-7-1.md#async-main), który umożliwia asynchroniczny punkt wejścia do pliku wykonywalnego. Jest on wyrażony jako wywołanie `SumPageSizesAsync` .

## <a name="create-the-asynchronous-sum-page-sizes-method"></a>Tworzenie asynchronicznej metody rozmiarów stron sum

Poniżej `Main` metody Dodaj `SumPageSizesAsync` metodę:

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

Metoda rozpoczyna się od utworzenia wystąpienia i uruchomienia <xref:System.Diagnostics.Stopwatch> . Następnie zawiera zapytanie, które po wykonaniu tworzy kolekcję zadań. Każde wywołanie `ProcessUrlAsync` w poniższym kodzie zwraca a <xref:System.Threading.Tasks.Task%601> , gdzie `TResult` jest liczbą całkowitą:

```csharp
IEnumerable<Task<int>> downloadTasksQuery =
    from url in s_urlList
    select ProcessUrlAsync(url, s_client);
```

Z powodu [odroczonego wykonania](../../../../standard/linq/deferred-execution-example.md) za pomocą LINQ, należy wywołać, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> Aby rozpocząć każde zadanie.

```csharp
List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
```

`while`Pętla wykonuje następujące kroki dla każdego zadania w kolekcji:

1. Oczekuje na wywołanie w `WhenAny` celu zidentyfikowania pierwszego zadania w kolekcji, które zakończyło pobieranie.

    ```csharp
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
    ```

1. Usuwa to zadanie z kolekcji.

    ```csharp
    downloadTasks.Remove(firstFinishedTask);
    ```

1. Czeka `finishedTask` , który jest zwracany przez wywołanie metody `ProcessUrlAsync` . `finishedTask`Zmienna to <xref:System.Threading.Tasks.Task%601> gdzie `TResult` jest liczbą całkowitą. Zadanie zostało już ukończone, ale czeka na pobranie długości pobranej witryny sieci Web, jak pokazano w poniższym przykładzie. Jeśli zadanie jest błędne, `await` program zgłosi pierwszy wyjątek podrzędny zapisany w `AggregateException` , w przeciwieństwie do odczytu <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> właściwości, która spowodowałaby wygenerowanie `AggregateException` .

    ```csharp
    total += await finishedTask;
    ```

## <a name="add-process-method"></a>Dodaj metodę procesu

Dodaj następującą `ProcessUrlAsync` metodę poniżej `SumPageSizesAsync` metody:

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client)
{
    byte[] content = await client.GetByteArrayAsync(url);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

W przypadku dowolnego podanego adresu URL metoda użyje `client` dostarczonego wystąpienia w celu uzyskania odpowiedzi jako `byte[]` . Długość jest zwracana po zapisaniu adresu URL i długości w konsoli.

Uruchom program kilka razy, aby sprawdzić, czy pobrane długości nie zawsze pojawiają się w tej samej kolejności.

> [!CAUTION]
> Można użyć `WhenAny` w pętli, jak opisano w przykładzie, w celu rozwiązania problemów obejmujących niewielką liczbę zadań. Jednak inne podejścia są bardziej wydajne, jeśli masz dużą liczbę zadań do przetworzenia. Aby uzyskać więcej informacji i przykładów, zobacz [Przetwarzanie zadań po ich zakończeniu](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete).

## <a name="complete-example"></a>Pełny przykład

Poniższy kod jest pełnym tekstem pliku *program.cs* na przykład.

:::code language="csharp" source="snippets/multiple-tasks/Program.cs":::

## <a name="see-also"></a>Zobacz także

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Programowanie asynchroniczne z Async i Await (C#)](index.md)
