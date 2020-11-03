---
title: Instrukcje najwyższego poziomu — samouczek języka C#
description: W tym samouczku pokazano, jak za pomocą instrukcji najwyższego poziomu można eksperymentować i udowodnić koncepcje podczas eksplorowania pomysłów.
ms.date: 10/28/2020
ms.openlocfilehash: 5e5dc6cec382baa69ac8cb4625684315bb2cd5e0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282256"
---
# <a name="tutorial-explore-ideas-using-top-level-statements-to-build-code-as-you-learn"></a><span data-ttu-id="8e896-103">Samouczek: Eksplorowanie pomysłów przy użyciu instrukcji najwyższego poziomu do kompilowania kodu w trakcie nauki</span><span class="sxs-lookup"><span data-stu-id="8e896-103">Tutorial: Explore ideas using top-level statements to build code as you learn</span></span>

<span data-ttu-id="8e896-104">Z tego samouczka dowiesz się, jak wykonywać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="8e896-104">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="8e896-105">Zapoznaj się z zasadami dotyczącymi używania instrukcji najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="8e896-105">Learn the rules governing your use of top-level statements.</span></span>
> - <span data-ttu-id="8e896-106">Użyj instrukcji najwyższego poziomu do eksplorowania algorytmów.</span><span class="sxs-lookup"><span data-stu-id="8e896-106">Use top-level statements to explore algorithms.</span></span>
> - <span data-ttu-id="8e896-107">Refaktoryzacja eksploracji do składników wielokrotnego użytku.</span><span class="sxs-lookup"><span data-stu-id="8e896-107">Refactor explorations into reusable components.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8e896-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="8e896-108">Prerequisites</span></span>

<span data-ttu-id="8e896-109">Musisz skonfigurować maszynę do uruchamiania programu .NET 5, który obejmuje kompilator C# 9.</span><span class="sxs-lookup"><span data-stu-id="8e896-109">You'll need to set up your machine to run .NET 5, which includes the C# 9 compiler.</span></span> <span data-ttu-id="8e896-110">Kompilator języka C# 9 jest dostępny w programie [Visual Studio 2019 w wersji 16,9 Preview 1](https://visualstudio.microsoft.com/vs/preview/) lub [.NET 5,0 SDK](https://dot.net/get-dotnet5).</span><span class="sxs-lookup"><span data-stu-id="8e896-110">The C# 9 compiler is available starting with [Visual Studio 2019 version 16.9 preview 1](https://visualstudio.microsoft.com/vs/preview/) or [.NET 5.0 SDK](https://dot.net/get-dotnet5).</span></span>

<span data-ttu-id="8e896-111">W tym samouczku założono, że znasz języki C# i .NET, w tym Visual Studio lub interfejs wiersza polecenia platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8e896-111">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="start-exploring"></a><span data-ttu-id="8e896-112">Rozpocznij eksplorację</span><span class="sxs-lookup"><span data-stu-id="8e896-112">Start exploring</span></span>

<span data-ttu-id="8e896-113">Instrukcje najwyższego poziomu pozwalają uniknąć dodatkowych procedury wymaganych przez umieszczenie punktu wejścia programu w statycznej metodzie w klasie.</span><span class="sxs-lookup"><span data-stu-id="8e896-113">Top-level statements enable you to avoid the extra ceremony required by placing your program's entry point in a static method in a class.</span></span> <span data-ttu-id="8e896-114">Typowy punkt początkowy nowej aplikacji konsolowej wygląda podobnie do następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="8e896-114">The typical starting point for a new console application looks like the following code:</span></span>

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

<span data-ttu-id="8e896-115">Poprzedni kod jest wynikiem uruchomienia `dotnet new console` polecenia i utworzenia nowej aplikacji konsolowej.</span><span class="sxs-lookup"><span data-stu-id="8e896-115">The preceding code is the result of running the `dotnet new console` command and creating a new console application.</span></span> <span data-ttu-id="8e896-116">Te 11 wierszy zawierają tylko jeden wiersz kodu wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="8e896-116">Those 11 lines contain only one line of executable code.</span></span> <span data-ttu-id="8e896-117">Można uprościć ten program przy użyciu nowych instrukcji najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="8e896-117">You can simplify that program with the new top-level statements feature.</span></span> <span data-ttu-id="8e896-118">Dzięki temu można usunąć wszystkie wiersze, ale dwa z nich w tym programie:</span><span class="sxs-lookup"><span data-stu-id="8e896-118">That enables you to remove all but two of the lines in this program:</span></span>

