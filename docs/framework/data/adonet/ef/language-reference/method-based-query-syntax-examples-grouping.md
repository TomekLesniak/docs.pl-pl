---
title: Przykłady składni zapytania oparte na metodzie, grupowanie
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 2d84e755217878bfa248add37a752224a20d3f84
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191986"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="805f3-102">Przykłady składni zapytania oparte na metodzie, grupowanie</span><span class="sxs-lookup"><span data-stu-id="805f3-102">Method-Based Query Syntax Examples: Grouping</span></span>

<span data-ttu-id="805f3-103">W przykładach w tym temacie pokazano, jak używać `GroupBy` metody do wykonywania zapytań względem [modelu sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) przy użyciu składni zapytania opartego na metodzie.</span><span class="sxs-lookup"><span data-stu-id="805f3-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="805f3-104">Model sprzedaży AdventureWorks używany w tych przykładach jest oparty na tabelach Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="805f3-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="805f3-105">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="805f3-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="805f3-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="805f3-106">Example</span></span>  

 <span data-ttu-id="805f3-107">W poniższym przykładzie zastosowano `GroupBy` metodę w celu zwrócenia `Address` obiektów, które są pogrupowane według kodu pocztowego.</span><span class="sxs-lookup"><span data-stu-id="805f3-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="805f3-108">Wyniki są rzutowane na typ anonimowy.</span><span class="sxs-lookup"><span data-stu-id="805f3-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="805f3-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="805f3-109">Example</span></span>  

 <span data-ttu-id="805f3-110">W poniższym przykładzie zastosowano `GroupBy` metodę w celu zwrócenia `Contact` obiektów, które są pogrupowane według pierwszej litery nazwisko kontaktu.</span><span class="sxs-lookup"><span data-stu-id="805f3-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="805f3-111">Wyniki są również sortowane według pierwszej litery ostatniej nazwy i są rzutowane na typ anonimowy.</span><span class="sxs-lookup"><span data-stu-id="805f3-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="805f3-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="805f3-112">Example</span></span>  

 <span data-ttu-id="805f3-113">W poniższym przykładzie zastosowano `GroupBy` metodę w celu zwrócenia `SalesOrderHeader` obiektów, które są pogrupowane według identyfikatora klienta.</span><span class="sxs-lookup"><span data-stu-id="805f3-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="805f3-114">Zwracana jest również liczba sprzedaży dla każdego klienta.</span><span class="sxs-lookup"><span data-stu-id="805f3-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="805f3-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="805f3-115">See also</span></span>

- [<span data-ttu-id="805f3-116">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="805f3-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
