---
title: Przykłady składni wyrażeń zapytania, porządkowanie
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
ms.openlocfilehash: ed03fc248ed48f56998bc27f7e880b1e8aa443d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156787"
---
# <a name="query-expression-syntax-examples-ordering"></a><span data-ttu-id="38a2f-102">Przykłady składni wyrażeń zapytania, porządkowanie</span><span class="sxs-lookup"><span data-stu-id="38a2f-102">Query Expression Syntax Examples: Ordering</span></span>

<span data-ttu-id="38a2f-103">W przykładach w tym temacie pokazano, jak za `OrderBy` pomocą `OrderByDescending` metod i zbadać [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) przy użyciu składni wyrażeń zapytań.</span><span class="sxs-lookup"><span data-stu-id="38a2f-103">The examples in this topic demonstrate how to use the `OrderBy` and `OrderByDescending` methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="38a2f-104">Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="38a2f-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="38a2f-105">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="38a2f-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a><span data-ttu-id="38a2f-106">OrderBy</span><span class="sxs-lookup"><span data-stu-id="38a2f-106">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="38a2f-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="38a2f-107">Example</span></span>  

 <span data-ttu-id="38a2f-108">Poniższy przykład używa <xref:System.Linq.Enumerable.OrderBy%2A> do zwracania listy kontaktów uporządkowanych według nazwiska.</span><span class="sxs-lookup"><span data-stu-id="38a2f-108">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="38a2f-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="38a2f-109">Example</span></span>  

 <span data-ttu-id="38a2f-110">Poniższy przykład używa <xref:System.Linq.Enumerable.OrderBy%2A> do sortowania listy kontaktów według długości nazwiska.</span><span class="sxs-lookup"><span data-stu-id="38a2f-110">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="38a2f-111">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="38a2f-111">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="38a2f-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="38a2f-112">Example</span></span>  

 <span data-ttu-id="38a2f-113">Poniższy przykład używa `orderby… descending` ( `Order By … Descending` w Visual Basic), który jest odpowiednikiem <xref:System.Linq.Enumerable.OrderByDescending%2A> metody, aby posortować Cennik od najwyższego do najniższego.</span><span class="sxs-lookup"><span data-stu-id="38a2f-113">The following example uses `orderby… descending` (`Order By … Descending` in Visual Basic), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a><span data-ttu-id="38a2f-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="38a2f-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="38a2f-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="38a2f-115">Example</span></span>  

 <span data-ttu-id="38a2f-116">Poniższy przykład używa <xref:System.Linq.Queryable.OrderBy%2A> i <xref:System.Linq.Queryable.ThenBy%2A> zwraca listę kontaktów uporządkowanych według nazwiska, a następnie według imienia i nazwiska.</span><span class="sxs-lookup"><span data-stu-id="38a2f-116">The following example uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="38a2f-117">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="38a2f-117">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="38a2f-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="38a2f-118">Example</span></span>  

 <span data-ttu-id="38a2f-119">Poniższy przykład używa `OrderBy… Descending` , który jest odpowiednikiem <xref:System.Linq.Enumerable.ThenByDescending%2A> metody, aby posortować listę produktów, najpierw według nazwy, a następnie według cennika od najwyższego do najniższego.</span><span class="sxs-lookup"><span data-stu-id="38a2f-119">The following example uses `OrderBy… Descending`, which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="38a2f-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="38a2f-120">See also</span></span>

- [<span data-ttu-id="38a2f-121">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="38a2f-121">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
