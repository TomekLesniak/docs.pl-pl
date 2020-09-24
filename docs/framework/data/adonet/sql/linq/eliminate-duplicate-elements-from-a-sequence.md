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
# <a name="eliminate-duplicate-elements-from-a-sequence"></a>Eliminowanie zduplikowanych elementów z sekwencji

Użyj <xref:System.Linq.Queryable.Distinct%2A> operatora, aby wyeliminować zduplikowane elementy z sekwencji.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa <xref:System.Linq.Queryable.Distinct%2A> do wybierania sekwencji unikatowych miast, którzy mają klientów.  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady zapytań](query-examples.md)
