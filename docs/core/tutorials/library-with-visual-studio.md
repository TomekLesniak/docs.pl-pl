---
title: Tworzenie biblioteki klas .NET Standard przy użyciu programu Visual Studio
description: Dowiedz się, jak utworzyć .NET Standard bibliotekę klas przy użyciu programu Visual Studio.
ms.date: 08/07/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet,contperfq1
ms.openlocfilehash: 595e93d8d8d22478c6770ddd4f70a0214653f5b9
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2020
ms.locfileid: "88187950"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio"></a><span data-ttu-id="ddac1-103">Samouczek: Tworzenie biblioteki .NET Standard przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ddac1-103">Tutorial: Create a .NET Standard library using Visual Studio</span></span>

<span data-ttu-id="ddac1-104">W tym samouczku utworzysz prostą bibliotekę klas, która zawiera pojedynczą metodę obsługi ciągów.</span><span class="sxs-lookup"><span data-stu-id="ddac1-104">In this tutorial, you create a simple class library that contains a single string-handling method.</span></span>

<span data-ttu-id="ddac1-105">*Biblioteka klas* definiuje typy i metody, które są wywoływane przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="ddac1-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="ddac1-106">Biblioteka klas, która jest przeznaczona dla .NET Standard 2,0 umożliwia wywoływanie biblioteki przez dowolną implementację platformy .NET, która obsługuje tę wersję .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ddac1-106">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span>

<span data-ttu-id="ddac1-107">Po zakończeniu biblioteki klas można ją rozpowszechnić jako pakiet NuGet lub jako składnik powiązany z aplikacją, która go używa.</span><span class="sxs-lookup"><span data-stu-id="ddac1-107">When you finish your class library, you can distribute it as a NuGet package or as a component bundled with the application that uses it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ddac1-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="ddac1-108">Prerequisites</span></span>

- <span data-ttu-id="ddac1-109">[Program Visual Studio 2019 w wersji 16,6 lub nowszej](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) z zainstalowanym **wieloplatformowym obciążeniem programistycznym dla platformy .NET Core** .</span><span class="sxs-lookup"><span data-stu-id="ddac1-109">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="ddac1-110">Zestaw .NET Core 3,1 SDK jest instalowany automatycznie po wybraniu tego obciążenia.</span><span class="sxs-lookup"><span data-stu-id="ddac1-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="ddac1-111">Tworzenie rozwiązania</span><span class="sxs-lookup"><span data-stu-id="ddac1-111">Create a solution</span></span>

<span data-ttu-id="ddac1-112">Zacznij od utworzenia pustego rozwiązania, aby umieścić projekt biblioteki klas w.</span><span class="sxs-lookup"><span data-stu-id="ddac1-112">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="ddac1-113">Rozwiązanie programu Visual Studio służy jako kontener dla jednego lub wielu projektów.</span><span class="sxs-lookup"><span data-stu-id="ddac1-113">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="ddac1-114">Dodasz kolejne powiązane projekty do tego samego rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="ddac1-114">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="ddac1-115">Aby utworzyć puste rozwiązanie:</span><span class="sxs-lookup"><span data-stu-id="ddac1-115">To create the blank solution:</span></span>

1. <span data-ttu-id="ddac1-116">Uruchom program Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ddac1-116">Start Visual Studio.</span></span>

2. <span data-ttu-id="ddac1-117">W oknie uruchamiania wybierz pozycję **Utwórz nowy projekt**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-117">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="ddac1-118">Na stronie **Tworzenie nowego projektu** wprowadź **rozwiązanie** w polu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="ddac1-118">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="ddac1-119">Wybierz szablon **pustego rozwiązania** , a następnie wybierz przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-119">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Pusty szablon rozwiązania w programie Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="ddac1-121">Na stronie **Konfiguruj nowy projekt** wprowadź **ClassLibraryProjects** w polu **Nazwa projektu** .</span><span class="sxs-lookup"><span data-stu-id="ddac1-121">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="ddac1-122">Następnie wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-122">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="ddac1-123">Tworzenie projektu biblioteki klas</span><span class="sxs-lookup"><span data-stu-id="ddac1-123">Create a class library project</span></span>

