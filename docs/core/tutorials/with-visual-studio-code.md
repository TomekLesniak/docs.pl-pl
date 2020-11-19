---
title: Tworzenie aplikacji konsolowej .NET przy użyciu Visual Studio Code
description: Dowiedz się, jak utworzyć aplikację konsolową .NET przy użyciu Visual Studio Code i interfejsu wiersza polecenia platformy .NET.
ms.date: 11/17/2020
ms.openlocfilehash: dbbdf88b0c84089249eb7e446c25eddc11543c1a
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915872"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-code"></a><span data-ttu-id="36883-103">Samouczek: Tworzenie aplikacji konsolowej .NET przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="36883-103">Tutorial: Create a .NET console application using Visual Studio Code</span></span>

<span data-ttu-id="36883-104">W tym samouczku pokazano, jak utworzyć i uruchomić aplikację konsolową .NET przy użyciu Visual Studio Code i interfejsu wiersza polecenia platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="36883-104">This tutorial shows how to create and run a .NET console application by using Visual Studio Code and the .NET CLI.</span></span> <span data-ttu-id="36883-105">Zadania projektu, takie jak tworzenie, kompilowanie i uruchamianie projektu, są wykonywane przy użyciu interfejsu wiersza polecenia platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="36883-105">Project tasks, such as creating, compiling, and running a project are done by using the .NET CLI.</span></span> <span data-ttu-id="36883-106">Możesz wykonać czynności opisane w tym samouczku z innym edytorem kodu i uruchamiać polecenia w terminalu, jeśli wolisz.</span><span class="sxs-lookup"><span data-stu-id="36883-106">You can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36883-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="36883-107">Prerequisites</span></span>

