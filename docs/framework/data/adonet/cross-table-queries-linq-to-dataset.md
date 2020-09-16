---
title: Zapytania między tabelami (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
ms.openlocfilehash: b62f5fbb6b964ed70f6bf7fc08b62a74a7c06c45
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554726"
---
# <a name="cross-table-queries-linq-to-dataset"></a>Zapytania między tabelami (LINQ to DataSet)
Oprócz wykonywania zapytań w pojedynczej tabeli, można również wykonywać zapytania między tabelami w LINQ to DataSet. Odbywa się to przy użyciu *sprzężenia*. Sprzężenie to skojarzenie obiektów w jednym źródle danych z obiektami, które współużytkują wspólny atrybut w innym źródle danych, takim jak identyfikator produktu lub kontaktu. W programowaniu zorientowanym na obiekt relacje między obiektami są stosunkowo proste, ponieważ każdy obiekt ma element członkowski, który odwołuje się do innego obiektu. Nawigowanie po relacjach nie jest jednak proste w tabelach zewnętrznych baz danych. Tabele bazy danych nie zawierają wbudowanych relacji. W takich przypadkach operacji JOIN można użyć do dopasowania elementów z każdego źródła. Na przykład, uwzględniając dwie tabele zawierające informacje o produkcie i informacje o sprzedaży, można użyć operacji JOIN w celu dopasowania informacji o sprzedaży i produktów dla tego samego zamówienia sprzedaży.  
  
 Architektura programu Query-Integrated Language (LINQ) zawiera dwa operatory sprzężenia <xref:System.Linq.Enumerable.Join%2A> i <xref:System.Linq.Enumerable.GroupJoin%2A> . Operatory te wykonują *Equi-joins*: to jest, sprzężenia, które pasują do dwóch źródeł danych tylko wtedy, gdy ich klucze są równe. (Z kolei język Transact-SQL obsługuje operatory sprzężenia inne niż `equals` , takie jak `less than` operator).  
  
 W terminologii relacyjnej bazy danych <xref:System.Linq.Enumerable.Join%2A> implementuje sprzężenie wewnętrzne. Sprzężenie wewnętrzne to typ sprzężenia, w którym zwracane są tylko te obiekty, które mają dopasowanie w odwrotnym zestawie danych.  
  
 <xref:System.Linq.Enumerable.GroupJoin%2A>Operatory nie mają bezpośredniego odpowiednika w warunkach relacyjnej bazy danych. implementują nadzbiór sprzężeń wewnętrznych i Lewe sprzężenia zewnętrzne. Lewe sprzężenie zewnętrzne to sprzężenie zwracające każdy element pierwszej (lewej) kolekcji, nawet jeśli nie ma skorelowanych elementów w drugiej kolekcji.  
  
 Aby uzyskać więcej informacji na temat sprzężeń, zobacz [Operacje łączenia](/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120)).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład wykonuje tradycyjne sprzężenie `SalesOrderHeader` `SalesOrderDetail` tabel i z przykładowej bazy danych AdventureWorks, aby uzyskać zamówienia online z miesiąca sierpnia.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>Zobacz także

- [Wykonywanie zapytania do zestawów danych](querying-datasets-linq-to-dataset.md)
- [Zapytania jednotabelowe](single-table-queries-linq-to-dataset.md)
- [Wykonywanie zapytania do typizowanych zestawów danych](querying-typed-datasets.md)
- [Operacje połączone](/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))
- [Przykłady LINQ to DataSet](linq-to-dataset-examples.md)
