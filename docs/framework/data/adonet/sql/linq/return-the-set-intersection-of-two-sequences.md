---
title: Zwracanie zestawu części wspólnych dwóch sekwencji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 421ec544345e41f910bf80c855a3a6b4de1c46a6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200228"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="c986a-102">Zwracanie zestawu części wspólnych dwóch sekwencji</span><span class="sxs-lookup"><span data-stu-id="c986a-102">Return the Set Intersection of Two Sequences</span></span>

<span data-ttu-id="c986a-103">Użyj <xref:System.Linq.Queryable.Intersect%2A> operatora, aby zwrócić zestaw przecięcia z dwiema sekwencjami.</span><span class="sxs-lookup"><span data-stu-id="c986a-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c986a-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="c986a-104">Example</span></span>  

 <span data-ttu-id="c986a-105">Ten przykład używa <xref:System.Linq.Queryable.Intersect%2A> do zwracania sekwencji wszystkich krajów/regionów, w których zarówno `Customers` , jak i na `Employees` żywo.</span><span class="sxs-lookup"><span data-stu-id="c986a-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="c986a-106">W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Linq.Queryable.Intersect%2A> operacja jest również zdefiniowana tylko dla zestawów.</span><span class="sxs-lookup"><span data-stu-id="c986a-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="c986a-107">Semantyka dla wielozestawów jest niezdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="c986a-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c986a-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c986a-108">See also</span></span>

- [<span data-ttu-id="c986a-109">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="c986a-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="c986a-110">Translacja standardowego operatora zapytania</span><span class="sxs-lookup"><span data-stu-id="c986a-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
