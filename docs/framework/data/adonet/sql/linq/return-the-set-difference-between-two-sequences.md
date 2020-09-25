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
# <a name="return-the-set-difference-between-two-sequences"></a>Zwracanie zestawu różnic między dwoma sekwencjami

Użyj <xref:System.Linq.Queryable.Except%2A> operatora, aby zwrócić różnicę zestawu między dwiema sekwencjami.  
  
## <a name="example"></a>Przykład  

 Ten przykład używa <xref:System.Linq.Queryable.Except%2A> do zwracania sekwencji wszystkich krajów/regionów, w których `Customers` Live, ale w których nie ma na `Employees` żywo.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Linq.Queryable.Except%2A> operacja jest również zdefiniowana tylko dla zestawów. Semantyka dla wielozestawów jest niezdefiniowana.  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady zapytań](query-examples.md)
- [Translacja standardowego operatora zapytania](standard-query-operator-translation.md)