1. <span data-ttu-id="ddac1-124">Dodaj nowy projekt biblioteki klas .NET Standard o nazwie "StringLibrary" do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="ddac1-124">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="ddac1-125">Kliknij prawym przyciskiem myszy rozwiązanie w **Eksplorator rozwiązań** i wybierz polecenie **Dodaj**  >  **Nowy projekt**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-125">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="ddac1-126">Na stronie **Dodawanie nowego projektu** wprowadź **bibliotekę** w polu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="ddac1-126">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="ddac1-127">Wybierz pozycję **C#** lub **Visual Basic** z listy język, a następnie wybierz pozycję **wszystkie platformy** z listy platform.</span><span class="sxs-lookup"><span data-stu-id="ddac1-127">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="ddac1-128">Wybierz szablon **Biblioteka klas (.NET standard)** , a następnie wybierz przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-128">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="ddac1-129">Na stronie **Konfiguruj nowy projekt** wprowadź **StringLibrary** w polu **Nazwa projektu** .</span><span class="sxs-lookup"><span data-stu-id="ddac1-129">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="ddac1-130">Następnie wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-130">Then, choose **Create**.</span></span>

1. <span data-ttu-id="ddac1-131">Upewnij się, że biblioteka jest ukierunkowana na poprawną wersję .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ddac1-131">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="ddac1-132">Kliknij prawym przyciskiem myszy projekt Biblioteka w **Eksplorator rozwiązań**, a następnie wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-132">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="ddac1-133">Pole tekstowe **platformy docelowej** pokazuje, że projekt jest docelowy .NET Standard 2,0.</span><span class="sxs-lookup"><span data-stu-id="ddac1-133">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Właściwości projektu dla biblioteki klas](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="ddac1-135">Jeśli używasz Visual Basic, wyczyść tekst w polu tekstowym **główna przestrzeń nazw** .</span><span class="sxs-lookup"><span data-stu-id="ddac1-135">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   ![Właściwości projektu dla biblioteki klas](./media/library-with-visual-studio/vb/library-project-properties.png)

   <span data-ttu-id="ddac1-137">Dla każdego projektu Visual Basic automatycznie tworzy przestrzeń nazw, która odnosi się do nazwy projektu.</span><span class="sxs-lookup"><span data-stu-id="ddac1-137">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="ddac1-138">W tym samouczku zdefiniujesz przestrzeń nazw najwyższego poziomu za pomocą [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) słowa kluczowego w pliku kodu.</span><span class="sxs-lookup"><span data-stu-id="ddac1-138">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="ddac1-139">Zastąp kod w oknie kodu dla *Class1.cs*  lub *Class1. vb* następującym kodem i Zapisz plik.</span><span class="sxs-lookup"><span data-stu-id="ddac1-139">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="ddac1-140">Jeśli język, którego chcesz użyć, nie jest wyświetlany, Zmień selektor języka w górnej części strony.</span><span class="sxs-lookup"><span data-stu-id="ddac1-140">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="ddac1-141">Biblioteka klas, `UtilityLibraries.StringLibrary` ,,, zawiera metodę o nazwie `StartsWithUpper` .</span><span class="sxs-lookup"><span data-stu-id="ddac1-141">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="ddac1-142">Ta metoda zwraca <xref:System.Boolean> wartość wskazującą, czy bieżące wystąpienie ciągu zaczyna się od wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="ddac1-142">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="ddac1-143">Standard Unicode rozróżnia wielkie litery od małych liter.</span><span class="sxs-lookup"><span data-stu-id="ddac1-143">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="ddac1-144"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType>Metoda zwraca `true` czy znak jest pisany wielką literą.</span><span class="sxs-lookup"><span data-stu-id="ddac1-144">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

   <span data-ttu-id="ddac1-145">`StartsWithUpper` jest zaimplementowany jako [Metoda rozszerzająca](../../csharp/programming-guide/classes-and-structs/extension-methods.md) , aby można było wywołać ją tak, jakby była elementem członkowskim <xref:System.String> klasy.</span><span class="sxs-lookup"><span data-stu-id="ddac1-145">`StartsWithUpper` is implemented as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

1. <span data-ttu-id="ddac1-146">Na pasku menu wybierz opcję **Kompiluj**  >  **rozwiązanie kompilacji** , aby sprawdzić, czy projekt kompiluje się bez błędu.</span><span class="sxs-lookup"><span data-stu-id="ddac1-146">On the menu bar, select **Build** > **Build Solution** to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="ddac1-147">Dodawanie aplikacji konsolowej do rozwiązania</span><span class="sxs-lookup"><span data-stu-id="ddac1-147">Add a console app to the solution</span></span>

<span data-ttu-id="ddac1-148">Dodaj aplikację konsolową, która używa biblioteki klas.</span><span class="sxs-lookup"><span data-stu-id="ddac1-148">Add a console application that uses the class library.</span></span> <span data-ttu-id="ddac1-149">Aplikacja wyświetli monit o wprowadzenie ciągu i zgłoszenie, czy ciąg rozpoczyna się od wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="ddac1-149">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="ddac1-150">Dodaj nową aplikację konsolową .NET Core do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="ddac1-150">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="ddac1-151">Kliknij prawym przyciskiem myszy rozwiązanie w **Eksplorator rozwiązań** i wybierz polecenie **Dodaj**  >  **Nowy projekt**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-151">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="ddac1-152">Na stronie **Dodawanie nowego projektu** wprowadź w polu wyszukiwania **konsolę** .</span><span class="sxs-lookup"><span data-stu-id="ddac1-152">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="ddac1-153">Wybierz pozycję **C#** lub **Visual Basic** z listy język, a następnie wybierz pozycję **wszystkie platformy** z listy platform.</span><span class="sxs-lookup"><span data-stu-id="ddac1-153">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="ddac1-154">Wybierz szablon **Aplikacja konsolowa (.NET Core)** , a następnie wybierz przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-154">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="ddac1-155">Na stronie **Konfiguruj nowy projekt** wprowadź wartość **Prezentacja** w polu **Nazwa projektu** .</span><span class="sxs-lookup"><span data-stu-id="ddac1-155">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="ddac1-156">Następnie wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-156">Then choose **Create**.</span></span>

1. <span data-ttu-id="ddac1-157">W oknie kodu dla pliku *program.cs* lub *program. vb* Zastąp cały kod następującym kodem.</span><span class="sxs-lookup"><span data-stu-id="ddac1-157">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="ddac1-158">Kod używa `row` zmiennej do obsługi liczby wierszy danych zapisywana w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="ddac1-158">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="ddac1-159">Za każdym razem, gdy jest większy lub równy 25, kod czyści okno konsoli i wyświetla komunikat dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ddac1-159">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="ddac1-160">Program poprosi użytkownika o wprowadzenie ciągu.</span><span class="sxs-lookup"><span data-stu-id="ddac1-160">The program prompts the user to enter a string.</span></span> <span data-ttu-id="ddac1-161">Wskazuje, czy ciąg rozpoczyna się od wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="ddac1-161">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="ddac1-162">Jeśli użytkownik naciśnie klawisz <kbd>Enter</kbd> bez wprowadzania ciągu, aplikacja zostanie zakończona, a okno konsoli zostanie zamknięte.</span><span class="sxs-lookup"><span data-stu-id="ddac1-162">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="ddac1-163">Dodaj odwołanie do projektu</span><span class="sxs-lookup"><span data-stu-id="ddac1-163">Add a project reference</span></span>

<span data-ttu-id="ddac1-164">Początkowo nowy projekt aplikacji konsolowej nie ma dostępu do biblioteki klas.</span><span class="sxs-lookup"><span data-stu-id="ddac1-164">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="ddac1-165">Aby zezwolić na wywoływanie metod w bibliotece klas, Utwórz odwołanie do projektu do projektu biblioteki klas.</span><span class="sxs-lookup"><span data-stu-id="ddac1-165">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="ddac1-166">W **Eksplorator rozwiązań**kliknij prawym przyciskiem myszy `ShowCase` węzeł **zależności** projektu i wybierz polecenie **Dodaj odwołanie do projektu**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-166">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   ![Dodaj menu kontekstowe odwołania w programie Visual Studio](media/library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="ddac1-168">W oknie dialogowym **Menedżer odwołań** wybierz projekt **StringLibrary** , a następnie wybierz **przycisk OK**.</span><span class="sxs-lookup"><span data-stu-id="ddac1-168">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   ![Okno dialogowe programu Reference Manager z wybraną pozycją StringLibrary](media/library-with-visual-studio/manage-project-references.png)

## <a name="run-the-app"></a><span data-ttu-id="ddac1-170">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="ddac1-170">Run the app</span></span>

1. <span data-ttu-id="ddac1-171">W **Eksplorator rozwiązań**kliknij prawym przyciskiem myszy projekt **pokazu** i wybierz polecenie **Ustaw jako projekt startowy** w menu kontekstowym.</span><span class="sxs-lookup"><span data-stu-id="ddac1-171">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Menu kontekstowe projektu programu Visual Studio, aby ustawić projekt startowy](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="ddac1-173">Naciśnij klawisz <kbd>Ctrl</kbd> + <kbd>F5</kbd> , aby skompilować i uruchomić program bez debugowania.</span><span class="sxs-lookup"><span data-stu-id="ddac1-173">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to compile and run the program without debugging.</span></span>

   ![Pasek narzędzi projektu programu Visual Studio z widocznym przyciskiem Debuguj](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. <span data-ttu-id="ddac1-175">Wypróbuj program, wprowadzając ciągi i naciskając klawisz <kbd>Enter</kbd>, a następnie naciśnij klawisz <kbd>Enter</kbd> , aby wyjść.</span><span class="sxs-lookup"><span data-stu-id="ddac1-175">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Okno konsoli z uruchomionym pokazem":::

## <a name="additional-resources"></a><span data-ttu-id="ddac1-177">Zasoby dodatkowe</span><span class="sxs-lookup"><span data-stu-id="ddac1-177">Additional resources</span></span>

* [<span data-ttu-id="ddac1-178">Tworzenie bibliotek przy użyciu interfejs wiersza polecenia platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="ddac1-178">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="ddac1-179">[Wersje .NET Standard i obsługiwane przez nich platformy](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="ddac1-179">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ddac1-180">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="ddac1-180">Next steps</span></span>

<span data-ttu-id="ddac1-181">W tym samouczku utworzono bibliotekę klas.</span><span class="sxs-lookup"><span data-stu-id="ddac1-181">In this tutorial, you created a class library.</span></span> <span data-ttu-id="ddac1-182">W następnym samouczku dowiesz się, jak jednostkowo testować bibliotekę klas.</span><span class="sxs-lookup"><span data-stu-id="ddac1-182">In the next tutorial, you learn how to unit test the class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ddac1-183">Testowanie jednostkowe biblioteki .NET Standard przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ddac1-183">Unit test a .NET Standard library using Visual Studio</span></span>](testing-library-with-visual-studio.md)

<span data-ttu-id="ddac1-184">Możesz też pominąć zautomatyzowane testowanie jednostkowe i dowiedzieć się, jak udostępnić bibliotekę, tworząc pakiet NuGet:</span><span class="sxs-lookup"><span data-stu-id="ddac1-184">Or you can skip automated unit testing and learn how to share the library by creating a NuGet package:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ddac1-185">Tworzenie i publikowanie pakietu przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ddac1-185">Create and publish a package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio)

<span data-ttu-id="ddac1-186">Lub Dowiedz się, jak opublikować aplikację konsolową.</span><span class="sxs-lookup"><span data-stu-id="ddac1-186">Or learn how to publish a console app.</span></span> <span data-ttu-id="ddac1-187">Jeśli opublikujesz aplikację konsolową z rozwiązania utworzonego w tym samouczku, Biblioteka klas przejdzie z nim jako plik *. dll* .</span><span class="sxs-lookup"><span data-stu-id="ddac1-187">If you publish the console app from the solution you created in this tutorial, the class library goes with it as a *.dll* file.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ddac1-188">Publikowanie aplikacji konsolowej .NET Core przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ddac1-188">Publish a .NET Core console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
