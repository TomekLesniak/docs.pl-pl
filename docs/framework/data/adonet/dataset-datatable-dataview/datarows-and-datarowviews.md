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
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="1746b-102">Elementy DataRow i DataRowView</span><span class="sxs-lookup"><span data-stu-id="1746b-102">DataRows and DataRowViews</span></span>

<span data-ttu-id="1746b-103">A <xref:System.Data.DataView> uwidacznia wyliczalną kolekcję <xref:System.Data.DataRowView> obiektów.</span><span class="sxs-lookup"><span data-stu-id="1746b-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="1746b-104">Obiekty **DataRowView** uwidaczniają wartości jako tablice obiektów, które są indeksowane przez nazwę lub odwołanie porządkowe kolumny w tabeli źródłowej.</span><span class="sxs-lookup"><span data-stu-id="1746b-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="1746b-105">Możesz uzyskać dostęp do programu <xref:System.Data.DataRow> , który jest udostępniany przez **DataRowView** , przy użyciu <xref:System.Data.DataRowView.Row%2A> właściwości **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="1746b-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="1746b-106">Podczas wyświetlania wartości przy użyciu **DataRowView** <xref:System.Data.DataView.RowStateFilter%2A> Właściwość **widoku** danych określa, która wersja wiersza podstawowego elementu **DataRow** jest uwidoczniona.</span><span class="sxs-lookup"><span data-stu-id="1746b-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="1746b-107">Aby uzyskać informacje o uzyskiwaniu dostępu do różnych wersji wierszy przy użyciu elementu **DataRow**, zobacz [Stany wiersza i wersje wierszy](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="1746b-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="1746b-108">Poniższy przykład kodu wyświetla wszystkie bieżące i oryginalne wartości w tabeli.</span><span class="sxs-lookup"><span data-stu-id="1746b-108">The following code example displays all the current and original values in a table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1746b-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1746b-109">See also</span></span>

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="1746b-110">Elementy DataView</span><span class="sxs-lookup"><span data-stu-id="1746b-110">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="1746b-111">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1746b-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