```csharp
using System;

Console.WriteLine("Hello World!");
```

<span data-ttu-id="8e896-119">Ta akcja upraszcza to, co jest potrzebne do rozpoczęcia eksplorowania nowych pomysłów.</span><span class="sxs-lookup"><span data-stu-id="8e896-119">This action simplifies what's needed to begin exploring new ideas.</span></span> <span data-ttu-id="8e896-120">Można użyć instrukcji najwyższego poziomu dla scenariuszy skryptów lub do eksplorowania.</span><span class="sxs-lookup"><span data-stu-id="8e896-120">You can use top-level statements for scripting scenarios, or to explore.</span></span> <span data-ttu-id="8e896-121">Po uzyskaniu podstawowych działań możesz rozpocząć refaktoryzację kodu i utworzyć metody, klasy lub inne zestawy dla utworzonych przez siebie składników wielokrotnego użytku.</span><span class="sxs-lookup"><span data-stu-id="8e896-121">Once you've got the basics working, you can start refactoring the code and create methods, classes, or other assemblies for reusable components you've built.</span></span> <span data-ttu-id="8e896-122">Instrukcje najwyższego poziomu umożliwiają szybkie eksperymentowanie i początkujące samouczki.</span><span class="sxs-lookup"><span data-stu-id="8e896-122">Top-level statements do enable quick experimentation and beginner tutorials.</span></span> <span data-ttu-id="8e896-123">Zapewniają one również gładką ścieżkę od eksperymentu do pełnych programów.</span><span class="sxs-lookup"><span data-stu-id="8e896-123">They also provide a smooth path from experimentation to full programs.</span></span>

<span data-ttu-id="8e896-124">Instrukcje najwyższego poziomu są wykonywane w kolejności, w jakiej występują w pliku.</span><span class="sxs-lookup"><span data-stu-id="8e896-124">Top-level statements are executed in the order they appear in the file.</span></span> <span data-ttu-id="8e896-125">Instrukcji najwyższego poziomu można używać tylko w jednym pliku źródłowym w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8e896-125">Top-level statements can only be used in one source file in your application.</span></span> <span data-ttu-id="8e896-126">Kompilator generuje błąd, jeśli są używane w więcej niż jednym pliku.</span><span class="sxs-lookup"><span data-stu-id="8e896-126">The compiler generates an error if you use them in more than one file.</span></span>

## <a name="build-a-magic-net-answer-machine"></a><span data-ttu-id="8e896-127">Tworzenie komputera z odpowiedzią programu .NET Magic</span><span class="sxs-lookup"><span data-stu-id="8e896-127">Build a magic .NET answer machine</span></span>

<span data-ttu-id="8e896-128">Na potrzeby tego samouczka utworzysz aplikację konsolową, która odbierze odpowiedź "tak" lub "No" z pytaniem losowym.</span><span class="sxs-lookup"><span data-stu-id="8e896-128">For this tutorial, let's build a console application that answers a "yes" or "no" question with a random answer.</span></span> <span data-ttu-id="8e896-129">Zostanie utworzona funkcja krok po kroku.</span><span class="sxs-lookup"><span data-stu-id="8e896-129">You'll build out the functionality step by step.</span></span> <span data-ttu-id="8e896-130">Możesz skupić się na zadaniu, a nie na procedury potrzeby struktury typowego programu.</span><span class="sxs-lookup"><span data-stu-id="8e896-130">You can focus on your task rather than ceremony needed for the structure of a typical program.</span></span> <span data-ttu-id="8e896-131">Następnie, gdy będziesz zadowolony z funkcjonalności, możesz ponownie poznać aplikację jako dopasowaną.</span><span class="sxs-lookup"><span data-stu-id="8e896-131">Then, once you're happy with the functionality, you can refactor the application as you see fit.</span></span>

<span data-ttu-id="8e896-132">Dobrym punktem początkowym jest zapisanie pytania z powrotem do konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="8e896-132">A good starting point is to write the question back to the console.</span></span> <span data-ttu-id="8e896-133">Możesz rozpocząć od zapisania następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="8e896-133">You can start by writing the following code:</span></span>

```csharp
using System;

Console.WriteLine(args);
```

