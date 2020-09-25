---
title: Przykłady składni zapytania oparte na metodzie, operatory elementu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 96d393a34af69935e75582ef1954ddd661a355f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192051"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="7dd4c-102">Przykłady składni zapytania oparte na metodzie, operatory elementu</span><span class="sxs-lookup"><span data-stu-id="7dd4c-102">Method-Based Query Syntax Examples: Element Operators</span></span>

<span data-ttu-id="7dd4c-103">W przykładach w tym temacie pokazano, jak używać <xref:System.Linq.Enumerable.First%2A> metody do wykonywania zapytań względem [modelu sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) przy użyciu składni zapytania opartego na metodzie.</span><span class="sxs-lookup"><span data-stu-id="7dd4c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="7dd4c-104">Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7dd4c-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="7dd4c-105">W przykładzie w tym temacie są stosowane następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="7dd4c-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="7dd4c-106">Pierwsze</span><span class="sxs-lookup"><span data-stu-id="7dd4c-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="7dd4c-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="7dd4c-107">Example</span></span>  

 <span data-ttu-id="7dd4c-108">W poniższym przykładzie zastosowano <xref:System.Linq.Enumerable.First%2A> metodę w celu znalezienia pierwszego adresu e-mail, który rozpoczyna się od "Caroline".</span><span class="sxs-lookup"><span data-stu-id="7dd4c-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="7dd4c-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7dd4c-109">See also</span></span>

- [<span data-ttu-id="7dd4c-110">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="7dd4c-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
