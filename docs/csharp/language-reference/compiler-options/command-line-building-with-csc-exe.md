---
description: Kompilacja w wierszu polecenia z csc.exe
title: Kompilacja w wierszu polecenia z csc.exe
ms.date: 04/19/2017
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
ms.openlocfilehash: 9ffd164602862fce7f5e4f0982d3eda7cb403e60
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125933"
---
# <a name="command-line-build-with-cscexe"></a><span data-ttu-id="d2757-103">Kompilacja w wierszu polecenia z csc.exe</span><span class="sxs-lookup"><span data-stu-id="d2757-103">Command-line build with csc.exe</span></span>

<span data-ttu-id="d2757-104">Kompilator języka C# można wywołać, wpisując nazwę pliku wykonywalnego (*csc.exe*) w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="d2757-104">You can invoke the C# compiler by typing the name of its executable file (*csc.exe*) at a command prompt.</span></span>

<span data-ttu-id="d2757-105">W przypadku korzystania z okna **wiersz polecenia dla deweloperów dla programu Visual Studio** wszystkie wymagane zmienne środowiskowe są ustawiane dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="d2757-105">If you use the **Developer Command Prompt for Visual Studio** window, all the necessary environment variables are set for you.</span></span> <span data-ttu-id="d2757-106">Aby uzyskać informacje na temat sposobu uzyskiwania dostępu do tego narzędzia, zobacz temat [wiersz polecenia dla deweloperów for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md) .</span><span class="sxs-lookup"><span data-stu-id="d2757-106">For information on how to access this tool, see the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md) topic.</span></span>

