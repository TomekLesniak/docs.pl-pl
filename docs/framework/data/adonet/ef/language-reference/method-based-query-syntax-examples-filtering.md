---
title: Przykłady składni zapytania oparte na metodzie, filtrowanie
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e40e314c-eb30-4f44-a054-41e511e35832
ms.openlocfilehash: 392181f201c7b18b1b38f62f5f35c5657cbbe601
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191999"
---
# <a name="method-based-query-syntax-examples-filtering"></a><span data-ttu-id="e2a06-102">Przykłady składni zapytania oparte na metodzie, filtrowanie</span><span class="sxs-lookup"><span data-stu-id="e2a06-102">Method-Based Query Syntax Examples: Filtering</span></span>

<span data-ttu-id="e2a06-103">W przykładach w tym temacie pokazano, jak za `Where` pomocą `Where…Contains` metod i zbadać [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) przy użyciu składni zapytania opartego na metodzie.</span><span class="sxs-lookup"><span data-stu-id="e2a06-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="e2a06-104">Uwaga, gdzie...`Contains`</span><span class="sxs-lookup"><span data-stu-id="e2a06-104">Note, Where…`Contains`</span></span> <span data-ttu-id="e2a06-105">nie można użyć jako części [skompilowanego zapytania](compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="e2a06-105">cannot be used as a part of a [compiled query](compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="e2a06-106">Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e2a06-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e2a06-107">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="e2a06-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="e2a06-108">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="e2a06-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="e2a06-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="e2a06-109">Example</span></span>  

 <span data-ttu-id="e2a06-110">Poniższy przykład zwraca wszystkie zamówienia online.</span><span class="sxs-lookup"><span data-stu-id="e2a06-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1_mq)]
 [!code-vb[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1_mq)]  
  
### <a name="example"></a><span data-ttu-id="e2a06-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="e2a06-111">Example</span></span>  

 <span data-ttu-id="e2a06-112">Poniższy przykład zwraca zamówienia, w których ilość zamówienia jest większa niż 2 i mniejsza niż 6.</span><span class="sxs-lookup"><span data-stu-id="e2a06-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2_mq)]
 [!code-vb[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2_mq)]  
  
### <a name="example"></a><span data-ttu-id="e2a06-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="e2a06-113">Example</span></span>  

 <span data-ttu-id="e2a06-114">Poniższy przykład zwraca wszystkie kolorowe produkty.</span><span class="sxs-lookup"><span data-stu-id="e2a06-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3_mq)]
 [!code-vb[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3_mq)]  
  
### <a name="example"></a><span data-ttu-id="e2a06-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="e2a06-115">Example</span></span>  

 <span data-ttu-id="e2a06-116">W poniższym przykładzie użyto `Where` metody, aby znaleźć zamówienia, które zostały wprowadzone po 1 grudnia 2003, a następnie użyć `order.SalesOrderDetail` właściwości nawigacji, aby uzyskać szczegółowe informacje dotyczące poszczególnych zamówień.</span><span class="sxs-lookup"><span data-stu-id="e2a06-116">The following example uses the `Where` method to find orders that were made after December 1, 2003 and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty_mq)]
 [!code-vb[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty_mq)]  
  
## <a name="wherecontains"></a><span data-ttu-id="e2a06-117">Gdzie... Wyświetlana</span><span class="sxs-lookup"><span data-stu-id="e2a06-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="e2a06-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="e2a06-118">Example</span></span>  

 <span data-ttu-id="e2a06-119">Poniższy przykład używa tablicy jako części `Where…Contains` klauzuli, aby znaleźć wszystkie produkty, które są `ProductModelID` zgodne z wartością w tablicy.</span><span class="sxs-lookup"><span data-stu-id="e2a06-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#3)]
 [!code-vb[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#3)]  
  
> [!NOTE]
> <span data-ttu-id="e2a06-120">Jako część predykatu w `Where…Contains` klauzuli, można użyć <xref:System.Array> , a <xref:System.Collections.Generic.List%601> lub kolekcji dowolnego typu, który implementuje <xref:System.Collections.Generic.IEnumerable%601> interfejs.</span><span class="sxs-lookup"><span data-stu-id="e2a06-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="e2a06-121">Można również zadeklarować i zainicjować kolekcję w ramach zapytania LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="e2a06-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="e2a06-122">Aby uzyskać więcej informacji, zobacz następny przykład.</span><span class="sxs-lookup"><span data-stu-id="e2a06-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e2a06-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="e2a06-123">Example</span></span>  

 <span data-ttu-id="e2a06-124">Poniższy przykład deklaruje i inicjuje tablice w `Where…Contains` klauzuli, aby znaleźć wszystkie produkty, które mają `ProductModelID` lub `Size` , które pasują do wartości w tablicach.</span><span class="sxs-lookup"><span data-stu-id="e2a06-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or a `Size` that matches a value in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#4)]
 [!code-vb[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e2a06-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e2a06-125">See also</span></span>

- [<span data-ttu-id="e2a06-126">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e2a06-126">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
