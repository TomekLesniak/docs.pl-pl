---
title: Testowanie biblioteki klas .NET przy użyciu programu Visual Studio
description: Dowiedz się, jak utworzyć i uruchomić projekt testu jednostkowego dla biblioteki klas .NET przy użyciu programu Visual Studio.
ms.date: 11/18/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 3d56627b937fa0ad5f8002f396ce617e09ce9d2c
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916129"
---
# <a name="tutorial-test-a-net-class-library-with-net-using-visual-studio"></a><span data-ttu-id="3eb3c-103">Samouczek: testowanie biblioteki klas .NET w programie .NET przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3eb3c-103">Tutorial: Test a .NET class library with .NET using Visual Studio</span></span>

<span data-ttu-id="3eb3c-104">W tym samouczku pokazano, jak zautomatyzować testy jednostkowe przez dodanie projektu testowego do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-104">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3eb3c-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="3eb3c-105">Prerequisites</span></span>

- <span data-ttu-id="3eb3c-106">Ten samouczek współdziała z rozwiązaniem tworzonym w temacie [Tworzenie biblioteki klas platformy .NET przy użyciu programu Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="3eb3c-106">This tutorial works with the solution that you create in [Create a .NET class library using Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="3eb3c-107">Tworzenie projektu testu jednostkowego</span><span class="sxs-lookup"><span data-stu-id="3eb3c-107">Create a unit test project</span></span>

<span data-ttu-id="3eb3c-108">Testy jednostkowe zapewniają zautomatyzowane testowanie oprogramowania podczas opracowywania i publikowania.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-108">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="3eb3c-109">[MSTest](https://github.com/Microsoft/testfx-docs) jest jednym z trzech platform testowych, spośród których można dokonać wyboru.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-109">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="3eb3c-110">Inne to [xUnit](https://xunit.net/) i [nunit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="3eb3c-110">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="3eb3c-111">Uruchom program Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-111">Start Visual Studio.</span></span>

1. <span data-ttu-id="3eb3c-112">Otwórz `ClassLibraryProjects` rozwiązanie utworzone w temacie [Tworzenie biblioteki klas .NET przy użyciu programu Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="3eb3c-112">Open the `ClassLibraryProjects` solution you created in [Create a .NET class library using Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="3eb3c-113">Dodaj nowy projekt testu jednostkowego o nazwie "StringLibraryTest" do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-113">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="3eb3c-114">Kliknij prawym przyciskiem myszy rozwiązanie w **Eksplorator rozwiązań** i wybierz polecenie **Dodaj**  >  **Nowy projekt**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-114">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="3eb3c-115">Na stronie **Dodawanie nowego projektu** wprowadź **MSTest** w polu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-115">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="3eb3c-116">Wybierz pozycję **C#** lub **Visual Basic** z listy język, a następnie wybierz pozycję **wszystkie platformy** z listy platform.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-116">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="3eb3c-117">Wybierz szablon **projektu test jednostkowy** , a następnie wybierz przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-117">Choose the **Unit Test Project** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="3eb3c-118">Na stronie **Konfiguruj nowy projekt** wprowadź **StringLibraryTest** w polu **Nazwa projektu** .</span><span class="sxs-lookup"><span data-stu-id="3eb3c-118">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="3eb3c-119">Następnie wybierz przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-119">Then choose **Next**.</span></span>

   1. <span data-ttu-id="3eb3c-120">Na stronie **Informacje dodatkowe** wybierz pozycję **.NET 5,0 (Current)** w polu **platforma docelowa** .</span><span class="sxs-lookup"><span data-stu-id="3eb3c-120">On the **Additional information** page, select **.NET 5.0 (Current)** in the **Target Framework** box.</span></span> <span data-ttu-id="3eb3c-121">Następnie wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-121">Then choose **Create**.</span></span>

1. <span data-ttu-id="3eb3c-122">Program Visual Studio tworzy projekt i otwiera plik klasy w oknie kodu przy użyciu następującego kodu.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-122">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="3eb3c-123">Jeśli język, którego chcesz użyć, nie jest wyświetlany, Zmień selektor języka w górnej części strony.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-123">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

   namespace StringLibraryTest
   {
       [TestClass]
       public class UnitTest1
       {
           [TestMethod]
           public void TestMethod1()
           {
           }
       }
   }
   ```

   ```vb
   Imports Microsoft.VisualStudio.TestTools.UnitTesting

   Namespace StringLibraryTest
       <TestClass>
       Public Class UnitTest1
           <TestMethod>
           Sub TestSub()

           End Sub
       End Class
   End Namespace
   ```

   <span data-ttu-id="3eb3c-124">Kod źródłowy utworzony przez szablon testu jednostkowego wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="3eb3c-124">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="3eb3c-125">Importuje <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> przestrzeń nazw, która zawiera typy używane do testowania jednostkowego.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-125">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="3eb3c-126">Stosuje <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> atrybut do `UnitTest1` klasy.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-126">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="3eb3c-127">Stosuje <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> atrybut do definiowania `TestMethod1` w języku C# lub `TestSub` w Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-127">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="3eb3c-128">Każda metoda oznaczona przy użyciu elementu [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) w klasie testowej oznaczona przy użyciu elementu [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) jest wykonywana automatycznie, gdy test jednostkowy jest uruchamiany.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-128">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="3eb3c-129">Dodaj odwołanie do projektu</span><span class="sxs-lookup"><span data-stu-id="3eb3c-129">Add a project reference</span></span>

<span data-ttu-id="3eb3c-130">Aby projekt testowy mógł współpracował z `StringLibrary` klasą, Dodaj odwołanie w projekcie **StringLibraryTest** do `StringLibrary` projektu.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-130">For the test project to work with the `StringLibrary` class, add a reference in the **StringLibraryTest** project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="3eb3c-131">W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy węzeł **zależności** projektu **StringLibraryTest** i wybierz polecenie **Dodaj odwołanie do projektu** z menu kontekstowego.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-131">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="3eb3c-132">W oknie dialogowym **Menedżer odwołań** rozwiń węzeł **projekty** , a następnie zaznacz pole wyboru obok pozycji **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-132">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="3eb3c-133">Dodanie odwołania do `StringLibrary` zestawu umożliwia kompilatorowi znalezienie metod **StringLibrary** podczas kompilowania projektu **StringLibraryTest** .</span><span class="sxs-lookup"><span data-stu-id="3eb3c-133">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="3eb3c-134">Wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-134">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="3eb3c-135">Dodawanie i uruchamianie metod testów jednostkowych</span><span class="sxs-lookup"><span data-stu-id="3eb3c-135">Add and run unit test methods</span></span>

<span data-ttu-id="3eb3c-136">Gdy program Visual Studio uruchamia test jednostkowy, wykonuje każdą metodę, która jest oznaczona <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> atrybutem w klasie, która jest oznaczona  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> atrybutem.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-136">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="3eb3c-137">Metoda testowa kończy się po znalezieniu pierwszego błędu lub gdy wszystkie testy zawarte w metodzie zakończyły się powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-137">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="3eb3c-138">Najczęstsze testy wywołują elementy członkowskie <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> klasy.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-138">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="3eb3c-139">Wiele metod Assert obejmuje co najmniej dwa parametry, z których jeden jest oczekiwany wynik testu, a drugi jest rzeczywistym wynikiem testu.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-139">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="3eb3c-140">`Assert`W poniższej tabeli przedstawiono niektóre z najczęściej wywoływanych metod:</span><span class="sxs-lookup"><span data-stu-id="3eb3c-140">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="3eb3c-141">Metody Assert</span><span class="sxs-lookup"><span data-stu-id="3eb3c-141">Assert methods</span></span>     | <span data-ttu-id="3eb3c-142">Funkcja</span><span class="sxs-lookup"><span data-stu-id="3eb3c-142">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="3eb3c-143">Sprawdza, czy dwie wartości lub obiekty są równe.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-143">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="3eb3c-144">Potwierdzenie kończy się niepowodzeniem, jeśli wartości lub obiekty nie są równe.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-144">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="3eb3c-145">Sprawdza, czy dwie zmienne obiektów odwołują się do tego samego obiektu.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-145">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="3eb3c-146">Potwierdzenie kończy się niepowodzeniem, jeśli zmienne odwołują się do różnych obiektów.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-146">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="3eb3c-147">Sprawdza, czy warunek to `false` .</span><span class="sxs-lookup"><span data-stu-id="3eb3c-147">Verifies that a condition is `false`.</span></span> <span data-ttu-id="3eb3c-148">Potwierdzenie kończy się niepowodzeniem, jeśli warunek ma wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="3eb3c-148">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="3eb3c-149">Sprawdza, czy obiekt nie jest `null` .</span><span class="sxs-lookup"><span data-stu-id="3eb3c-149">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="3eb3c-150">Potwierdzenie kończy się niepowodzeniem, jeśli obiekt jest `null` .</span><span class="sxs-lookup"><span data-stu-id="3eb3c-150">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="3eb3c-151">Można również użyć <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metody w metodzie testowej, aby wskazać typ wyjątku, który ma zostać zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-151">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="3eb3c-152">Test zakończy się niepowodzeniem, jeśli określony wyjątek nie zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-152">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="3eb3c-153">W testowaniu `StringLibrary.StartsWithUpper` metody, należy podać kilka ciągów zaczynających się od wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-153">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="3eb3c-154">Oczekiwano, że metoda zwraca `true` w tych przypadkach, więc można wywołać <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-154">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3eb3c-155">Podobnie, chcesz podać kilka ciągów, które zaczynają się od znaku innego niż wielkie litery.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-155">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="3eb3c-156">Oczekiwano, że metoda zwraca `false` w tych przypadkach, więc można wywołać <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-156">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="3eb3c-157">Ponieważ metoda biblioteki obsługuje ciągi, należy również upewnić się, że pomyślnie obsługuje [pusty ciąg ( `String.Empty` )](xref:System.String.Empty), prawidłowy ciąg, który nie zawiera znaków i <xref:System.String.Length> ma wartość 0, i `null` ciąg, który nie został zainicjowany.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-157">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="3eb3c-158">Można wywołać `StartsWithUpper` bezpośrednio jako metodę statyczną i przekazać pojedynczy <xref:System.String> argument.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-158">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="3eb3c-159">Lub można wywołać `StartsWithUpper` jako metodę rozszerzającą dla `string` zmiennej przypisanej do `null` .</span><span class="sxs-lookup"><span data-stu-id="3eb3c-159">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="3eb3c-160">Zdefiniujesz trzy metody, z których każda wywołuje <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> metodę dla każdego elementu w tablicy ciągów.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-160">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="3eb3c-161">Wywołasz Przeciążenie metody, które pozwala określić komunikat o błędzie, który ma być wyświetlany w przypadku niepowodzenia testu.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-161">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="3eb3c-162">Komunikat identyfikuje ciąg, który spowodował awarię.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-162">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="3eb3c-163">Aby utworzyć metody testowe:</span><span class="sxs-lookup"><span data-stu-id="3eb3c-163">To create the test methods:</span></span>

1. <span data-ttu-id="3eb3c-164">W oknie kod *UnitTest1.cs* lub *UnitTest1. vb* Zastąp kod następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="3eb3c-164">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   <span data-ttu-id="3eb3c-165">Test wielkich liter w `TestStartsWithUpper` metodzie zawiera alfabet grecki (u + 0391) oraz wielką literę pauzy (u + 041C).</span><span class="sxs-lookup"><span data-stu-id="3eb3c-165">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="3eb3c-166">Test małymi literami w `TestDoesNotStartWithUpper` metodzie obejmuje małą literę alfa (u + 03B1) i małą literę cyrylicy GHE (u + 0433).</span><span class="sxs-lookup"><span data-stu-id="3eb3c-166">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="3eb3c-167">Na pasku menu wybierz pozycję **plik**  >  **Zapisz UnitTest1.cs jako** lub Zapisz **plik**  >  **UnitTest1. vb jako**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-167">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="3eb3c-168">W oknie dialogowym **Zapisz plik jako** wybierz strzałkę obok przycisku **Zapisz** , a następnie wybierz pozycję **Zapisz z kodowaniem**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-168">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/save-file-as-dialog.png" alt-text="Okno dialogowe zapisywania pliku w programie Visual Studio":::

1. <span data-ttu-id="3eb3c-170">W oknie dialogowym **Potwierdzanie zapisywania jako** wybierz przycisk **tak** , aby zapisać plik.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-170">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="3eb3c-171">W oknie dialogowym **Zaawansowane opcje zapisywania** wybierz pozycję **Unicode (UTF-8 z podpisem)-strona kodowa 65001** z listy rozwijanej **kodowanie** i wybierz **przycisk OK**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-171">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/advanced-save-options.png" alt-text="Zaawansowane opcje zapisywania programu Visual Studio — okno dialogowe":::

   <span data-ttu-id="3eb3c-173">Jeśli kod źródłowy nie zostanie zapisany jako plik zakodowany w formacie UTF8, program Visual Studio może go zapisać jako plik ASCII.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-173">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="3eb3c-174">Gdy tak się stanie, środowisko uruchomieniowe nie dekoduje znaków UTF8 poza zakresem ASCII, a wyniki testu nie będą poprawne.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-174">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="3eb3c-175">Na pasku menu wybierz kolejno opcje **test**  >  **Uruchom wszystkie testy**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-175">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="3eb3c-176">Jeśli okno **Eksplorator testów** nie jest otwarte, otwórz je, wybierając **Testuj**  >  **Eksploratora testów**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-176">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="3eb3c-177">Trzy testy są wymienione w sekcji **testy zakończone** , a sekcja **podsumowania** raportuje wynik przebiegu testu.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-177">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/test-explorer-window.png" alt-text="Okno Eksploratora testów z przekazaniem testów":::

## <a name="handle-test-failures"></a><span data-ttu-id="3eb3c-179">Obsługa niepowodzeń testów</span><span class="sxs-lookup"><span data-stu-id="3eb3c-179">Handle test failures</span></span>

<span data-ttu-id="3eb3c-180">Jeśli wykonujesz programowanie sterowane testami (TDD), najpierw napiszesz testy i nie powiodą się po raz pierwszy.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-180">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="3eb3c-181">Następnie dodasz kod do aplikacji, która pomyślnie testuje.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-181">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="3eb3c-182">Na potrzeby tego samouczka utworzono test po zapisaniu kodu aplikacji, który jest weryfikowany, więc niepowodzenie testu nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-182">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="3eb3c-183">Aby sprawdzić, czy test zakończy się niepowodzeniem, gdy spodziewasz się niepowodzeniem, Dodaj nieprawidłową wartość do danych wejściowych testu.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-183">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="3eb3c-184">Zmodyfikuj `words` tablicę w `TestDoesNotStartWithUpper` metodzie, aby uwzględnić ciąg "Error".</span><span class="sxs-lookup"><span data-stu-id="3eb3c-184">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="3eb3c-185">Nie musisz zapisywać pliku, ponieważ program Visual Studio automatycznie zapisuje otwarte pliki w przypadku skompilowania rozwiązania do uruchamiania testów.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-185">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="3eb3c-186">Uruchom test, wybierając pozycję **test**  >  **Uruchom wszystkie testy** z paska menu.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-186">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="3eb3c-187">Okno **Eksplorator testów** wskazuje, że dwa testy zostały wykonane pomyślnie i jeden z nich zakończył się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-187">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/failed-test-window.png" alt-text="Okno Eksploratora testów z niepowodzeniem testami":::

1. <span data-ttu-id="3eb3c-189">Wybierz test zakończony niepowodzeniem `TestDoesNotStartWith` .</span><span class="sxs-lookup"><span data-stu-id="3eb3c-189">Select the failed test, `TestDoesNotStartWith`.</span></span>

   <span data-ttu-id="3eb3c-190">W oknie **Eksplorator testów** zostanie wyświetlony komunikat utworzony przez potwierdzenie: "Assert. IsFalse nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-190">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="3eb3c-191">Oczekiwano dla elementu "Error": false; rzeczywista: true ".</span><span class="sxs-lookup"><span data-stu-id="3eb3c-191">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="3eb3c-192">Z powodu błędu nie przetestowano ciągów w tablicy po "błędzie".</span><span class="sxs-lookup"><span data-stu-id="3eb3c-192">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/failed-test-detail.png" alt-text="Okno Eksploratora testów przedstawiające błąd potwierdzenia IsFalse":::

1. <span data-ttu-id="3eb3c-194">Usuń ciąg "Error", który został dodany w kroku 1.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-194">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="3eb3c-195">Uruchom ponownie test i testy zakończone powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-195">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="3eb3c-196">Testowanie wersji wydania biblioteki</span><span class="sxs-lookup"><span data-stu-id="3eb3c-196">Test the Release version of the library</span></span>

<span data-ttu-id="3eb3c-197">Teraz, gdy testy zostały zakończone przed uruchomieniem kompilacji biblioteki, należy uruchomić testy w dodatkowym czasie względem kompilacji wydania biblioteki.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-197">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="3eb3c-198">Wiele czynników, w tym Optymalizacja kompilatora, może czasami generować różne zachowanie między kompilacjami w wersji Debug i Release.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-198">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="3eb3c-199">Aby przetestować kompilację wydania:</span><span class="sxs-lookup"><span data-stu-id="3eb3c-199">To test the Release build:</span></span>

1. <span data-ttu-id="3eb3c-200">Na pasku narzędzi programu Visual Studio Zmień konfigurację kompilacji z **Debuguj** do **Release**.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-200">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Pasek narzędzi programu Visual Studio z wyróżnioną kompilacją wydania":::

1. <span data-ttu-id="3eb3c-202">W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt **StringLibrary** i wybierz polecenie **Kompiluj** z menu kontekstowego, aby ponownie skompilować bibliotekę.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-202">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/build-library-context-menu.png" alt-text="Menu kontekstowe StringLibrary z poleceniem Build":::

1. <span data-ttu-id="3eb3c-204">Uruchom testy jednostkowe, wybierając pozycję **test Uruchom**  >  **wszystkie testy** z paska menu.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-204">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="3eb3c-205">Testy zostały zakończone pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-205">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="3eb3c-206">Debuguj testy</span><span class="sxs-lookup"><span data-stu-id="3eb3c-206">Debug tests</span></span>

<span data-ttu-id="3eb3c-207">Jeśli używasz programu Visual Studio jako środowiska IDE, możesz użyć tego samego procesu, który został przedstawiony w [samouczku: debugowanie aplikacji konsolowej .NET za pomocą programu Visual Studio](debugging-with-visual-studio.md) do debugowania kodu przy użyciu projektu testów jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-207">If you're using Visual Studio as your IDE, you can use the same process shown in [Tutorial: Debug a .NET console application using Visual Studio](debugging-with-visual-studio.md) to debug code using your unit test project.</span></span> <span data-ttu-id="3eb3c-208">Zamiast rozpoczynać projekt aplikacji *Prezentacja* , kliknij prawym przyciskiem myszy projekt **StringLibraryTests** , a następnie wybierz polecenie **Debuguj testy** z menu kontekstowego.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-208">Instead of starting the *ShowCase* app project, right-click the **StringLibraryTests** project, and select **Debug Tests** from the context menu.</span></span>

<span data-ttu-id="3eb3c-209">Program Visual Studio uruchamia projekt testowy z dołączonym debugerem.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-209">Visual Studio starts the test project with the debugger attached.</span></span> <span data-ttu-id="3eb3c-210">Wykonanie zostanie zatrzymane na dowolnym punkcie przerwania, który został dodany do projektu testowego lub kodu biblioteki źródłowej.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-210">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3eb3c-211">Zasoby dodatkowe</span><span class="sxs-lookup"><span data-stu-id="3eb3c-211">Additional resources</span></span>

* [<span data-ttu-id="3eb3c-212">Podstawowe informacje o teście jednostkowym — Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3eb3c-212">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
* [<span data-ttu-id="3eb3c-213">Testy jednostkowe w programie .NET</span><span class="sxs-lookup"><span data-stu-id="3eb3c-213">Unit testing in .NET</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="3eb3c-214">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="3eb3c-214">Next steps</span></span>

<span data-ttu-id="3eb3c-215">W tym samouczku przetestowano bibliotekę klas.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-215">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="3eb3c-216">Bibliotekę można udostępniać innym osobom, publikując ją w pakiecie [NuGet](https://nuget.org) jako pakiet.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-216">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="3eb3c-217">Aby dowiedzieć się, jak, postępuj zgodnie z samouczkiem NuGet:</span><span class="sxs-lookup"><span data-stu-id="3eb3c-217">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3eb3c-218">Tworzenie i publikowanie pakietu NuGet przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3eb3c-218">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="3eb3c-219">W przypadku opublikowania biblioteki jako pakietu NuGet inne osoby mogą ją zainstalować i używać.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-219">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="3eb3c-220">Aby dowiedzieć się, jak, postępuj zgodnie z samouczkiem NuGet:</span><span class="sxs-lookup"><span data-stu-id="3eb3c-220">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3eb3c-221">Instalowanie i używanie pakietu w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3eb3c-221">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="3eb3c-222">Biblioteka nie musi być dystrybuowana jako pakiet.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-222">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="3eb3c-223">Można go powiązać z aplikacją konsolową, która go używa.</span><span class="sxs-lookup"><span data-stu-id="3eb3c-223">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="3eb3c-224">Aby dowiedzieć się, jak opublikować aplikację konsolową, zobacz wcześniejszy samouczek w tej serii:</span><span class="sxs-lookup"><span data-stu-id="3eb3c-224">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3eb3c-225">Publikowanie aplikacji konsolowej .NET przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3eb3c-225">Publish a .NET console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
