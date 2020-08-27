---
title: Informacje o F# Interactive (dotnet)
description: 'Dowiedz się, jak F# Interactive (dotnet FSI) służy do interaktywnego uruchamiania kodu F # za pomocą konsoli programu lub wykonywania skryptów języka F #.'
ms.date: 08/20/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: 760b096c8a3ee0d495b893ab66fa6f9007cdbbf9
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867623"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="3db46-103">Programowanie interaktywne przy użyciu języka F\#</span><span class="sxs-lookup"><span data-stu-id="3db46-103">Interactive programming with F\#</span></span>

<span data-ttu-id="3db46-104">F# Interactive (dotnet FSI) służy do interaktywnego uruchamiania kodu F # za pomocą konsoli programu lub do wykonywania skryptów języka F #.</span><span class="sxs-lookup"><span data-stu-id="3db46-104">F# Interactive (dotnet fsi) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="3db46-105">Inaczej mówiąc, program F # Interactive wykonuje REPL (odczyt, oszacowanie i drukowanie) dla języka F #.</span><span class="sxs-lookup"><span data-stu-id="3db46-105">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="3db46-106">Aby uruchomić F# Interactive z konsoli programu, uruchom polecenie `dotnet fsi` .</span><span class="sxs-lookup"><span data-stu-id="3db46-106">To run F# Interactive from the console, run `dotnet fsi`.</span></span> <span data-ttu-id="3db46-107">Znajdziesz się `dotnet fsi` w dowolnym zestawie SDK platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="3db46-107">You will find `dotnet fsi` in any .NET SDK.</span></span>

