---
title: Eliminowanie zduplikowanych elementów z sekwencji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
ms.openlocfilehash: 0dca1a635fd1cc6e48e8ad914909769b2cf0e66d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161376"
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a><span data-ttu-id="03730-102">Eliminowanie zduplikowanych elementów z sekwencji</span><span class="sxs-lookup"><span data-stu-id="03730-102">Eliminate Duplicate Elements from a Sequence</span></span>

<span data-ttu-id="03730-103">Użyj <xref:System.Linq.Queryable.Distinct%2A> operatora, aby wyeliminować zduplikowane elementy z sekwencji.</span><span class="sxs-lookup"><span data-stu-id="03730-103">Use the <xref:System.Linq.Queryable.Distinct%2A> operator to eliminate duplicate elements from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03730-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="03730-104">Example</span></span>  

 <span data-ttu-id="03730-105">Poniższy przykład używa <xref:System.Linq.Queryable.Distinct%2A> do wybierania sekwencji unikatowych miast, którzy mają klientów.</span><span class="sxs-lookup"><span data-stu-id="03730-105">The following example uses <xref:System.Linq.Queryable.Distinct%2A> to select a sequence of the unique cities that have customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a><span data-ttu-id="03730-106">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="03730-106">See also</span></span>

- [<span data-ttu-id="03730-107">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="03730-107">Query Examples</span></span>](query-examples.md)
