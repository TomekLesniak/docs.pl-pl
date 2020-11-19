---
title: Testowanie biblioteki klas .NET przy użyciu Visual Studio Code
description: Dowiedz się, jak używać Visual Studio Code i interfejsu wiersza polecenia platformy .NET do tworzenia i uruchamiania projektu testów jednostkowych dla biblioteki klas .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 4528bd203ae03988a1d1d80a7e904e94e68c1d04
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915859"
---
# <a name="tutorial-test-a-net-class-library-using-visual-studio-code"></a><span data-ttu-id="33f04-103">Samouczek: testowanie biblioteki klas .NET przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="33f04-103">Tutorial: Test a .NET class library using Visual Studio Code</span></span>

<span data-ttu-id="33f04-104">W tym samouczku pokazano, jak zautomatyzować testy jednostkowe przez dodanie projektu testowego do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="33f04-104">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="33f04-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="33f04-105">Prerequisites</span></span>

- <span data-ttu-id="33f04-106">Ten samouczek współdziała z rozwiązaniem tworzonym w temacie [Tworzenie biblioteki klas platformy .NET przy użyciu Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="33f04-106">This tutorial works with the solution that you create in [Create a .NET class library using Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="33f04-107">Tworzenie projektu testu jednostkowego</span><span class="sxs-lookup"><span data-stu-id="33f04-107">Create a unit test project</span></span>

<span data-ttu-id="33f04-108">Testy jednostkowe zapewniają zautomatyzowane testowanie oprogramowania podczas opracowywania i publikowania.</span><span class="sxs-lookup"><span data-stu-id="33f04-108">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="33f04-109">Platforma testowa używana w tym samouczku to MSTest.</span><span class="sxs-lookup"><span data-stu-id="33f04-109">The testing framework that you use in this tutorial is MSTest.</span></span> <span data-ttu-id="33f04-110">[MSTest](https://github.com/Microsoft/testfx-docs) jest jednym z trzech platform testowych, spośród których można dokonać wyboru.</span><span class="sxs-lookup"><span data-stu-id="33f04-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="33f04-111">Inne to [xUnit](https://xunit.net/) i [nunit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="33f04-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="33f04-112">Uruchom program Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="33f04-112">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="33f04-113">Otwórz `ClassLibraryProjects` rozwiązanie utworzone w temacie [Tworzenie biblioteki klas .NET przy użyciu Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="33f04-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET class library using Visual Studio Code](library-with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="33f04-114">Utwórz projekt testu jednostkowego o nazwie "StringLibraryTest".</span><span class="sxs-lookup"><span data-stu-id="33f04-114">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="33f04-115">Szablon projektu tworzy plik UnitTest1.cs o następującym kodzie:</span><span class="sxs-lookup"><span data-stu-id="33f04-115">The project template creates a UnitTest1.cs file with the following code:</span></span>

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

   <span data-ttu-id="33f04-116">Kod źródłowy utworzony przez szablon testu jednostkowego wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="33f04-116">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="33f04-117">Importuje <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> przestrzeń nazw, która zawiera typy używane do testowania jednostkowego.</span><span class="sxs-lookup"><span data-stu-id="33f04-117">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="33f04-118">Stosuje <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> atrybut do `UnitTest1` klasy.</span><span class="sxs-lookup"><span data-stu-id="33f04-118">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="33f04-119">Stosuje <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> atrybut do zdefiniowania `TestMethod1` .</span><span class="sxs-lookup"><span data-stu-id="33f04-119">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="33f04-120">Każda metoda oznaczona przy użyciu elementu [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) w klasie testowej oznaczona przy użyciu elementu [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) jest wykonywana automatycznie, gdy test jednostkowy jest uruchamiany.</span><span class="sxs-lookup"><span data-stu-id="33f04-120">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="33f04-121">Dodaj projekt testowy do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="33f04-121">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

## <a name="add-a-project-reference"></a><span data-ttu-id="33f04-122">Dodaj odwołanie do projektu</span><span class="sxs-lookup"><span data-stu-id="33f04-122">Add a project reference</span></span>

<span data-ttu-id="33f04-123">Aby projekt testowy mógł współpracował z `StringLibrary` klasą, Dodaj odwołanie w `StringLibraryTest` projekcie do `StringLibrary` projektu.</span><span class="sxs-lookup"><span data-stu-id="33f04-123">For the test project to work with the `StringLibrary` class, add a reference in the `StringLibraryTest` project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="33f04-124">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="33f04-124">Run the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="33f04-125">Dodawanie i uruchamianie metod testów jednostkowych</span><span class="sxs-lookup"><span data-stu-id="33f04-125">Add and run unit test methods</span></span>

<span data-ttu-id="33f04-126">Gdy program Visual Studio uruchamia test jednostkowy, wykonuje każdą metodę, która jest oznaczona <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> atrybutem w klasie, która jest oznaczona  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> atrybutem.</span><span class="sxs-lookup"><span data-stu-id="33f04-126">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="33f04-127">Metoda testowa kończy się po znalezieniu pierwszego błędu lub gdy wszystkie testy zawarte w metodzie zakończyły się powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="33f04-127">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="33f04-128">Najczęstsze testy wywołują elementy członkowskie <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> klasy.</span><span class="sxs-lookup"><span data-stu-id="33f04-128">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="33f04-129">Wiele metod Assert obejmuje co najmniej dwa parametry, z których jeden jest oczekiwany wynik testu, a drugi jest rzeczywistym wynikiem testu.</span><span class="sxs-lookup"><span data-stu-id="33f04-129">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="33f04-130">`Assert`W poniższej tabeli przedstawiono niektóre z najczęściej wywoływanych metod:</span><span class="sxs-lookup"><span data-stu-id="33f04-130">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="33f04-131">Metody Assert</span><span class="sxs-lookup"><span data-stu-id="33f04-131">Assert methods</span></span>     | <span data-ttu-id="33f04-132">Funkcja</span><span class="sxs-lookup"><span data-stu-id="33f04-132">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="33f04-133">Sprawdza, czy dwie wartości lub obiekty są równe.</span><span class="sxs-lookup"><span data-stu-id="33f04-133">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="33f04-134">Potwierdzenie kończy się niepowodzeniem, jeśli wartości lub obiekty nie są równe.</span><span class="sxs-lookup"><span data-stu-id="33f04-134">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="33f04-135">Sprawdza, czy dwie zmienne obiektów odwołują się do tego samego obiektu.</span><span class="sxs-lookup"><span data-stu-id="33f04-135">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="33f04-136">Potwierdzenie kończy się niepowodzeniem, jeśli zmienne odwołują się do różnych obiektów.</span><span class="sxs-lookup"><span data-stu-id="33f04-136">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="33f04-137">Sprawdza, czy warunek to `false` .</span><span class="sxs-lookup"><span data-stu-id="33f04-137">Verifies that a condition is `false`.</span></span> <span data-ttu-id="33f04-138">Potwierdzenie kończy się niepowodzeniem, jeśli warunek ma wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="33f04-138">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="33f04-139">Sprawdza, czy obiekt nie jest `null` .</span><span class="sxs-lookup"><span data-stu-id="33f04-139">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="33f04-140">Potwierdzenie kończy się niepowodzeniem, jeśli obiekt jest `null` .</span><span class="sxs-lookup"><span data-stu-id="33f04-140">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="33f04-141">Można również użyć <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metody w metodzie testowej, aby wskazać typ wyjątku, który ma zostać zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="33f04-141">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="33f04-142">Test zakończy się niepowodzeniem, jeśli określony wyjątek nie zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="33f04-142">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="33f04-143">W testowaniu `StringLibrary.StartsWithUpper` metody, należy podać kilka ciągów zaczynających się od wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="33f04-143">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="33f04-144">Oczekiwano, że metoda zwraca `true` w tych przypadkach, więc można wywołać <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="33f04-144">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="33f04-145">Podobnie, chcesz podać kilka ciągów, które zaczynają się od znaku innego niż wielkie litery.</span><span class="sxs-lookup"><span data-stu-id="33f04-145">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="33f04-146">Oczekiwano, że metoda zwraca `false` w tych przypadkach, więc można wywołać <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="33f04-146">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="33f04-147">Ponieważ metoda biblioteki obsługuje ciągi, należy również upewnić się, że pomyślnie obsługuje [pusty ciąg ( `String.Empty` )](xref:System.String.Empty) i a i `null` ciąg.</span><span class="sxs-lookup"><span data-stu-id="33f04-147">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="33f04-148">Pusty ciąg jest taki, który nie zawiera znaków i <xref:System.String.Length> ma wartość 0.</span><span class="sxs-lookup"><span data-stu-id="33f04-148">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="33f04-149">`null`Ciąg to taki, który nie został zainicjowany.</span><span class="sxs-lookup"><span data-stu-id="33f04-149">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="33f04-150">Można wywołać `StartsWithUpper` bezpośrednio jako metodę statyczną i przekazać pojedynczy <xref:System.String> argument.</span><span class="sxs-lookup"><span data-stu-id="33f04-150">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="33f04-151">Lub można wywołać `StartsWithUpper` jako metodę rozszerzającą dla `string` zmiennej przypisanej do `null` .</span><span class="sxs-lookup"><span data-stu-id="33f04-151">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="33f04-152">Zdefiniujesz trzy metody, z których każda wywołuje <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> metodę dla każdego elementu w tablicy ciągów.</span><span class="sxs-lookup"><span data-stu-id="33f04-152">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="33f04-153">Wywołasz Przeciążenie metody, które pozwala określić komunikat o błędzie, który ma być wyświetlany w przypadku niepowodzenia testu.</span><span class="sxs-lookup"><span data-stu-id="33f04-153">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="33f04-154">Komunikat identyfikuje ciąg, który spowodował awarię.</span><span class="sxs-lookup"><span data-stu-id="33f04-154">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="33f04-155">Aby utworzyć metody testowe:</span><span class="sxs-lookup"><span data-stu-id="33f04-155">To create the test methods:</span></span>

1. <span data-ttu-id="33f04-156">Otwórz *StringLibraryTest/UnitTest1. cs* i Zastąp cały kod następującym kodem.</span><span class="sxs-lookup"><span data-stu-id="33f04-156">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="33f04-157">Test wielkich liter w `TestStartsWithUpper` metodzie zawiera alfabet grecki (u + 0391) oraz wielką literę pauzy (u + 041C).</span><span class="sxs-lookup"><span data-stu-id="33f04-157">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="33f04-158">Test małymi literami w `TestDoesNotStartWithUpper` metodzie obejmuje małą literę alfa (u + 03B1) i małą literę cyrylicy GHE (u + 0433).</span><span class="sxs-lookup"><span data-stu-id="33f04-158">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="33f04-159">Zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="33f04-159">Save your changes.</span></span>

1. <span data-ttu-id="33f04-160">Uruchom testy:</span><span class="sxs-lookup"><span data-stu-id="33f04-160">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="33f04-161">Dane wyjściowe terminalu pokazują, że wszystkie testy zostały zakończone.</span><span class="sxs-lookup"><span data-stu-id="33f04-161">The terminal output shows that all tests passed.</span></span>

   ```output
   Starting test execution, please wait...
   A total of 1 test files matched the specified pattern.

   Passed!  - Failed:     0, Passed:     3, Skipped:     0, Total:     3, Duration: 3 ms - StringLibraryTest.dll (net5.0)
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="33f04-162">Obsługa niepowodzeń testów</span><span class="sxs-lookup"><span data-stu-id="33f04-162">Handle test failures</span></span>

<span data-ttu-id="33f04-163">Jeśli wykonujesz programowanie sterowane testami (TDD), najpierw napiszesz testy i nie powiodą się po raz pierwszy.</span><span class="sxs-lookup"><span data-stu-id="33f04-163">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="33f04-164">Następnie dodasz kod do aplikacji, która pomyślnie testuje.</span><span class="sxs-lookup"><span data-stu-id="33f04-164">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="33f04-165">Na potrzeby tego samouczka utworzono test po zapisaniu kodu aplikacji, który jest weryfikowany, więc niepowodzenie testu nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="33f04-165">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="33f04-166">Aby sprawdzić, czy test zakończy się niepowodzeniem, gdy spodziewasz się niepowodzeniem, Dodaj nieprawidłową wartość do danych wejściowych testu.</span><span class="sxs-lookup"><span data-stu-id="33f04-166">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="33f04-167">Zmodyfikuj `words` tablicę w `TestDoesNotStartWithUpper` metodzie, aby uwzględnić ciąg "Error".</span><span class="sxs-lookup"><span data-stu-id="33f04-167">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="33f04-168">Uruchom testy:</span><span class="sxs-lookup"><span data-stu-id="33f04-168">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="33f04-169">Dane wyjściowe terminalu pokazują, że jeden test zakończy się niepowodzeniem i zawiera komunikat o błędzie dla testu zakończonego niepowodzeniem: "Assert. IsFalse nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="33f04-169">The terminal output shows that one test fails, and it provides an error message for the failed test: "Assert.IsFalse failed.</span></span> <span data-ttu-id="33f04-170">Oczekiwano dla elementu "Error": false; rzeczywista: true ".</span><span class="sxs-lookup"><span data-stu-id="33f04-170">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="33f04-171">Z powodu błędu nie przetestowano ciągów w tablicy po "błędzie".</span><span class="sxs-lookup"><span data-stu-id="33f04-171">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   ```output
   Starting test execution, please wait...
   A total of 1 test files matched the specified pattern.
     Failed TestDoesNotStartWithUpper [28 ms]
     Error Message:
      Assert.IsFalse failed. Expected for 'Error': false; Actual: True
     Stack Trace:
        at StringLibraryTest.UnitTest1.TestDoesNotStartWithUpper() in C:\ClassLibraryProjects\StringLibraryTest\UnitTest1.cs:line 33

   Failed!  - Failed:     1, Passed:     2, Skipped:     0, Total:     3, Duration: 31 ms - StringLibraryTest.dll (net5.0)
   ```

1. <span data-ttu-id="33f04-172">Usuń ciąg "Error", który został dodany w kroku 1.</span><span class="sxs-lookup"><span data-stu-id="33f04-172">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="33f04-173">Uruchom ponownie test i testy zakończone powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="33f04-173">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="33f04-174">Testowanie wersji wydania biblioteki</span><span class="sxs-lookup"><span data-stu-id="33f04-174">Test the Release version of the library</span></span>

<span data-ttu-id="33f04-175">Teraz, gdy testy zostały zakończone przed uruchomieniem kompilacji biblioteki, należy uruchomić testy w dodatkowym czasie względem kompilacji wydania biblioteki.</span><span class="sxs-lookup"><span data-stu-id="33f04-175">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="33f04-176">Wiele czynników, w tym Optymalizacja kompilatora, może czasami generować różne zachowanie między kompilacjami w wersji Debug i Release.</span><span class="sxs-lookup"><span data-stu-id="33f04-176">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="33f04-177">Uruchom testy z konfiguracją kompilacji wydania:</span><span class="sxs-lookup"><span data-stu-id="33f04-177">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="33f04-178">Testy zostały zakończone pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="33f04-178">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="33f04-179">Debuguj testy</span><span class="sxs-lookup"><span data-stu-id="33f04-179">Debug tests</span></span>

<span data-ttu-id="33f04-180">Jeśli używasz Visual Studio Code jako środowiska IDE, możesz użyć tego samego procesu, który jest wyświetlany w [debugowaniu aplikacji konsolowej .NET za pomocą Visual Studio Code](debugging-with-visual-studio-code.md) do debugowania kodu przy użyciu projektu testu jednostkowego.</span><span class="sxs-lookup"><span data-stu-id="33f04-180">If you're using Visual Studio Code as your IDE, you can use the same process shown in [Debug a .NET console application using Visual Studio Code](debugging-with-visual-studio-code.md) to debug code using your unit test project.</span></span> <span data-ttu-id="33f04-181">Zamiast rozpoczynać projekt aplikacji *pokazu* Otwórz *StringLibraryTest/UnitTest1. cs*, a następnie wybierz opcję **Uruchom wszystkie testy** między wierszami 7 i 8.</span><span class="sxs-lookup"><span data-stu-id="33f04-181">Instead of starting the *ShowCase* app project, open *StringLibraryTest/UnitTest1.cs*, and select **Run All Tests** between lines 7 and 8.</span></span> <span data-ttu-id="33f04-182">Jeśli nie możesz go znaleźć, naciśnij klawisz <kbd>Ctrl</kbd> + <kbd>SHIFT</kbd> + <kbd>P</kbd> , aby otworzyć paletę poleceń i wprowadzić **ponowne załadowanie okna**.</span><span class="sxs-lookup"><span data-stu-id="33f04-182">If you're unable to find it, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> to open the command palette and enter **Reload Window**.</span></span>

<span data-ttu-id="33f04-183">Visual Studio Code uruchamia projekt testowy z dołączonym debugerem.</span><span class="sxs-lookup"><span data-stu-id="33f04-183">Visual Studio Code starts the test project with the debugger attached.</span></span> <span data-ttu-id="33f04-184">Wykonanie zostanie zatrzymane na dowolnym punkcie przerwania, który został dodany do projektu testowego lub kodu biblioteki źródłowej.</span><span class="sxs-lookup"><span data-stu-id="33f04-184">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33f04-185">Zasoby dodatkowe</span><span class="sxs-lookup"><span data-stu-id="33f04-185">Additional resources</span></span>

* [<span data-ttu-id="33f04-186">Testy jednostkowe w programie .NET</span><span class="sxs-lookup"><span data-stu-id="33f04-186">Unit testing in .NET</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="33f04-187">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="33f04-187">Next steps</span></span>

<span data-ttu-id="33f04-188">W tym samouczku przetestowano bibliotekę klas.</span><span class="sxs-lookup"><span data-stu-id="33f04-188">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="33f04-189">Bibliotekę można udostępniać innym osobom, publikując ją w pakiecie [NuGet](https://nuget.org) jako pakiet.</span><span class="sxs-lookup"><span data-stu-id="33f04-189">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="33f04-190">Aby dowiedzieć się, jak, postępuj zgodnie z samouczkiem NuGet:</span><span class="sxs-lookup"><span data-stu-id="33f04-190">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="33f04-191">Tworzenie i publikowanie pakietu przy użyciu interfejsu wiersza polecenia dotnet</span><span class="sxs-lookup"><span data-stu-id="33f04-191">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="33f04-192">W przypadku opublikowania biblioteki jako pakietu NuGet inne osoby mogą ją zainstalować i używać.</span><span class="sxs-lookup"><span data-stu-id="33f04-192">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="33f04-193">Aby dowiedzieć się, jak, postępuj zgodnie z samouczkiem NuGet:</span><span class="sxs-lookup"><span data-stu-id="33f04-193">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="33f04-194">Instalowanie i używanie pakietu przy użyciu interfejsu wiersza polecenia dotnet</span><span class="sxs-lookup"><span data-stu-id="33f04-194">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="33f04-195">Biblioteka nie musi być dystrybuowana jako pakiet.</span><span class="sxs-lookup"><span data-stu-id="33f04-195">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="33f04-196">Można go powiązać z aplikacją konsolową, która go używa.</span><span class="sxs-lookup"><span data-stu-id="33f04-196">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="33f04-197">Aby dowiedzieć się, jak opublikować aplikację konsolową, zobacz wcześniejszy samouczek w tej serii:</span><span class="sxs-lookup"><span data-stu-id="33f04-197">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="33f04-198">Publikowanie aplikacji konsolowej .NET przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="33f04-198">Publish a .NET console application using Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
