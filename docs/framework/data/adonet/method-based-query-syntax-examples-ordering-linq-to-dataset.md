---
title: 'Przykłady składni zapytania oparte na metodzie: porządkowanie (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
ms.openlocfilehash: 635b7f6e498e27ef8ca2e133df639f1010184a93
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197875"
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="65685-102">Przykłady składni zapytania oparte na metodzie: porządkowanie (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="65685-102">Method-Based Query Syntax Examples: Ordering (LINQ to DataSet)</span></span>

<span data-ttu-id="65685-103">W przykładach w tym temacie pokazano, jak używać <xref:System.Linq.Enumerable.OrderBy%2A>  <xref:System.Linq.Enumerable.Reverse%2A> metod, i <xref:System.Linq.Enumerable.ThenBy%2A> do wykonywania zapytań <xref:System.Data.DataSet> i kolejności wyników przy użyciu składni zapytania metody.</span><span class="sxs-lookup"><span data-stu-id="65685-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>,  <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenBy%2A> methods to query a <xref:System.Data.DataSet> and order the results using the method query syntax.</span></span>  
  
 <span data-ttu-id="65685-104">`FillDataSet`Metoda użyta w tych przykładach jest określona w temacie [ładowanie danych do zestawu danych](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="65685-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="65685-105">W przykładach w tym temacie użyto tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="65685-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="65685-106">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="65685-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="65685-107">Aby uzyskać więcej informacji, zobacz [How to: Create a LINQ to DataSet Project in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="65685-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="65685-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="65685-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="65685-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="65685-109">Example</span></span>  

 <span data-ttu-id="65685-110">Ten przykład używa <xref:System.Linq.Enumerable.OrderBy%2A> metody z niestandardową funkcją porównującą, aby wykonać sortowanie ostatnich nazw bez uwzględniania wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="65685-110">This example uses the <xref:System.Linq.Enumerable.OrderBy%2A> method with a custom comparer to do a case-insensitive sort of last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a><span data-ttu-id="65685-111">Reverse</span><span class="sxs-lookup"><span data-stu-id="65685-111">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="65685-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="65685-112">Example</span></span>  

 <span data-ttu-id="65685-113">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Reverse%2A> metodę, aby utworzyć listę zamówień, która `OrderDate` jest wcześniejsza niż 20 lutego 2002.</span><span class="sxs-lookup"><span data-stu-id="65685-113">This example uses the <xref:System.Linq.Enumerable.Reverse%2A> method to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a><span data-ttu-id="65685-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="65685-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="65685-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="65685-115">Example</span></span>  

 <span data-ttu-id="65685-116">Ten przykład używa <xref:System.Linq.Enumerable.OrderBy%2A> <xref:System.Linq.Enumerable.ThenBy%2A> metod i z niestandardowymi modułami porównującymi, aby najpierw sortować według cennika, a następnie wykonywać sortowanie nazw produktów bez uwzględniania wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="65685-116">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.ThenBy%2A> methods with a custom comparer to first sort by list price, and then perform a case-insensitive descending sort of the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="65685-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="65685-117">See also</span></span>

- [<span data-ttu-id="65685-118">Ładowanie danych do zestawu danych</span><span class="sxs-lookup"><span data-stu-id="65685-118">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="65685-119">Przykłady LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="65685-119">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="65685-120">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="65685-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="65685-121">Standardowe operatory zapytań — Omówienie (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65685-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
