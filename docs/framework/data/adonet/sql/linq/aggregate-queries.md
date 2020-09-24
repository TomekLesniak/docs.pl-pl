---
title: Zapytania zagregowane
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 8dfe24a84c707b6d21afb7ccfc57ac7b0423942f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161545"
---
# <a name="aggregate-queries"></a>Zapytania zagregowane

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] obsługuje `Average` operatory, `Count` , `Max` , `Min` i `Sum` agregacji. Zwróć uwagę na następujące cechy agregacji operatorów w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] :  
  
- Zapytania agregujące są wykonywane natychmiastowo.  
  
     Aby uzyskać więcej informacji, zobacz [wprowadzenie do zapytań LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
- Zapytania agregujące zwykle zwracają liczbę zamiast kolekcji.  
  
     Aby uzyskać więcej informacji, zobacz [operacje agregacji](/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).  
  
- Nie można wywoływać agregacji dla typów anonimowych.  
  
 Przykłady w poniższych tematach pochodzą z przykładowej bazy danych Northwind. Aby uzyskać więcej informacji, zobacz [Pobieranie przykładowych baz danych](downloading-sample-databases.md).  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Zwracanie średniej wartości z sekwencji numerycznej](return-the-average-value-from-a-numeric-sequence.md)  
 Pokazuje, jak używać <xref:System.Linq.Enumerable.Average%2A> operatora.  
  
 [Licznik liczby elementów w sekwencji](count-the-number-of-elements-in-a-sequence.md)  
 Pokazuje, jak używać <xref:System.Linq.Enumerable.Count%2A> operatora.  
  
 [Odnajdywanie wartości maksymalnej w sekwencji numerycznej](find-the-maximum-value-in-a-numeric-sequence.md)  
 Pokazuje, jak używać <xref:System.Linq.Enumerable.Max%2A> operatora.  
  
 [Odnajdywanie wartości minimalnej w sekwencji numerycznej](find-the-minimum-value-in-a-numeric-sequence.md)  
 Pokazuje, jak używać <xref:System.Linq.Enumerable.Min%2A> operatora.  
  
 [Obliczanie sumy wartości w sekwencji numerycznej](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 Pokazuje, jak używać <xref:System.Linq.Enumerable.Sum%2A> operatora.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Przykłady zapytań](query-examples.md)  
 Oferuje linki do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zapytań w Visual Basic i C#.  
  
 [Pojęcia dotyczące zapytań](query-concepts.md)  
 Zawiera łącza do tematów objaśniających koncepcje projektowania zapytań LINQ w programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .  
  
 [Wprowadzenie do kwerend LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 Wyjaśnia, w jaki sposób zapytania działają w LINQ.
