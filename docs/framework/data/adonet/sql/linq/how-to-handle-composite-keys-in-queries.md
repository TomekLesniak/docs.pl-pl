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
# <a name="how-to-handle-composite-keys-in-queries"></a>Instrukcje: Obsługa kluczy złożonych w zapytaniach

Niektóre operatory mogą przyjmować tylko jeden argument. Jeśli argument musi zawierać więcej niż jedną kolumnę z bazy danych, należy utworzyć typ anonimowy, aby reprezentować kombinację.  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie pokazano zapytanie, które wywołuje `GroupBy` operator, który może przyjmować tylko jeden `key` argument.  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a>Przykład  

 Ta sama sytuacja dotyczy sprzężeń, jak w poniższym przykładzie:  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Zobacz też

- [Pojęcia dotyczące zapytań](query-concepts.md)