1. <span data-ttu-id="36883-108">[Visual Studio Code](https://code.visualstudio.com/) z zainstalowanym [rozszerzeniem języka C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) .</span><span class="sxs-lookup"><span data-stu-id="36883-108">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="36883-109">Aby uzyskać informacje na temat sposobu instalowania rozszerzeń na Visual Studio Code, zobacz [vs Code rozszerzenia Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="36883-109">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="36883-110">[Zestaw .net 5,0 SDK lub nowszy](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="36883-110">The [.NET 5.0 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="36883-111">Tworzenie aplikacji</span><span class="sxs-lookup"><span data-stu-id="36883-111">Create the app</span></span>

<span data-ttu-id="36883-112">Utwórz projekt aplikacji konsolowej platformy .NET o nazwie "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="36883-112">Create a .NET console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="36883-113">Uruchom program Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="36883-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="36883-114">Wybierz pozycję **plik**  >  **Otwórz folder** (Otwórz **plik**  >  **...** na macOS) z menu głównego.</span><span class="sxs-lookup"><span data-stu-id="36883-114">Select **File** > **Open Folder** (**File** > **Open...** on macOS) from the main menu.</span></span>

1. <span data-ttu-id="36883-115">W oknie dialogowym **Otwieranie folderu** Utwórz folder *HelloWorld* i kliknij pozycję **Wybierz folder** (**Otwórz** w macOS).</span><span class="sxs-lookup"><span data-stu-id="36883-115">In the **Open Folder** dialog, create a *HelloWorld* folder and click **Select Folder** (**Open** on macOS).</span></span>

   <span data-ttu-id="36883-116">Nazwa folderu domyślnie zmienia nazwę projektu i nazwę przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="36883-116">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="36883-117">Kod zostanie dodany później w samouczku, który zakłada, że przestrzeń nazw projektu to `HelloWorld` .</span><span class="sxs-lookup"><span data-stu-id="36883-117">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="36883-118">Otwórz **Terminal** w Visual Studio Code, wybierając pozycję **Wyświetl**  >  **Terminal** z menu głównego.</span><span class="sxs-lookup"><span data-stu-id="36883-118">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="36883-119">Zostanie otwarty **Terminal** z wierszem polecenia w folderze *HelloWorld* .</span><span class="sxs-lookup"><span data-stu-id="36883-119">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="36883-120">W **terminalu** wprowadź następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="36883-120">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new console
   ```

<span data-ttu-id="36883-121">Szablon tworzy prostą aplikację "Hello world".</span><span class="sxs-lookup"><span data-stu-id="36883-121">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="36883-122">Wywołuje metodę, <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> Aby wyświetlić " :::no-loc text="Hello World!"::: " w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="36883-122">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display ":::no-loc text="Hello World!":::" in the console window.</span></span>

<span data-ttu-id="36883-123">Kod szablonu definiuje klasę, `Program` przy użyciu pojedynczej metody, `Main` która przyjmuje <xref:System.String> tablicę jako argument:</span><span class="sxs-lookup"><span data-stu-id="36883-123">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="36883-124">`Main` jest punktem wejścia aplikacji, metoda, która jest wywoływana automatycznie przez środowisko uruchomieniowe podczas uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="36883-124">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="36883-125">Wszystkie argumenty wiersza polecenia dostarczone podczas uruchamiania aplikacji są dostępne w tablicy *args* .</span><span class="sxs-lookup"><span data-stu-id="36883-125">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="36883-126">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="36883-126">Run the app</span></span>

<span data-ttu-id="36883-127">Uruchom następujące polecenie w **terminalu**:</span><span class="sxs-lookup"><span data-stu-id="36883-127">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="36883-128">Program wyświetla "Hello world!"</span><span class="sxs-lookup"><span data-stu-id="36883-128">The program displays "Hello World!"</span></span> <span data-ttu-id="36883-129">i zakończenia.</span><span class="sxs-lookup"><span data-stu-id="36883-129">and ends.</span></span>

![Polecenie dotnet Run](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="36883-131">Ulepszanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="36883-131">Enhance the app</span></span>

<span data-ttu-id="36883-132">Podnieś poziom aplikacji, aby monitować użytkownika o jego nazwę i wyświetlić go wraz z datą i godziną.</span><span class="sxs-lookup"><span data-stu-id="36883-132">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="36883-133">Otwórz plik *Program.cs*, klikając go.</span><span class="sxs-lookup"><span data-stu-id="36883-133">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="36883-134">Przy pierwszym otwarciu pliku C# w Visual Studio Code [OmniSharp](https://www.omnisharp.net/) ładuje się w edytorze.</span><span class="sxs-lookup"><span data-stu-id="36883-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Otwórz plik Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="36883-136">Wybierz opcję **tak** , gdy Visual Studio Code zostanie wyświetlony komunikat z prośbą o dodanie brakujących zasobów do kompilowania i debugowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="36883-136">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![Monituj o brakujące zasoby](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="36883-138">Zastąp zawartość `Main` metody w *program.cs*, która jest wierszem, który wywołuje `Console.WriteLine` , przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="36883-138">Replace the contents of the `Main` method in *Program.cs*, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="36883-139">Ten kod wyświetla monit w oknie konsoli i czeka, aż użytkownik wprowadzi ciąg, a następnie klawisz <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="36883-139">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="36883-140">Ten ciąg jest przechowywany w zmiennej o nazwie `name` .</span><span class="sxs-lookup"><span data-stu-id="36883-140">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="36883-141">Pobiera również wartość <xref:System.DateTime.Now?displayProperty=nameWithType> właściwości, która zawiera bieżący czas lokalny i przypisuje go do zmiennej o nazwie `date` .</span><span class="sxs-lookup"><span data-stu-id="36883-141">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="36883-142">I wyświetla te wartości w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="36883-142">And it displays these values in the console window.</span></span> <span data-ttu-id="36883-143">Na koniec wyświetla monit w oknie konsoli i wywołuje <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> metodę, aby czekać na dane wejściowe użytkownika.</span><span class="sxs-lookup"><span data-stu-id="36883-143">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="36883-144">`\n`Reprezentuje znak nowego wiersza.</span><span class="sxs-lookup"><span data-stu-id="36883-144">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="36883-145">Znak dolara ( `$` ) przed ciągiem umożliwia umieszczenie wyrażeń takich jak nazwy zmiennych w nawiasach klamrowych w ciągu.</span><span class="sxs-lookup"><span data-stu-id="36883-145">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="36883-146">Wartość wyrażenia jest wstawiana do ciągu zamiast wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="36883-146">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="36883-147">Ta składnia jest określana mianem [ciągów interpolowanych](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="36883-147">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="36883-148">Zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="36883-148">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="36883-149">W Visual Studio Code należy jawnie zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="36883-149">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="36883-150">W przeciwieństwie do programu Visual Studio zmiany plików nie są automatycznie zapisywane podczas kompilowania i uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="36883-150">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="36883-151">Ponownie uruchom program:</span><span class="sxs-lookup"><span data-stu-id="36883-151">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="36883-152">Odpowiedz na monit, wprowadzając nazwę i naciskając klawisz <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="36883-152">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Okno terminalu ze zmodyfikowanymi danymi wyjściowymi programu":::

1. <span data-ttu-id="36883-154">Naciśnij dowolny klawisz, aby zakończyć program.</span><span class="sxs-lookup"><span data-stu-id="36883-154">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="36883-155">Zasoby dodatkowe</span><span class="sxs-lookup"><span data-stu-id="36883-155">Additional resources</span></span>

- [<span data-ttu-id="36883-156">Konfigurowanie Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="36883-156">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a><span data-ttu-id="36883-157">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="36883-157">Next steps</span></span>

<span data-ttu-id="36883-158">W tym samouczku utworzono aplikację konsolową .NET.</span><span class="sxs-lookup"><span data-stu-id="36883-158">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="36883-159">W następnym samouczku debugujesz aplikację.</span><span class="sxs-lookup"><span data-stu-id="36883-159">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="36883-160">Debugowanie aplikacji konsolowej .NET przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="36883-160">Debug a .NET console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
