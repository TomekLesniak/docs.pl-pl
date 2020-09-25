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
# <a name="return-the-set-union-of-two-sequences"></a>Zwracanie sumy zbiorów dwóch sekwencji

Użyj <xref:System.Linq.Queryable.Union%2A> operatora, aby zwrócić zestaw zbiorów dwóch sekwencji.  
  
## <a name="example"></a>Przykład  

 Ten przykład używa <xref:System.Linq.Queryable.Union%2A> do zwracania sekwencji wszystkich krajów/regionów, w których jest albo `Customers` lub `Employees` .  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 W programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Linq.Queryable.Union%2A> operator jest zdefiniowany dla wielozbiorów jako nieuporządkowane łączenie wielozestawów (w efekcie w wyniku [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) klauzuli w języku SQL).

Aby uzyskać więcej informacji i przykładów, zobacz <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType> .
  
## <a name="see-also"></a>Zobacz też

- [Przykłady zapytań](query-examples.md)
- [Translacja standardowego operatora zapytania](standard-query-operator-translation.md)
