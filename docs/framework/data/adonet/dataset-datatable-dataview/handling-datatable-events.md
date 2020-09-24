---
title: Obsługa zdarzeń elementu DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62f404a5-13ea-4b93-a29f-55b74a16c9d3
ms.openlocfilehash: c00e5e42508160a210d16f058c46afbf62ae0ee0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164730"
---
# <a name="handling-datatable-events"></a>Obsługa zdarzeń elementu DataTable

<xref:System.Data.DataTable>Obiekt zawiera serię zdarzeń, które mogą być przetwarzane przez aplikację. W poniższej tabeli opisano `DataTable` zdarzenia.  
  
|Zdarzenie|Opis|  
|-----------|-----------------|  
|<xref:System.Data.DataTable.Initialized>|Występuje po <xref:System.Data.DataTable.EndInit%2A> wywołaniu metody klasy `DataTable` . To zdarzenie jest przeznaczone głównie do obsługi scenariuszy czasu projektowania.|  
|<xref:System.Data.DataTable.ColumnChanged>|Występuje po pomyślnej zmianie wartości w <xref:System.Data.DataColumn> .|  
|<xref:System.Data.DataTable.ColumnChanging>|Występuje, gdy wartość zostanie przesłana dla elementu `DataColumn` .|  
|<xref:System.Data.DataTable.RowChanged>|Występuje po `DataColumn` <xref:System.Data.DataRow.RowState%2A> <xref:System.Data.DataRow> pomyślnym zmianie wartości lub elementu w `DataTable` .|  
|<xref:System.Data.DataTable.RowChanging>|Występuje, gdy została przesłana zmiana dotycząca `DataColumn` wartości lub `RowState` z `DataRow` w `DataTable` .|  
|<xref:System.Data.DataTable.RowDeleted>|Występuje po `DataRow` oznaczeniu elementu w elemencie `DataTable` jako `Deleted` .|  
|<xref:System.Data.DataTable.RowDeleting>|Występuje przed `DataRow` `DataTable` oznaczeniem elementu w `Deleted` .|  
|<xref:System.Data.DataTable.TableCleared>|Występuje po <xref:System.Data.DataTable.Clear%2A> `DataTable` pomyślnym wyczyszczeniu wywołania metody `DataRow` .|  
|<xref:System.Data.DataTable.TableClearing>|Występuje po `Clear` wywołaniu metody, ale przed rozpoczęciem `Clear` operacji.|  
|<xref:System.Data.DataTable.TableNewRow>|Występuje po utworzeniu nowej `DataRow` przez wywołanie `NewRow` metody `DataTable` .|  
|<xref:System.ComponentModel.MarshalByValueComponent.Disposed>|Występuje, gdy `DataTable` jest `Disposed` . Dziedziczone z <xref:System.ComponentModel.MarshalByValueComponent> .|  
  
> [!NOTE]
> Większość operacji, które dodają lub usuwają wiersze, nie powodują `ColumnChanged` `ColumnChanging` zdarzeń i. Jednak `ReadXml` Metoda wykonuje podnoszenie `ColumnChanged` i `ColumnChanging` zdarzenia, chyba że `XmlReadMode` jest ustawiona na `DiffGram` lub jest ustawiona na, `Auto` gdy dokument XML jest odczytywany `DiffGram` .  
  
> [!WARNING]
> Uszkodzenie danych może wystąpić, jeśli dane są modyfikowane w przypadku, gdy `DataSet` `RowChanged` zdarzenie jest zgłaszane. Wyjątek nie zostanie zgłoszony, jeśli wystąpi takie uszkodzenie danych.  
  
