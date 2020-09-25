---
title: 'Instrukcje: Pobieranie jednocześnie wielu obiektów'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 98827989f72b7922a325a9e13b5f46cb18ac5395
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197316"
---
# <a name="how-to-retrieve-many-objects-at-once"></a>Instrukcje: Pobieranie jednocześnie wielu obiektów

Można pobrać wiele obiektów w jednym zapytaniu przy użyciu <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> .  
  
## <a name="example"></a>Przykład  

 Poniższy kod używa <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> metody do pobierania obu `Customer` `Order` obiektów i.  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a>Zobacz też

- [Pojęcia dotyczące zapytań](query-concepts.md)
