---
title: Przykłady składni wyrażeń zapytania, operatory elementu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 8cd550120e949f247a17ca6c7dafca06607a4e7e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152991"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="59673-102">Przykłady składni wyrażeń zapytania, operatory elementu</span><span class="sxs-lookup"><span data-stu-id="59673-102">Query Expression Syntax Examples: Element Operators</span></span>

<span data-ttu-id="59673-103">W przykładach w tym temacie pokazano, jak używać <xref:System.Linq.Enumerable.First%2A> metody do wykonywania zapytań względem [modelu sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) przy użyciu składni wyrażenia zapytania.</span><span class="sxs-lookup"><span data-stu-id="59673-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using the query expression syntax.</span></span> <span data-ttu-id="59673-104">Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="59673-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="59673-105">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="59673-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="59673-106">Pierwsze</span><span class="sxs-lookup"><span data-stu-id="59673-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="59673-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="59673-107">Example</span></span>  

 <span data-ttu-id="59673-108">Poniższy przykład używa <xref:System.Linq.Enumerable.First%2A> metody do zwrócenia pierwszego kontaktu, którego imię ma wartość "Brooke".</span><span class="sxs-lookup"><span data-stu-id="59673-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="59673-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="59673-109">See also</span></span>

- [<span data-ttu-id="59673-110">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="59673-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