<span data-ttu-id="3db46-108">Aby uzyskać informacje o dostępnych opcjach wiersza polecenia, zobacz [opcje F# Interactive](../../language-reference/fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="3db46-108">For information about command line options available, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

<span data-ttu-id="3db46-109">Aby uruchomić F# Interactive za pomocą programu Visual Studio, można kliknąć odpowiedni przycisk paska narzędzi z etykietą **F# Interactive**lub użyć klawiszy **Ctrl + Alt + F**.</span><span class="sxs-lookup"><span data-stu-id="3db46-109">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive**, or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="3db46-110">Spowoduje to otwarcie okna interaktywnego, okna narzędzia z uruchomioną sesją F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="3db46-110">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="3db46-111">Możesz również wybrać kod, który ma być uruchamiany w oknie interaktywnym i nacisnąć kombinację klawiszy **ALT + ENTER**.</span><span class="sxs-lookup"><span data-stu-id="3db46-111">You can also select some code that you want to run in the interactive window and hit the key combination **Alt+Enter**.</span></span> <span data-ttu-id="3db46-112">F# Interactive uruchamia się w oknie narzędzia z etykietą **F# Interactive**.</span><span class="sxs-lookup"><span data-stu-id="3db46-112">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="3db46-113">W przypadku korzystania z tej kombinacji klawiszy upewnij się, że okno edytora ma fokus.</span><span class="sxs-lookup"><span data-stu-id="3db46-113">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="3db46-114">Niezależnie od tego, czy używasz konsoli programu, czy programu Visual Studio, zostanie wyświetlony wiersz polecenia, a interpreter czeka na dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="3db46-114">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="3db46-115">Możesz wprowadzić kod tak samo jak w pliku kodu.</span><span class="sxs-lookup"><span data-stu-id="3db46-115">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="3db46-116">Aby skompilować i wykonać kod, wprowadź dwa średnika (**;;**), aby zakończyć wiersz lub kilka wierszy danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="3db46-116">To compile and execute the code, enter two semicolons (**;;**) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="3db46-117">F# Interactive próbuje skompilować kod i, jeśli to się powiedzie, wykonuje kod i drukuje sygnaturę typów i wartości, które zostały skompilowane.</span><span class="sxs-lookup"><span data-stu-id="3db46-117">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="3db46-118">Jeśli wystąpią błędy, interpreter wyświetla komunikaty o błędach.</span><span class="sxs-lookup"><span data-stu-id="3db46-118">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="3db46-119">Kod wprowadzony w tej samej sesji ma dostęp do dowolnych wcześniej wprowadzonych konstrukcji, dzięki czemu można kompilować programy.</span><span class="sxs-lookup"><span data-stu-id="3db46-119">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="3db46-120">Obszerny bufor w oknie narzędzi umożliwia skopiowanie kodu do pliku w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="3db46-120">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="3db46-121">W przypadku uruchamiania w programie Visual Studio F# Interactive uruchamiane niezależnie od projektu, więc na przykład nie można używać konstrukcji zdefiniowanych w projekcie w F# Interactive, chyba że skopiujesz kod funkcji do okna interaktywnego.</span><span class="sxs-lookup"><span data-stu-id="3db46-121">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="3db46-122">Jeśli masz otwarty projekt, który odwołuje się do niektórych bibliotek, możesz odwoływać się do nich w F# Interactive przez **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="3db46-122">If you have a project open that references some libraries, you can reference these in F# Interactive through **Solution Explorer**.</span></span> <span data-ttu-id="3db46-123">Aby odwołać się do biblioteki w F# Interactive, rozwiń węzeł **odwołania** , otwórz menu skrótów dla biblioteki i wybierz polecenie **Wyślij do F# Interactive**.</span><span class="sxs-lookup"><span data-stu-id="3db46-123">To reference a library in F# Interactive, expand the **References** node, open the shortcut menu for the library, and choose **Send to F# Interactive**.</span></span>

<span data-ttu-id="3db46-124">Można kontrolować F# Interactive argumenty wiersza polecenia (Opcje), dostosowując ustawienia.</span><span class="sxs-lookup"><span data-stu-id="3db46-124">You can control the F# Interactive command line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="3db46-125">W menu **Narzędzia** wybierz pozycję **Opcje...**, a następnie rozwiń węzeł **Narzędzia języka F #**.</span><span class="sxs-lookup"><span data-stu-id="3db46-125">On the **Tools** menu, select **Options...**, and then expand **F# Tools**.</span></span> <span data-ttu-id="3db46-126">Te dwie ustawienia, które można zmienić, to opcje F# Interactive i ustawienie **F# Interactive 64-bitowe** , które jest istotne tylko w przypadku uruchamiania F# Interactive na komputerze 64-bitowym.</span><span class="sxs-lookup"><span data-stu-id="3db46-126">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="3db46-127">To ustawienie określa, czy chcesz uruchomić dedykowaną 64-bitową wersję fsi.exe lub fsianycpu.exe, która korzysta z architektury komputera, aby określić, czy uruchomić program jako proces 32-bitowy czy 64-bitowy.</span><span class="sxs-lookup"><span data-stu-id="3db46-127">This setting determines whether you want to run the dedicated 64-bit version of fsi.exe or fsianycpu.exe, which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>

## <a name="scripting-with-f"></a><span data-ttu-id="3db46-128">Wykonywanie skryptów przy użyciu języka F\#</span><span class="sxs-lookup"><span data-stu-id="3db46-128">Scripting with F\#</span></span>

<span data-ttu-id="3db46-129">Skrypty używają rozszerzenia pliku **. FSX** lub **. FSSCRIPT**.</span><span class="sxs-lookup"><span data-stu-id="3db46-129">Scripts use the file extension **.fsx** or **.fsscript**.</span></span> <span data-ttu-id="3db46-130">Zamiast kompilowania kodu źródłowego, a następnie uruchamiania skompilowanego zestawu, można po prostu uruchomić polecenie **dotnet FSI** i określić nazwę pliku skryptu kodu źródłowego języka f #, a program F # Interactive odczytuje kod i wykonuje go w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="3db46-130">Instead of compiling source code and then later running the compiled assembly, you can just run **dotnet fsi** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span>

## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a><span data-ttu-id="3db46-131">Różnice między środowiskami interaktywnymi, skryptowymi i skompilowanymi</span><span class="sxs-lookup"><span data-stu-id="3db46-131">Differences between the interactive, scripting, and compiled environments</span></span>

<span data-ttu-id="3db46-132">Podczas kompilowania kodu w F# Interactive, niezależnie od tego, czy uruchamiasz **interaktywnie** , czy uruchamiasz skrypt, jest zdefiniowany symbol Interactive.</span><span class="sxs-lookup"><span data-stu-id="3db46-132">When you are compiling code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="3db46-133">Podczas kompilowania kodu w kompilatorze jest zdefiniowany symbol **skompilowany** .</span><span class="sxs-lookup"><span data-stu-id="3db46-133">When you are compiling code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="3db46-134">W tym przypadku, jeśli kod musi być inny w skompilowanych i interaktywnych trybach, można użyć dyrektyw preprocesora dla kompilacji warunkowej, aby określić, która z nich ma być używana.</span><span class="sxs-lookup"><span data-stu-id="3db46-134">Thus, if code needs to be different in compiled and interactive modes, you can use preprocessor directives for conditional compilation to determine which to use.</span></span>

<span data-ttu-id="3db46-135">Niektóre dyrektywy są dostępne podczas wykonywania skryptów w F# Interactive, które nie są dostępne podczas wykonywania kompilatora.</span><span class="sxs-lookup"><span data-stu-id="3db46-135">Some directives are available when you are executing scripts in F# Interactive that are not available when you are executing the compiler.</span></span> <span data-ttu-id="3db46-136">Poniższa tabela zawiera podsumowanie dyrektyw, które są dostępne podczas korzystania z F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="3db46-136">The following table summarizes directives that are available when you are using F# Interactive.</span></span>

|<span data-ttu-id="3db46-137">Dyrektywę</span><span class="sxs-lookup"><span data-stu-id="3db46-137">Directive</span></span>|<span data-ttu-id="3db46-138">Opis</span><span class="sxs-lookup"><span data-stu-id="3db46-138">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="3db46-139">**#help**</span><span class="sxs-lookup"><span data-stu-id="3db46-139">**#help**</span></span>|<span data-ttu-id="3db46-140">Wyświetla informacje dotyczące dostępnych dyrektyw.</span><span class="sxs-lookup"><span data-stu-id="3db46-140">Displays information about available directives.</span></span>|
|<span data-ttu-id="3db46-141">**#I**</span><span class="sxs-lookup"><span data-stu-id="3db46-141">**#I**</span></span>|<span data-ttu-id="3db46-142">Określa ścieżkę wyszukiwania zestawu w cudzysłowie.</span><span class="sxs-lookup"><span data-stu-id="3db46-142">Specifies an assembly search path in quotation marks.</span></span>|
|<span data-ttu-id="3db46-143">**#load**</span><span class="sxs-lookup"><span data-stu-id="3db46-143">**#load**</span></span>|<span data-ttu-id="3db46-144">Odczytuje plik źródłowy, kompiluje go i uruchamia.</span><span class="sxs-lookup"><span data-stu-id="3db46-144">Reads a source file, compiles it, and runs it.</span></span>|
|<span data-ttu-id="3db46-145">**#quit**</span><span class="sxs-lookup"><span data-stu-id="3db46-145">**#quit**</span></span>|<span data-ttu-id="3db46-146">Kończy sesję F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="3db46-146">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="3db46-147">**#r**</span><span class="sxs-lookup"><span data-stu-id="3db46-147">**#r**</span></span>|<span data-ttu-id="3db46-148">Odwołuje się do zestawu.</span><span class="sxs-lookup"><span data-stu-id="3db46-148">References an assembly.</span></span>|
|<span data-ttu-id="3db46-149">**#time ["on" &#124; "off"]**</span><span class="sxs-lookup"><span data-stu-id="3db46-149">**#time ["on"&#124;"off"]**</span></span>|<span data-ttu-id="3db46-150">Niezależnie od tego **#time** włącza, czy mają być wyświetlane informacje o wydajności.</span><span class="sxs-lookup"><span data-stu-id="3db46-150">By itself, **#time** toggles whether to display performance information.</span></span> <span data-ttu-id="3db46-151">Gdy jest włączona, F# Interactive miary czasu rzeczywistego, czasu procesora oraz informacje o wyrzucaniu elementów bezużytecznych dla każdej sekcji kodu, który jest interpretowany i wykonywany.</span><span class="sxs-lookup"><span data-stu-id="3db46-151">When it is enabled, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="3db46-152">Gdy określisz pliki lub ścieżki w F# Interactive, oczekiwano literału ciągu.</span><span class="sxs-lookup"><span data-stu-id="3db46-152">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="3db46-153">W związku z tym pliki i ścieżki muszą być ujęte w znaki cudzysłowu, a normalne znaki ucieczki mają zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="3db46-153">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="3db46-154">Ponadto można użyć znaku @, aby spowodować, że F# Interactive interpretuje ciąg, który zawiera ścieżkę jako ciąg Verbatim.</span><span class="sxs-lookup"><span data-stu-id="3db46-154">Also, you can use the @ character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="3db46-155">Powoduje to, że F# Interactive ignoruje wszystkie znaki ucieczki.</span><span class="sxs-lookup"><span data-stu-id="3db46-155">This causes F# Interactive to ignore any escape characters.</span></span>

<span data-ttu-id="3db46-156">Jedną z różnic między skompilowanym i interaktywnym trybem jest sposób dostępu do argumentów wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="3db46-156">One of the differences between compiled and interactive mode is the way you access command line arguments.</span></span> <span data-ttu-id="3db46-157">W trybie skompilowanym Użyj **System. Environment. GetCommandLineArgs**.</span><span class="sxs-lookup"><span data-stu-id="3db46-157">In compiled mode, use **System.Environment.GetCommandLineArgs**.</span></span> <span data-ttu-id="3db46-158">W skryptach Użyj **FSI. CommandLineArgs —**.</span><span class="sxs-lookup"><span data-stu-id="3db46-158">In scripts, use **fsi.CommandLineArgs**.</span></span>

<span data-ttu-id="3db46-159">Poniższy kod ilustruje sposób tworzenia funkcji, która odczytuje argumenty wiersza polecenia w skrypcie, a także pokazuje, jak odwoływać się do innego zestawu ze skryptu.</span><span class="sxs-lookup"><span data-stu-id="3db46-159">The following code illustrates how to create a function that reads the command line arguments in a script and also demonstrates how to reference another assembly from a script.</span></span> <span data-ttu-id="3db46-160">Pierwszy plik kodu, **. FS**, jest kodem, do którego odwołuje się zestaw.</span><span class="sxs-lookup"><span data-stu-id="3db46-160">The first code file, **MyAssembly.fs**, is the code for the assembly being referenced.</span></span> <span data-ttu-id="3db46-161">Skompiluj ten plik przy użyciu wiersza polecenia: **Urząd nadzoru systemu.** , a następnie wykonaj drugi plik jako skrypt z wierszem polecenia: **FSI--exec plik1. FSX** test</span><span class="sxs-lookup"><span data-stu-id="3db46-161">Compile this file with the command line: **fsc -a MyAssembly.fs** and then execute the second file as a script with the command line: **fsi --exec file1.fsx** test</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

```fsharp
// file1.fsx
#r "MyAssembly.dll"

printfn "Command line arguments: "

for arg in fsi.CommandLineArgs do
    printfn "%s" arg

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="3db46-162">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="3db46-162">The output is as follows:</span></span>

```console
Command line arguments:
file1.fsx
test
90
```

## <a name="package-management-in-f-interactive"></a><span data-ttu-id="3db46-163">Zarządzanie pakietami w F# Interactive</span><span class="sxs-lookup"><span data-stu-id="3db46-163">Package Management in F# Interactive</span></span>

[!NOTE] <span data-ttu-id="3db46-164">Zarządzanie pakietami jest dostępne jako funkcja w wersji zapoznawczej w wersjach `dotnet fsi` dostarczonych w `3.1.300` i nowszych wersjach zestawu .NET SDK, a także wszystkich `5.*` wersjach zestawu .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="3db46-164">Package management is available as a preview feature in versions of `dotnet fsi` shipped in the `3.1.300` and greater versions of the .NET SDK, as well as all `5.*` versions of the .NET SDK.</span></span> <span data-ttu-id="3db46-165">Aby włączyć ją w tej wersji zapoznawczej, uruchom polecenie `dotnet fsi` z `--langversion:preview` argumentem.</span><span class="sxs-lookup"><span data-stu-id="3db46-165">To enable it in this preview release, run `dotnet fsi` with the `--langversion:preview` argument.</span></span>

<span data-ttu-id="3db46-166">`#r`Składnia do odwoływania się do biblioteki DLL w F# Interactive może być również używana do odwoływania się do pakietu NuGet za pomocą następującej składni:</span><span class="sxs-lookup"><span data-stu-id="3db46-166">The `#r` syntax for referencing a DLL in F# Interactive can also be used to reference a nuget package via the following syntax:</span></span>

```fsharp
#r "nuget: <package name>
```

<span data-ttu-id="3db46-167">Na przykład, aby odwołać się do `FSharp.Data` pakietu, należy użyć następującego `#r` odwołania:</span><span class="sxs-lookup"><span data-stu-id="3db46-167">For example, to reference the `FSharp.Data` package, use the following `#r` reference:</span></span>

```fsharp
#r "nuget: FSharp.Data"
```

<span data-ttu-id="3db46-168">Po wykonaniu tego wiersza Najnowsza wersja `FSharp.Data` pakietu zostanie pobrana do pamięci podręcznej NuGet i przywoływana w bieżącej sesji F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="3db46-168">After executing this line, the latest version of the `FSharp.Data` package will be downloaded to your nuget cache and referenced in the current F# Interactive session.</span></span>

<span data-ttu-id="3db46-169">Oprócz nazwy pakietu do określonych wersji pakietu można odwoływać się za pomocą krótkiej składni:</span><span class="sxs-lookup"><span data-stu-id="3db46-169">In addition to the package name, specific versions of a package can be referenced via a short syntax:</span></span>

```fsharp
#r "nuget: FSharp.Data, 3.3.2"
```

<span data-ttu-id="3db46-170">lub bardziej jawny sposób:</span><span class="sxs-lookup"><span data-stu-id="3db46-170">or in a more explicit fashion:</span></span>

```fsharp
#r "nuget: FSharp.Data, Version=3.3.2"
```

## <a name="related-articles"></a><span data-ttu-id="3db46-171">Pokrewne artykuły:</span><span class="sxs-lookup"><span data-stu-id="3db46-171">Related articles</span></span>

|<span data-ttu-id="3db46-172">Tytuł</span><span class="sxs-lookup"><span data-stu-id="3db46-172">Title</span></span>|<span data-ttu-id="3db46-173">Opis</span><span class="sxs-lookup"><span data-stu-id="3db46-173">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="3db46-174">Opcje interakcyjne F#</span><span class="sxs-lookup"><span data-stu-id="3db46-174">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="3db46-175">Opisuje składnię i opcje wiersza polecenia dla F# Interactive, fsi.exe.</span><span class="sxs-lookup"><span data-stu-id="3db46-175">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
|[<span data-ttu-id="3db46-176">Dokumentacja biblioteki F# Interactive</span><span class="sxs-lookup"><span data-stu-id="3db46-176">F# Interactive Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-interactive-library-reference)|<span data-ttu-id="3db46-177">Opisuje funkcje biblioteki dostępne podczas wykonywania kodu w języku F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="3db46-177">Describes library functionality available when executing code in F# interactive.</span></span>|
