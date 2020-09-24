---
title: Przykłady składni zapytania oparte na metodzie, porządkowanie
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: 02889fb4172d24634cdcb1c8384a804b2ce1a0e8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191934"
---
# <a name="method-based-query-syntax-examples-ordering"></a><span data-ttu-id="c0d2e-102">Przykłady składni zapytania oparte na metodzie, porządkowanie</span><span class="sxs-lookup"><span data-stu-id="c0d2e-102">Method-Based Query Syntax Examples: Ordering</span></span>

<span data-ttu-id="c0d2e-103">W przykładach w tym temacie pokazano, jak używać <xref:System.Linq.Enumerable.ThenBy%2A> metody do wykonywania zapytań względem [modelu sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) przy użyciu składni zapytania opartego na metodzie.</span><span class="sxs-lookup"><span data-stu-id="c0d2e-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ThenBy%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="c0d2e-104">Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c0d2e-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="c0d2e-105">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="c0d2e-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a><span data-ttu-id="c0d2e-106">ThenBy</span><span class="sxs-lookup"><span data-stu-id="c0d2e-106">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="c0d2e-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="c0d2e-107">Example</span></span>  

 <span data-ttu-id="c0d2e-108">Poniższy przykład w składni zapytania opartej na metodzie <xref:System.Linq.Queryable.OrderBy%2A> i <xref:System.Linq.Queryable.ThenBy%2A> zwraca listę kontaktów uporządkowanych według imienia i nazwiska, a następnie według imienia i nazwiska.</span><span class="sxs-lookup"><span data-stu-id="c0d2e-108">The following example in method-based query syntax uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="c0d2e-109">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="c0d2e-109">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="c0d2e-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="c0d2e-110">Example</span></span>  

 <span data-ttu-id="c0d2e-111">W poniższym przykładzie zastosowano <xref:System.Linq.Queryable.OrderBy%2A> metody i, <xref:System.Linq.Queryable.ThenByDescending%2A> Aby najpierw posortować według cennika, a następnie wykonać malejące sortowanie nazw produktów.</span><span class="sxs-lookup"><span data-stu-id="c0d2e-111">The following example uses the <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenByDescending%2A> methods to first sort by list price, and then perform a descending sort of the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="c0d2e-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c0d2e-112">See also</span></span>

- [<span data-ttu-id="c0d2e-113">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c0d2e-113">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
