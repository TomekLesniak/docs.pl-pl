---
title: Modyfikowanie elementów DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 8e3a3f92fe8ecc94a041fbcb1540bae18a41dbef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203686"
---
# <a name="modifying-dataviews"></a>Modyfikowanie elementów DataView

Można użyć <xref:System.Data.DataView> do dodawania, usuwania lub modyfikowania wierszy danych w tabeli źródłowej. Możliwość używania elementu **DataView** do modyfikowania danych w źródłowej tabeli jest kontrolowana przez ustawienie jednej z trzech właściwości logicznych elementu **DataView**. Te właściwości to <xref:System.Data.DataView.AllowNew%2A> , <xref:System.Data.DataView.AllowEdit%2A> i <xref:System.Data.DataView.AllowDelete%2A> . Domyślnie ustawiono **wartość true** .  
  
 Jeśli **AllowNew** ma **wartość true**, można użyć <xref:System.Data.DataView.AddNew%2A> metody **widoku** danych, aby utworzyć nowy <xref:System.Data.DataRowView> . Należy zauważyć, że nowy wiersz nie jest faktycznie dodawany do elementu bazowego <xref:System.Data.DataTable> do momentu <xref:System.Data.DataRowView.EndEdit%2A> wywołania metody **DataRowView** . Jeśli <xref:System.Data.DataRowView.CancelEdit%2A> wywoływana jest metoda **DataRowView** , nowy wiersz jest odrzucany. Należy zauważyć, że można edytować tylko jeden **DataRowView** w danym momencie. W przypadku wywołania metody **AddNew** lub **elementu BeginEdit** **DataRowView** , gdy istnieje oczekujący wiersz, **EndEdit** jest wywoływana niejawnie w oczekującym wierszu. Gdy **EndEdit** jest wywoływana, zmiany są stosowane do bazowego **elementu DataTable** i później mogą być zatwierdzane lub odrzucane przy użyciu metod **AcceptChanges** lub **RejectChanges** obiektu **DataTable**, **DataSet**lub **DataRow** . Jeśli **AllowNew** ma **wartość false**, wyjątek jest zgłaszany w przypadku wywołania metody **AddNew** elementu **DataRowView**.  
  
 Jeśli **AllowEdit** ma **wartość true**, można zmodyfikować zawartość obiektu **DataRow** za pośrednictwem **DataRowView**. Można potwierdzić zmiany w wierszu źródłowym przy użyciu **DataRowView. EndEdit** lub odrzucić zmiany przy użyciu **DataRowView. CancelEdit**. Należy zauważyć, że w danym momencie można edytować tylko jeden wiersz. W przypadku wywołania metody **AddNew** lub **elementu BeginEdit** **DataRowView** , gdy istnieje oczekujący wiersz, **EndEdit** jest wywoływana niejawnie w oczekującym wierszu. Gdy **EndEdit** jest wywoływana, proponowane zmiany są umieszczane w **bieżącej** wersji wiersza bazowego elementu **DataRow** i mogą być później zatwierdzane lub odrzucane przy użyciu metod **AcceptChanges** lub **RejectChanges** obiektu **DataTable**, **DataSet**lub **DataRow** . Jeśli **AllowEdit** ma **wartość false**, wyjątek jest zgłaszany w przypadku próby zmodyfikowania wartości w **widoku**danych.  
  
 Podczas edytowania istniejącej **DataRowView** zdarzenia powiązanej **tabeli DataTable** będą nadal zgłaszane z proponowanymi zmianami. Należy pamiętać, że jeśli wywołasz **EndEdit** lub **CancelEdit** na bazowym elemencie **DataRow**, oczekujące zmiany zostaną zastosowane lub anulowane niezależnie od tego, czy **EndEdit** lub **CancelEdit** są wywoływane na **DataRowView**.  
  
 Jeśli **AllowDelete** ma **wartość true**, można usunąć wiersze z **widoku** danych za pomocą metody **delete** obiektu **DataView** lub **DataRowView** , a wiersze są usuwane z bazowego **elementu DataTable**. Można później zatwierdzać lub odrzucać usunięcia przy użyciu metody **AcceptChanges** lub **RejectChanges** . Jeśli **AllowDelete** ma **wartość false**, wyjątek jest zgłaszany w przypadku wywołania metody **delete** elementu **DataView** lub **DataRowView**.  
  
 Poniższy przykład kodu wyłącza używanie elementu **DataView** do usuwania wierszy i dodaje nowy wiersz do źródłowej tabeli przy użyciu **widoku**danych.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [Elementy DataView](dataviews.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
