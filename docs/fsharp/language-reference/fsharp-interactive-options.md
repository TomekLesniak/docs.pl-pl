---
title: Opcje interaktywne
description: Dowiedz się więcej na temat opcji wiersza polecenia obsługiwanych przez F# Interactive, fsi.exe.
ms.date: 08/15/2020
ms.openlocfilehash: da2251c1d2e57090ed926e501cebf3c53ac58052
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558611"
---
# <a name="f-interactive-options"></a><span data-ttu-id="c5495-103">Opcje F# Interactive</span><span class="sxs-lookup"><span data-stu-id="c5495-103">F# Interactive options</span></span>

<span data-ttu-id="c5495-104">W tym artykule opisano opcje wiersza polecenia obsługiwane przez F# Interactive, `fsi.exe` .</span><span class="sxs-lookup"><span data-stu-id="c5495-104">This article describes the command-line options supported by F# Interactive, `fsi.exe`.</span></span> <span data-ttu-id="c5495-105">F# Interactive akceptuje wiele z tych samych opcji wiersza polecenia co kompilator języka F #, ale również akceptuje pewne dodatkowe opcje.</span><span class="sxs-lookup"><span data-stu-id="c5495-105">F# Interactive accepts many of the same command-line options as the F# compiler, but also accepts some additional options.</span></span>

## <a name="use-f-interactive-for-scripting"></a><span data-ttu-id="c5495-106">Używanie F# Interactive do obsługi skryptów</span><span class="sxs-lookup"><span data-stu-id="c5495-106">Use F# Interactive for scripting</span></span>

<span data-ttu-id="c5495-107">F# Interactive, `dotnet fsi` , może być uruchamiany interaktywnie lub można uruchomić z wiersza polecenia, aby uruchomić skrypt.</span><span class="sxs-lookup"><span data-stu-id="c5495-107">F# Interactive, `dotnet fsi`, can be launched interactively, or it can be launched from the command line to run a script.</span></span> <span data-ttu-id="c5495-108">Składnia wiersza polecenia jest</span><span class="sxs-lookup"><span data-stu-id="c5495-108">The command-line syntax is</span></span>

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

<span data-ttu-id="c5495-109">Rozszerzenie pliku dla plików skryptów języka F # to `.fsx` .</span><span class="sxs-lookup"><span data-stu-id="c5495-109">The file extension for F# script files is `.fsx`.</span></span>

## <a name="table-of-f-interactive-options"></a><span data-ttu-id="c5495-110">Tabela opcji F# Interactive</span><span class="sxs-lookup"><span data-stu-id="c5495-110">Table of F# Interactive Options</span></span>

<span data-ttu-id="c5495-111">Poniższa tabela zawiera podsumowanie opcji obsługiwanych przez F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="c5495-111">The following table summarizes the options supported by F# Interactive.</span></span> <span data-ttu-id="c5495-112">Można ustawić te opcje w wierszu polecenia lub w środowisku IDE programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c5495-112">You can set these options on the command line or through the Visual Studio IDE.</span></span> <span data-ttu-id="c5495-113">Aby ustawić te opcje w środowisku IDE programu Visual Studio, otwórz menu **Narzędzia** , wybierz polecenie **Opcje**, rozwiń węzeł **Narzędzia F #** , a następnie wybierz **F# Interactive**.</span><span class="sxs-lookup"><span data-stu-id="c5495-113">To set these options in the Visual Studio IDE, open the **Tools** menu, select **Options**, expand the **F# Tools** node, and then select **F# Interactive**.</span></span>

<span data-ttu-id="c5495-114">Gdy listy pojawiają się w F# Interactive argumenty opcji, elementy listy są oddzielone średnikami ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="c5495-114">Where lists appear in F# Interactive option arguments, list elements are separated by semicolons (`;`).</span></span>