<span data-ttu-id="d2757-107">Jeśli używasz standardowego okna wiersza polecenia, musisz dostosować ścieżkę przed wywołaniem *csc.exe* z dowolnego podkatalogu na komputerze.</span><span class="sxs-lookup"><span data-stu-id="d2757-107">If you use a standard Command Prompt window, you must adjust your path before you can invoke *csc.exe* from any subdirectory on your computer.</span></span> <span data-ttu-id="d2757-108">Należy również uruchomić *VsDevCmd.bat* , aby ustawić odpowiednie zmienne środowiskowe do obsługi kompilacji w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="d2757-108">You also must run *VsDevCmd.bat* to set the appropriate environment variables to support command-line builds.</span></span> <span data-ttu-id="d2757-109">Aby uzyskać więcej informacji na temat *VsDevCmd.bat*, w tym instrukcje dotyczące sposobu znajdowania i uruchamiania, zobacz [jak ustawić zmienne środowiskowe dla wiersza polecenia programu Visual Studio](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="d2757-109">For more information about *VsDevCmd.bat*, including instructions for how to find and run it, see [How to set environment variables for the Visual Studio Command Line](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>

<span data-ttu-id="d2757-110">Jeśli pracujesz na komputerze, na którym jest tylko zestaw Windows Software Development Kit (SDK), możesz użyć kompilatora C# w **wierszu polecenia zestawu SDK**, który można otworzyć z poziomu opcji menu **Microsoft .NET Framework SDK** .</span><span class="sxs-lookup"><span data-stu-id="d2757-110">If you're working on a computer that has only the Windows Software Development Kit (SDK), you can use the C# compiler at the **SDK Command Prompt**, which you open from the **Microsoft .NET Framework SDK** menu option.</span></span>

<span data-ttu-id="d2757-111">Można również użyć programu MSBuild do programistycznego kompilowania programów w języku C#.</span><span class="sxs-lookup"><span data-stu-id="d2757-111">You can also use MSBuild to build C# programs programmatically.</span></span> <span data-ttu-id="d2757-112">Aby uzyskać więcej informacji, zobacz [MSBuild](/visualstudio/msbuild/msbuild).</span><span class="sxs-lookup"><span data-stu-id="d2757-112">For more information, see [MSBuild](/visualstudio/msbuild/msbuild).</span></span>

<span data-ttu-id="d2757-113">Plik wykonywalny *csc.exe* zwykle znajduje się w folderze Microsoft. NET\Framework \\ *\<Version>* w katalogu *systemu Windows* .</span><span class="sxs-lookup"><span data-stu-id="d2757-113">The *csc.exe* executable file usually is located in the Microsoft.NET\Framework\\*\<Version>* folder under the *Windows* directory.</span></span> <span data-ttu-id="d2757-114">Jego lokalizacja może się różnić w zależności od dokładnej konfiguracji określonego komputera.</span><span class="sxs-lookup"><span data-stu-id="d2757-114">Its location might vary depending on the exact configuration of a particular computer.</span></span> <span data-ttu-id="d2757-115">Jeśli na komputerze zainstalowano więcej niż jedną wersję .NET Framework, znajdziesz wiele wersji tego pliku.</span><span class="sxs-lookup"><span data-stu-id="d2757-115">If more than one version of the .NET Framework is installed on your computer, you'll find multiple versions of this file.</span></span> <span data-ttu-id="d2757-116">Aby uzyskać więcej informacji na temat takich instalacji, zobacz [How to: Określanie, które wersje .NET Framework są zainstalowane](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="d2757-116">For more information about such installations, see [How to: determine which versions of the .NET Framework are installed](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

> [!TIP]
> <span data-ttu-id="d2757-117">Podczas kompilowania projektu przy użyciu programu Visual Studio IDE, można wyświetlić polecenie **CSC** i skojarzone z nim opcje kompilatora w oknie **danych wyjściowych** .</span><span class="sxs-lookup"><span data-stu-id="d2757-117">When you build a project by using the Visual Studio IDE, you can display the **csc** command and its associated compiler options in the **Output** window.</span></span> <span data-ttu-id="d2757-118">Aby wyświetlić te informacje, postępuj zgodnie z instrukcjami w temacie [How to: View, Save i Configure log Build Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) , aby zmienić poziom szczegółowości danych dziennika na **normalny** lub **szczegółowy**.</span><span class="sxs-lookup"><span data-stu-id="d2757-118">To display this information, follow the instructions in [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) to change the verbosity level of the log data to **Normal** or **Detailed**.</span></span> <span data-ttu-id="d2757-119">Po odbudowaniu projektu Przeszukaj okno **dane wyjściowe** dla **CSC** , aby znaleźć wywołanie kompilatora języka C#.</span><span class="sxs-lookup"><span data-stu-id="d2757-119">After you rebuild your project, search the **Output** window for **csc** to find the invocation of the C# compiler.</span></span>

 <span data-ttu-id="d2757-120">**W tym temacie**</span><span class="sxs-lookup"><span data-stu-id="d2757-120">**In this topic**</span></span>

- [<span data-ttu-id="d2757-121">Reguły dla składni wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="d2757-121">Rules for command-line syntax</span></span>](#rules-for-command-line-syntax-for-the-c-compiler)

- [<span data-ttu-id="d2757-122">Przykładowe wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="d2757-122">Sample command lines</span></span>](#sample-command-lines-for-the-c-compiler)

- [<span data-ttu-id="d2757-123">Różnice między kompilatorem C# i wyjściem kompilatora języka C++</span><span class="sxs-lookup"><span data-stu-id="d2757-123">Differences between C# compiler and C++ compiler output</span></span>](#differences-between-c-compiler-and-c-compiler-output)

## <a name="rules-for-command-line-syntax-for-the-c-compiler"></a><span data-ttu-id="d2757-124">Reguły dla składni wiersza polecenia dla kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="d2757-124">Rules for command-line syntax for the C# compiler</span></span>

<span data-ttu-id="d2757-125">Kompilator języka C# używa następujących reguł, gdy interpretuje argumenty podane w wierszu polecenia systemu operacyjnego:</span><span class="sxs-lookup"><span data-stu-id="d2757-125">The C# compiler uses the following rules when it interprets arguments given on the operating system command line:</span></span>

- <span data-ttu-id="d2757-126">Argumenty są rozdzielane znakami odstępu, który jest spacją lub tabulatorem.</span><span class="sxs-lookup"><span data-stu-id="d2757-126">Arguments are delimited by white space, which is either a space or a tab.</span></span>

- <span data-ttu-id="d2757-127">Znak karetki (^) nie jest rozpoznawany jako znak ucieczki lub ogranicznik.</span><span class="sxs-lookup"><span data-stu-id="d2757-127">The caret character (^) is not recognized as an escape character or delimiter.</span></span> <span data-ttu-id="d2757-128">Ten znak jest obsługiwany przez analizator wiersza polecenia w systemie operacyjnym przed przekazaniem go do `argv` tablicy w programie.</span><span class="sxs-lookup"><span data-stu-id="d2757-128">The character is handled by the command-line parser in the operating system before it's passed to the `argv` array in the program.</span></span>

- <span data-ttu-id="d2757-129">Ciąg ujęty w znaki podwójnego cudzysłowu ("String") jest interpretowany jako pojedynczy argument, niezależnie od białego miejsca zawartego w.</span><span class="sxs-lookup"><span data-stu-id="d2757-129">A string enclosed in double quotation marks ("string") is interpreted as a single argument, regardless of white space that is contained within.</span></span> <span data-ttu-id="d2757-130">Ciąg w cudzysłowie może być osadzony w argumencie.</span><span class="sxs-lookup"><span data-stu-id="d2757-130">A quoted string can be embedded in an argument.</span></span>

- <span data-ttu-id="d2757-131">Podwójny cudzysłów poprzedzony ukośnikiem odwrotnym ( \\ ") jest interpretowany jako literał podwójnego znaku cudzysłowu (").</span><span class="sxs-lookup"><span data-stu-id="d2757-131">A double quotation mark preceded by a backslash (\\") is interpreted as a literal double quotation mark character (").</span></span>

- <span data-ttu-id="d2757-132">Ukośniki odwrotne są interpretowane dosłownie, chyba że od razu poprzedzają podwójny cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="d2757-132">Backslashes are interpreted literally, unless they immediately precede a double quotation mark.</span></span>

- <span data-ttu-id="d2757-133">Jeśli parzysta liczba kresek ułamkowych jest poprzedzona znakiem podwójnego cudzysłowu, jeden ukośnik odwrotny jest umieszczany w `argv` tablicy dla każdej pary ukośników odwrotnych, a podwójny cudzysłów jest interpretowany jako ogranicznik ciągu.</span><span class="sxs-lookup"><span data-stu-id="d2757-133">If an even number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is interpreted as a string delimiter.</span></span>

- <span data-ttu-id="d2757-134">Jeśli po parzystej liczbie ukośników odwrotnych następuje znak podwójnego cudzysłowu, jeden ukośnik odwrotny jest umieszczany w `argv` tablicy dla każdej pary ukośników odwrotnych, a podwójny cudzysłów jest "ucieczkd" przez resztę ukośnika odwrotnego.</span><span class="sxs-lookup"><span data-stu-id="d2757-134">If an odd number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is "escaped" by the remaining backslash.</span></span> <span data-ttu-id="d2757-135">Powoduje to dodanie literału podwójnego cudzysłowu (") do elementu `argv` .</span><span class="sxs-lookup"><span data-stu-id="d2757-135">This causes a literal double quotation mark (") to be added in `argv`.</span></span>

## <a name="sample-command-lines-for-the-c-compiler"></a><span data-ttu-id="d2757-136">Przykładowe wiersze poleceń dla kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="d2757-136">Sample command lines for the C# compiler</span></span>

- <span data-ttu-id="d2757-137">Kompiluje *File.exe*tworzenia *File.cs* :</span><span class="sxs-lookup"><span data-stu-id="d2757-137">Compiles *File.cs* producing *File.exe*:</span></span>

  ```console
  csc File.cs
  ```

- <span data-ttu-id="d2757-138">Kompiluje *File.dll*tworzenia *File.cs* :</span><span class="sxs-lookup"><span data-stu-id="d2757-138">Compiles *File.cs* producing *File.dll*:</span></span>

  ```console
  csc -target:library File.cs
  ```

- <span data-ttu-id="d2757-139">Kompiluje *File.cs* i tworzy *My.exe*:</span><span class="sxs-lookup"><span data-stu-id="d2757-139">Compiles *File.cs* and creates *My.exe*:</span></span>

  ```console
  csc -out:My.exe File.cs
  ```

- <span data-ttu-id="d2757-140">Kompiluje wszystkie pliki C# w bieżącym katalogu z włączonymi optymalizacjami i definiuje symbol debugowania.</span><span class="sxs-lookup"><span data-stu-id="d2757-140">Compiles all the C# files in the current directory with optimizations enabled and defines the DEBUG symbol.</span></span> <span data-ttu-id="d2757-141">Dane wyjściowe są *File2.exe*:</span><span class="sxs-lookup"><span data-stu-id="d2757-141">The output is *File2.exe*:</span></span>

  ```console
  csc -define:DEBUG -optimize -out:File2.exe *.cs
  ```

- <span data-ttu-id="d2757-142">Kompiluje wszystkie pliki w języku C# w bieżącym katalogu, które wygenerowały wersję Debug *File2.dll*.</span><span class="sxs-lookup"><span data-stu-id="d2757-142">Compiles all the C# files in the current directory producing a debug version of *File2.dll*.</span></span> <span data-ttu-id="d2757-143">Brak logo i nie są wyświetlane żadne ostrzeżenia:</span><span class="sxs-lookup"><span data-stu-id="d2757-143">No logo and no warnings are displayed:</span></span>

  ```console
  csc -target:library -out:File2.dll -warn:0 -nologo -debug *.cs
  ```

- <span data-ttu-id="d2757-144">Kompiluje wszystkie pliki C# w bieżącym katalogu na *coś. xyz* (Biblioteka DLL):</span><span class="sxs-lookup"><span data-stu-id="d2757-144">Compiles all the C# files in the current directory to *Something.xyz* (a DLL):</span></span>

  ```console
  csc -target:library -out:Something.xyz *.cs
  ```

## <a name="differences-between-c-compiler-and-c-compiler-output"></a><span data-ttu-id="d2757-145">Różnice między kompilatorem C# i wyjściem kompilatora języka C++</span><span class="sxs-lookup"><span data-stu-id="d2757-145">Differences between C# compiler and C++ compiler output</span></span>

<span data-ttu-id="d2757-146">Nie ma plików obiektów (*. obj*) utworzonych w wyniku wywoływania kompilatora języka C#; pliki wyjściowe są tworzone bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="d2757-146">There are no object (*.obj*) files created as a result of invoking the C# compiler; output files are created directly.</span></span> <span data-ttu-id="d2757-147">W związku z tym kompilator języka C# nie potrzebuje konsolidatora.</span><span class="sxs-lookup"><span data-stu-id="d2757-147">As a result of this, the C# compiler does not need a linker.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2757-148">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d2757-148">See also</span></span>

- [<span data-ttu-id="d2757-149">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="d2757-149">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="d2757-150">Opcje kompilatora C# w porządku alfabetycznym</span><span class="sxs-lookup"><span data-stu-id="d2757-150">C# Compiler Options Listed Alphabetically</span></span>](./listed-alphabetically.md)
- [<span data-ttu-id="d2757-151">Opcje kompilatora C# w rozbiciu na kategorie</span><span class="sxs-lookup"><span data-stu-id="d2757-151">C# Compiler Options Listed by Category</span></span>](./listed-by-category.md)
- [<span data-ttu-id="d2757-152">Main () i argumenty wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="d2757-152">Main() and Command-Line Arguments</span></span>](../../programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="d2757-153">Argumenty wiersza poleceń</span><span class="sxs-lookup"><span data-stu-id="d2757-153">Command-Line Arguments</span></span>](../../programming-guide/main-and-command-args/command-line-arguments.md)
- [<span data-ttu-id="d2757-154">Wyświetlanie argumentów wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="d2757-154">How to display command-line arguments</span></span>](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [<span data-ttu-id="d2757-155">Main() — Zwracane wartości</span><span class="sxs-lookup"><span data-stu-id="d2757-155">Main() Return Values</span></span>](../../programming-guide/main-and-command-args/main-return-values.md)
