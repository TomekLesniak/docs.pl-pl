---
title: Przekształcanie danych za pomocą LINQ (C#)
description: Dowiedz się, jak przetwarzać dane przy użyciu zapytań LINQ w języku C#. Sekwencję można modyfikować, sortując i grupując i tworząc nowe typy przy użyciu klauzuli select.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: af08938b6b8f169ded2180529c2b4aadebefef55
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558813"
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="41d4f-104">Przekształcanie danych za pomocą LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="41d4f-104">Data Transformations with LINQ (C#)</span></span>
<span data-ttu-id="41d4f-105">Zapytanie zintegrowane z językiem (LINQ) nie tylko pobiera dane.</span><span class="sxs-lookup"><span data-stu-id="41d4f-105">Language-Integrated Query (LINQ) is not only about retrieving data.</span></span> <span data-ttu-id="41d4f-106">Jest to również zaawansowane narzędzie do przekształcania danych.</span><span class="sxs-lookup"><span data-stu-id="41d4f-106">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="41d4f-107">Używając zapytania LINQ, można użyć sekwencji źródłowej jako danych wejściowych i zmodyfikować ją na wiele sposobów, aby utworzyć nową sekwencję wyjściową.</span><span class="sxs-lookup"><span data-stu-id="41d4f-107">By using a LINQ query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="41d4f-108">Można zmodyfikować samą sekwencję bez modyfikowania samych elementów przez sortowanie i grupowanie.</span><span class="sxs-lookup"><span data-stu-id="41d4f-108">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="41d4f-109">Jednak prawdopodobnie najbardziej wydajną funkcją zapytań LINQ jest możliwość tworzenia nowych typów.</span><span class="sxs-lookup"><span data-stu-id="41d4f-109">But perhaps the most powerful feature of LINQ queries is the ability to create new types.</span></span> <span data-ttu-id="41d4f-110">Jest to realizowane w klauzuli [SELECT](../../../language-reference/keywords/select-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="41d4f-110">This is accomplished in the [select](../../../language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="41d4f-111">Na przykład można wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="41d4f-111">For example, you can perform the following tasks:</span></span>  
  
- <span data-ttu-id="41d4f-112">Scalanie wielu sekwencji wejściowych w jedną sekwencję wyjściową, która ma nowy typ.</span><span class="sxs-lookup"><span data-stu-id="41d4f-112">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
- <span data-ttu-id="41d4f-113">Utwórz sekwencje danych wyjściowych, których elementy składają się tylko z jednej lub kilku właściwości każdego elementu w sekwencji źródłowej.</span><span class="sxs-lookup"><span data-stu-id="41d4f-113">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
- <span data-ttu-id="41d4f-114">Utwórz sekwencje danych wyjściowych, których elementy składają się z wyników operacji wykonanych na danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="41d4f-114">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
- <span data-ttu-id="41d4f-115">Utwórz sekwencje wyjściowe w innym formacie.</span><span class="sxs-lookup"><span data-stu-id="41d4f-115">Create output sequences in a different format.</span></span> <span data-ttu-id="41d4f-116">Na przykład możesz przekształcić dane z wierszy SQL lub plików tekstowych do formatu XML.</span><span class="sxs-lookup"><span data-stu-id="41d4f-116">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="41d4f-117">Poniżej przedstawiono kilka przykładów.</span><span class="sxs-lookup"><span data-stu-id="41d4f-117">These are just several examples.</span></span> <span data-ttu-id="41d4f-118">Oczywiście te przekształcenia można łączyć na różne sposoby w tym samym zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="41d4f-118">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="41d4f-119">Ponadto sekwencja wyjściowa jednego zapytania może służyć jako sekwencja wejściowa dla nowej kwerendy.</span><span class="sxs-lookup"><span data-stu-id="41d4f-119">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="41d4f-120">Łączenie wielu danych wejściowych w jedną sekwencję wyjściową</span><span class="sxs-lookup"><span data-stu-id="41d4f-120">Joining Multiple Inputs into One Output Sequence</span></span>  
 <span data-ttu-id="41d4f-121">Za pomocą zapytania LINQ można utworzyć sekwencję wyjściową zawierającą elementy z więcej niż jednej sekwencji danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="41d4f-121">You can use a LINQ query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="41d4f-122">Poniższy przykład pokazuje, jak połączyć dwie struktury danych w pamięci, ale te same zasady można stosować do łączenia danych ze źródeł XML lub SQL lub zestawów danych.</span><span class="sxs-lookup"><span data-stu-id="41d4f-122">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="41d4f-123">Założono następujące dwa typy klas:</span><span class="sxs-lookup"><span data-stu-id="41d4f-123">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 <span data-ttu-id="41d4f-124">W poniższym przykładzie pokazano zapytanie:</span><span class="sxs-lookup"><span data-stu-id="41d4f-124">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 <span data-ttu-id="41d4f-125">Aby uzyskać więcej informacji, zobacz [Klauzula join](../../../language-reference/keywords/join-clause.md) i [klauzula SELECT](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="41d4f-125">For more information, see [join clause](../../../language-reference/keywords/join-clause.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="41d4f-126">Wybranie podzestawu każdego elementu źródłowego</span><span class="sxs-lookup"><span data-stu-id="41d4f-126">Selecting a Subset of each Source Element</span></span>  
 <span data-ttu-id="41d4f-127">Istnieją dwa podstawowe sposoby wybierania podzbioru każdego elementu w sekwencji źródłowej:</span><span class="sxs-lookup"><span data-stu-id="41d4f-127">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1. <span data-ttu-id="41d4f-128">Aby zaznaczyć tylko jeden element członkowski elementu źródłowego, użyj operacji z kropką.</span><span class="sxs-lookup"><span data-stu-id="41d4f-128">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="41d4f-129">W poniższym przykładzie Załóżmy, że `Customer` obiekt zawiera kilka właściwości publicznych, w tym ciąg o nazwie `City` .</span><span class="sxs-lookup"><span data-stu-id="41d4f-129">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="41d4f-130">Po wykonaniu to zapytanie będzie generować sekwencję wyjściową ciągów.</span><span class="sxs-lookup"><span data-stu-id="41d4f-130">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. <span data-ttu-id="41d4f-131">Aby utworzyć elementy, które zawierają więcej niż jedną właściwość z elementu źródłowego, można użyć inicjatora obiektów z obiektem nazwanym lub typem anonimowym.</span><span class="sxs-lookup"><span data-stu-id="41d4f-131">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="41d4f-132">W poniższym przykładzie pokazano użycie typu anonimowego do hermetyzacji dwóch właściwości z każdego `Customer` elementu:</span><span class="sxs-lookup"><span data-stu-id="41d4f-132">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="41d4f-133">Aby uzyskać więcej informacji, zobacz [Inicjatory obiektów i kolekcji](../../classes-and-structs/object-and-collection-initializers.md) oraz [Typy anonimowe](../../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="41d4f-133">For more information, see [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="41d4f-134">Przekształcanie obiektów w pamięci do formatu XML</span><span class="sxs-lookup"><span data-stu-id="41d4f-134">Transforming in-Memory Objects into XML</span></span>  
 <span data-ttu-id="41d4f-135">Zapytania LINQ ułatwiają Przekształcanie danych między strukturami danych w pamięci, bazami danych SQL, ADO.NETmi i strumieniami XML.</span><span class="sxs-lookup"><span data-stu-id="41d4f-135">LINQ queries make it easy to transform data between in-memory data structures, SQL databases, ADO.NET Datasets and XML streams or documents.</span></span> <span data-ttu-id="41d4f-136">Poniższy przykład przekształca obiekty w strukturze danych w pamięci na elementy XML.</span><span class="sxs-lookup"><span data-stu-id="41d4f-136">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 <span data-ttu-id="41d4f-137">Kod generuje następujące dane wyjściowe XML:</span><span class="sxs-lookup"><span data-stu-id="41d4f-137">The code produces the following XML output:</span></span>  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 <span data-ttu-id="41d4f-138">Aby uzyskać więcej informacji, zobacz [Tworzenie drzew XML w języku C# (LINQ to XML)](../../../../standard/linq/create-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="41d4f-138">For more information, see [Creating XML Trees in C# (LINQ to XML)](../../../../standard/linq/create-xml-trees.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="41d4f-139">Wykonywanie operacji na elementach źródłowych</span><span class="sxs-lookup"><span data-stu-id="41d4f-139">Performing Operations on Source Elements</span></span>  
 <span data-ttu-id="41d4f-140">Sekwencja wyjściowa może nie zawierać żadnych elementów ani właściwości elementów z sekwencji źródłowej.</span><span class="sxs-lookup"><span data-stu-id="41d4f-140">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="41d4f-141">Wyjście może zamiast tego być sekwencją wartości, które są obliczane przy użyciu elementów źródłowych jako argumentów wejściowych.</span><span class="sxs-lookup"><span data-stu-id="41d4f-141">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span>

 <span data-ttu-id="41d4f-142">Następujące zapytanie zajmie sekwencję liczb reprezentujących promienie okręgów, oblicza obszar dla każdego promienia i zwraca sekwencję wyjściową zawierającą ciągi sformatowane w obszarze obliczeniowym.</span><span class="sxs-lookup"><span data-stu-id="41d4f-142">The following query will take a sequence of numbers that represent radii of circles, calculate the area for each radius, and return an output sequence containing strings formatted with the calculated area.</span></span>

 <span data-ttu-id="41d4f-143">Każdy ciąg dla sekwencji wyjściowej zostanie sformatowany przy użyciu [interpolacji ciągów](../../../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="41d4f-143">Each string for the output sequence will be formatted using [string interpolation](../../../language-reference/tokens/interpolated.md).</span></span> <span data-ttu-id="41d4f-144">Ciąg interpolowany będzie miał `$` przed znakiem cudzysłowu otwierającego ciąg, a operacje mogą być wykonywane w nawiasach klamrowych umieszczonych wewnątrz ciągu interpolowanego.</span><span class="sxs-lookup"><span data-stu-id="41d4f-144">An interpolated string will have a `$` in front of the string's opening quotation mark, and operations can be performed within curly braces placed inside the interpolated string.</span></span> <span data-ttu-id="41d4f-145">Po wykonaniu tych operacji wyniki zostaną połączone.</span><span class="sxs-lookup"><span data-stu-id="41d4f-145">Once those operations are performed, the results will be concatenated.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41d4f-146">Metody wywołujące w wyrażeniach zapytań nie są obsługiwane, jeśli zapytanie zostanie przetłumaczone na inną domenę.</span><span class="sxs-lookup"><span data-stu-id="41d4f-146">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="41d4f-147">Na przykład nie można wywołać zwykłej metody C# w [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] , ponieważ SQL Server nie ma kontekstu dla tego elementu.</span><span class="sxs-lookup"><span data-stu-id="41d4f-147">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="41d4f-148">Można jednak mapować procedury składowane na metody i wywoływać je.</span><span class="sxs-lookup"><span data-stu-id="41d4f-148">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="41d4f-149">Aby uzyskać więcej informacji, zobacz [procedury składowane](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="41d4f-149">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="41d4f-150">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="41d4f-150">See also</span></span>

- [<span data-ttu-id="41d4f-151">Language-Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="41d4f-151">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="41d4f-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="41d4f-152">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="41d4f-153">LINQ do DataSet</span><span class="sxs-lookup"><span data-stu-id="41d4f-153">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)
- [<span data-ttu-id="41d4f-154">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="41d4f-154">LINQ to XML (C#)</span></span>](../../../../standard/linq/linq-xml-overview.md)
- [<span data-ttu-id="41d4f-155">Wyrażenia zapytania LINQ</span><span class="sxs-lookup"><span data-stu-id="41d4f-155">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="41d4f-156">SELECT — klauzula</span><span class="sxs-lookup"><span data-stu-id="41d4f-156">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
