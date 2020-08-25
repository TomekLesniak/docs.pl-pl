---
title: Tworzenie aplikacji konsolowej platformy .NET Core przy użyciu Visual Studio dla komputerów Mac
description: Dowiedz się, jak utworzyć aplikację konsolową .NET Core przy użyciu Visual Studio dla komputerów Mac.
ms.date: 06/02/2020
ms.openlocfilehash: e0b18837bf8bef5be5f20b84341bde8526b9f7a2
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811876"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="4e382-103">Samouczek: Tworzenie aplikacji konsolowej platformy .NET Core przy użyciu Visual Studio dla komputerów Mac</span><span class="sxs-lookup"><span data-stu-id="4e382-103">Tutorial: Create a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="4e382-104">W tym samouczku pokazano, jak utworzyć i uruchomić aplikację konsolową .NET Core przy użyciu Visual Studio dla komputerów Mac.</span><span class="sxs-lookup"><span data-stu-id="4e382-104">This tutorial shows how to create and run a .NET Core console application using Visual Studio for Mac.</span></span>

> [!NOTE]
> <span data-ttu-id="4e382-105">Opinie są wysoce wyceniane.</span><span class="sxs-lookup"><span data-stu-id="4e382-105">Your feedback is highly valued.</span></span> <span data-ttu-id="4e382-106">Istnieją dwa sposoby przekazywania opinii zespołowi programistycznemu na Visual Studio dla komputerów Mac:</span><span class="sxs-lookup"><span data-stu-id="4e382-106">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="4e382-107">W Visual Studio dla komputerów Mac wybierz pozycję **Pomoc**  >  **Zgłoś problem** z menu lub **Zgłoś problem** na ekranie powitalnym, co spowoduje otwarcie okna do zgłoszenia usterki.</span><span class="sxs-lookup"><span data-stu-id="4e382-107">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="4e382-108">Swoje opinie możesz śledzić w portalu [Społeczność deweloperów](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="4e382-108">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="4e382-109">Aby skorzystać z sugestii, wybierz pozycję **Pomoc**  >  **Podaj sugestię** z menu lub **Podaj sugestię** na ekranie powitalnym, co spowoduje przejście do [strony internetowej społeczność deweloperów Visual Studio dla komputerów Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="4e382-109">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4e382-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4e382-110">Prerequisites</span></span>

* <span data-ttu-id="4e382-111">[Visual Studio dla komputerów Mac w wersji 8,6 lub nowszej](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="4e382-111">[Visual Studio for Mac version 8.6 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="4e382-112">Wybierz opcję zainstalowania platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e382-112">Select the option to install .NET Core.</span></span> <span data-ttu-id="4e382-113">Instalowanie platformy Xamarin jest opcjonalne w przypadku programowania .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e382-113">Installing Xamarin is optional for .NET Core development.</span></span> <span data-ttu-id="4e382-114">Więcej informacji można znaleźć w następujących zasobach:</span><span class="sxs-lookup"><span data-stu-id="4e382-114">For more information, see the following resources:</span></span>

  * <span data-ttu-id="4e382-115">[Samouczek: instalowanie Visual Studio dla komputerów Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="4e382-115">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="4e382-116">[Obsługiwane wersje macOS](../install/dependencies.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="4e382-116">[Supported macOS versions](../install/dependencies.md?pivots=os-macos).</span></span>
  * <span data-ttu-id="4e382-117">[Wersje programu .NET Core obsługiwane przez Visual Studio dla komputerów Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="4e382-117">[.NET Core versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="4e382-118">Tworzenie aplikacji</span><span class="sxs-lookup"><span data-stu-id="4e382-118">Create the app</span></span>

<span data-ttu-id="4e382-119">Utwórz projekt aplikacji konsolowej .NET Core o nazwie "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="4e382-119">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="4e382-120">Rozpocznij Visual Studio dla komputerów Mac.</span><span class="sxs-lookup"><span data-stu-id="4e382-120">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="4e382-121">W oknie uruchamiania wybierz pozycję **Nowy** .</span><span class="sxs-lookup"><span data-stu-id="4e382-121">Select **New** in the start window.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Przycisk Nowy na ekranie startowym Visual Studio dla komputerów Mac":::

1. <span data-ttu-id="4e382-123">W oknie dialogowym **Nowy projekt** wybierz pozycję **aplikacja** w węźle **Sieć Web i konsola** .</span><span class="sxs-lookup"><span data-stu-id="4e382-123">In the **New Project** dialog, select **App** under the **Web and Console** node.</span></span> <span data-ttu-id="4e382-124">Wybierz szablon **aplikacja konsoli** , a następnie wybierz przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="4e382-124">Select the **Console Application** template, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Lista nowych szablonów projektu":::

1. <span data-ttu-id="4e382-126">Na liście rozwijanej **platforma docelowa** okna dialogowego **Konfigurowanie nowej aplikacji konsoli** wybierz pozycję **.NET Core 3,1**, a następnie wybierz przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="4e382-126">In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET Core 3.1**, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/target-framework.png" alt-text="Wybierz platformę docelową":::

1. <span data-ttu-id="4e382-128">Wpisz "HelloWorld" jako **nazwę projektu**, a następnie wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="4e382-128">Type "HelloWorld" for the **Project Name**, and select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Okno dialogowe Konfigurowanie nowej aplikacji konsolowej":::

<span data-ttu-id="4e382-130">Szablon tworzy prostą aplikację "Hello world".</span><span class="sxs-lookup"><span data-stu-id="4e382-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="4e382-131">Wywołuje metodę, <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> Aby wyświetlić "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="4e382-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="4e382-132">w oknie terminalu.</span><span class="sxs-lookup"><span data-stu-id="4e382-132">in the terminal window.</span></span>

<span data-ttu-id="4e382-133">Kod szablonu definiuje klasę, `Program` przy użyciu pojedynczej metody, `Main` która przyjmuje <xref:System.String> tablicę jako argument:</span><span class="sxs-lookup"><span data-stu-id="4e382-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="4e382-134">`Main` jest punktem wejścia aplikacji, metoda, która jest wywoływana automatycznie przez środowisko uruchomieniowe podczas uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="4e382-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="4e382-135">Wszystkie argumenty wiersza polecenia dostarczone podczas uruchamiania aplikacji są dostępne w `args` tablicy.</span><span class="sxs-lookup"><span data-stu-id="4e382-135">Any command-line arguments supplied when the application is launched are available in the `args` array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="4e382-136">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="4e382-136">Run the app</span></span>

1. <span data-ttu-id="4e382-137">Naciśnij pozycję <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Enter</kbd>), aby uruchomić aplikację bez debugowania.</span><span class="sxs-lookup"><span data-stu-id="4e382-137">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="Terminal zawiera Hello world!":::

1. <span data-ttu-id="4e382-139">Zamknij okno **terminalu** .</span><span class="sxs-lookup"><span data-stu-id="4e382-139">Close the **Terminal** window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="4e382-140">Ulepszanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="4e382-140">Enhance the app</span></span>

<span data-ttu-id="4e382-141">Podnieś poziom aplikacji, aby monitować użytkownika o jego nazwę i wyświetlić go wraz z datą i godziną.</span><span class="sxs-lookup"><span data-stu-id="4e382-141">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="4e382-142">W *program.cs*Zastąp zawartość `Main` metody, która jest wierszem, który wywołuje `Console.WriteLine` , przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="4e382-142">In *Program.cs*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="4e382-143">Ten kod wyświetla monit w oknie konsoli i czeka, aż użytkownik wprowadzi ciąg, a następnie klawisz <kbd>Enter</kbd> .</span><span class="sxs-lookup"><span data-stu-id="4e382-143">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key.</span></span> <span data-ttu-id="4e382-144">Ten ciąg jest przechowywany w zmiennej o nazwie `name` .</span><span class="sxs-lookup"><span data-stu-id="4e382-144">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="4e382-145">Pobiera również wartość <xref:System.DateTime.Now?displayProperty=nameWithType> właściwości, która zawiera bieżący czas lokalny i przypisuje go do zmiennej o nazwie `date` .</span><span class="sxs-lookup"><span data-stu-id="4e382-145">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="4e382-146">I wyświetla te wartości w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="4e382-146">And it displays these values in the console window.</span></span> <span data-ttu-id="4e382-147">Na koniec wyświetla monit w oknie konsoli i wywołuje <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> metodę, aby czekać na dane wejściowe użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4e382-147">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="4e382-148">`\n`Reprezentuje znak nowego wiersza.</span><span class="sxs-lookup"><span data-stu-id="4e382-148">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="4e382-149">Znak dolara ( `$` ) przed ciągiem umożliwia umieszczenie wyrażeń takich jak nazwy zmiennych w nawiasach klamrowych w ciągu.</span><span class="sxs-lookup"><span data-stu-id="4e382-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="4e382-150">Wartość wyrażenia jest wstawiana do ciągu zamiast wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="4e382-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="4e382-151">Ta składnia jest określana mianem [ciągów interpolowanych](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="4e382-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="4e382-152">Naciśnij pozycję <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Enter</kbd>), aby uruchomić aplikację.</span><span class="sxs-lookup"><span data-stu-id="4e382-152">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.</span></span>

1. <span data-ttu-id="4e382-153">Odpowiedz na monit, wprowadzając nazwę i naciskając klawisz <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4e382-153">Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Terminal pokazuje zmodyfikowane dane wyjściowe programu":::

1. <span data-ttu-id="4e382-155">Zamknij Terminal.</span><span class="sxs-lookup"><span data-stu-id="4e382-155">Close the terminal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e382-156">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="4e382-156">Next steps</span></span>

<span data-ttu-id="4e382-157">W tym samouczku utworzono aplikację konsolową .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e382-157">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="4e382-158">W następnym samouczku debugujesz aplikację.</span><span class="sxs-lookup"><span data-stu-id="4e382-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4e382-159">Debugowanie aplikacji konsolowej .NET Core w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4e382-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio-mac.md)
