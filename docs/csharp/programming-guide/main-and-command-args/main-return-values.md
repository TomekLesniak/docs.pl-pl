---
title: Main () zwracane wartości — Przewodnik programowania w języku C#
description: Uzyskaj informacje na temat głównych () zwracanych wartości. Zobacz przykłady kodu, kod wygenerowany przez kompilator i wyświetlanie dodatkowych dostępnych zasobów.
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: 469ed872c1c8c4eb41eecd04277d4fc53fb3d112
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414646"
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="eaf8d-104">Main () — zwracane wartości (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="eaf8d-104">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="eaf8d-105">`Main`Metoda może zwracać `void` :</span><span class="sxs-lookup"><span data-stu-id="eaf8d-105">The `Main` method can return `void`:</span></span>

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

<span data-ttu-id="eaf8d-106">Może również zwrócić `int` :</span><span class="sxs-lookup"><span data-stu-id="eaf8d-106">It can also return an `int`:</span></span>

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

<span data-ttu-id="eaf8d-107">Jeśli wartość zwracana z `Main` nie jest używana, zwracający `void` umożliwia nieznacznie łatwiejszy kod.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-107">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="eaf8d-108">Jednak zwrócenie liczby całkowitej umożliwia programowi przekazywanie informacji o stanie do innych programów lub skryptów, które wywołują plik wykonywalny.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-108">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="eaf8d-109">Wartość zwracana z `Main` jest traktowana jako kod zakończenia procesu.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-109">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="eaf8d-110">Jeśli `void` jest zwracany z `Main` , kod zakończenia będzie niejawnie `0` .</span><span class="sxs-lookup"><span data-stu-id="eaf8d-110">If `void` is returned from `Main`, the exit code will be implicitly `0`.</span></span> <span data-ttu-id="eaf8d-111">Poniższy przykład pokazuje, w jaki sposób można uzyskać dostęp do zwracanej wartości `Main` .</span><span class="sxs-lookup"><span data-stu-id="eaf8d-111">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="eaf8d-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="eaf8d-112">Example</span></span>

<span data-ttu-id="eaf8d-113">W tym przykładzie zastosowano narzędzia wiersza polecenia [platformy .NET Core](../../../core/introduction.md) .</span><span class="sxs-lookup"><span data-stu-id="eaf8d-113">This example uses [.NET Core](../../../core/introduction.md) command-line tools.</span></span> <span data-ttu-id="eaf8d-114">Jeśli nie znasz narzędzi wiersza polecenia programu .NET Core, możesz dowiedzieć się więcej o nich w tym artykule dotyczącym [uruchamiania](../../../core/tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="eaf8d-114">If you are unfamiliar with .NET Core command-line tools, you can learn about them in this [get-started article](../../../core/tutorials/with-visual-studio-code.md).</span></span>

<span data-ttu-id="eaf8d-115">Zmodyfikuj `Main` metodę w *program.cs* w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="eaf8d-115">Modify the `Main` method in *program.cs* as follows:</span></span>

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

<span data-ttu-id="eaf8d-116">Gdy program jest wykonywany w systemie Windows, wszelkie wartości zwrócone przez `Main` funkcję są przechowywane w zmiennej środowiskowej.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-116">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="eaf8d-117">Tę zmienną środowiskową można pobrać przy użyciu `ERRORLEVEL` pliku wsadowego lub `$LastExitCode` z programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-117">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="eaf8d-118">Aplikację można skompilować przy użyciu polecenia [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` .</span><span class="sxs-lookup"><span data-stu-id="eaf8d-118">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="eaf8d-119">Następnie utwórz skrypt programu PowerShell, aby uruchomić aplikację i wyświetlić wynik.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-119">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="eaf8d-120">Wklej następujący kod do pliku tekstowego i Zapisz go jako `test.ps1` folder zawierający projekt.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-120">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="eaf8d-121">Uruchom skrypt programu PowerShell, wpisując `test.ps1` w wierszu polecenia programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-121">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="eaf8d-122">Ponieważ kod zwraca zero, plik wsadowy będzie zgłaszał powodzenie.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-122">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="eaf8d-123">Jeśli jednak zmienisz MainReturnValTest.cs w taki sposób, aby zwracał wartość różną od zera, a następnie ponownie skompilujesz program, kolejne wykonanie skryptu programu PowerShell zgłosi błąd.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-123">However, if you change MainReturnValTest.cs to return a non-zero value and then recompile the program, subsequent execution of the powershell script will report failure.</span></span>

```dotnetcli
dotnet run
```

```powershell
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="eaf8d-124">Przykładowe dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="eaf8d-124">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="eaf8d-125">Asynchroniczne główne wartości zwracane</span><span class="sxs-lookup"><span data-stu-id="eaf8d-125">Async Main return values</span></span>

<span data-ttu-id="eaf8d-126">Asynchroniczne główne wartości zwracane umożliwiają przenoszenie kodu standardowego niezbędnego do wywołania metod asynchronicznych w programie `Main` do kodu wygenerowanego przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-126">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="eaf8d-127">Wcześniej należy napisać tę konstrukcję, aby wywołać kod asynchroniczny i upewnić się, że program został uruchomiony do momentu ukończenia operacji asynchronicznej:</span><span class="sxs-lookup"><span data-stu-id="eaf8d-127">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

<span data-ttu-id="eaf8d-128">Teraz można je zastąpić:</span><span class="sxs-lookup"><span data-stu-id="eaf8d-128">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="eaf8d-129">Zaletą nowej składni jest to, że kompilator zawsze generuje poprawny kod.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-129">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="eaf8d-130">Kod wygenerowany przez kompilator</span><span class="sxs-lookup"><span data-stu-id="eaf8d-130">Compiler-generated code</span></span>

<span data-ttu-id="eaf8d-131">Gdy punkt wejścia aplikacji zwraca `Task` lub `Task<int>` , kompilator generuje nowy punkt wejścia, który wywołuje metodę punktu wejścia zadeklarowaną w kodzie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-131">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="eaf8d-132">Przy założeniu, że ten punkt wejścia jest wywoływany `$GeneratedMain` , kompilator generuje następujący kod dla tych punktów wejścia:</span><span class="sxs-lookup"><span data-stu-id="eaf8d-132">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="eaf8d-133">`static Task Main()` powoduje, że kompilator emituje odpowiednik `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="eaf8d-133">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="eaf8d-134">`static Task Main(string[])` powoduje, że kompilator emituje odpowiednik `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="eaf8d-134">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="eaf8d-135">`static Task<int> Main()` powoduje, że kompilator emituje odpowiednik `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="eaf8d-135">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="eaf8d-136">`static Task<int> Main(string[])` powoduje, że kompilator emituje odpowiednik `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="eaf8d-136">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="eaf8d-137">Jeśli przykłady użyto `async` modyfikatora `Main` metody, kompilator wygeneruje ten sam kod.</span><span class="sxs-lookup"><span data-stu-id="eaf8d-137">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="eaf8d-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eaf8d-138">See also</span></span>

- [<span data-ttu-id="eaf8d-139">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="eaf8d-139">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="eaf8d-140">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="eaf8d-140">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="eaf8d-141">Main () i argumenty wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="eaf8d-141">Main() and Command-Line Arguments</span></span>](index.md)
- [<span data-ttu-id="eaf8d-142">Wyświetlanie argumentów wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="eaf8d-142">How to display command line arguments</span></span>](./how-to-display-command-line-arguments.md)
