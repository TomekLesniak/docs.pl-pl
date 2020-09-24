---
title: 'Przykłady składni zapytania oparte na metodzie: operatory agregujące (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ed5f01d-acb2-4dd4-be60-f04c2d570fa8
ms.openlocfilehash: f702506e648c73dc179cf1755a467b13afce4bc6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164665"
---
# <a name="method-based-query-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="d56ed-102">Przykłady składni zapytania oparte na metodzie: operatory agregujące (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="d56ed-102">Method-Based Query Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>

<span data-ttu-id="d56ed-103">W przykładach w tym temacie pokazano, jak używać operatorów,,,,, <xref:System.Linq.Enumerable.Aggregate%2A> <xref:System.Linq.Enumerable.Average%2A> <xref:System.Linq.Enumerable.Count%2A> <xref:System.Linq.Enumerable.LongCount%2A> <xref:System.Linq.Enumerable.Max%2A> <xref:System.Linq.Enumerable.Min%2A> i <xref:System.Linq.Enumerable.Sum%2A> do wykonywania zapytań dotyczących <xref:System.Data.DataSet> danych i agregacji przy użyciu metody składni zapytania.</span><span class="sxs-lookup"><span data-stu-id="d56ed-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> operators to query a <xref:System.Data.DataSet> and aggregate data using method query syntax.</span></span>  
  
 <span data-ttu-id="d56ed-104">`FillDataSet`Metoda użyta w tych przykładach jest określona w temacie [ładowanie danych do zestawu danych](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="d56ed-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="d56ed-105">W przykładach w tym temacie użyto tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d56ed-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d56ed-106">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="d56ed-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="d56ed-107">Aby uzyskać więcej informacji, zobacz [How to: Create a LINQ to DataSet Project in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="d56ed-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="aggregate"></a><span data-ttu-id="d56ed-108">Agregacja</span><span class="sxs-lookup"><span data-stu-id="d56ed-108">Aggregate</span></span>  
  
### <a name="example"></a><span data-ttu-id="d56ed-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-109">Example</span></span>  

 <span data-ttu-id="d56ed-110">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Aggregate%2A> metodę, aby pobrać 5 pierwszych kontaktów z `Contact` tabeli i utworzyć rozdzielaną przecinkami listę nazwisk.</span><span class="sxs-lookup"><span data-stu-id="d56ed-110">This example uses the <xref:System.Linq.Enumerable.Aggregate%2A> method to get the first 5 contacts from the `Contact` table and build a comma-delimited list of the last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#aggregate_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#aggregate_mq)]  
  
## <a name="average"></a><span data-ttu-id="d56ed-111">Średnia</span><span class="sxs-lookup"><span data-stu-id="d56ed-111">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="d56ed-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-112">Example</span></span>  

 <span data-ttu-id="d56ed-113">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Average%2A> metodę, aby znaleźć średnią cenę cennika produktów.</span><span class="sxs-lookup"><span data-stu-id="d56ed-113">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-114">Example</span></span>  

 <span data-ttu-id="d56ed-115">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Average%2A> metodę w celu wyszukania średniej ceny za produkty poszczególnych stylów.</span><span class="sxs-lookup"><span data-stu-id="d56ed-115">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-116">Example</span></span>  

 <span data-ttu-id="d56ed-117">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Average%2A> metodę, aby znaleźć średnią należną kwotę.</span><span class="sxs-lookup"><span data-stu-id="d56ed-117">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-118">Example</span></span>  

 <span data-ttu-id="d56ed-119">Ten przykład używa <xref:System.Linq.Enumerable.Average%2A> metody, aby uzyskać średnią łączną liczbę należną dla każdego identyfikatora osoby kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="d56ed-119">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-120">Example</span></span>  

 <span data-ttu-id="d56ed-121">Ten przykład używa <xref:System.Linq.Enumerable.Average%2A> metody, aby uzyskać zamówienia z średnią `TotalDue` dla każdego kontaktu.</span><span class="sxs-lookup"><span data-stu-id="d56ed-121">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="d56ed-122">Liczba</span><span class="sxs-lookup"><span data-stu-id="d56ed-122">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="d56ed-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-123">Example</span></span>  

 <span data-ttu-id="d56ed-124">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Count%2A> metodę, aby zwrócić liczbę produktów w `Product` tabeli.</span><span class="sxs-lookup"><span data-stu-id="d56ed-124">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the `Product` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#count)]
 [!code-vb[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-125">Example</span></span>  

 <span data-ttu-id="d56ed-126">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Count%2A> metodę, aby zwrócić listę identyfikatorów kontaktu oraz liczbę zamówień, które każdy z nich ma.</span><span class="sxs-lookup"><span data-stu-id="d56ed-126">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-127">Example</span></span>  

 <span data-ttu-id="d56ed-128">Ten przykład grupuje produkty według koloru i używa <xref:System.Linq.Enumerable.Count%2A> metody do zwrócenia liczby produktów w każdej grupie kolorów.</span><span class="sxs-lookup"><span data-stu-id="d56ed-128">This example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="d56ed-129">LongCount</span><span class="sxs-lookup"><span data-stu-id="d56ed-129">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="d56ed-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-130">Example</span></span>  

 <span data-ttu-id="d56ed-131">Ten przykład pobiera liczbę kontaktów jako długą liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="d56ed-131">This example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="d56ed-132">Maks.</span><span class="sxs-lookup"><span data-stu-id="d56ed-132">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="d56ed-133">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-133">Example</span></span>  

 <span data-ttu-id="d56ed-134">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Max%2A> metodę w celu uzyskania największej wartości całkowitej.</span><span class="sxs-lookup"><span data-stu-id="d56ed-134">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-135">Example</span></span>  

 <span data-ttu-id="d56ed-136">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Max%2A> metodę, aby uzyskać największą łączną ilość należną dla każdego identyfikatora osoby kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="d56ed-136">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-137">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-137">Example</span></span>  

 <span data-ttu-id="d56ed-138">Ten przykład używa <xref:System.Linq.Enumerable.Max%2A> metody, aby uzyskać zamówienia o największych `TotalDue` dla każdego identyfikatora osoby kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="d56ed-138">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="d56ed-139">Min.</span><span class="sxs-lookup"><span data-stu-id="d56ed-139">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="d56ed-140">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-140">Example</span></span>  

 <span data-ttu-id="d56ed-141">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Min%2A> metodę w celu uzyskania najmniejszej liczby zaległych.</span><span class="sxs-lookup"><span data-stu-id="d56ed-141">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-142">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-142">Example</span></span>  

 <span data-ttu-id="d56ed-143">Ten przykład używa <xref:System.Linq.Enumerable.Min%2A> metody, aby uzyskać najmniejszą łączną ilość należną dla każdego identyfikatora osoby kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="d56ed-143">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-144">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-144">Example</span></span>  

 <span data-ttu-id="d56ed-145">Ten przykład używa <xref:System.Linq.Enumerable.Min%2A> metody, aby uzyskać zamówienia z najmniejszą łączną należną dla każdego kontaktu.</span><span class="sxs-lookup"><span data-stu-id="d56ed-145">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="d56ed-146">Suma</span><span class="sxs-lookup"><span data-stu-id="d56ed-146">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="d56ed-147">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-147">Example</span></span>  

 <span data-ttu-id="d56ed-148">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Sum%2A> metodę, aby uzyskać łączną liczbę wielkości zamówienia w `SalesOrderDetail` tabeli.</span><span class="sxs-lookup"><span data-stu-id="d56ed-148">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the `SalesOrderDetail` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="d56ed-149">Przykład</span><span class="sxs-lookup"><span data-stu-id="d56ed-149">Example</span></span>  

 <span data-ttu-id="d56ed-150">Ten przykład używa <xref:System.Linq.Enumerable.Sum%2A> metody, aby uzyskać łączną ilość należną dla każdego identyfikatora osoby kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="d56ed-150">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="d56ed-151">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d56ed-151">See also</span></span>

- [<span data-ttu-id="d56ed-152">Ładowanie danych do zestawu danych</span><span class="sxs-lookup"><span data-stu-id="d56ed-152">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="d56ed-153">Przykłady LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d56ed-153">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="d56ed-154">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="d56ed-154">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="d56ed-155">Standardowe operatory zapytań — Omówienie (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d56ed-155">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
