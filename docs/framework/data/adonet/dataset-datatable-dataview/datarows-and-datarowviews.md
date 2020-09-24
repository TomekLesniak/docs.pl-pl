---
title: Elementy DataRow i DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: bce90c1d310178e66da7c758c6df2cd357199c8b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153290"
---
# <a name="datarows-and-datarowviews"></a>Elementy DataRow i DataRowView

A <xref:System.Data.DataView> uwidacznia wyliczalną kolekcję <xref:System.Data.DataRowView> obiektów. Obiekty **DataRowView** uwidaczniają wartości jako tablice obiektów, które są indeksowane przez nazwę lub odwołanie porządkowe kolumny w tabeli źródłowej. Możesz uzyskać dostęp do programu <xref:System.Data.DataRow> , który jest udostępniany przez **DataRowView** , przy użyciu <xref:System.Data.DataRowView.Row%2A> właściwości **DataRowView**.  
  
 Podczas wyświetlania wartości przy użyciu **DataRowView** <xref:System.Data.DataView.RowStateFilter%2A> Właściwość **widoku** danych określa, która wersja wiersza podstawowego elementu **DataRow** jest uwidoczniona. Aby uzyskać informacje o uzyskiwaniu dostępu do różnych wersji wierszy przy użyciu elementu **DataRow**, zobacz [Stany wiersza i wersje wierszy](row-states-and-row-versions.md).  
  
 Poniższy przykład kodu wyświetla wszystkie bieżące i oryginalne wartości w tabeli.  
  
```vb  
Dim catView As DataView = New DataView(catDS.Tables("Categories"))  
Console.WriteLine("Current Values:")  
WriteView(catView)  
Console.WriteLine("Original Values:")  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal  
WriteView(catView)
  
Public Shared Sub WriteView(thisDataView As DataView)  
  Dim rowView As DataRowView  
  Dim i As Integer  
  
  For Each rowView In thisDataView  
    For i = 0 To thisDataView.Table.Columns.Count - 1  
      Console.Write(rowView(i) & vbTab)  
    Next  
    Console.WriteLine()  
  Next  
End Sub  
```  
  
```csharp  
DataView catView = new DataView(catDS.Tables["Categories"]);  
Console.WriteLine("Current Values:");  
WriteView(catView);  
Console.WriteLine("Original Values:");  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal;  
WriteView(catView);  
  
public static void WriteView(DataView thisDataView)  
{  
  foreach (DataRowView rowView in thisDataView)  
  {  
    for (int i = 0; i < thisDataView.Table.Columns.Count; i++)  
      Console.Write(rowView[i] + "\t");  
    Console.WriteLine();  
  }  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [Elementy DataView](dataviews.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
