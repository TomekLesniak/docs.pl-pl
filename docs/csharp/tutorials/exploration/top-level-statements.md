---
title: Instrukcje najwyższego poziomu — samouczek języka C#
description: W tym samouczku pokazano, jak za pomocą instrukcji najwyższego poziomu można eksperymentować i udowodnić koncepcje podczas eksplorowania pomysłów.
ms.date: 10/28/2020
ms.openlocfilehash: 210fbd83bf4677061cab303089d0b27f1a4a7d01
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189401"
---
# <a name="tutorial-explore-ideas-using-top-level-statements-to-build-code-as-you-learn"></a>Samouczek: Eksplorowanie pomysłów przy użyciu instrukcji najwyższego poziomu do kompilowania kodu w trakcie nauki

Z tego samouczka dowiesz się, jak wykonywać następujące czynności:

> [!div class="checklist"]
>
> - Zapoznaj się z zasadami dotyczącymi używania instrukcji najwyższego poziomu.
> - Użyj instrukcji najwyższego poziomu do eksplorowania algorytmów.
> - Refaktoryzacja eksploracji do składników wielokrotnego użytku.

## <a name="prerequisites"></a>Wymagania wstępne

Musisz skonfigurować maszynę do uruchamiania programu .NET 5, który obejmuje kompilator C# 9. Kompilator języka C# 9 jest dostępny w programie [Visual Studio 2019 w wersji 16,9 Preview 1](https://visualstudio.microsoft.com/vs/preview/) lub [.NET 5,0 SDK](https://dot.net/get-dotnet5).

W tym samouczku założono, że znasz języki C# i .NET, w tym Visual Studio lub interfejs wiersza polecenia platformy .NET Core.

## <a name="start-exploring"></a>Rozpocznij eksplorację

Instrukcje najwyższego poziomu pozwalają uniknąć dodatkowych procedury wymaganych przez umieszczenie punktu wejścia programu w statycznej metodzie w klasie. Typowy punkt początkowy nowej aplikacji konsolowej wygląda podobnie do następującego kodu:

```csharp
using System;

namespace Application
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Poprzedni kod jest wynikiem uruchomienia `dotnet new console` polecenia i utworzenia nowej aplikacji konsolowej. Te 11 wierszy zawierają tylko jeden wiersz kodu wykonywalnego. Można uprościć ten program przy użyciu nowych instrukcji najwyższego poziomu. Dzięki temu można usunąć wszystkie wiersze, ale dwa z nich w tym programie:

```csharp
using System;

Console.WriteLine("Hello World!");
```

Ta akcja upraszcza to, co jest potrzebne do rozpoczęcia eksplorowania nowych pomysłów. Można użyć instrukcji najwyższego poziomu dla scenariuszy skryptów lub do eksplorowania. Po uzyskaniu podstawowych działań możesz rozpocząć refaktoryzację kodu i utworzyć metody, klasy lub inne zestawy dla utworzonych przez siebie składników wielokrotnego użytku. Instrukcje najwyższego poziomu umożliwiają szybkie eksperymentowanie i początkujące samouczki. Zapewniają one również gładką ścieżkę od eksperymentu do pełnych programów.

Instrukcje najwyższego poziomu są wykonywane w kolejności, w jakiej występują w pliku. Instrukcji najwyższego poziomu można używać tylko w jednym pliku źródłowym w aplikacji. Kompilator generuje błąd, jeśli są używane w więcej niż jednym pliku.

## <a name="build-a-magic-net-answer-machine"></a>Tworzenie komputera z odpowiedzią programu .NET Magic

Na potrzeby tego samouczka utworzysz aplikację konsolową, która odbierze odpowiedź "tak" lub "No" z pytaniem losowym. Zostanie utworzona funkcja krok po kroku. Możesz skupić się na zadaniu, a nie na procedury potrzeby struktury typowego programu. Następnie, gdy będziesz zadowolony z funkcjonalności, możesz ponownie poznać aplikację jako dopasowaną.

Dobrym punktem początkowym jest zapisanie pytania z powrotem do konsoli programu. Możesz rozpocząć od zapisania następującego kodu:

```csharp
using System;

Console.WriteLine(args);
```

Nie deklaruje `args` zmiennej. W przypadku pojedynczego pliku źródłowego, który zawiera instrukcje najwyższego poziomu, kompilator rozpoznaje `args` do oznaczania argumentów wiersza polecenia. Typ argumentów to `string[]` , jak w przypadku wszystkich programów C#.

Możesz przetestować kod, uruchamiając następujące `dotnet run` polecenie:

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?
```

Argumenty po `--` wierszu polecenia są przekazane do programu. Możesz zobaczyć typ `args` zmiennej, ponieważ jest to nowości wydrukowany w konsoli programu:

```console
System.String[]
```

Aby napisać pytanie do konsoli programu, należy wyliczyć argumenty i oddzielić je spacją. Zastąp `WriteLine` wywołanie następującym kodem:

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="EchoInput":::

Teraz, po uruchomieniu programu, w celu poprawnego wyświetlenia pytania jako ciągu argumentów.

## <a name="respond-with-a-random-answer"></a>Odpowiedź z losową odpowiedzią

Po echaniu pytania można dodać kod w celu wygenerowania losowej odpowiedzi. Zacznij od dodania tablicy możliwych odpowiedzi:

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="Answers":::