<span data-ttu-id="8e896-134">Nie deklaruje `args` zmiennej.</span><span class="sxs-lookup"><span data-stu-id="8e896-134">You don't declare an `args` variable.</span></span> <span data-ttu-id="8e896-135">W przypadku pojedynczego pliku źródłowego, który zawiera instrukcje najwyższego poziomu, kompilator rozpoznaje `args` do oznaczania argumentów wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="8e896-135">For the single source file that contains your top-level statements, the compiler recognizes `args` to mean the command-line arguments.</span></span> <span data-ttu-id="8e896-136">Typ argumentów to `string[]` , jak w przypadku wszystkich programów C#.</span><span class="sxs-lookup"><span data-stu-id="8e896-136">The type of args is a `string[]`, as in all C# programs.</span></span>

<span data-ttu-id="8e896-137">Możesz przetestować kod, uruchamiając następujące `dotnet run` polecenie:</span><span class="sxs-lookup"><span data-stu-id="8e896-137">You can test your code by running the following `dotnet run` command:</span></span>

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?
```

<span data-ttu-id="8e896-138">Argumenty po `--` wierszu polecenia są przekazane do programu.</span><span class="sxs-lookup"><span data-stu-id="8e896-138">The arguments after the `--` on the command line are passed to the program.</span></span> <span data-ttu-id="8e896-139">Możesz zobaczyć typ `args` zmiennej, ponieważ jest to nowości wydrukowany w konsoli programu:</span><span class="sxs-lookup"><span data-stu-id="8e896-139">You can see the type of the `args` variable, because that's what's printed to the console:</span></span>

```console
System.String[]
```

<span data-ttu-id="8e896-140">Aby napisać pytanie do konsoli programu, należy wyliczyć argumenty i oddzielić je spacją.</span><span class="sxs-lookup"><span data-stu-id="8e896-140">To write the question to the console, you'll need to enumerate the arguments and separate them with a space.</span></span> <span data-ttu-id="8e896-141">Zastąp `WriteLine` wywołanie następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="8e896-141">Replace the `WriteLine` call with the following code:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="EchoInput":::

<span data-ttu-id="8e896-142">Teraz, po uruchomieniu programu, w celu poprawnego wyświetlenia pytania jako ciągu argumentów.</span><span class="sxs-lookup"><span data-stu-id="8e896-142">Now, when you run the program, it will correctly display the question as a string of arguments.</span></span>

## <a name="respond-with-a-random-answer"></a><span data-ttu-id="8e896-143">Odpowiedź z losową odpowiedzią</span><span class="sxs-lookup"><span data-stu-id="8e896-143">Respond with a random answer</span></span>

<span data-ttu-id="8e896-144">Po echaniu pytania można dodać kod w celu wygenerowania losowej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="8e896-144">After echoing the question, you can add the code to generate the random answer.</span></span> <span data-ttu-id="8e896-145">Zacznij od dodania tablicy możliwych odpowiedzi:</span><span class="sxs-lookup"><span data-stu-id="8e896-145">Start by adding an array of possible answers:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="Answers":::

<span data-ttu-id="8e896-146">Ta tablica zawiera 12 odpowiedzi, które są pozytywne, sześć, które nie są zatwierdzane i sześć, które są ujemne.</span><span class="sxs-lookup"><span data-stu-id="8e896-146">This array has 12 answers that are affirmative, six that are non-committal, and six that are negative.</span></span> <span data-ttu-id="8e896-147">Następnie Dodaj następujący kod w celu wygenerowania i wyświetlenia losowej odpowiedzi z tablicy:</span><span class="sxs-lookup"><span data-stu-id="8e896-147">Next, add the following code to generate and display a random answer from the array:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="GenerateAnswer":::

<span data-ttu-id="8e896-148">Możesz ponownie uruchomić aplikację, aby zobaczyć wyniki.</span><span class="sxs-lookup"><span data-stu-id="8e896-148">You can run the application again to see the results.</span></span> <span data-ttu-id="8e896-149">Powinny pojawić się następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="8e896-149">You should see something like the following output:</span></span>

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?

Should I use top level statements in all my programs?
Better not tell you now.
```

