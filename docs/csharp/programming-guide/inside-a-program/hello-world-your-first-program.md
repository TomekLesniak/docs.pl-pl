---
title: Hello world — pierwszy program korzystający z programu Visual Studio w systemie Windows lub Mac — Przewodnik programowania w języku C#
description: Program Visual Studio to profesjonalne środowisko programistyczne z wieloma funkcjami programistycznymi dla platformy .NET. Użyj programu Visual Studio, aby utworzyć wersję C# Hello world!
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: b78937b8ba1c7d4718bfb6252dac705945336d2a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301830"
---
# <a name="hello-world----your-first-program"></a><span data-ttu-id="0ec5c-104">Hello world — pierwszy program</span><span class="sxs-lookup"><span data-stu-id="0ec5c-104">Hello World -- Your first program</span></span>

<span data-ttu-id="0ec5c-105">W tym artykule opisano tworzenie tradycyjnych "Hello world!" przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0ec5c-105">In this article, you'll use Visual Studio to create the traditional "Hello World!"</span></span> <span data-ttu-id="0ec5c-106">Program.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-106">program.</span></span> <span data-ttu-id="0ec5c-107">Program Visual Studio to profesjonalne zintegrowane środowisko programistyczne (IDE) z wieloma funkcjami przeznaczonymi do programowania na platformie .NET.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-107">Visual Studio is a professional Integrated Development Environment (IDE) with many features designed for .NET development.</span></span> <span data-ttu-id="0ec5c-108">Do utworzenia tego programu będziesz używać tylko kilku funkcji w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-108">You'll use only a few of the features in Visual Studio to create this program.</span></span> <span data-ttu-id="0ec5c-109">Aby dowiedzieć się więcej na temat programu Visual Studio, zobacz [wprowadzenie with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span><span class="sxs-lookup"><span data-stu-id="0ec5c-109">To learn more about Visual Studio, see [Getting Started with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a><span data-ttu-id="0ec5c-110">Tworzenie nowej aplikacji</span><span class="sxs-lookup"><span data-stu-id="0ec5c-110">Create a new application</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="0ec5c-111">Windows</span><span class="sxs-lookup"><span data-stu-id="0ec5c-111">Windows</span></span>](#tab/windows)

<span data-ttu-id="0ec5c-112">Uruchom program Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-112">Start Visual Studio.</span></span> <span data-ttu-id="0ec5c-113">Zobaczysz następujący obraz w systemie Windows:</span><span class="sxs-lookup"><span data-stu-id="0ec5c-113">You'll see the following image on Windows:</span></span>

