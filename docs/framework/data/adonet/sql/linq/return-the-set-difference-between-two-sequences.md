---
title: Zwracanie zestawu różnic między dwoma sekwencjami
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 49a8d22377ef1f7d0fde16880a82002754e1bbc4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200332"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="ac6c0-102">Zwracanie zestawu różnic między dwoma sekwencjami</span><span class="sxs-lookup"><span data-stu-id="ac6c0-102">Return the Set Difference Between Two Sequences</span></span>

<span data-ttu-id="ac6c0-103">Użyj <xref:System.Linq.Queryable.Except%2A> operatora, aby zwrócić różnicę zestawu między dwiema sekwencjami.</span><span class="sxs-lookup"><span data-stu-id="ac6c0-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac6c0-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="ac6c0-104">Example</span></span>  

 <span data-ttu-id="ac6c0-105">Ten przykład używa <xref:System.Linq.Queryable.Except%2A> do zwracania sekwencji wszystkich krajów/regionów, w których `Customers` Live, ale w których nie ma na `Employees` żywo.</span><span class="sxs-lookup"><span data-stu-id="ac6c0-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="ac6c0-106">W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Linq.Queryable.Except%2A> operacja jest również zdefiniowana tylko dla zestawów.</span><span class="sxs-lookup"><span data-stu-id="ac6c0-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="ac6c0-107">Semantyka dla wielozestawów jest niezdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="ac6c0-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac6c0-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ac6c0-108">See also</span></span>

- [<span data-ttu-id="ac6c0-109">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="ac6c0-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="ac6c0-110">Translacja standardowego operatora zapytania</span><span class="sxs-lookup"><span data-stu-id="ac6c0-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