Ta tablica zawiera 12 odpowiedzi, które są pozytywne, sześć, które nie są zatwierdzane i sześć, które są ujemne. Następnie Dodaj następujący kod w celu wygenerowania i wyświetlenia losowej odpowiedzi z tablicy:

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="GenerateAnswer":::

Możesz ponownie uruchomić aplikację, aby zobaczyć wyniki. Powinny pojawić się następujące dane wyjściowe:

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?

Should I use top level statements in all my programs?
Better not tell you now.
```

Ten kod odpowiada na pytania, ale dodamy jeszcze jedną funkcję. Lubisz, aby Twoja aplikacja zakwestionowała symulację odpowiedzi. Można to zrobić, dodając bit animacji ASCII i zatrzymując podczas pracy.  Dodaj następujący kod po wierszu, który echo pytanie:

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="AnimationFirstPass":::

Należy również dodać `using` instrukcję na początku pliku źródłowego:

```csharp
using System.Threading.Tasks;
```

`using`Instrukcje muszą znajdować się przed innymi instrukcjami w pliku. W przeciwnym razie jest to błąd kompilatora. Możesz ponownie uruchomić program i wyświetlić animację. Zapewnia to lepszy komfort pracy. Eksperymentuj z długością opóźnienia, aby dopasować swój smak.

Poprzedni kod tworzy zestaw obracających się linii rozdzielonych spacją. Dodanie `await` słowa kluczowego powoduje, że kompilator generuje punkt wejścia programu jako metodę, która ma `async` modyfikator, i zwraca <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> . Ten program nie zwraca wartości, więc punkt wejścia programu zwraca `Task` . Jeśli program zwraca liczbę całkowitą, należy dodać instrukcję return do końca instrukcji najwyższego poziomu. Ta instrukcja return powinna określać wartość całkowitą do zwrócenia. Jeśli instrukcje najwyższego poziomu zawierają `await` wyrażenie, zwracany jest tekst <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> .

## <a name="refactoring-for-the-future"></a>Refaktoryzacja w przyszłości

Program powinien wyglądać podobnie do następującego kodu:

```csharp
using System;
using System.Threading.Tasks;

Console.WriteLine();
foreach(var s in args)
{
    Console.Write(s);
    Console.Write(' ');
}
Console.WriteLine();

for (int i = 0; i < 20; i++)
{
    Console.Write("| -");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("/ \\");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("- |");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("\\ /");
    await Task.Delay(50);
    Console.Write("\b\b\b");
}
Console.WriteLine();

string[] answers =
{
    "It is certain.",       "Reply hazy, try again.",     "Don’t count on it.",
    "It is decidedly so.",  "Ask again later.",           "My reply is no.",
    "Without a doubt.",     "Better not tell you now.",   "My sources say no.",
    "Yes – definitely.",    "Cannot predict now.",        "Outlook not so good.",
    "You may rely on it.",  "Concentrate and ask again.", "Very doubtful.",
    "As I see it, yes.",
    "Most likely.",
    "Outlook good.",
    "Yes.",
    "Signs point to yes.",
};

var index = new Random().Next(answers.Length - 1);
Console.WriteLine(answers[index]);
```

Poprzedni kod jest odpowiedni. Działa. Nie jest to jednak wielokrotne użycie. Teraz, gdy masz już działającą aplikację, czas na pobranie części do ponownego użycia.

Jeden kandydat to kod, który wyświetla oczekującą animację. Ten fragment kodu może być metodą:

Możesz rozpocząć od utworzenia lokalnej funkcji w pliku. Zastąp bieżącą animację następującym kodem:

```csharp
await ShowConsoleAnimation();

static async Task ShowConsoleAnimation()
{
    for (int i = 0; i < 20; i++)
    {
        Console.Write("| -");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("/ \\");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("- |");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("\\ /");
        await Task.Delay(50);
        Console.Write("\b\b\b");
    }
    Console.WriteLine();
}
```

Poprzedni kod tworzy funkcję lokalną wewnątrz metody Main. Nadal nie można tego ponownie używać. Dlatego Wyodrębnij ten kod do klasy. Utwórz nowy plik o nazwie *Utilities.cs* i Dodaj następujący kod:

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="SnippetUtilities":::

Instrukcje najwyższego poziomu mogą znajdować się tylko w jednym pliku, a ten plik nie może zawierać przestrzeni nazw ani typów.

Na koniec można wyczyścić kod animacji, aby usunąć pewne duplikacje:

:::code language="csharp" source="snippets/top-level-statements/Utiliities.cs" ID="Animation":::

Teraz masz kompletną aplikację i można było ponownie obsłużyć składniki wielokrotnego użytku do późniejszego użycia.

## <a name="summary"></a>Podsumowanie

Instrukcje najwyższego poziomu ułatwiają tworzenie prostych programów służących do eksplorowania nowych algorytmów. Aby eksperymentować z algorytmami, spróbuj wykonać różne fragmenty kodu. Po uzyskaniu informacji o działaniu można ponownie określić kod, który będzie bardziej konserwowany.

Instrukcje najwyższego poziomu upraszczają programy, które są oparte na aplikacjach konsolowych. Obejmują one funkcje platformy Azure, akcje GitHub i inne małe narzędzia.
