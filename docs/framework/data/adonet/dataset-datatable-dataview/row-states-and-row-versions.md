---
title: Stany wiersza i wersje wiersza
ms.date: 07/19/2018
dev_langs:
- csharp
- vb
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
ms.openlocfilehash: 1b80ae78fad22989f99fb1e992d4978a192e0c66
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204531"
---
# <a name="row-states-and-row-versions"></a>Stany wiersza i wersje wiersza

ADO.NET zarządza wierszami w tabelach przy użyciu stanów i wersji wiersza. Stan wiersza wskazuje stan wiersza; wersje wierszy obsługują wartości przechowywane w wierszu w miarę ich modyfikacji, w tym bieżące, oryginalne i domyślne wartości. Na przykład po dokonaniu modyfikacji kolumny w wierszu wiersz będzie miał stan wiersza `Modified` i dwie wersje wierszy: `Current` , które zawierają wartości bieżącego wiersza, i `Original` , które zawierają wartości wierszy przed modyfikacją kolumny.  
  
 Każdy <xref:System.Data.DataRow> obiekt ma <xref:System.Data.DataRow.RowState%2A> Właściwość, którą można sprawdzić w celu określenia bieżącego stanu wiersza. W poniższej tabeli przedstawiono krótki opis każdej `RowState` wartości wyliczenia.  
  
|RowState wartość|Opis|  
|--------------------|-----------------|  
|<xref:System.Data.DataRowState.Unchanged>|Od momentu ostatniego wywołania `AcceptChanges` lub od momentu utworzenia wiersza nie wprowadzono żadnych zmian `DataAdapter.Fill` .|  
|<xref:System.Data.DataRowState.Added>|Wiersz został dodany do tabeli, ale `AcceptChanges` nie został wywołany.|  
|<xref:System.Data.DataRowState.Modified>|Jakiś element wiersza został zmieniony.|  
|<xref:System.Data.DataRowState.Deleted>|Wiersz został usunięty z tabeli i `AcceptChanges` nie został wywołany.|  
|<xref:System.Data.DataRowState.Detached>|Wiersz nie jest częścią żadnego elementu `DataRowCollection` . `RowState`Nowo utworzony wiersz jest ustawiony na `Detached` . Po `DataRow` dodaniu nowego do obiektu `DataRowCollection` przez wywołanie `Add` metody, wartość `RowState` właściwości jest ustawiona na `Added` .<br /><br /> `Detached` jest również ustawiony dla wiersza, który został usunięty z `DataRowCollection` `Remove` metody lub przez metodę, `Delete` a następnie metodę `AcceptChanges` .|  
  
 Gdy `AcceptChanges` jest wywoływana w <xref:System.Data.DataSet> , <xref:System.Data.DataTable> , lub <xref:System.Data.DataRow> , wszystkie wiersze ze stanem wiersza `Deleted` są usuwane. W pozostałych wierszach jest przyznany stan wiersza `Unchanged` , a wartości w `Original` wierszu wersji są zastępowane `Current` wartościami wersji wiersza. Gdy `RejectChanges` jest wywoływana, wszystkie wiersze ze stanem wiersza `Added` są usuwane. W pozostałych wierszach jest przyznany stan wiersza `Unchanged` , a wartości w `Current` wierszu wersji są zastępowane `Original` wartościami wersji wiersza.  
  
 Możesz wyświetlić różne wersje wierszy wiersza, przekazując <xref:System.Data.DataRowVersion> parametr z odwołaniem do kolumny, jak pokazano w poniższym przykładzie.  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 W poniższej tabeli przedstawiono krótki opis każdej `DataRowVersion` wartości wyliczenia.  
  
|DataRowVersion wartość|Opis|  
|--------------------------|-----------------|  
|<xref:System.Data.DataRowVersion.Current>|Bieżące wartości dla wiersza. Ta wersja wiersza nie istnieje dla wierszy z `RowState` `Deleted` .|  
|<xref:System.Data.DataRowVersion.Default>|Domyślna wersja wiersza dla konkretnego wiersza. Domyślna wersja wiersza dla elementu `Added` , `Modified` , lub `Deleted` jest `Current` . Domyślna wersja wiersza dla `Detached` wiersza to `Proposed` .|  
|<xref:System.Data.DataRowVersion.Original>|Oryginalne wartości dla wiersza. Ta wersja wiersza nie istnieje dla wierszy z `RowState` `Added` .|  
|<xref:System.Data.DataRowVersion.Proposed>|Proponowane wartości dla wiersza. Ta wersja wiersza istnieje podczas operacji edycji w wierszu lub dla wiersza, który nie jest częścią `DataRowCollection` .|  
  
 Możesz sprawdzić, czy `DataRow` ma określoną wersję wiersza, wywołując <xref:System.Data.DataRow.HasVersion%2A> metodę i przekazując `DataRowVersion` jako argument. Na przykład program `DataRow.HasVersion(DataRowVersion.Original)` zwróci `false` dla nowo dodanych wierszy przed `AcceptChanges` wywołaniem.  
  
 Poniższy przykład kodu wyświetla wartości we wszystkich usuniętych wierszach tabeli. `Deleted` wiersze nie mają `Current` wersji wiersza, dlatego należy je przekazać `DataRowVersion.Original` podczas uzyskiwania dostępu do wartości kolumn.  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- [Operowanie na danych w elemencie DataTable](manipulating-data-in-a-datatable.md)
- [Elementy DataSet, DataTable i DataView](index.md)
- [Elementy DataAdapter i DataReader](../dataadapters-and-datareaders.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