<span data-ttu-id="8e896-150">Ten kod odpowiada na pytania, ale dodamy jeszcze jedną funkcję.</span><span class="sxs-lookup"><span data-stu-id="8e896-150">This code answers the questions, but let's add one more feature.</span></span> <span data-ttu-id="8e896-151">Lubisz, aby Twoja aplikacja zakwestionowała symulację odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="8e896-151">You'd like your question app to simulate thinking about the answer.</span></span> <span data-ttu-id="8e896-152">Można to zrobić, dodając bit animacji ASCII i zatrzymując podczas pracy.</span><span class="sxs-lookup"><span data-stu-id="8e896-152">You can do that by adding a bit of ASCII animation, and pausing while working.</span></span>  <span data-ttu-id="8e896-153">Dodaj następujący kod po wierszu, który echo pytanie:</span><span class="sxs-lookup"><span data-stu-id="8e896-153">Add the following code after the line that echoes the question:</span></span>

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="AnimationFirstPass":::

<span data-ttu-id="8e896-154">Należy również dodać `using` instrukcję na początku pliku źródłowego:</span><span class="sxs-lookup"><span data-stu-id="8e896-154">You'll also need to add a `using` statement to the top of the source file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="8e896-155">`using`Instrukcje muszą znajdować się przed innymi instrukcjami w pliku.</span><span class="sxs-lookup"><span data-stu-id="8e896-155">The `using` statements must be before any other statements in the file.</span></span> <span data-ttu-id="8e896-156">W przeciwnym razie jest to błąd kompilatora.</span><span class="sxs-lookup"><span data-stu-id="8e896-156">Otherwise, it's a compiler error.</span></span> <span data-ttu-id="8e896-157">Możesz ponownie uruchomić program i wyświetlić animację.</span><span class="sxs-lookup"><span data-stu-id="8e896-157">You can run the program again and see the animation.</span></span> <span data-ttu-id="8e896-158">Zapewnia to lepszy komfort pracy.</span><span class="sxs-lookup"><span data-stu-id="8e896-158">That makes a better experience.</span></span> <span data-ttu-id="8e896-159">Eksperymentuj z długością opóźnienia, aby dopasować swój smak.</span><span class="sxs-lookup"><span data-stu-id="8e896-159">Experiment with the length of the delay to match your taste.</span></span>

<span data-ttu-id="8e896-160">Poprzedni kod tworzy zestaw obracających się linii rozdzielonych spacją.</span><span class="sxs-lookup"><span data-stu-id="8e896-160">The preceding code creates a set of spinning lines separated by a space.</span></span> <span data-ttu-id="8e896-161">Dodanie `await` słowa kluczowego powoduje, że kompilator generuje punkt wejścia programu jako metodę, która ma `async` modyfikator, i zwraca <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="8e896-161">Adding the `await` keyword instructs the compiler to generate the program entry point as a method that has the `async` modifier, and returns a <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8e896-162">Ten program nie zwraca wartości, więc punkt wejścia programu zwraca `Task` .</span><span class="sxs-lookup"><span data-stu-id="8e896-162">This program does not return a value, so the program entry point returns a `Task`.</span></span> <span data-ttu-id="8e896-163">Jeśli program zwraca liczbę całkowitą, należy dodać instrukcję return do końca instrukcji najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="8e896-163">If your program returns an integer value, you would add a return statement to the end of your top-level statements.</span></span> <span data-ttu-id="8e896-164">Ta instrukcja return powinna określać wartość całkowitą do zwrócenia.</span><span class="sxs-lookup"><span data-stu-id="8e896-164">That return statement would specify the integer value to return.</span></span> <span data-ttu-id="8e896-165">Jeśli instrukcje najwyższego poziomu zawierają `await` wyrażenie, zwracany jest tekst <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="8e896-165">If your top-level statements include an `await` expression, the return type becomes <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>.</span></span>

## <a name="refactoring-for-the-future"></a><span data-ttu-id="8e896-166">Refaktoryzacja w przyszłości</span><span class="sxs-lookup"><span data-stu-id="8e896-166">Refactoring for the future</span></span>

<span data-ttu-id="8e896-167">Program powinien wyglądać podobnie do następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="8e896-167">Your program should look like the following code:</span></span>

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

<span data-ttu-id="8e896-168">Poprzedni kod jest odpowiedni.</span><span class="sxs-lookup"><span data-stu-id="8e896-168">The preceding code is reasonable.</span></span> <span data-ttu-id="8e896-169">Działa.</span><span class="sxs-lookup"><span data-stu-id="8e896-169">It works.</span></span> <span data-ttu-id="8e896-170">Nie jest to jednak wielokrotne użycie.</span><span class="sxs-lookup"><span data-stu-id="8e896-170">But it isn't reusable.</span></span> <span data-ttu-id="8e896-171">Teraz, gdy masz już działającą aplikację, czas na pobranie części do ponownego użycia.</span><span class="sxs-lookup"><span data-stu-id="8e896-171">Now that you have the application working, it's time to pull out reusable parts.</span></span>

