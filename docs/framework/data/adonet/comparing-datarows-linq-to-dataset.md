---
title: Porównywanie wierszy DataRows (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
ms.openlocfilehash: 8cce52734c83e42312d71806d4151ef21e4df0ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203803"
---
# <a name="comparing-datarows-linq-to-dataset"></a>Porównywanie wierszy DataRows (LINQ to DataSet)

Załączone w języku zapytanie (LINQ) definiuje różne operatory zestawów do porównywania elementów źródłowych, aby sprawdzić, czy są równe. LINQ udostępnia następujące operatory zestawu:  
  
- <xref:System.Linq.Enumerable.Distinct%2A>  
  
- <xref:System.Linq.Enumerable.Union%2A>  
  
- <xref:System.Linq.Enumerable.Intersect%2A>  
  
- <xref:System.Linq.Enumerable.Except%2A>  
  
 Te operatory porównują elementy źródłowe, <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> wywołując <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> metody i dla każdej kolekcji elementów. W przypadku <xref:System.Data.DataRow> , te operatory wykonują porównanie odwołań, które zwykle nie jest idealnym zachowaniem dla operacji ustawiania w danych tabelarycznych. W przypadku operacji ustawiania zazwyczaj należy określić, czy wartości elementów są równe, a nie odwołania do elementów. W związku z tym <xref:System.Data.DataRowComparer> Klasa została dodana do LINQ to DataSet. Ta klasa może służyć do porównywania wartości wierszy.  
  
 <xref:System.Data.DataRowComparer>Klasa zawiera implementację porównania wartości dla <xref:System.Data.DataRow> , więc ta klasa może być używana do ustawiania operacji, takich jak <xref:System.Linq.Enumerable.Distinct%2A> . Nie można bezpośrednio utworzyć wystąpienia tej klasy; Zamiast tego <xref:System.Data.DataRowComparer.Default%2A> Właściwość musi być używana do zwracania wystąpienia <xref:System.Data.DataRowComparer%601> . <xref:System.Data.DataRowComparer%601.Equals%2A>Metoda jest następnie wywoływana, a dwa <xref:System.Data.DataRow> obiekty, które mają być porównane, są przenoszone jako parametry wejściowe. <xref:System.Data.DataRowComparer%601.Equals%2A>Metoda zwraca `true` , czy uporządkowany zestaw wartości kolumn w obu <xref:System.Data.DataRow> obiektach jest równy; w przeciwnym razie `false` .  
  
## <a name="example"></a>Przykład  

 Ten przykład używa `Intersect` do zwracania kontaktów, które pojawiają się w obu tabelach.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a>Przykład  

 Poniższy przykład porównuje dwa wiersze i pobiera ich kody skrótów.  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataRowComparer>
- [Ładowanie danych do zestawu danych](loading-data-into-a-dataset.md)
- [Przykłady LINQ to DataSet](linq-to-dataset-examples.md)