|<span data-ttu-id="c5495-115">Opcja</span><span class="sxs-lookup"><span data-stu-id="c5495-115">Option</span></span>|<span data-ttu-id="c5495-116">Opis</span><span class="sxs-lookup"><span data-stu-id="c5495-116">Description</span></span>|
|------|-----------|
|**--**|<span data-ttu-id="c5495-117">Służy do Poinstruuj F# Interactive, aby traktować pozostałe argumenty jako argumenty wiersza polecenia do programu lub skryptu języka F #, do którego można uzyskać dostęp w kodzie przy użyciu listy **FSI. CommandLineArgs —**.</span><span class="sxs-lookup"><span data-stu-id="c5495-117">Used to instruct F# Interactive to treat remaining arguments as command-line arguments to the F# program or script, which you can access in code by using the list **fsi.CommandLineArgs**.</span></span>|
|<span data-ttu-id="c5495-118">**--zaewidencjonowano**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-118">**--checked**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c5495-119">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-119">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-120">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-120">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-121">**--CodePage: &lt; int&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-121">**--codepage:&lt;int&gt;**</span></span>|<span data-ttu-id="c5495-122">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-122">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-123">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-123">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-124">**--consolecolors**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-124">**--consolecolors**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c5495-125">Wyświetla ostrzeżenia i komunikaty o błędach w kolorze.</span><span class="sxs-lookup"><span data-stu-id="c5495-125">Outputs warning and error messages in color.</span></span>|
|<span data-ttu-id="c5495-126">**--crossoptimize**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-126">**--crossoptimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c5495-127">Włączać lub wyłączać optymalizacje między modułami.</span><span class="sxs-lookup"><span data-stu-id="c5495-127">Enable or disable cross-module optimizations.</span></span>|
|<span data-ttu-id="c5495-128">**--Debug**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-128">**--debug**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="c5495-129">**--Debug:**[**full**&#124;**pdbonly**&#124;**Portable**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="c5495-129">**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span><br /><br /><span data-ttu-id="c5495-130">**-g**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-130">**-g**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="c5495-131">**-g:**[**pełna**&#124;**pdbonly**&#124;**przenośny**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="c5495-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span>|<span data-ttu-id="c5495-132">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-132">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-133">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-133">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-134">**--define: &lt; ciąg&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-134">**--define:&lt;string&gt;**</span></span>|<span data-ttu-id="c5495-135">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-135">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-136">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-136">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-137">**--deterministyczny**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-137">**--deterministic**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c5495-138">Tworzy deterministyczny zestaw (w tym identyfikator GUID i sygnaturę czasową wersji modułu).</span><span class="sxs-lookup"><span data-stu-id="c5495-138">Produces a deterministic assembly (including module version GUID and timestamp).</span></span>|
|<span data-ttu-id="c5495-139">**--exec**</span><span class="sxs-lookup"><span data-stu-id="c5495-139">**--exec**</span></span>|<span data-ttu-id="c5495-140">Nakazuje programowi F # Interactive Kończenie po załadowaniu plików lub uruchomieniu pliku skryptu podanym w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="c5495-140">Instructs F# interactive to exit after loading the files or running the script file given on the command line.</span></span>|
|<span data-ttu-id="c5495-141">**--fullpaths —**</span><span class="sxs-lookup"><span data-stu-id="c5495-141">**--fullpaths**</span></span>|<span data-ttu-id="c5495-142">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-142">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-143">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-143">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-144">**--GUI**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-144">**--gui**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c5495-145">Włącza lub wyłącza pętlę zdarzeń Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c5495-145">Enables or disables the Windows Forms event loop.</span></span> <span data-ttu-id="c5495-146">Wartość domyślna jest włączona.</span><span class="sxs-lookup"><span data-stu-id="c5495-146">The default is enabled.</span></span>|
|<span data-ttu-id="c5495-147">**--Pomoc**</span><span class="sxs-lookup"><span data-stu-id="c5495-147">**--help**</span></span><br /><br /><span data-ttu-id="c5495-148">**-?**</span><span class="sxs-lookup"><span data-stu-id="c5495-148">**-?**</span></span>|<span data-ttu-id="c5495-149">Służy do wyświetlania składni wiersza polecenia i krótkiego opisu każdej opcji.</span><span class="sxs-lookup"><span data-stu-id="c5495-149">Used to display the command-line syntax and a brief description of each option.</span></span>|
|<span data-ttu-id="c5495-150">**--lib: &lt; Lista folderów&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-150">**--lib:&lt;folder-list&gt;**</span></span><br /><br /><span data-ttu-id="c5495-151">**-I: &lt; Lista folderów&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-151">**-I:&lt;folder-list&gt;**</span></span>|<span data-ttu-id="c5495-152">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-152">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-153">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-153">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-154">**--Load: &lt; filename&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-154">**--load:&lt;filename&gt;**</span></span>|<span data-ttu-id="c5495-155">Kompiluje dany kod źródłowy przy uruchamianiu i ładuje skompilowane konstrukcje F # do sesji.</span><span class="sxs-lookup"><span data-stu-id="c5495-155">Compiles the given source code at startup and loads the compiled F# constructs into the session.</span></span>|
|<span data-ttu-id="c5495-156">**--mlcompatibility**</span><span class="sxs-lookup"><span data-stu-id="c5495-156">**--mlcompatibility**</span></span>|<span data-ttu-id="c5495-157">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-157">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-158">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-158">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-159">**--noframework**</span><span class="sxs-lookup"><span data-stu-id="c5495-159">**--noframework**</span></span>|<span data-ttu-id="c5495-160">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-160">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-161">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md)</span><span class="sxs-lookup"><span data-stu-id="c5495-161">For more information, see [Compiler Options](compiler-options.md)</span></span>|
|<span data-ttu-id="c5495-162">**--nologo**</span><span class="sxs-lookup"><span data-stu-id="c5495-162">**--nologo**</span></span>|<span data-ttu-id="c5495-163">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-163">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-164">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-164">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-165">**--nowarn: &lt; Ostrzeżenie-lista&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-165">**--nowarn:&lt;warning-list&gt;**</span></span>|<span data-ttu-id="c5495-166">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-166">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-167">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-167">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-168">**--Optymalizuj**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-168">**--optimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c5495-169">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-169">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-170">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-170">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-171">**--preferreduilang: &lt; lang&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-171">**--preferreduilang:&lt;lang&gt;**</span></span>| <span data-ttu-id="c5495-172">Określa nazwę preferowanej kultury języka wyjściowego (na przykład es-ES, ja-JP).</span><span class="sxs-lookup"><span data-stu-id="c5495-172">Specifies the preferred output language culture name (for example, es-ES, ja-JP).</span></span> |
|<span data-ttu-id="c5495-173">**--quiet**</span><span class="sxs-lookup"><span data-stu-id="c5495-173">**--quiet**</span></span>|<span data-ttu-id="c5495-174">Pomiń dane wyjściowe F# Interactive strumienia **stdout** .</span><span class="sxs-lookup"><span data-stu-id="c5495-174">Suppress F# Interactive's output to the **stdout** stream.</span></span>|
|<span data-ttu-id="c5495-175">**--Cytaty-debugowanie**</span><span class="sxs-lookup"><span data-stu-id="c5495-175">**--quotations-debug**</span></span>|<span data-ttu-id="c5495-176">Określa, że powinny być emitowane dodatkowe informacje o debugowaniu dla wyrażeń, które pochodzą z literałów cytatu w języku F # i odbitej definicji.</span><span class="sxs-lookup"><span data-stu-id="c5495-176">Specifies that extra debugging information should be emitted for expressions that are derived from F# quotation literals and reflected definitions.</span></span> <span data-ttu-id="c5495-177">Informacje debugowania są dodawane do atrybutów niestandardowych węzła drzewa wyrażenia języka F #.</span><span class="sxs-lookup"><span data-stu-id="c5495-177">The debug information is added to the custom attributes of an F# expression tree node.</span></span> <span data-ttu-id="c5495-178">Zobacz [cytaty kodu](code-quotations.md) i [expr. CustomAttributes —](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span><span class="sxs-lookup"><span data-stu-id="c5495-178">See [Code Quotations](code-quotations.md) and [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span></span>|
|<span data-ttu-id="c5495-179">**--ReadLine**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-179">**--readline**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c5495-180">Włącza lub wyłącza uzupełnianie kart w trybie interaktywnym.</span><span class="sxs-lookup"><span data-stu-id="c5495-180">Enable or disable tab completion in interactive mode.</span></span>|
|<span data-ttu-id="c5495-181">**--Reference: &lt; filename&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-181">**--reference:&lt;filename&gt;**</span></span><br /><br /><span data-ttu-id="c5495-182">**-r: &lt; filename&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-182">**-r:&lt;filename&gt;**</span></span>|<span data-ttu-id="c5495-183">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-183">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-184">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-184">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-185">**--tailcalls**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-185">**--tailcalls**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c5495-186">Włącza lub wyłącza użycie instrukcji "tail IL", która powoduje, że ramka stosu będzie ponownie używana na potrzeby funkcji cyklicznych.</span><span class="sxs-lookup"><span data-stu-id="c5495-186">Enable or disable the use of the tail IL instruction, which causes the stack frame to be reused for tail recursive functions.</span></span> <span data-ttu-id="c5495-187">Ta opcja jest domyślnie włączona.</span><span class="sxs-lookup"><span data-stu-id="c5495-187">This option is enabled by default.</span></span>|
|<span data-ttu-id="c5495-188">**--targetprofile: &lt; ciąg&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-188">**--targetprofile:&lt;string&gt;**</span></span>|<span data-ttu-id="c5495-189">Określa Profil platformy docelowej tego zestawu.</span><span class="sxs-lookup"><span data-stu-id="c5495-189">Specifies target framework profile of this assembly.</span></span> <span data-ttu-id="c5495-190">Prawidłowe wartości to `mscorlib` , `netcore` , lub `netstandard` .</span><span class="sxs-lookup"><span data-stu-id="c5495-190">Valid values are `mscorlib`, `netcore`, or `netstandard`.</span></span> <span data-ttu-id="c5495-191">Wartość domyślna to `mscorlib`.</span><span class="sxs-lookup"><span data-stu-id="c5495-191">The default is `mscorlib`.</span></span>|
|<span data-ttu-id="c5495-192">**--Użyj: &lt; filename&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-192">**--use:&lt;filename&gt;**</span></span>|<span data-ttu-id="c5495-193">Instruuje interpretera, aby używał danego pliku przy uruchamianiu jako początkowej danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="c5495-193">Tells the interpreter to use the given file on startup as initial input.</span></span>|
|<span data-ttu-id="c5495-194">**--utf8output —**</span><span class="sxs-lookup"><span data-stu-id="c5495-194">**--utf8output**</span></span>|<span data-ttu-id="c5495-195">Taka sama jak opcja kompilatora fsc.exe.</span><span class="sxs-lookup"><span data-stu-id="c5495-195">Same as the fsc.exe compiler option.</span></span> <span data-ttu-id="c5495-196">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-196">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-197">**--WARN: &lt; ostrzeżenie-poziom&gt;**</span><span class="sxs-lookup"><span data-stu-id="c5495-197">**--warn:&lt;warning-level&gt;**</span></span>|<span data-ttu-id="c5495-198">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-198">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-199">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-199">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-200">**--warnaserror —**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c5495-200">**--warnaserror**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c5495-201">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-201">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-202">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-202">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c5495-203">**--warnaserror —**[ **+**&#124;**-** ]:\*\* &lt; int-list &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="c5495-203">**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**</span></span>|<span data-ttu-id="c5495-204">Taka sama jak opcja kompilatora **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c5495-204">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c5495-205">Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5495-205">For more information, see [Compiler Options](compiler-options.md).</span></span>|

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="c5495-206">F# Interactive drukowanie strukturalne</span><span class="sxs-lookup"><span data-stu-id="c5495-206">F# Interactive structured printing</span></span>

<span data-ttu-id="c5495-207">F# Interactive ( `dotnet fsi` ) używa rozszerzonej wersji [prostego formatowania tekstu](plaintext-formatting.md) do raportowania wartości.</span><span class="sxs-lookup"><span data-stu-id="c5495-207">F# Interactive (`dotnet fsi`) uses an extended version of [structured plain text formatting](plaintext-formatting.md) to report values.</span></span>

1. <span data-ttu-id="c5495-208">`%A`Obsługiwane są wszystkie funkcje formatowania zwykłego tekstu, a niektóre można dodatkowo dostosować.</span><span class="sxs-lookup"><span data-stu-id="c5495-208">All features of `%A` plain text formatting are supported, and some are additionally customizable.</span></span>

2. <span data-ttu-id="c5495-209">Drukowanie jest kolorowe, jeśli kolory są obsługiwane przez konsolę wyjściową.</span><span class="sxs-lookup"><span data-stu-id="c5495-209">Printing is colorized if colors are supported by the output console.</span></span>

3. <span data-ttu-id="c5495-210">Limit jest umieszczany w pokazanych długośćch ciągów, chyba że jawnie przeznaczysz ten ciąg.</span><span class="sxs-lookup"><span data-stu-id="c5495-210">A limit is placed on the length of strings shown, unless you explicitly evaluate that string.</span></span>

4. <span data-ttu-id="c5495-211">Zestaw ustawień definiowanych przez użytkownika jest dostępny za pośrednictwem `fsi` obiektu.</span><span class="sxs-lookup"><span data-stu-id="c5495-211">A set of user-definable settings is available via the `fsi` object.</span></span>

<span data-ttu-id="c5495-212">Dostępne ustawienia umożliwiające dostosowanie drukowania zwykłego tekstu dla raportowanych wartości to:</span><span class="sxs-lookup"><span data-stu-id="c5495-212">The available settings to customize plain text printing for reported values are:</span></span>

```fsharp
open System.Globalization

fsi.FormatProvider <- CultureInfo("de-DE")  // control the default culture for primitives

fsi.PrintWidth <- 120        // Control the width used for structured printing

fsi.PrintDepth <- 10         // Control the maximum depth of nested printing

fsi.PrintLength <- 10        // Control the length of lists and arrays

fsi.PrintSize <- 100         // Control the maximum overall object count

fsi.ShowProperties <- false  // Control whether properties of .NET objects are shown by default

fsi.ShowIEnumerable <- false // Control whether sequence values are expanded by default

fsi.ShowDeclarationValues <- false // Control whether values are shown for declaration outputs
```

### <a name="customize-with-addprinter-and-addprinttransformer"></a><span data-ttu-id="c5495-213">Dostosuj przy użyciu programu `AddPrinter` i `AddPrintTransformer`</span><span class="sxs-lookup"><span data-stu-id="c5495-213">Customize with `AddPrinter` and `AddPrintTransformer`</span></span>

<span data-ttu-id="c5495-214">Drukowanie w danych wyjściowych F# Interactive można dostosować za pomocą `fsi.AddPrinter` i `fsi.AddPrintTransformer` .</span><span class="sxs-lookup"><span data-stu-id="c5495-214">Printing in F# Interactive outputs can be customized by using `fsi.AddPrinter` and `fsi.AddPrintTransformer`.</span></span>
<span data-ttu-id="c5495-215">Pierwsza funkcja daje tekst, aby zastąpić drukowanie obiektu.</span><span class="sxs-lookup"><span data-stu-id="c5495-215">The first function gives text to replace the printing of an object.</span></span> <span data-ttu-id="c5495-216">Druga funkcja zwraca obiekt surogatu do wyświetlenia.</span><span class="sxs-lookup"><span data-stu-id="c5495-216">The second function returns a surrogate object to display instead.</span></span> <span data-ttu-id="c5495-217">Rozważmy na przykład następujący kod F #:</span><span class="sxs-lookup"><span data-stu-id="c5495-217">For example, consider the following F# code:</span></span>

```fsharp
open System

fsi.AddPrinter<DateTime>(fun dt -> dt.ToString("s"))

type DateAndLabel =
    { Date: DateTime
      Label: string  }

let newYearsDay1999 =
    { Date = DateTime(1999, 1, 1)
      Label = "New Year" }
```

<span data-ttu-id="c5495-218">W przypadku uruchomienia przykładu w F# Interactive dane wyjściowe w oparciu o zestaw opcji formatowania.</span><span class="sxs-lookup"><span data-stu-id="c5495-218">If you execute the example in F# Interactive, it outputs based on the formatting option set.</span></span> <span data-ttu-id="c5495-219">W takim przypadku ma wpływ na formatowanie daty i godziny:</span><span class="sxs-lookup"><span data-stu-id="c5495-219">In this case, it affects the formatting of date and time:</span></span>

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

<span data-ttu-id="c5495-220">`fsi.AddPrintTransformer` może służyć do nadawania obiektu zastępczego do drukowania:</span><span class="sxs-lookup"><span data-stu-id="c5495-220">`fsi.AddPrintTransformer` can be used to give a surrogate object for printing:</span></span>

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

<span data-ttu-id="c5495-221">Te dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="c5495-221">This outputs:</span></span>

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

<span data-ttu-id="c5495-222">Jeśli funkcja Transformer przekazała `fsi.AddPrintTransformer` wartość Returns `null` , transformator wydruku jest ignorowany.</span><span class="sxs-lookup"><span data-stu-id="c5495-222">If the transformer function passed to `fsi.AddPrintTransformer` returns `null`, then the print transformer is ignored.</span></span>
<span data-ttu-id="c5495-223">Można go użyć do filtrowania dowolnej wartości wejściowej, zaczynając od typu `obj` .</span><span class="sxs-lookup"><span data-stu-id="c5495-223">This can be used to filter any input value by starting with type `obj`.</span></span>  <span data-ttu-id="c5495-224">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="c5495-224">For example:</span></span>

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

<span data-ttu-id="c5495-225">Te dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="c5495-225">This outputs:</span></span>

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a><span data-ttu-id="c5495-226">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="c5495-226">Related topics</span></span>

|<span data-ttu-id="c5495-227">Tytuł</span><span class="sxs-lookup"><span data-stu-id="c5495-227">Title</span></span>|<span data-ttu-id="c5495-228">Opis</span><span class="sxs-lookup"><span data-stu-id="c5495-228">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="c5495-229">Opcje kompilatora</span><span class="sxs-lookup"><span data-stu-id="c5495-229">Compiler Options</span></span>](compiler-options.md)|<span data-ttu-id="c5495-230">Opisuje opcje wiersza polecenia dostępne dla kompilatora F #, **fsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="c5495-230">Describes command-line options available for the F# compiler, **fsc.exe**.</span></span>|
