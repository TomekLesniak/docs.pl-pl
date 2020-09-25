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
# <a name="return-the-set-intersection-of-two-sequences"></a>Zwracanie zestawu części wspólnych dwóch sekwencji

Użyj <xref:System.Linq.Queryable.Intersect%2A> operatora, aby zwrócić zestaw przecięcia z dwiema sekwencjami.  
  
## <a name="example"></a>Przykład  

 Ten przykład używa <xref:System.Linq.Queryable.Intersect%2A> do zwracania sekwencji wszystkich krajów/regionów, w których zarówno `Customers` , jak i na `Employees` żywo.  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Linq.Queryable.Intersect%2A> operacja jest również zdefiniowana tylko dla zestawów. Semantyka dla wielozestawów jest niezdefiniowana.  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady zapytań](query-examples.md)
- [Translacja standardowego operatora zapytania](standard-query-operator-translation.md)
