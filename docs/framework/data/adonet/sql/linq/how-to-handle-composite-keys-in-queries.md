---
title: 'Instrukcje: Obsługa kluczy złożonych w zapytaniach'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: bc16dde89f67572b03102b1c091993ed163b443c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203530"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="a53f6-102">Instrukcje: Obsługa kluczy złożonych w zapytaniach</span><span class="sxs-lookup"><span data-stu-id="a53f6-102">How to: Handle Composite Keys in Queries</span></span>

<span data-ttu-id="a53f6-103">Niektóre operatory mogą przyjmować tylko jeden argument.</span><span class="sxs-lookup"><span data-stu-id="a53f6-103">Some operators can take only one argument.</span></span> <span data-ttu-id="a53f6-104">Jeśli argument musi zawierać więcej niż jedną kolumnę z bazy danych, należy utworzyć typ anonimowy, aby reprezentować kombinację.</span><span class="sxs-lookup"><span data-stu-id="a53f6-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a53f6-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="a53f6-105">Example</span></span>  

 <span data-ttu-id="a53f6-106">W poniższym przykładzie pokazano zapytanie, które wywołuje `GroupBy` operator, który może przyjmować tylko jeden `key` argument.</span><span class="sxs-lookup"><span data-stu-id="a53f6-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="a53f6-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="a53f6-107">Example</span></span>  

 <span data-ttu-id="a53f6-108">Ta sama sytuacja dotyczy sprzężeń, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a53f6-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a53f6-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a53f6-109">See also</span></span>

- [<span data-ttu-id="a53f6-110">Pojęcia dotyczące zapytań</span><span class="sxs-lookup"><span data-stu-id="a53f6-110">Query Concepts</span></span>](query-concepts.md)
