---
title: Przykłady składni zapytania oparte na metodzie, projekcja
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: 32db3d0f85e525ad1850df59f0abe66bf82b137b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175788"
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="3ece4-102">Przykłady składni zapytania oparte na metodzie, projekcja</span><span class="sxs-lookup"><span data-stu-id="3ece4-102">Method-Based Query Syntax Examples: Projection</span></span>

<span data-ttu-id="3ece4-103">W przykładach w tym temacie pokazano, jak za <xref:System.Linq.Enumerable.Select%2A> pomocą <xref:System.Linq.Enumerable.SelectMany%2A> metod i zbadać [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) przy użyciu składni zapytania opartego na metodzie.</span><span class="sxs-lookup"><span data-stu-id="3ece4-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="3ece4-104">Model sprzedaży AdventureWorks używany w tych przykładach jest tworzony na podstawie tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3ece4-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="3ece4-105">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="3ece4-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="3ece4-106">Wybierz pozycję</span><span class="sxs-lookup"><span data-stu-id="3ece4-106">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="3ece4-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="3ece4-107">Example</span></span>  

 <span data-ttu-id="3ece4-108">W poniższym przykładzie zastosowano <xref:System.Linq.Queryable.Select%2A> metodę w celu zaprojektowania `Product.Name` `Product.ProductID` właściwości i w sekwencji typów anonimowych.</span><span class="sxs-lookup"><span data-stu-id="3ece4-108">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="3ece4-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="3ece4-109">Example</span></span>  

 <span data-ttu-id="3ece4-110">W poniższym przykładzie zastosowano <xref:System.Linq.Enumerable.Select%2A> metodę, aby zwrócić sekwencję tylko nazw produktów.</span><span class="sxs-lookup"><span data-stu-id="3ece4-110">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="3ece4-111">SelectMany</span><span class="sxs-lookup"><span data-stu-id="3ece4-111">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="3ece4-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="3ece4-112">Example</span></span>  

 <span data-ttu-id="3ece4-113">W poniższym przykładzie zastosowano <xref:System.Linq.Enumerable.SelectMany%2A> metodę, aby wybrać wszystkie zamówienia, których `TotalDue` wartość jest mniejsza niż 500,00.</span><span class="sxs-lookup"><span data-stu-id="3ece4-113">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="3ece4-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="3ece4-114">Example</span></span>  

 <span data-ttu-id="3ece4-115">W poniższym przykładzie użyto <xref:System.Linq.Enumerable.SelectMany%2A> metody, aby wybrać wszystkie zamówienia, w których zamówienie zostało wykonane w dniu 1 października 2002 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="3ece4-115">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="3ece4-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3ece4-116">See also</span></span>

- [<span data-ttu-id="3ece4-117">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="3ece4-117">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
