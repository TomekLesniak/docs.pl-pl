---
title: Konwertowanie typu na ogólny interfejs IEnumerable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: c2d34ae708f79d9f920679b3714a100fe8943c38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164418"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="82545-102">Konwertowanie typu na ogólny interfejs IEnumerable</span><span class="sxs-lookup"><span data-stu-id="82545-102">Convert a Type to a Generic IEnumerable</span></span>

<span data-ttu-id="82545-103">Użyj, <xref:System.Linq.Enumerable.AsEnumerable%2A> Aby zwrócić argument, który jest typem ogólnym `IEnumerable` .</span><span class="sxs-lookup"><span data-stu-id="82545-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82545-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="82545-104">Example</span></span>  

 <span data-ttu-id="82545-105">W tym przykładzie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (przy użyciu domyślnego generycznego `Query` ) próba konwersji zapytania na SQL i wykonania go na serwerze.</span><span class="sxs-lookup"><span data-stu-id="82545-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="82545-106">Natomiast `where` klauzula odwołuje się do zdefiniowanej przez użytkownika metody po stronie klienta ( `isValidProduct` ), której nie można przekonwertować na SQL.</span><span class="sxs-lookup"><span data-stu-id="82545-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="82545-107">Rozwiązaniem jest określenie, że implementacja ogólna po stronie klienta <xref:System.Collections.Generic.IEnumerable%601> `where` zastąpi ogólny <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="82545-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="82545-108">W tym celu należy wycofać <xref:System.Linq.Enumerable.AsEnumerable%2A> operatora.</span><span class="sxs-lookup"><span data-stu-id="82545-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="82545-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="82545-109">See also</span></span>

- [<span data-ttu-id="82545-110">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="82545-110">Query Examples</span></span>](query-examples.md)
