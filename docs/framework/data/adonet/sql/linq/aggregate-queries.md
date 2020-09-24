---
title: Zapytania zagregowane
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 8dfe24a84c707b6d21afb7ccfc57ac7b0423942f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161545"
---
# <a name="aggregate-queries"></a><span data-ttu-id="753e5-102">Zapytania zagregowane</span><span class="sxs-lookup"><span data-stu-id="753e5-102">Aggregate Queries</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="753e5-103">obsługuje `Average` operatory, `Count` , `Max` , `Min` i `Sum` agregacji.</span><span class="sxs-lookup"><span data-stu-id="753e5-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="753e5-104">Zwróć uwagę na następujące cechy agregacji operatorów w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="753e5-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="753e5-105">Zapytania agregujące są wykonywane natychmiastowo.</span><span class="sxs-lookup"><span data-stu-id="753e5-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="753e5-106">Aby uzyskać więcej informacji, zobacz [wprowadzenie do zapytań LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="753e5-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="753e5-107">Zapytania agregujące zwykle zwracają liczbę zamiast kolekcji.</span><span class="sxs-lookup"><span data-stu-id="753e5-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="753e5-108">Aby uzyskać więcej informacji, zobacz [operacje agregacji](/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="753e5-108">For more information, see [Aggregation Operations](/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="753e5-109">Nie można wywoływać agregacji dla typów anonimowych.</span><span class="sxs-lookup"><span data-stu-id="753e5-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="753e5-110">Przykłady w poniższych tematach pochodzą z przykładowej bazy danych Northwind.</span><span class="sxs-lookup"><span data-stu-id="753e5-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="753e5-111">Aby uzyskać więcej informacji, zobacz [Pobieranie przykładowych baz danych](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="753e5-111">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="753e5-112">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="753e5-112">In This Section</span></span>  

 [<span data-ttu-id="753e5-113">Zwracanie średniej wartości z sekwencji numerycznej</span><span class="sxs-lookup"><span data-stu-id="753e5-113">Return the Average Value From a Numeric Sequence</span></span>](return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="753e5-114">Pokazuje, jak używać <xref:System.Linq.Enumerable.Average%2A> operatora.</span><span class="sxs-lookup"><span data-stu-id="753e5-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="753e5-115">Licznik liczby elementów w sekwencji</span><span class="sxs-lookup"><span data-stu-id="753e5-115">Count the Number of Elements in a Sequence</span></span>](count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="753e5-116">Pokazuje, jak używać <xref:System.Linq.Enumerable.Count%2A> operatora.</span><span class="sxs-lookup"><span data-stu-id="753e5-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="753e5-117">Odnajdywanie wartości maksymalnej w sekwencji numerycznej</span><span class="sxs-lookup"><span data-stu-id="753e5-117">Find the Maximum Value in a Numeric Sequence</span></span>](find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="753e5-118">Pokazuje, jak używać <xref:System.Linq.Enumerable.Max%2A> operatora.</span><span class="sxs-lookup"><span data-stu-id="753e5-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="753e5-119">Odnajdywanie wartości minimalnej w sekwencji numerycznej</span><span class="sxs-lookup"><span data-stu-id="753e5-119">Find the Minimum Value in a Numeric Sequence</span></span>](find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="753e5-120">Pokazuje, jak używać <xref:System.Linq.Enumerable.Min%2A> operatora.</span><span class="sxs-lookup"><span data-stu-id="753e5-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="753e5-121">Obliczanie sumy wartości w sekwencji numerycznej</span><span class="sxs-lookup"><span data-stu-id="753e5-121">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="753e5-122">Pokazuje, jak używać <xref:System.Linq.Enumerable.Sum%2A> operatora.</span><span class="sxs-lookup"><span data-stu-id="753e5-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="753e5-123">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="753e5-123">Related Sections</span></span>  

 [<span data-ttu-id="753e5-124">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="753e5-124">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="753e5-125">Oferuje linki do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zapytań w Visual Basic i C#.</span><span class="sxs-lookup"><span data-stu-id="753e5-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="753e5-126">Pojęcia dotyczące zapytań</span><span class="sxs-lookup"><span data-stu-id="753e5-126">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="753e5-127">Zawiera łącza do tematów objaśniających koncepcje projektowania zapytań LINQ w programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="753e5-127">Provides links to topics that explain concepts for designing LINQ queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="753e5-128">Wprowadzenie do kwerend LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="753e5-128">Introduction to LINQ Queries (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="753e5-129">Wyjaśnia, w jaki sposób zapytania działają w LINQ.</span><span class="sxs-lookup"><span data-stu-id="753e5-129">Explains how queries work in LINQ.</span></span>
