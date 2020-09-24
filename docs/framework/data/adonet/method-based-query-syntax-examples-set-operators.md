---
title: 'Przykłady składni zapytania oparte na metodzie: Ustaw operatory (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: f91d009e66f1f0da25e508994040d7e9f80fc681
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147869"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="566d1-102">Przykłady składni zapytania oparte na metodzie: Ustaw operatory (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="566d1-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>

<span data-ttu-id="566d1-103">W przykładach w tym temacie pokazano, jak używać <xref:System.Linq.Enumerable.Distinct%2A> <xref:System.Linq.Enumerable.Except%2A> operatorów,, <xref:System.Linq.Enumerable.Intersect%2A> i <xref:System.Linq.Enumerable.Union%2A> do wykonywania operacji porównania na podstawie wartości na zestawach wierszy danych.[ Ładowanie danych do zestawu danych](loading-data-into-a-dataset.md) zobacz [porównywanie wierszy DataRows](comparing-datarows-linq-to-dataset.md) , aby uzyskać więcej informacji na temat <xref:System.Data.DataRowComparer> .</span><span class="sxs-lookup"><span data-stu-id="566d1-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](loading-data-into-a-dataset.md) See [Comparing DataRows](comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="566d1-104">`FillDataSet`Metoda użyta w tych przykładach jest określona w temacie [ładowanie danych do zestawu danych](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="566d1-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="566d1-105">W przykładach w tym temacie użyto tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="566d1-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="566d1-106">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="566d1-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="566d1-107">Aby uzyskać więcej informacji, zobacz [How to: Create a LINQ to DataSet Project in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="566d1-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="566d1-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="566d1-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="566d1-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="566d1-109">Example</span></span>  

 <span data-ttu-id="566d1-110">W tym przykładzie użyto <xref:System.Linq.Enumerable.Distinct%2A> metody, aby usunąć zduplikowane elementy w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="566d1-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="566d1-111">Z wyjątkiem</span><span class="sxs-lookup"><span data-stu-id="566d1-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="566d1-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="566d1-112">Example</span></span>  

 <span data-ttu-id="566d1-113">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Except%2A> metodę, aby zwrócić kontakty, które pojawiają się w pierwszej tabeli, ale nie w drugim.</span><span class="sxs-lookup"><span data-stu-id="566d1-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="566d1-114">Wspólnej</span><span class="sxs-lookup"><span data-stu-id="566d1-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="566d1-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="566d1-115">Example</span></span>  

 <span data-ttu-id="566d1-116">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Intersect%2A> metodę, aby zwrócić kontakty, które są wyświetlane w obu tabelach.</span><span class="sxs-lookup"><span data-stu-id="566d1-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="566d1-117">Unia</span><span class="sxs-lookup"><span data-stu-id="566d1-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="566d1-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="566d1-118">Example</span></span>  

 <span data-ttu-id="566d1-119">W tym przykładzie zastosowano <xref:System.Linq.Enumerable.Union%2A> metodę w celu zwrócenia unikatowych kontaktów z jednej z dwóch tabel.</span><span class="sxs-lookup"><span data-stu-id="566d1-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="566d1-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="566d1-120">See also</span></span>

- [<span data-ttu-id="566d1-121">Ładowanie danych do zestawu danych</span><span class="sxs-lookup"><span data-stu-id="566d1-121">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="566d1-122">Przykłady LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="566d1-122">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="566d1-123">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="566d1-123">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="566d1-124">Standardowe operatory zapytań — Omówienie (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566d1-124">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