![Ekran powitalny programu Visual Studio w systemie Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

<span data-ttu-id="0ec5c-115">Wybierz pozycję **Utwórz nowy projekt** w prawym dolnym rogu obrazu.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-115">Select **Create a new project** in the lower right corner of the image.</span></span> <span data-ttu-id="0ec5c-116">Program Visual Studio Wyświetla okno dialogowe **Nowy projekt** :</span><span class="sxs-lookup"><span data-stu-id="0ec5c-116">Visual Studio displays the **New Project** dialog:</span></span>

![Ekran nowego projektu programu Visual Studio w systemie Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> <span data-ttu-id="0ec5c-118">Jeśli jest to pierwsze uruchomienie programu Visual Studio, lista **ostatnio używanych szablonów projektu** jest pusta.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-118">If this is the first time you've started Visual Studio, the **Recent project templates** list is empty.</span></span>

<span data-ttu-id="0ec5c-119">W oknie dialogowym Nowy projekt wybierz pozycję "Aplikacja konsolowa (.NET Core)", a następnie naciśnij przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-119">On the new project dialog, choose "Console App (.NET Core)" and then press **Next**.</span></span> <span data-ttu-id="0ec5c-120">Nadaj projektowi nazwę, na przykład "HelloWorld", a następnie naciśnij pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-120">Give your project a name, such as "HelloWorld", then press **Create**.</span></span>

<span data-ttu-id="0ec5c-121">Program Visual Studio otwiera projekt.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-121">Visual Studio opens your project.</span></span> <span data-ttu-id="0ec5c-122">To już podstawowy "Hello world!"</span><span class="sxs-lookup"><span data-stu-id="0ec5c-122">It's already a basic "Hello World!"</span></span> <span data-ttu-id="0ec5c-123">przyklad.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-123">example.</span></span> <span data-ttu-id="0ec5c-124">Naciśnij klawisz `Ctrl`  +  `F5` , aby uruchomić projekt.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-124">Press `Ctrl` + `F5` to run your project.</span></span> <span data-ttu-id="0ec5c-125">Program Visual Studio kompiluje projekt, konwertując kod źródłowy do pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-125">Visual Studio builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="0ec5c-126">Następnie uruchamia okno poleceń, w którym jest uruchamiana nowa aplikacja.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-126">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="0ec5c-127">W oknie powinien zostać wyświetlony następujący tekst:</span><span class="sxs-lookup"><span data-stu-id="0ec5c-127">You should see the following text in the window:</span></span>

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="0ec5c-128">Naciśnij klawisz, aby zamknąć okno.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-128">Press a key to close the window.</span></span>

# <a name="macos"></a>[<span data-ttu-id="0ec5c-129">macOS</span><span class="sxs-lookup"><span data-stu-id="0ec5c-129">macOS</span></span>](#tab/macos)

<span data-ttu-id="0ec5c-130">Rozpocznij Visual Studio dla komputerów Mac.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-130">Start Visual Studio for Mac.</span></span> <span data-ttu-id="0ec5c-131">Na komputerze Mac zobaczysz następujący obraz:</span><span class="sxs-lookup"><span data-stu-id="0ec5c-131">You'll see the following image on Mac:</span></span>

![Ekran powitalny programu Visual Studio na komputerze Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> <span data-ttu-id="0ec5c-133">Jeśli jest to pierwsze uruchomienie Visual Studio dla komputerów Mac, lista **ostatnich projektów** jest pusta.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-133">If this is the first time you've started Visual Studio for Mac, the **Recent projects** list is empty.</span></span>

<span data-ttu-id="0ec5c-134">Wybierz pozycję **Nowy** w prawym górnym rogu obrazu.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-134">Select **New** in the upper right corner of the image.</span></span> <span data-ttu-id="0ec5c-135">Visual Studio dla komputerów Mac wyświetla okno dialogowe **Nowy projekt** :</span><span class="sxs-lookup"><span data-stu-id="0ec5c-135">Visual Studio for Mac displays the **New Project** dialog:</span></span>

![Ekran nowego projektu programu Visual Studio na komputerze Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

<span data-ttu-id="0ec5c-137">W oknie dialogowym Nowy projekt wybierz pozycję ".NET Core" i "Aplikacja konsolowa", a następnie naciśnij przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-137">On the new project dialog, choose ".NET Core", and "Console App" and then press **Next**.</span></span> <span data-ttu-id="0ec5c-138">Musisz wybrać platformę docelową.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-138">You'll need to select the target framework.</span></span> <span data-ttu-id="0ec5c-139">Wartość domyślna to "prawidłowo", więc naciśnij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-139">The default is fine, so press next.</span></span> <span data-ttu-id="0ec5c-140">Nadaj projektowi nazwę, na przykład "HelloWorld", a następnie naciśnij pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-140">Give your project a name, such as "HelloWorld", then press **Create**.</span></span> <span data-ttu-id="0ec5c-141">Możesz użyć domyślnej lokalizacji projektu.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-141">You can use the default project location.</span></span> <span data-ttu-id="0ec5c-142">Nie dodawaj tego projektu do kontroli źródła.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-142">Don't add this project to source control.</span></span>

<span data-ttu-id="0ec5c-143">Visual Studio dla komputerów Mac otwiera projekt.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-143">Visual Studio for Mac opens your project.</span></span> <span data-ttu-id="0ec5c-144">To już podstawowy "Hello world!"</span><span class="sxs-lookup"><span data-stu-id="0ec5c-144">It's already a basic "Hello World!"</span></span> <span data-ttu-id="0ec5c-145">przyklad.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-145">example.</span></span> <span data-ttu-id="0ec5c-146">Naciśnij klawisz `Ctrl`  +  `Fn`  +  `F5` , aby uruchomić projekt.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-146">Press `Ctrl` + `Fn` + `F5` to run your project.</span></span> <span data-ttu-id="0ec5c-147">Visual Studio dla komputerów Mac kompiluje projekt, konwertując kod źródłowy do pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-147">Visual Studio for Mac builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="0ec5c-148">Następnie uruchamia okno poleceń, w którym jest uruchamiana nowa aplikacja.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-148">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="0ec5c-149">W oknie powinien zostać wyświetlony następujący tekst:</span><span class="sxs-lookup"><span data-stu-id="0ec5c-149">You should see the following text in the window:</span></span>

```console
Hello World!

Press any key to close this window . . .
```

<span data-ttu-id="0ec5c-150">Naciśnij klawisz, aby zakończyć sesję.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-150">Press a key to end the session.</span></span>

---

## <a name="elements-of-a-c-program"></a><span data-ttu-id="0ec5c-151">Elementy programu C#</span><span class="sxs-lookup"><span data-stu-id="0ec5c-151">Elements of a C# program</span></span>

<span data-ttu-id="0ec5c-152">Przeanalizujmy ważne części tego programu.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-152">Let's examine the important parts of this program.</span></span> <span data-ttu-id="0ec5c-153">Pierwszy wiersz zawiera komentarz.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-153">The first line contains a comment.</span></span> <span data-ttu-id="0ec5c-154">Znaki `//` konwertują resztę wiersza do komentarza.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-154">The characters `//` convert the rest of the line to a comment.</span></span>

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="0ec5c-155">Możesz również dodać komentarz do bloku tekstu, umieszczając go między `/*` `*/` znakami i.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-155">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="0ec5c-156">Pokazano to w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-156">This is shown in the following example.</span></span>

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

<span data-ttu-id="0ec5c-157">Aplikacja konsolowa w języku C# musi zawierać `Main` metodę, w której kontrolka zaczyna się i skończy.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-157">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="0ec5c-158">`Main`Metoda ta umożliwia tworzenie obiektów i wykonywanie innych metod.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-158">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="0ec5c-159">`Main`Metoda jest metodą [statyczną](../../language-reference/keywords/static.md) , która znajduje się wewnątrz klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-159">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="0ec5c-160">W poprzednim "Hello world!"</span><span class="sxs-lookup"><span data-stu-id="0ec5c-160">In the previous "Hello World!"</span></span> <span data-ttu-id="0ec5c-161">przykład znajduje się w klasie o nazwie `Hello` .</span><span class="sxs-lookup"><span data-stu-id="0ec5c-161">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="0ec5c-162">Metodę można zadeklarować `Main` w jeden z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="0ec5c-162">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="0ec5c-163">Może zwrócić `void` .</span><span class="sxs-lookup"><span data-stu-id="0ec5c-163">It can return `void`.</span></span> <span data-ttu-id="0ec5c-164">Oznacza to, że program nie zwraca wartości.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-164">That means your program doesn't return a value.</span></span>

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="0ec5c-165">Może również zwracać liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-165">It can also return an integer.</span></span> <span data-ttu-id="0ec5c-166">Liczba całkowita jest **kodem zakończenia** dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-166">The integer is the **exit code** for your application.</span></span>

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="0ec5c-167">Za pomocą jednego z typów zwracanych można przyjmować argumenty.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-167">With either of the return types, it can take arguments.</span></span>

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

<span data-ttu-id="0ec5c-168">-lub-</span><span class="sxs-lookup"><span data-stu-id="0ec5c-168">-or-</span></span>

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="0ec5c-169">Parametr `Main` metody, `args` , jest `string` tablicą zawierającą argumenty wiersza polecenia używane do wywołania programu.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-169">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span>

<span data-ttu-id="0ec5c-170">Aby uzyskać więcej informacji o używaniu argumentów wiersza polecenia, zobacz przykłady w [Main () i argumenty wiersza polecenia](../main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ec5c-170">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md).</span></span>

## <a name="input-and-output"></a><span data-ttu-id="0ec5c-171">Dane wejściowe i wyjściowe</span><span class="sxs-lookup"><span data-stu-id="0ec5c-171">Input and output</span></span>

<span data-ttu-id="0ec5c-172">Programy języka C# zwykle używają usług wejścia/wyjścia dostarczonych przez bibliotekę wykonawczą platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-172">C# programs generally use the input/output services provided by the run-time library of .NET.</span></span> <span data-ttu-id="0ec5c-173">Instrukcja `System.Console.WriteLine("Hello World!");` używa <xref:System.Console.WriteLine%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-173">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="0ec5c-174">Jest to jedna z metod wyjściowych <xref:System.Console> klasy w bibliotece wykonawczej.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-174">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="0ec5c-175">Wyświetla jego parametr String w standardowym strumieniu wyjściowym, po którym następuje nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-175">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="0ec5c-176">Inne <xref:System.Console> metody są dostępne dla różnych operacji wejścia i wyjścia.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-176">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="0ec5c-177">Jeśli dołączysz `using System;` dyrektywę na początku programu, możesz bezpośrednio użyć <xref:System> klas i metod bez ich w pełni kwalifikujących się.</span><span class="sxs-lookup"><span data-stu-id="0ec5c-177">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="0ec5c-178">Na przykład można wywołać `Console.WriteLine` zamiast `System.Console.WriteLine` :</span><span class="sxs-lookup"><span data-stu-id="0ec5c-178">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="0ec5c-179">Aby uzyskać więcej informacji na temat metod wejścia/wyjścia, zobacz <xref:System.IO> .</span><span class="sxs-lookup"><span data-stu-id="0ec5c-179">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ec5c-180">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0ec5c-180">See also</span></span>

- [<span data-ttu-id="0ec5c-181">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="0ec5c-181">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0ec5c-182">Przykłady i samouczki</span><span class="sxs-lookup"><span data-stu-id="0ec5c-182">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="0ec5c-183">Main () i argumenty wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="0ec5c-183">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="0ec5c-184">Wprowadzenie z Visual C #</span><span class="sxs-lookup"><span data-stu-id="0ec5c-184">Getting Started with Visual C#</span></span>](/visualstudio/ide/quickstart-csharp-console)
