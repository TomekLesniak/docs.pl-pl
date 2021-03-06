---
title: Definiowanie kluczy podstawowych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 94b033d58061e3d2e48a352d782eec7c4202fa43
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166836"
---
# <a name="defining-primary-keys"></a>Definiowanie kluczy podstawowych

Tabela bazy danych ma zwykle kolumnę lub grupę kolumn, która jednoznacznie identyfikuje każdy wiersz w tabeli. Ta kolumna identyfikująca lub grupa kolumn jest nazywana kluczem podstawowym.  
  
 Po zidentyfikowaniu pojedynczej <xref:System.Data.DataColumn> jako <xref:System.Data.DataTable.PrimaryKey%2A> dla elementu <xref:System.Data.DataTable> , w tabeli automatycznie ustawia <xref:System.Data.DataColumn.AllowDBNull%2A> Właściwość kolumny na **false** i <xref:System.Data.DataColumn.Unique%2A> Właściwość na **true**. W przypadku kluczy podstawowych z wieloma kolumnami tylko właściwość **AllowDBNull** jest automatycznie ustawiana na **wartość false**.  
  
 Właściwość **PrimaryKey** elementu <xref:System.Data.DataTable> otrzymuje jako wartość tablicę co najmniej jednego obiektu **DataColumn** , jak pokazano w poniższych przykładach. Pierwszy przykład definiuje pojedynczą kolumnę jako klucz podstawowy.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 W poniższym przykładzie zdefiniowano dwie kolumny jako klucz podstawowy.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataTable>
- [Definicja schematu elementu DataTable](datatable-schema-definition.md)
- [Elementy DataTable](datatables.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
