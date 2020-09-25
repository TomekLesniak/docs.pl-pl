---
title: Relacje typu w operacjach kwerend LINQ (C#)
description: Dowiedz się, jak typy zmiennych w zapytaniu LINQ odnoszą się do siebie nawzajem. Operacje zapytań LINQ są silnie wpisywane w źródle danych, w zapytaniu i w wykonaniu.
ms.date: 07/20/2015
helpviewer_keywords:
- inferring type information [LINQ in C#]
- data sources [LINQ in C#], type relationships
- queries [LINQ in C#], type relationships
- relationships [LINQ in C#]
- type relationships [LINQ in C#]
- variable relationships [LINQ in C#]
- type information inferred [LINQ in C#]
- data transformations [LINQ in C#]
- LINQ [C#], type relationships
ms.assetid: 99118938-d47c-4d7e-bb22-2657a9f95268
ms.openlocfilehash: 78cdb550e59bc82386d34f0e2bf6b1cae11d72de
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203985"
---
# <a name="type-relationships-in-linq-query-operations-c"></a><span data-ttu-id="9c4cf-104">Relacje typu w operacjach kwerend LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="9c4cf-104">Type Relationships in LINQ Query Operations (C#)</span></span>

<span data-ttu-id="9c4cf-105">Aby efektywnie pisać zapytania, należy zrozumieć, jak typy zmiennych w kompletnej operacji zapytania wszystkie odnoszą się do siebie.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-105">To write queries effectively, you should understand how types of the variables in a complete query operation all relate to each other.</span></span> <span data-ttu-id="9c4cf-106">Jeśli rozumiesz te relacje, łatwiej będzie comprehend przykłady LINQ i przykłady kodu w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-106">If you understand these relationships you will more easily comprehend the LINQ samples and code examples in the documentation.</span></span> <span data-ttu-id="9c4cf-107">Ponadto dowiesz się, co się dzieje w tle, gdy zmienne są wpisywane niejawnie przy użyciu `var` .</span><span class="sxs-lookup"><span data-stu-id="9c4cf-107">Furthermore, you will understand what occurs behind the scenes when variables are implicitly typed by using `var`.</span></span>  
  
 <span data-ttu-id="9c4cf-108">Operacje zapytań LINQ są jednoznacznie wpisywane w źródle danych, w samej kwerendzie i w wykonaniu zapytania.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-108">LINQ query operations are strongly typed in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="9c4cf-109">Typ zmiennych w zapytaniu musi być zgodny z typem elementów w źródle danych i typem zmiennej iteracji w `foreach` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-109">The type of the variables in the query must be compatible with the type of the elements in the data source and with the type of the iteration variable in the `foreach` statement.</span></span> <span data-ttu-id="9c4cf-110">Takie silne wpisywanie gwarantuje, że błędy typu są przechwytywane w czasie kompilacji, gdy można je poprawić przed ich wystąpieniem przez użytkowników.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-110">This strong typing guarantees that type errors are caught at compile time when they can be corrected before users encounter them.</span></span>  
  
 <span data-ttu-id="9c4cf-111">Aby przedstawić te relacje typu, większość przykładów, które są zgodne z użyciem jawnego wpisywania dla wszystkich zmiennych.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-111">In order to demonstrate these type relationships, most of the examples that follow use explicit typing for all variables.</span></span> <span data-ttu-id="9c4cf-112">W ostatnim przykładzie pokazano, jak te same zasady mają zastosowanie nawet w przypadku użycia niejawnego wpisywania przy użyciu funkcji [var](../../../language-reference/keywords/var.md).</span><span class="sxs-lookup"><span data-stu-id="9c4cf-112">The last example shows how the same principles apply even when you use implicit typing by using [var](../../../language-reference/keywords/var.md).</span></span>  
  
## <a name="queries-that-do-not-transform-the-source-data"></a><span data-ttu-id="9c4cf-113">Zapytania, które nie przekształcają danych źródłowych</span><span class="sxs-lookup"><span data-stu-id="9c4cf-113">Queries that do not Transform the Source Data</span></span>  

 <span data-ttu-id="9c4cf-114">Na poniższej ilustracji przedstawiono LINQ to Objects operacji zapytania, która nie wykonuje transformacji danych.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-114">The following illustration shows a LINQ to Objects query operation that performs no transformations on the data.</span></span> <span data-ttu-id="9c4cf-115">Źródło zawiera sekwencję ciągów, a dane wyjściowe zapytania są również sekwencją ciągów.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-115">The source contains a sequence of strings and the query output is also a sequence of strings.</span></span>  
  
 ![Diagram przedstawiający relację typów danych w zapytaniu LINQ.](./media/type-relationships-in-linq-query-operations/linq-query-data-type-relation.png)  
  
1. <span data-ttu-id="9c4cf-117">Argument typu źródła danych określa typ zmiennej zakresu.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-117">The type argument of the data source determines the type of the range variable.</span></span>  
  
2. <span data-ttu-id="9c4cf-118">Typ wybranego obiektu określa typ zmiennej zapytania.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-118">The type of the object that is selected determines the type of the query variable.</span></span> <span data-ttu-id="9c4cf-119">Oto `name` ciąg.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-119">Here `name` is a string.</span></span> <span data-ttu-id="9c4cf-120">W związku z tym zmienna zapytania jest `IEnumerable<string>` .</span><span class="sxs-lookup"><span data-stu-id="9c4cf-120">Therefore, the query variable is an `IEnumerable<string>`.</span></span>  
  
3. <span data-ttu-id="9c4cf-121">Zmienna zapytania jest powtarzana w `foreach` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-121">The query variable is iterated over in the `foreach` statement.</span></span> <span data-ttu-id="9c4cf-122">Ponieważ zmienna zapytania jest sekwencją ciągów, Zmienna iteracji jest również ciągiem.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-122">Because the query variable is a sequence of strings, the iteration variable is also a string.</span></span>  
  
## <a name="queries-that-transform-the-source-data"></a><span data-ttu-id="9c4cf-123">Zapytania, które przekształcają dane źródłowe</span><span class="sxs-lookup"><span data-stu-id="9c4cf-123">Queries that Transform the Source Data</span></span>  

 <span data-ttu-id="9c4cf-124">Na poniższej ilustracji przedstawiono [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] operację zapytania, która wykonuje prostą transformację danych.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-124">The following illustration shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that performs a simple transformation on the data.</span></span> <span data-ttu-id="9c4cf-125">Zapytanie pobiera sekwencję `Customer` obiektów jako dane wejściowe i wybiera tylko `Name` Właściwość w wyniku.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-125">The query takes a sequence of `Customer` objects as input, and selects only the `Name` property in the result.</span></span> <span data-ttu-id="9c4cf-126">Ponieważ `Name` jest ciągiem, zapytanie tworzy sekwencję ciągów jako dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-126">Because `Name` is a string, the query produces a sequence of strings as output.</span></span>  
  
 ![Diagram przedstawiający zapytanie, które przekształca typ danych.](./media/type-relationships-in-linq-query-operations/linq-query-transform-data-type.png)  
  
1. <span data-ttu-id="9c4cf-128">Argument typu źródła danych określa typ zmiennej zakresu.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-128">The type argument of the data source determines the type of the range variable.</span></span>  
  
2. <span data-ttu-id="9c4cf-129">`select`Instrukcja zwraca `Name` właściwość zamiast kompletnego `Customer` obiektu.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-129">The `select` statement returns the `Name` property instead of the complete `Customer` object.</span></span> <span data-ttu-id="9c4cf-130">Ponieważ `Name` jest ciągiem, argument typu `custNameQuery` ma wartość, a `string` nie `Customer` .</span><span class="sxs-lookup"><span data-stu-id="9c4cf-130">Because `Name` is a string, the type argument of `custNameQuery` is `string`, not `Customer`.</span></span>  
  
3. <span data-ttu-id="9c4cf-131">Ponieważ `custNameQuery` jest sekwencją ciągów, `foreach` Zmienna iteracji pętli musi być również `string` .</span><span class="sxs-lookup"><span data-stu-id="9c4cf-131">Because `custNameQuery` is a sequence of strings, the `foreach` loop's iteration variable must also be a `string`.</span></span>  
  
 <span data-ttu-id="9c4cf-132">Na poniższej ilustracji przedstawiono nieco bardziej skomplikowaną transformację.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-132">The following illustration shows a slightly more complex transformation.</span></span> <span data-ttu-id="9c4cf-133">`select`Instrukcja zwraca typ anonimowy, który przechwytuje tylko dwa elementy członkowskie oryginalnego `Customer` obiektu.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-133">The `select` statement returns an anonymous type that captures just two members of the original `Customer` object.</span></span>  
  
 ![Diagram przedstawiający bardziej złożone zapytania, które przekształcają typ danych.](./media/type-relationships-in-linq-query-operations/linq-complex-query-transform-data-type.png)  
  
1. <span data-ttu-id="9c4cf-135">Argument typu źródła danych jest zawsze typem zmiennej zakresu w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-135">The type argument of the data source is always the type of the range variable in the query.</span></span>  
  
2. <span data-ttu-id="9c4cf-136">Ponieważ `select` instrukcja generuje typ anonimowy, zmienna zapytania musi być wpisana niejawnie przy użyciu `var` .</span><span class="sxs-lookup"><span data-stu-id="9c4cf-136">Because the `select` statement produces an anonymous type, the query variable must be implicitly typed by using `var`.</span></span>  
  
3. <span data-ttu-id="9c4cf-137">Ponieważ typ zmiennej zapytania jest niejawny, Zmienna iteracji w `foreach` pętli musi być również niejawna.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-137">Because the type of the query variable is implicit, the iteration variable in the `foreach` loop must also be implicit.</span></span>  
  
## <a name="letting-the-compiler-infer-type-information"></a><span data-ttu-id="9c4cf-138">Zezwalanie na informacje o typie wnioskowania kompilatora</span><span class="sxs-lookup"><span data-stu-id="9c4cf-138">Letting the compiler infer type information</span></span>  

 <span data-ttu-id="9c4cf-139">Chociaż należy zrozumieć relacje typu w operacji zapytania, masz możliwość zezwalania kompilatorowi na wykonywanie wszystkich zadań.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-139">Although you should understand the type relationships in a query operation, you have the option to let the compiler do all the work for you.</span></span> <span data-ttu-id="9c4cf-140">[Var](../../../language-reference/keywords/var.md) słowa kluczowego może być używana dla każdej zmiennej lokalnej w operacji zapytania.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-140">The keyword [var](../../../language-reference/keywords/var.md) can be used for any local variable in a query operation.</span></span> <span data-ttu-id="9c4cf-141">Poniższa ilustracja jest podobna do przykładu numer 2, który został omówiony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-141">The following illustration is similar to example number 2 that was discussed earlier.</span></span> <span data-ttu-id="9c4cf-142">Jednak kompilator dostarcza mocny typ dla każdej zmiennej w operacji zapytania.</span><span class="sxs-lookup"><span data-stu-id="9c4cf-142">However, the compiler supplies the strong type for each variable in the query operation.</span></span>  
  
 ![Diagram przedstawiający przepływ typu z niejawnym wpisywaniem.](./media/type-relationships-in-linq-query-operations/linq-type-flow-implicit-typing.png)  
  
 <span data-ttu-id="9c4cf-144">Aby uzyskać więcej informacji na temat `var` , zobacz [niejawnie wpisane zmienne lokalne](../../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="9c4cf-144">For more information about `var`, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
