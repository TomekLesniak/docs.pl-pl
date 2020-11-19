---
title: Tworzenie aplikacji konsolowej .NET przy użyciu programu Visual Studio
description: Dowiedz się, jak utworzyć aplikację konsolową .NET przy użyciu języka C# lub Visual Basic za pomocą programu Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e395122e59f17ed66bbd9d83b01610993f663ce1
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915948"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio"></a><span data-ttu-id="31baa-103">Samouczek: Tworzenie aplikacji konsolowej .NET przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="31baa-103">Tutorial: Create a .NET console application using Visual Studio</span></span>

<span data-ttu-id="31baa-104">W tym samouczku pokazano, jak utworzyć i uruchomić aplikację konsolową .NET w programie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="31baa-104">This tutorial shows how to create and run a .NET console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="31baa-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="31baa-105">Prerequisites</span></span>

- <span data-ttu-id="31baa-106">[Program Visual Studio 2019 w wersji 16,8 lub nowszej](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) z zainstalowanym **wieloplatformowym obciążeniem programistycznym dla platformy .NET Core** .</span><span class="sxs-lookup"><span data-stu-id="31baa-106">[Visual Studio 2019 version 16.8 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="31baa-107">Zestaw .NET 5,0 SDK jest instalowany automatycznie po wybraniu tego obciążenia.</span><span class="sxs-lookup"><span data-stu-id="31baa-107">The .NET 5.0 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="31baa-108">Aby uzyskać więcej informacji, zobacz [Instalowanie zestawu .NET SDK przy użyciu programu Visual Studio](../install/windows.md#install-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="31baa-108">For more information, see [Install the .NET SDK with Visual Studio](../install/windows.md#install-with-visual-studio).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="31baa-109">Tworzenie aplikacji</span><span class="sxs-lookup"><span data-stu-id="31baa-109">Create the app</span></span>

<span data-ttu-id="31baa-110">Utwórz projekt aplikacji konsolowej platformy .NET o nazwie "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="31baa-110">Create a .NET console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="31baa-111">Uruchom program Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="31baa-111">Start Visual Studio 2019.</span></span>

1. <span data-ttu-id="31baa-112">Wybierz pozycję **Narzędzia**  >  **Opcje**  >  **środowisko**  >  w **wersji zapoznawczej**, a następnie wybierz pozycję **Pokaż wszystkie szablony .NET Core w nowym projekcie (wymaga ponownego uruchomienia)**.</span><span class="sxs-lookup"><span data-stu-id="31baa-112">Select **Tools** > **Options** > **Environment** > **Preview features**, and then select **Show all .NET Core templates in the New project (requires restart)**.</span></span>

   :::image type="content" source="media/with-visual-studio/dotnet-options.png" alt-text="Pokaż wszystkie szablony platformy .NET — opcja":::

1. <span data-ttu-id="31baa-114">Zamknij i ponownie otwórz program Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31baa-114">Close and reopen Visual Studio.</span></span>

1. <span data-ttu-id="31baa-115">Na stronie startowej wybierz pozycję **Utwórz nowy projekt**.</span><span class="sxs-lookup"><span data-stu-id="31baa-115">On the start page, choose **Create a new project**.</span></span>

   :::image type="content" source="./media/with-visual-studio/start-window.png" alt-text="Przycisk Utwórz nowy projekt wybrany na stronie startowej programu Visual Studio":::

1. <span data-ttu-id="31baa-117">Na stronie **Tworzenie nowego projektu** wprowadź w polu wyszukiwania **konsolę** .</span><span class="sxs-lookup"><span data-stu-id="31baa-117">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="31baa-118">Następnie wybierz pozycję **C#** lub **Visual Basic** z listy język, a następnie wybierz pozycję **wszystkie platformy** z listy platform.</span><span class="sxs-lookup"><span data-stu-id="31baa-118">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="31baa-119">Wybierz szablon **aplikacja konsoli** , a następnie wybierz przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="31baa-119">Choose the **Console Application** template, and then choose **Next**.</span></span>

   :::image type="content" source="./media/with-visual-studio/create-new-project.png" alt-text="Utwórz nowe okno projektu z wybranymi filtrami":::

   > [!TIP]
   > <span data-ttu-id="31baa-121">Jeśli szablony platformy .NET nie są widoczne, prawdopodobnie brakuje wymaganego obciążenia.</span><span class="sxs-lookup"><span data-stu-id="31baa-121">If you don't see the .NET templates, you're probably missing the required workload.</span></span> <span data-ttu-id="31baa-122">W obszarze **nie można znaleźć tego, czego szukasz?** komunikat wybierz łącze **Zainstaluj więcej narzędzi i funkcji** .</span><span class="sxs-lookup"><span data-stu-id="31baa-122">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="31baa-123">Zostanie otwarty Instalator programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31baa-123">The Visual Studio Installer opens.</span></span> <span data-ttu-id="31baa-124">Upewnij się, że masz zainstalowaną **Międzyplatformowe obciążenie programistyczne dla platformy .NET Core** .</span><span class="sxs-lookup"><span data-stu-id="31baa-124">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

1. <span data-ttu-id="31baa-125">W oknie dialogowym **Konfigurowanie nowego projektu** wprowadź **HelloWorld** w polu **Nazwa projektu** .</span><span class="sxs-lookup"><span data-stu-id="31baa-125">In the **Configure your new project** dialog,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="31baa-126">Następnie wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="31baa-126">Then choose **Create**.</span></span>

   :::image type="content" source="./media/with-visual-studio/configure-new-project.png" alt-text="Skonfiguruj okno nowego projektu z nazwą projektu, lokalizacją i polami nazw rozwiązań":::

1. <span data-ttu-id="31baa-128">W oknie dialogowym **Informacje dodatkowe** wybierz pozycję **.NET 5,0 (bieżące)**, a następnie wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="31baa-128">In the **Additional information** dialog, select **.NET 5.0 (Current)**, and then select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio/additional-info.png" alt-text="Okno dialogowe informacji dodatkowych":::

<span data-ttu-id="31baa-130">Szablon tworzy prostą aplikację "Hello world".</span><span class="sxs-lookup"><span data-stu-id="31baa-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="31baa-131">Wywołuje metodę, <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> Aby wyświetlić "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="31baa-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="31baa-132">w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="31baa-132">in the console window.</span></span>

<span data-ttu-id="31baa-133">Kod szablonu definiuje klasę, `Program` przy użyciu pojedynczej metody, `Main` która przyjmuje <xref:System.String> tablicę jako argument:</span><span class="sxs-lookup"><span data-stu-id="31baa-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

```csharp
using System;

namespace HelloWorld
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

```vb
Imports System

Module Program
    Sub Main(args As String())
        Console.WriteLine("Hello World!")
    End Sub
End Module
```

<span data-ttu-id="31baa-134">`Main` jest punktem wejścia aplikacji, metoda, która jest wywoływana automatycznie przez środowisko uruchomieniowe podczas uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="31baa-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="31baa-135">Wszystkie argumenty wiersza polecenia dostarczone podczas uruchamiania aplikacji są dostępne w tablicy *args* .</span><span class="sxs-lookup"><span data-stu-id="31baa-135">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="31baa-136">Jeśli język, którego chcesz użyć, nie jest wyświetlany, Zmień selektor języka w górnej części strony.</span><span class="sxs-lookup"><span data-stu-id="31baa-136">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="31baa-137">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="31baa-137">Run the app</span></span>

1. <span data-ttu-id="31baa-138">Naciśnij klawisz <kbd>Ctrl</kbd> + <kbd>F5</kbd> , aby uruchomić program bez debugowania.</span><span class="sxs-lookup"><span data-stu-id="31baa-138">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

   <span data-ttu-id="31baa-139">Zostanie otwarte okno konsoli z tekstem "Hello world!"</span><span class="sxs-lookup"><span data-stu-id="31baa-139">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="31baa-140">Wydrukowano na ekranie.</span><span class="sxs-lookup"><span data-stu-id="31baa-140">printed on the screen.</span></span>

   :::image type="content" source="./media/with-visual-studio/hello-world-console.png" alt-text="Okno konsoli z pokazanymi Hello world naciśnij dowolny klawisz, aby kontynuować":::

1. <span data-ttu-id="31baa-142">Naciśnij dowolny klawisz, aby zamknąć okno konsoli.</span><span class="sxs-lookup"><span data-stu-id="31baa-142">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="31baa-143">Ulepszanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="31baa-143">Enhance the app</span></span>

<span data-ttu-id="31baa-144">Podnieś poziom aplikacji, aby monitować użytkownika o jego nazwę i wyświetlić go wraz z datą i godziną.</span><span class="sxs-lookup"><span data-stu-id="31baa-144">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="31baa-145">W programie *program.cs* lub *program. vb* Zastąp zawartość `Main` metody, która jest wierszem, który wywołuje `Console.WriteLine` , przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="31baa-145">In *Program.cs* or *Program.vb*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   <span data-ttu-id="31baa-146">Ten kod wyświetla monit w oknie konsoli i czeka, aż użytkownik wprowadzi ciąg, a następnie klawisz <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="31baa-146">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="31baa-147">Ten ciąg jest przechowywany w zmiennej o nazwie `name` .</span><span class="sxs-lookup"><span data-stu-id="31baa-147">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="31baa-148">Pobiera również wartość <xref:System.DateTime.Now?displayProperty=nameWithType> właściwości, która zawiera bieżący czas lokalny i przypisuje go do zmiennej o nazwie `date` ( `currentDate` w Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="31baa-148">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="31baa-149">I wyświetla te wartości w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="31baa-149">And it displays these values in the console window.</span></span> <span data-ttu-id="31baa-150">Na koniec wyświetla monit w oknie konsoli i wywołuje <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> metodę, aby czekać na dane wejściowe użytkownika.</span><span class="sxs-lookup"><span data-stu-id="31baa-150">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="31baa-151">`\n`( `vbCrLf` W Visual Basic) reprezentuje znak nowego wiersza.</span><span class="sxs-lookup"><span data-stu-id="31baa-151">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="31baa-152">Znak dolara ( `$` ) przed ciągiem umożliwia umieszczenie wyrażeń takich jak nazwy zmiennych w nawiasach klamrowych w ciągu.</span><span class="sxs-lookup"><span data-stu-id="31baa-152">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="31baa-153">Wartość wyrażenia jest wstawiana do ciągu zamiast wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="31baa-153">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="31baa-154">Ta składnia jest określana mianem [ciągów interpolowanych](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="31baa-154">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="31baa-155">Naciśnij klawisz <kbd>Ctrl</kbd> + <kbd>F5</kbd> , aby uruchomić program bez debugowania.</span><span class="sxs-lookup"><span data-stu-id="31baa-155">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

1. <span data-ttu-id="31baa-156">Odpowiedz na monit, wprowadzając nazwę i naciskając klawisz <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="31baa-156">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="./media/with-visual-studio/hello-world-update.png" alt-text="Okno konsoli ze zmodyfikowanym wyjściem programu":::

1. <span data-ttu-id="31baa-158">Naciśnij dowolny klawisz, aby zamknąć okno konsoli.</span><span class="sxs-lookup"><span data-stu-id="31baa-158">Press any key to close the console window.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31baa-159">Zasoby dodatkowe</span><span class="sxs-lookup"><span data-stu-id="31baa-159">Additional resources</span></span>

- [<span data-ttu-id="31baa-160">Bieżące wersje i wersje długoterminowe pomocy technicznej</span><span class="sxs-lookup"><span data-stu-id="31baa-160">Current releases and long-term support releases</span></span>](../releases-and-support.md#net-core-and-net-5-version-lifecycles)

## <a name="next-steps"></a><span data-ttu-id="31baa-161">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="31baa-161">Next steps</span></span>

<span data-ttu-id="31baa-162">W tym samouczku utworzono aplikację konsolową .NET.</span><span class="sxs-lookup"><span data-stu-id="31baa-162">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="31baa-163">W następnym samouczku debugujesz aplikację.</span><span class="sxs-lookup"><span data-stu-id="31baa-163">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="31baa-164">Debugowanie aplikacji konsolowej .NET przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="31baa-164">Debug a .NET console application using Visual Studio</span></span>](debugging-with-visual-studio.md)
