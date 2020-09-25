---
title: 'Przewodnik: Pisanie zapytań w języku C# (LINQ)'
description: W tym instruktażu pokazano, w jaki sposób funkcje języka C# są używane w wyrażeniach zapytań LINQ. W tym artykule program Visual Studio jest wykorzystywany jako środowisko programistyczne.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
ms.openlocfilehash: bdf91f6f52a68309cfcd276b222083c8cb67a0cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176243"
---
# <a name="walkthrough-writing-queries-in-c-linq"></a><span data-ttu-id="7c7c2-104">Przewodnik: Pisanie zapytań w języku C# (LINQ)</span><span class="sxs-lookup"><span data-stu-id="7c7c2-104">Walkthrough: Writing Queries in C# (LINQ)</span></span>

<span data-ttu-id="7c7c2-105">W tym instruktażu przedstawiono funkcje języka C#, które są używane do pisania wyrażeń zapytań LINQ.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-105">This walkthrough demonstrates the C# language features that are used to write LINQ query expressions.</span></span>  
  
## <a name="create-a-c-project"></a><span data-ttu-id="7c7c2-106">Utwórz projekt C#</span><span class="sxs-lookup"><span data-stu-id="7c7c2-106">Create a C# Project</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c7c2-107">Poniższe instrukcje dotyczą programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-107">The following instructions are for Visual Studio.</span></span> <span data-ttu-id="7c7c2-108">Jeśli używasz innego środowiska programistycznego, Utwórz projekt konsoli z odwołaniem do System.Core.dll i `using` dyrektywy dla <xref:System.Linq?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-108">If you are using a different development environment, create a console project with a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
#### <a name="to-create-a-project-in-visual-studio"></a><span data-ttu-id="7c7c2-109">Aby utworzyć projekt w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7c7c2-109">To create a project in Visual Studio</span></span>  
  
1. <span data-ttu-id="7c7c2-110">Uruchom program Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-110">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="7c7c2-111">Na pasku menu wybierz **plik**, **Nowy**, **projekt**.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-111">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="7c7c2-112">Zostanie otwarte okno dialogowe **Nowy projekt** .</span><span class="sxs-lookup"><span data-stu-id="7c7c2-112">The **New Project** dialog box opens.</span></span>  
  
3. <span data-ttu-id="7c7c2-113">Rozwiń węzeł **zainstalowane**, rozwiń węzeł **Szablony**, rozwiń pozycję **Visual C#**, a następnie wybierz pozycję **Aplikacja konsolowa**.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-113">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4. <span data-ttu-id="7c7c2-114">W polu tekstowym **Nazwa** wprowadź inną nazwę lub zaakceptuj nazwę domyślną, a następnie wybierz przycisk **OK** .</span><span class="sxs-lookup"><span data-stu-id="7c7c2-114">In the **Name** text box, enter a different name or accept the default name, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="7c7c2-115">Nowy projekt zostanie wyświetlony w **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-115">The new project appears in **Solution Explorer**.</span></span>  
  
5. <span data-ttu-id="7c7c2-116">Zwróć uwagę, że projekt zawiera odwołanie do System.Core.dll i `using` dyrektywy dla <xref:System.Linq?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-116">Notice that your project has a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="create-an-in-memory-data-source"></a><span data-ttu-id="7c7c2-117">Utwórz źródło danych w pamięci</span><span class="sxs-lookup"><span data-stu-id="7c7c2-117">Create an in-Memory Data Source</span></span>  

 <span data-ttu-id="7c7c2-118">Źródło danych dla zapytań jest prostą listą `Student` obiektów.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-118">The data source for the queries is a simple list of `Student` objects.</span></span> <span data-ttu-id="7c7c2-119">Każdy `Student` rekord ma imię, nazwisko i tablicę liczb całkowitych, która reprezentuje wyniki testu w klasie.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-119">Each `Student` record has a first name, last name, and an array of integers that represents their test scores in the class.</span></span> <span data-ttu-id="7c7c2-120">Skopiuj ten kod do projektu.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-120">Copy this code into your project.</span></span> <span data-ttu-id="7c7c2-121">Należy pamiętać o następujących cechach:</span><span class="sxs-lookup"><span data-stu-id="7c7c2-121">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="7c7c2-122">`Student`Klasa składa się z właściwości, które są implementowane.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-122">The `Student` class consists of auto-implemented properties.</span></span>  
  