## <a name="additional-related-events"></a>Dodatkowe powiązane zdarzenia  

 <xref:System.Data.DataTable.Constraints%2A>Właściwość przechowuje <xref:System.Data.ConstraintCollection> wystąpienie. <xref:System.Data.ConstraintCollection>Klasa ujawnia <xref:System.Data.ConstraintCollection.CollectionChanged> zdarzenie. To zdarzenie jest wyzwalane, gdy ograniczenie zostanie dodane, zmodyfikowane lub usunięte z `ConstraintCollection` .  
  
 <xref:System.Data.DataTable.Columns%2A>Właściwość przechowuje <xref:System.Data.DataColumnCollection> wystąpienie. `DataColumnCollection`Klasa ujawnia <xref:System.Data.DataColumnCollection.CollectionChanged> zdarzenie. To zdarzenie jest wyzwalane `DataColumn` , gdy element jest dodawany, modyfikowany lub usuwany z `DataColumnCollection` . Modyfikacje, które powodują pożar zdarzenia, obejmują zmiany nazwy, typu, wyrażenia lub liczby porządkowej kolumny.  
  
 <xref:System.Data.DataSet.Tables%2A>Właściwość <xref:System.Data.DataSet> <xref:System.Data.DataTableCollection> obiektu zawiera wystąpienie. `DataTableCollection`Klasa uwidacznia zarówno `CollectionChanged` zdarzenie, jak i `CollectionChanging` . Te zdarzenia są wyzwalane po `DataTable` dodaniu lub usunięciu z `DataSet` .  
  
 Zmiany w usłudze `DataRows` mogą również wyzwalać zdarzenia dla skojarzonego elementu <xref:System.Data.DataView> . `DataView`Klasa uwidacznia <xref:System.Data.DataView.ListChanged> zdarzenie, które jest wyzwalane, gdy `DataColumn` wartość ulegnie zmianie lub gdy zmieni się kompozycja lub porządek sortowania widoku. <xref:System.Data.DataRowView>Klasa uwidacznia <xref:System.Data.DataRowView.PropertyChanged> zdarzenie, które jest wyzwalane, gdy zostanie zmieniona skojarzona `DataColumn` wartość.  
  
## <a name="sequence-of-operations"></a>sekwencja operacji  

 Oto sekwencja operacji, które wystąpiły po `DataRow` dodaniu, zmodyfikowaniu lub usunięciu:  
  
1. Utwórz proponowany rekord i Zastosuj wszelkie zmiany.  
  
2. Ograniczenia check dla kolumn niebędących wyrażeniami wyrażeń.  
  
3. Zgłoś odpowiednie `RowChanging` `RowDeleting` zdarzenia lub.  
  
4. Ustaw proponowany rekord jako bieżący rekord.  
  
5. Aktualizowanie wszystkich skojarzonych indeksów.  
  
6. Zgłoś `ListChanged` zdarzenia dla skojarzonych `DataView` obiektów i `PropertyChanged` zdarzeń dla skojarzonych `DataRowView` obiektów.  
  
7. Oceń wszystkie kolumny wyrażeń, ale Opóźnij sprawdzanie ograniczeń dotyczących tych kolumn.  
  
8. Wywołaj `ListChanged` zdarzenia dla skojarzonych `DataView` obiektów i `PropertyChanged` zdarzeń dla skojarzonych obiektów, na `DataRowView` które mają wpływ oceny kolumn wyrażeń.  
  
9. Podnieś `RowChanged` lub zgłoś `RowDeleted` odpowiednie zdarzenia.  
  
10. Ograniczenia check dla kolumn wyrażeń.  
  
> [!NOTE]
> Zmiany w kolumnach wyrażeń nigdy nie powodują `DataTable` zdarzeń. Zmiany w kolumnach wyrażeń powodują podnoszenie `DataView` i `DataRowView` zdarzenia. Kolumny wyrażeń mogą mieć zależności dla wielu innych kolumn i mogą być oceniane wiele razy podczas jednej `DataRow` operacji. Każde obliczenie wyrażenia wywołuje zdarzenia, a pojedyncza `DataRow` operacja może spowodować wygenerowanie wielu `ListChanged` i `PropertyChanged` zdarzeń w przypadku, gdy dotyczy kolumn wyrażeń, może także uwzględniać wiele zdarzeń dla tej samej kolumny wyrażenia.  
  
> [!WARNING]
> Nie zgłaszaj <xref:System.NullReferenceException> w ramach `RowChanged` procedury obsługi zdarzeń. Jeśli <xref:System.NullReferenceException> jest zgłaszany w ramach `RowChanged` zdarzenia `DataTable` , `DataTable` zostanie uszkodzona.  
  
### <a name="example"></a>Przykład  

 Poniższy przykład ilustruje sposób tworzenia obsługi zdarzeń dla zdarzeń,,,,,,, `RowChanged` `RowChanging` `RowDeleted` `RowDeleting` `ColumnChanged` `ColumnChanging` `TableNewRow` `TableCleared` i `TableClearing` . Każdy program obsługi zdarzeń wyświetla dane wyjściowe w oknie konsoli, gdy jest on uruchamiany.  
  
 [!code-csharp[DataWorks DataTable.Events#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.Events/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.Events#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.Events/VB/source.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Operowanie na danych w elemencie DataTable](manipulating-data-in-a-datatable.md)
- [Obsługa zdarzeń elementu DataAdapter](../handling-dataadapter-events.md)
- [Obsługa zdarzeń elementu DataSet](handling-dataset-events.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
