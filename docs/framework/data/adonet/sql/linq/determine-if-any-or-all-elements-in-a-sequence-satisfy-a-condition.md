---
title: Określanie, czy niektóre lub wszystkie elementy w sekwencji spełniają warunek
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: 65a9a7cf289c2006bab14cb384efb07eaea7f7a0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194430"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a>Określanie, czy niektóre lub wszystkie elementy w sekwencji spełniają warunek

<xref:System.Linq.Enumerable.All%2A>Operator zwraca, `true` Jeśli wszystkie elementy w sekwencji spełniają warunek.  
  
 <xref:System.Linq.Queryable.Any%2A>Operator zwraca, `true` Jeśli którykolwiek element w sekwencji spełnia warunek.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład zwraca sekwencję klientów, którzy mają co najmniej jedno zamówienie. `Where` / `where` Klauzula ma wartość, `true` Jeśli dana wartość `Customer` ma `Order` .  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a>Przykład  

 Poniższy kod Visual Basic określa listę klientów, którzy nie przetworzyli zamówień, i gwarantuje, że dla każdego klienta na tej liście zostanie podana nazwa kontaktu.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład w języku C# zwraca sekwencję klientów, których zamówienia `ShipCity` zaczynają się od znaku "C". Również uwzględniono w zwracaniu klientów, którzy nie mają zamówień. (Według projektu, <xref:System.Linq.Queryable.All%2A> operator zwraca `true` dla pustej sekwencji). Klienci bez zamówień są eliminowani w danych wyjściowych konsoli za pomocą `Count` operatora.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady zapytań](query-examples.md)