- <span data-ttu-id="7c7c2-123">Każdy student na liście jest inicjowany przy użyciu inicjatora obiektów.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-123">Each student in the list is initialized with an object initializer.</span></span>  
  
- <span data-ttu-id="7c7c2-124">Sama lista została zainicjowana przy użyciu inicjatora kolekcji.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-124">The list itself is initialized with a collection initializer.</span></span>  
  
 <span data-ttu-id="7c7c2-125">Ta cała struktura danych zostanie zainicjowana i utworzona bez jawnych wywołań do jakiegokolwiek konstruktora lub jawnego dostępu do elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-125">This whole data structure will be initialized and instantiated without explicit calls to any constructor or explicit member access.</span></span> <span data-ttu-id="7c7c2-126">Aby uzyskać więcej informacji o tych nowych funkcjach, zobacz [Autozaimplementowane właściwości](../../classes-and-structs/auto-implemented-properties.md) i [obiekty i Inicjatory kolekcji](../../classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="7c7c2-126">For more information about these new features, see [Auto-Implemented Properties](../../classes-and-structs/auto-implemented-properties.md) and [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="7c7c2-127">Aby dodać źródło danych</span><span class="sxs-lookup"><span data-stu-id="7c7c2-127">To add the data source</span></span>  
  
- <span data-ttu-id="7c7c2-128">Dodaj `Student` klasę i zainicjowaną listę uczniów do `Program` klasy w projekcie.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-128">Add the `Student` class and the initialized list of students to the `Program` class in your project.</span></span>  
  
     [!code-csharp[CsLinqGettingStarted#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#11)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="7c7c2-129">Aby dodać nowego studenta do listy studentów</span><span class="sxs-lookup"><span data-stu-id="7c7c2-129">To add a new Student to the Students list</span></span>  
  
1. <span data-ttu-id="7c7c2-130">Dodaj nowy element `Student` do `Students` listy i użyj wybranych przez siebie ocen.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-130">Add a new `Student` to the `Students` list and use a name and test scores of your choice.</span></span> <span data-ttu-id="7c7c2-131">Spróbuj wpisać wszystkie nowe informacje ucznia, aby lepiej poznać składnię inicjatora obiektów.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-131">Try typing all the new student information in order to better learn the syntax for the object initializer.</span></span>  
  
## <a name="create-the-query"></a><span data-ttu-id="7c7c2-132">Utwórz zapytanie</span><span class="sxs-lookup"><span data-stu-id="7c7c2-132">Create the Query</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="7c7c2-133">Aby utworzyć proste zapytanie</span><span class="sxs-lookup"><span data-stu-id="7c7c2-133">To create a simple query</span></span>  
  
- <span data-ttu-id="7c7c2-134">W `Main` metodzie aplikacji Utwórz proste zapytanie, które po jego wykonaniu spowoduje utworzenie listy wszystkich uczniów, których wynikiem pierwszego testu była większa niż 90.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-134">In the application's `Main` method, create a simple query that, when it is executed, will produce a list of all students whose score on the first test was greater than 90.</span></span> <span data-ttu-id="7c7c2-135">Należy zauważyć, że ponieważ `Student` zaznaczony jest cały obiekt, typ zapytania to `IEnumerable<Student>` .</span><span class="sxs-lookup"><span data-stu-id="7c7c2-135">Note that because the whole `Student` object is selected, the type of the query is `IEnumerable<Student>`.</span></span> <span data-ttu-id="7c7c2-136">Chociaż kod może również używać niejawnego wpisywania przy użyciu słowa kluczowego [var](../../../language-reference/keywords/var.md) , jawne wpisywanie jest używane do jasnego ilustrowania wyników.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-136">Although the code could also use implicit typing by using the [var](../../../language-reference/keywords/var.md) keyword, explicit typing is used to clearly illustrate results.</span></span> <span data-ttu-id="7c7c2-137">(Aby uzyskać więcej informacji na temat `var` , zobacz [niejawnie wpisane zmienne lokalne](../../classes-and-structs/implicitly-typed-local-variables.md)).</span><span class="sxs-lookup"><span data-stu-id="7c7c2-137">(For more information about `var`, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).)</span></span>  
  
     <span data-ttu-id="7c7c2-138">Należy zauważyć, że zmienna zakresu zapytania, `student` , służy jako odwołanie do każdego `Student` ze źródeł, zapewniając dostęp do elementu członkowskiego dla każdego obiektu.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-138">Note also that the query's range variable, `student`, serves as a reference to each `Student` in the source, providing member access for each object.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#12)]  
  
## <a name="execute-the-query"></a><span data-ttu-id="7c7c2-139">Wykonanie zapytania</span><span class="sxs-lookup"><span data-stu-id="7c7c2-139">Execute the Query</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="7c7c2-140">Aby wykonać zapytanie</span><span class="sxs-lookup"><span data-stu-id="7c7c2-140">To execute the query</span></span>  
  
1. <span data-ttu-id="7c7c2-141">Teraz napisz `foreach` pętlę, która spowoduje wykonanie zapytania.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-141">Now write the `foreach` loop that will cause the query to execute.</span></span> <span data-ttu-id="7c7c2-142">Zwróć uwagę na następujące informacje dotyczące kodu:</span><span class="sxs-lookup"><span data-stu-id="7c7c2-142">Note the following about the code:</span></span>  
  
    - <span data-ttu-id="7c7c2-143">Każdy element w zwróconej sekwencji jest dostępny za pomocą zmiennej iteracji w `foreach` pętli.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-143">Each element in the returned sequence is accessed through the iteration variable in the `foreach` loop.</span></span>  
  
    - <span data-ttu-id="7c7c2-144">Typ tej zmiennej to `Student` , a typ zmiennej zapytania jest zgodny `IEnumerable<Student>` .</span><span class="sxs-lookup"><span data-stu-id="7c7c2-144">The type of this variable is `Student`, and the type of the query variable is compatible, `IEnumerable<Student>`.</span></span>  
  
2. <span data-ttu-id="7c7c2-145">Po dodaniu tego kodu, skompiluj i uruchom aplikację, aby wyświetlić wyniki w oknie **konsoli** .</span><span class="sxs-lookup"><span data-stu-id="7c7c2-145">After you have added this code, build and run the application to see the results in the **Console** window.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#13)]  
  
#### <a name="to-add-another-filter-condition"></a><span data-ttu-id="7c7c2-146">Aby dodać inny warunek filtru</span><span class="sxs-lookup"><span data-stu-id="7c7c2-146">To add another filter condition</span></span>  
  
1. <span data-ttu-id="7c7c2-147">W klauzuli można połączyć wiele warunków logicznych `where` w celu dokładniejszego uściślenia zapytania.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-147">You can combine multiple Boolean conditions in the `where` clause in order to further refine a query.</span></span> <span data-ttu-id="7c7c2-148">Poniższy kod dodaje warunek, aby zapytanie zwracało uczniów, których pierwszy wynik był ponad 90 i którego ostatni wynik był mniejszy niż 80.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-148">The following code adds a condition so that the query returns those students whose first score was over 90 and whose last score was less than 80.</span></span> <span data-ttu-id="7c7c2-149">`where`Klauzula powinna wyglądać podobnie do poniższego kodu.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-149">The `where` clause should resemble the following code.</span></span>  
  
    ```csharp
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     <span data-ttu-id="7c7c2-150">Aby uzyskać więcej informacji, zobacz [klauzula WHERE](../../../language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="7c7c2-150">For more information, see [where clause](../../../language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="7c7c2-151">Zmodyfikuj zapytanie</span><span class="sxs-lookup"><span data-stu-id="7c7c2-151">Modify the Query</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="7c7c2-152">Aby uporządkować wyniki</span><span class="sxs-lookup"><span data-stu-id="7c7c2-152">To order the results</span></span>  
  
1. <span data-ttu-id="7c7c2-153">Wyszukiwanie wyników będzie łatwiejsze, jeśli są one w pewnym rodzaju kolejności.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-153">It will be easier to scan the results if they are in some kind of order.</span></span> <span data-ttu-id="7c7c2-154">Zwracaną sekwencję można zamówić według dowolnego dostępnego pola w elementach źródłowych.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-154">You can order the returned sequence by any accessible field in the source elements.</span></span> <span data-ttu-id="7c7c2-155">Na przykład poniższa klauzula porządkuje `orderby` wyniki w kolejności alfabetycznej od A do z w zależności od nazwiska każdego ucznia.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-155">For example, the following `orderby` clause orders the results in alphabetical order from A to Z according to the last name of each student.</span></span> <span data-ttu-id="7c7c2-156">Dodaj następującą `orderby` klauzulę do zapytania, bezpośrednio po `where` instrukcji i przed `select` instrukcją:</span><span class="sxs-lookup"><span data-stu-id="7c7c2-156">Add the following `orderby` clause to your query, right after the `where` statement and before the `select` statement:</span></span>  
  
    ```csharp
    orderby student.Last ascending  
    ```  
  
2. <span data-ttu-id="7c7c2-157">Teraz zmień `orderby` klauzulę tak, aby zamówili wyniki w odwrotnej kolejności według wyniku pierwszego testu, od najwyższego do najniższego wyniku.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-157">Now change the `orderby` clause so that it orders the results in reverse order according to the score on the first test, from the highest score to the lowest score.</span></span>  
  
    ```csharp
    orderby student.Scores[0] descending  
    ```  
  
3. <span data-ttu-id="7c7c2-158">Zmień `WriteLine` ciąg formatu, aby zobaczyć wyniki:</span><span class="sxs-lookup"><span data-stu-id="7c7c2-158">Change the `WriteLine` format string so that you can see the scores:</span></span>  
  
    ```csharp
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     <span data-ttu-id="7c7c2-159">Aby uzyskać więcej informacji, zobacz [klauzula OrderBy](../../../language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="7c7c2-159">For more information, see [orderby clause](../../../language-reference/keywords/orderby-clause.md).</span></span>  
  
#### <a name="to-group-the-results"></a><span data-ttu-id="7c7c2-160">Aby pogrupować wyniki</span><span class="sxs-lookup"><span data-stu-id="7c7c2-160">To group the results</span></span>  
  
1. <span data-ttu-id="7c7c2-161">Grupowanie jest zaawansowaną możliwością w wyrażeniach zapytań.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-161">Grouping is a powerful capability in query expressions.</span></span> <span data-ttu-id="7c7c2-162">Zapytanie z klauzulą grupy tworzy sekwencję grup, a każda sama grupa zawiera a `Key` i sekwencję, która składa się z wszystkich członków tej grupy.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-162">A query with a group clause produces a sequence of groups, and each group itself contains a `Key` and a sequence that consists of all the members of that group.</span></span> <span data-ttu-id="7c7c2-163">Poniższe nowe zapytanie grupuje uczniów przy użyciu pierwszej litery nazwiska jako klucza.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-163">The following new query groups the students by using the first letter of their last name as the key.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#14)]  
  
2. <span data-ttu-id="7c7c2-164">Należy zauważyć, że typ zapytania został zmieniony.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-164">Note that the type of the query has now changed.</span></span> <span data-ttu-id="7c7c2-165">Teraz tworzy sekwencję grup, które mają `char` Typ jako klucz i sekwencję `Student` obiektów.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-165">It now produces a sequence of groups that have a `char` type as a key, and a sequence of `Student` objects.</span></span> <span data-ttu-id="7c7c2-166">Ponieważ typ zapytania został zmieniony, poniższy kod zmienia `foreach` również pętlę wykonywania:</span><span class="sxs-lookup"><span data-stu-id="7c7c2-166">Because the type of the query has changed, the following code changes the `foreach` execution loop also:</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#15)]  
  
3. <span data-ttu-id="7c7c2-167">Uruchom aplikację i Wyświetl wyniki w oknie **konsoli** .</span><span class="sxs-lookup"><span data-stu-id="7c7c2-167">Run the application and view the results in the **Console** window.</span></span>  
  
     <span data-ttu-id="7c7c2-168">Aby uzyskać więcej informacji, zobacz [klauzula](../../../language-reference/keywords/group-clause.md)Group.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-168">For more information, see [group clause](../../../language-reference/keywords/group-clause.md).</span></span>  
  
#### <a name="to-make-the-variables-implicitly-typed"></a><span data-ttu-id="7c7c2-169">Aby jawnie wpisać zmienną lokalną</span><span class="sxs-lookup"><span data-stu-id="7c7c2-169">To make the variables implicitly typed</span></span>  
  
1. <span data-ttu-id="7c7c2-170">Jawne kodowanie `IEnumerables` `IGroupings` może szybko stać się żmudnym.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-170">Explicitly coding `IEnumerables` of `IGroupings` can quickly become tedious.</span></span> <span data-ttu-id="7c7c2-171">Można napisać to samo zapytanie i `foreach` pętlę znacznie bardziej wygodnie przy użyciu `var` .</span><span class="sxs-lookup"><span data-stu-id="7c7c2-171">You can write the same query and `foreach` loop much more conveniently by using `var`.</span></span> <span data-ttu-id="7c7c2-172">`var`Słowo kluczowe nie zmienia typów obiektów; po prostu nakazuje kompilatorowi wywnioskowanie typów.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-172">The `var` keyword does not change the types of your objects; it just instructs the compiler to infer the types.</span></span> <span data-ttu-id="7c7c2-173">Zmień typ `studentQuery` i zmienną iteracji `group` na `var` i ponownie uruchom zapytanie.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-173">Change the type of `studentQuery` and the iteration variable `group` to `var` and rerun the query.</span></span> <span data-ttu-id="7c7c2-174">Należy zauważyć, że w wewnętrznej `foreach` pętli Zmienna iteracji jest nadal wpisana jako `Student` , a zapytanie działa tak jak wcześniej.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-174">Note that in the inner `foreach` loop, the iteration variable is still typed as `Student`, and the query works just as before.</span></span> <span data-ttu-id="7c7c2-175">Zmień `s` zmienną iteracji na `var` i ponownie uruchom zapytanie.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-175">Change the `s` iteration variable to `var` and run the query again.</span></span> <span data-ttu-id="7c7c2-176">Zobaczysz, że uzyskujesz dokładnie te same wyniki.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-176">You see that you get exactly the same results.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#16)]  
  
     <span data-ttu-id="7c7c2-177">Aby uzyskać więcej informacji na temat funkcji [var](../../../language-reference/keywords/var.md), zobacz [niejawnie wpisane zmienne lokalne](../../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="7c7c2-177">For more information about [var](../../../language-reference/keywords/var.md), see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
#### <a name="to-order-the-groups-by-their-key-value"></a><span data-ttu-id="7c7c2-178">Aby uporządkować grupy według kluczy wartości</span><span class="sxs-lookup"><span data-stu-id="7c7c2-178">To order the groups by their key value</span></span>  
  
1. <span data-ttu-id="7c7c2-179">Po uruchomieniu poprzedniej kwerendy należy zauważyć, że grupy nie są w kolejności alfabetycznej.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-179">When you run the previous query, you notice that the groups are not in alphabetical order.</span></span> <span data-ttu-id="7c7c2-180">Aby to zmienić, należy podać `orderby` klauzulę po `group` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-180">To change this, you must provide an `orderby` clause after the `group` clause.</span></span> <span data-ttu-id="7c7c2-181">Jednak aby użyć `orderby` klauzuli, najpierw potrzebny jest identyfikator, który służy jako odwołanie do grup utworzonych przez `group` klauzulę.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-181">But to use an `orderby` clause, you first need an identifier that serves as a reference to the groups created by the `group` clause.</span></span> <span data-ttu-id="7c7c2-182">Identyfikator można podać za pomocą `into` słowa kluczowego w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="7c7c2-182">You provide the identifier by using the `into` keyword, as follows:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#17)]  
  
     <span data-ttu-id="7c7c2-183">Po uruchomieniu tego zapytania zobaczysz, że grupy są teraz sortowane w kolejności alfabetycznej.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-183">When you run this query, you will see the groups are now sorted in alphabetical order.</span></span>  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a><span data-ttu-id="7c7c2-184">Aby wprowadzić identyfikator przy użyciu let</span><span class="sxs-lookup"><span data-stu-id="7c7c2-184">To introduce an identifier by using let</span></span>  
  
1. <span data-ttu-id="7c7c2-185">Możesz użyć `let` słowa kluczowego, aby wprowadzić identyfikator dla dowolnego wyniku wyrażenia w wyrażeniu zapytania.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-185">You can use the `let` keyword to introduce an identifier for any expression result in the query expression.</span></span> <span data-ttu-id="7c7c2-186">Ten identyfikator może być wygodą, tak jak w poniższym przykładzie, lub może zwiększyć wydajność, przechowując wyniki wyrażenia, aby nie trzeba było obliczyć ich wiele razy.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-186">This identifier can be a convenience, as in the following example, or it can enhance performance by storing the results of an expression so that it does not have to be calculated multiple times.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#18)]  
  
     <span data-ttu-id="7c7c2-187">Aby uzyskać więcej informacji, zobacz [klauzula Let](../../../language-reference/keywords/let-clause.md).</span><span class="sxs-lookup"><span data-stu-id="7c7c2-187">For more information, see [let clause](../../../language-reference/keywords/let-clause.md).</span></span>  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a><span data-ttu-id="7c7c2-188">Aby użyć metody składni w wyrażeniu zapytania</span><span class="sxs-lookup"><span data-stu-id="7c7c2-188">To use method syntax in a query expression</span></span>  
  
1. <span data-ttu-id="7c7c2-189">Zgodnie z opisem w składni [zapytania i składni metody w LINQ](./query-syntax-and-method-syntax-in-linq.md), niektóre operacje zapytań można wyrazić tylko przy użyciu składni metody.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-189">As described in [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md), some query operations can only be expressed by using method syntax.</span></span> <span data-ttu-id="7c7c2-190">Poniższy kod oblicza łączny wynik dla każdej `Student` z nich w sekwencji źródłowej, a następnie wywołuje `Average()` metodę dla wyników tego zapytania, aby obliczyć średnią ocenę klasy.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-190">The following code calculates the total score for each `Student` in the source sequence, and then calls the `Average()` method on the results of that query to calculate the average score of the class.</span></span>
  
     [!code-csharp[csLINQGettingStarted#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#19)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a><span data-ttu-id="7c7c2-191">Aby przekształcić lub zaprojektować w klauzuli wyboru</span><span class="sxs-lookup"><span data-stu-id="7c7c2-191">To transform or project in the select clause</span></span>  
  
1. <span data-ttu-id="7c7c2-192">Jest bardzo często źródłem zapytania, aby utworzyć sekwencję, której elementy różnią się od elementów w sekwencjach źródłowych.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-192">It is very common for a query to produce a sequence whose elements differ from the elements in the source sequences.</span></span> <span data-ttu-id="7c7c2-193">Usuń lub Skomentuj poprzednią pętlę zapytania i wykonywania, a następnie zastąp ją poniższym kodem.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-193">Delete or comment out your previous query and execution loop, and replace it with the following code.</span></span> <span data-ttu-id="7c7c2-194">Należy zauważyć, że zapytanie zwraca sekwencję ciągów (nie `Students` ), a ten fakt jest odzwierciedlony w `foreach` pętli.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-194">Note that the query returns a sequence of strings (not `Students`), and this fact is reflected in the `foreach` loop.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#20)]  
  
2. <span data-ttu-id="7c7c2-195">Kod we wcześniejszej części tego instruktażu wskazywał, że średni wynik klasy wynosi około 334.</span><span class="sxs-lookup"><span data-stu-id="7c7c2-195">Code earlier in this walkthrough indicated that the average class score is approximately 334.</span></span> <span data-ttu-id="7c7c2-196">Aby utworzyć sekwencję `Students` , której łączny wynik jest większy niż średnia klasy, wraz z ich `Student ID` , można użyć typu anonimowego w `select` instrukcji:</span><span class="sxs-lookup"><span data-stu-id="7c7c2-196">To produce a sequence of `Students` whose total score is greater than the class average, together with their `Student ID`, you can use an anonymous type in the `select` statement:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#21)]  
  
## <a name="next-steps"></a><span data-ttu-id="7c7c2-197">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="7c7c2-197">Next Steps</span></span>  

 <span data-ttu-id="7c7c2-198">Po zapoznaniu się z podstawowymi aspektami pracy z zapytaniami w języku C# można przystąpić do zapoznania się z dokumentacją i przykładami dotyczącymi określonego typu dostawcy LINQ:</span><span class="sxs-lookup"><span data-stu-id="7c7c2-198">After you are familiar with the basic aspects of working with queries in C#, you are ready to read the documentation and samples for the specific type of LINQ provider you are interested in:</span></span>  
  
 [<span data-ttu-id="7c7c2-199">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7c7c2-199">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="7c7c2-200">LINQ do DataSet</span><span class="sxs-lookup"><span data-stu-id="7c7c2-200">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [<span data-ttu-id="7c7c2-201">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="7c7c2-201">LINQ to XML (C#)</span></span>](../../../../standard/linq/linq-xml-overview.md)  
  
 [<span data-ttu-id="7c7c2-202">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="7c7c2-202">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="7c7c2-203">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7c7c2-203">See also</span></span>

- [<span data-ttu-id="7c7c2-204">Language-Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7c7c2-204">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="7c7c2-205">Wyrażenia zapytania LINQ</span><span class="sxs-lookup"><span data-stu-id="7c7c2-205">LINQ Query Expressions</span></span>](../../../linq/index.md)