<span data-ttu-id="8e896-172">Jeden kandydat to kod, który wyświetla oczekującą animację.</span><span class="sxs-lookup"><span data-stu-id="8e896-172">One candidate is the code that displays the waiting animation.</span></span> <span data-ttu-id="8e896-173">Ten fragment kodu może być metodą:</span><span class="sxs-lookup"><span data-stu-id="8e896-173">That snippet can become a method:</span></span>

<span data-ttu-id="8e896-174">Możesz rozpocząć od utworzenia lokalnej funkcji w pliku.</span><span class="sxs-lookup"><span data-stu-id="8e896-174">You can start by creating a local function in your file.</span></span> <span data-ttu-id="8e896-175">Zastąp bieżącą animację następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="8e896-175">Replace the current animation with the following code:</span></span>

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

<span data-ttu-id="8e896-176">Poprzedni kod tworzy funkcję lokalną wewnątrz metody Main.</span><span class="sxs-lookup"><span data-stu-id="8e896-176">The preceding code creates a local function inside your main method.</span></span> <span data-ttu-id="8e896-177">Nadal nie można tego ponownie używać.</span><span class="sxs-lookup"><span data-stu-id="8e896-177">That's still not reusable.</span></span> <span data-ttu-id="8e896-178">Dlatego Wyodrębnij ten kod do klasy.</span><span class="sxs-lookup"><span data-stu-id="8e896-178">So, extract that code into a class.</span></span> <span data-ttu-id="8e896-179">Utwórz nowy plik o nazwie *Utilities.cs* i Dodaj następujący kod:</span><span class="sxs-lookup"><span data-stu-id="8e896-179">Create a new file named *utilities.cs* and add the following code:</span></span>

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="SnippetUtilities":::

<span data-ttu-id="8e896-180">Instrukcje najwyższego poziomu mogą znajdować się tylko w jednym pliku, a ten plik nie może zawierać przestrzeni nazw ani typów.</span><span class="sxs-lookup"><span data-stu-id="8e896-180">Top-level statements can only be in one file, and that file cannot contain namespaces or types.</span></span>

<span data-ttu-id="8e896-181">Na koniec można wyczyścić kod animacji, aby usunąć pewne duplikacje:</span><span class="sxs-lookup"><span data-stu-id="8e896-181">Finally, you can clean the animation code to remove some duplication:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Utilities.cs" ID="Animation":::

<span data-ttu-id="8e896-182">Teraz masz kompletną aplikację i można było ponownie obsłużyć składniki wielokrotnego użytku do późniejszego użycia.</span><span class="sxs-lookup"><span data-stu-id="8e896-182">Now you have a complete application, and you've refactored the reusable parts for later use.</span></span>

## <a name="summary"></a><span data-ttu-id="8e896-183">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="8e896-183">Summary</span></span>

<span data-ttu-id="8e896-184">Instrukcje najwyższego poziomu ułatwiają tworzenie prostych programów służących do eksplorowania nowych algorytmów.</span><span class="sxs-lookup"><span data-stu-id="8e896-184">Top-level statements make it easier to create simple programs for use to explore new algorithms.</span></span> <span data-ttu-id="8e896-185">Aby eksperymentować z algorytmami, spróbuj wykonać różne fragmenty kodu.</span><span class="sxs-lookup"><span data-stu-id="8e896-185">You can experiment with algorithms by trying different snippets of code.</span></span> <span data-ttu-id="8e896-186">Po uzyskaniu informacji o działaniu można ponownie określić kod, który będzie bardziej konserwowany.</span><span class="sxs-lookup"><span data-stu-id="8e896-186">Once you've learned what works, you can refactor the code to be more maintainable.</span></span>

<span data-ttu-id="8e896-187">Instrukcje najwyższego poziomu upraszczają programy, które są oparte na aplikacjach konsolowych.</span><span class="sxs-lookup"><span data-stu-id="8e896-187">Top-level statements simplify programs that are based on console applications.</span></span> <span data-ttu-id="8e896-188">Obejmują one funkcje platformy Azure, akcje GitHub i inne małe narzędzia.</span><span class="sxs-lookup"><span data-stu-id="8e896-188">These include Azure functions, GitHub actions, and other small utilities.</span></span>
