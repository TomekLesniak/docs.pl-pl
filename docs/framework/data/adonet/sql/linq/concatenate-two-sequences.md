---
title: Łączenie dwóch sekwencji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
ms.openlocfilehash: 87d341357b8d11eafbc3f3867c45ac5a32270688
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164405"
---
# <a name="concatenate-two-sequences"></a>Łączenie dwóch sekwencji

Użyj <xref:System.Linq.Queryable.Concat%2A> operatora, aby połączyć dwie sekwencje.  
  
 <xref:System.Linq.Queryable.Concat%2A>Operator jest zdefiniowany dla uporządkowanych zestawów wielozbiorowych, gdzie zamówienia odbiornika i argumentu są takie same.  
  
 Porządkowanie w języku SQL to ostatni krok przed wygenerowanymi wynikami. Z tego powodu <xref:System.Linq.Queryable.Concat%2A> operator jest implementowany przy użyciu `UNION ALL` i nie zachowuje kolejności argumentów. Aby upewnić się, że kolejność jest prawidłowa w wynikach, upewnij się, że zostały one jawnie uporządkowane.  
  
## <a name="example"></a>Przykład  

 Ten przykład używa <xref:System.Linq.Queryable.Concat%2A> do zwracania sekwencji wszystkich `Customer` i `Employee` numerów telefonów i faksów.  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a>Przykład  

 Ten przykład używa <xref:System.Linq.Queryable.Concat%2A> do zwracania sekwencji wszystkich `Customer` i `Employee` nazwy i mapowania numerów telefonów.  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady zapytań](query-examples.md)
- [Translacja standardowego operatora zapytania](standard-query-operator-translation.md)
