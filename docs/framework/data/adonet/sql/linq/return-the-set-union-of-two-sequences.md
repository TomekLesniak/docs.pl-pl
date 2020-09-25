---
title: Zwracanie sumy zbiorów dwóch sekwencji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 0fe32d8c3c37e99a50ca03262dc6184337b4450e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200209"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="129a5-102">Zwracanie sumy zbiorów dwóch sekwencji</span><span class="sxs-lookup"><span data-stu-id="129a5-102">Return the Set Union of Two Sequences</span></span>

<span data-ttu-id="129a5-103">Użyj <xref:System.Linq.Queryable.Union%2A> operatora, aby zwrócić zestaw zbiorów dwóch sekwencji.</span><span class="sxs-lookup"><span data-stu-id="129a5-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="129a5-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="129a5-104">Example</span></span>  

 <span data-ttu-id="129a5-105">Ten przykład używa <xref:System.Linq.Queryable.Union%2A> do zwracania sekwencji wszystkich krajów/regionów, w których jest albo `Customers` lub `Employees` .</span><span class="sxs-lookup"><span data-stu-id="129a5-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries/regions in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="129a5-106">W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Linq.Queryable.Union%2A> operator jest zdefiniowany dla wielozbiorów jako nieuporządkowane łączenie wielozestawów (w efekcie w wyniku [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) klauzuli w języku SQL).</span><span class="sxs-lookup"><span data-stu-id="129a5-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) clause in SQL).</span></span>

<span data-ttu-id="129a5-107">Aby uzyskać więcej informacji i przykładów, zobacz <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="129a5-107">For more info and examples, see <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="129a5-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="129a5-108">See also</span></span>

- [<span data-ttu-id="129a5-109">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="129a5-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="129a5-110">Translacja standardowego operatora zapytania</span><span class="sxs-lookup"><span data-stu-id="129a5-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
