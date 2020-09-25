---
title: Informacje o błędzie wiersza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
ms.openlocfilehash: 8673b7fbc2e4238f7047698376c53af991de9f1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181170"
---
# <a name="row-error-information"></a>Informacje o błędzie wiersza

Aby uniknąć konieczności reagowania na błędy wierszy podczas edytowania wartości w <xref:System.Data.DataTable> , można dodać informacje o błędzie do wiersza w celu późniejszego użycia. <xref:System.Data.DataRow>Obiekt zawiera <xref:System.Data.DataRow.RowError%2A> Właściwość dla każdego wiersza w tym celu. Dodanie danych do właściwości **RowError** obiektu **DataRow** ustawia <xref:System.Data.DataRow.HasErrors%2A> właściwość elementu **DataRow** na **wartość true**. Jeśli element **DataRow** jest częścią **elementu DataTable**, a **obiekt DataRow. HasErrors** ma **wartość true**, właściwość **DataTable. HasErrors** ma również **wartość true**. Dotyczy to również **zestawu danych** , do którego należy element **DataTable** . Podczas testowania pod kątem błędów można sprawdzić Właściwość **HasErrors** , aby określić, czy informacje o błędzie zostały dodane do dowolnych wierszy. Jeśli **HasErrors** ma **wartość true**, można użyć <xref:System.Data.DataTable.GetErrors%2A> metody **tabeli DataTable** do zwrócenia i sprawdzenia tylko wierszy z błędami, jak pokazano w poniższym przykładzie.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
workTable.Columns.Add("CustID", Type.GetType("System.Int32"))  
workTable.Columns.Add("Total", Type.GetType("System.Double"))  
  
AddHandler workTable.RowChanged, New DataRowChangeEventHandler(AddressOf OnRowChanged)  
  
Dim i  As Int32  
  
For i  = 0 To 10  
  workTable.Rows.Add(New Object() {i , i *100})  
Next  
  
If workTable.HasErrors Then  
  Console.WriteLine("Errors in Table " & workTable.TableName)  
  
  Dim myRow As DataRow  
  
  For Each myRow In workTable.GetErrors()  
    Console.WriteLine("CustID = " & myRow("CustID").ToString())  
    Console.WriteLine(" Error = " & myRow.RowError & vbCrLf)  
  Next  
End If  
  
Private Shared Sub OnRowChanged( _  
    sender As Object, args As DataRowChangeEventArgs)  
  ' Check for zero values.  
  If CDbl(args.Row("Total")) = 0 Then args.Row.RowError = _  
      "Total cannot be 0."  
End Sub  
```  
  
```csharp  
DataTable  workTable = new DataTable("Customers");  
workTable.Columns.Add("CustID", typeof(Int32));  
workTable.Columns.Add("Total", typeof(Double));  
  
workTable.RowChanged += new DataRowChangeEventHandler(OnRowChanged);  
  
for (int i = 0; i < 10; i++)  
  workTable.Rows.Add(new Object[] {i, i*100});  
  
if (workTable.HasErrors)  
{  
  Console.WriteLine("Errors in Table " + workTable.TableName);  
  
  foreach (DataRow myRow in workTable.GetErrors())  
  {  
    Console.WriteLine("CustID = " + myRow["CustID"]);  
    Console.WriteLine(" Error = " + myRow.RowError + "\n");  
  }  
}  
  
protected static void OnRowChanged(  
    Object sender, DataRowChangeEventArgs args)  
{  
  // Check for zero values.  
  if (args.Row["Total"].Equals(0D))  
    args.Row.RowError = "Total cannot be 0.";  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- [Operowanie na danych w elemencie DataTable](manipulating-data-in-a-datatable.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
