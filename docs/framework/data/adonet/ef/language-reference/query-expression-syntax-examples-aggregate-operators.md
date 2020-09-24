---
title: Przykłady składni wyrażeń zapytania, operatory agregacji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
ms.openlocfilehash: 4842bdb3aeb024afc72bde43d056b48b0d8258b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153004"
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="4bd4c-102">Przykłady składni wyrażeń zapytania, operatory agregacji</span><span class="sxs-lookup"><span data-stu-id="4bd4c-102">Query Expression Syntax Examples: Aggregate Operators</span></span>

<span data-ttu-id="4bd4c-103">W przykładach w tym temacie przedstawiono sposób użycia <xref:System.Linq.Enumerable.Average%2A> metod, <xref:System.Linq.Enumerable.Count%2A> , <xref:System.Linq.Enumerable.Max%2A> , <xref:System.Linq.Enumerable.Min%2A> i <xref:System.Linq.Enumerable.Sum%2A> do wykonywania zapytań dotyczących [modelu sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) przy użyciu składni wyrażeń zapytań.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="4bd4c-104">Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="4bd4c-105">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="4bd4c-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="4bd4c-106">Średnia</span><span class="sxs-lookup"><span data-stu-id="4bd4c-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="4bd4c-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="4bd4c-107">Example</span></span>  

 <span data-ttu-id="4bd4c-108">W poniższym przykładzie zastosowano <xref:System.Linq.Enumerable.Average%2A> metodę w celu wyszukania średniej ceny za produkty poszczególnych stylów.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="4bd4c-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="4bd4c-109">Example</span></span>  

 <span data-ttu-id="4bd4c-110">Poniższy przykład używa, <xref:System.Linq.Enumerable.Average%2A> Aby pobrać średnią łączną liczbę należną dla każdego identyfikatora osoby kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-110">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="4bd4c-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="4bd4c-111">Example</span></span>  

 <span data-ttu-id="4bd4c-112">Poniższy przykład używa, <xref:System.Linq.Enumerable.Average%2A> Aby uzyskać zamówienia z średnią sumą należną dla każdego kontaktu.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-112">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="4bd4c-113">Liczba</span><span class="sxs-lookup"><span data-stu-id="4bd4c-113">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="4bd4c-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="4bd4c-114">Example</span></span>  

 <span data-ttu-id="4bd4c-115">Poniższy przykład używa <xref:System.Linq.Enumerable.Count%2A> do zwracania listy identyfikatorów kontaktu oraz liczby zamówień, z których każdy ma.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-115">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="4bd4c-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="4bd4c-116">Example</span></span>  

 <span data-ttu-id="4bd4c-117">Poniższy przykład grupuje produkty według koloru i używa <xref:System.Linq.Enumerable.Count%2A> do zwracania liczby produktów w każdej grupie kolorów.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-117">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="4bd4c-118">Maks.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-118">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="4bd4c-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="4bd4c-119">Example</span></span>  

 <span data-ttu-id="4bd4c-120">W poniższym przykładzie zastosowano <xref:System.Linq.Enumerable.Max%2A> metodę w celu uzyskania największego łącznego terminu dla każdego identyfikatora osoby kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-120">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="4bd4c-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="4bd4c-121">Example</span></span>  

 <span data-ttu-id="4bd4c-122">Poniższy przykład używa metody, <xref:System.Linq.Enumerable.Max%2A> Aby uzyskać zamówienia z największą sumą należną dla każdego identyfikatora osoby kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-122">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="4bd4c-123">Min.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-123">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="4bd4c-124">Przykład</span><span class="sxs-lookup"><span data-stu-id="4bd4c-124">Example</span></span>  

 <span data-ttu-id="4bd4c-125">Poniższy przykład używa metody, <xref:System.Linq.Enumerable.Min%2A> Aby uzyskać najmniejszą łączną ilość należną dla każdego identyfikatora osoby kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-125">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="4bd4c-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="4bd4c-126">Example</span></span>  

 <span data-ttu-id="4bd4c-127">Poniższy przykład używa metody, <xref:System.Linq.Enumerable.Min%2A> Aby uzyskać zamówienia o najmniejszej łącznej wartości należnej dla każdego kontaktu.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-127">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="4bd4c-128">Suma</span><span class="sxs-lookup"><span data-stu-id="4bd4c-128">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="4bd4c-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="4bd4c-129">Example</span></span>  

 <span data-ttu-id="4bd4c-130">W poniższym przykładzie zastosowano <xref:System.Linq.Enumerable.Sum%2A> metodę, aby uzyskać łączną ilość należną dla każdego identyfikatora osoby kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-130">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="4bd4c-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4bd4c-131">See also</span></span>

- [<span data-ttu-id="4bd4c-132">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4bd4c-132">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
