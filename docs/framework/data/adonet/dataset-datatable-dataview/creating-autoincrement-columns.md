---
title: Tworzenie kolumn typu AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 9a979f39003e60c70c03206bd886bdd6827c82e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203725"
---
# <a name="creating-autoincrement-columns"></a>Tworzenie kolumn typu AutoIncrement

Aby zapewnić unikatowe wartości kolumn, można ustawić wartości kolumn, które mają być zwiększane automatycznie po dodaniu nowych wierszy do tabeli. Aby utworzyć funkcję autozwiększania <xref:System.Data.DataColumn> , ustaw <xref:System.Data.DataColumn.AutoIncrement%2A> Właściwość kolumny na **true**. <xref:System.Data.DataColumn>Następnie rozpoczyna się od wartości zdefiniowanej we <xref:System.Data.DataColumn.AutoIncrementSeed%2A> właściwości, a każdy wiersz dodaliśmy wartość kolumny **AutoIncrement** zwiększa się o wartość zdefiniowaną we <xref:System.Data.DataColumn.AutoIncrementStep%2A> Właściwości kolumny.  
  
 W przypadku kolumn typu **AutoIncrement** zalecamy, aby <xref:System.Data.DataColumn.ReadOnly%2A> Właściwość **DataColumn** była ustawiona na **wartość true**.  
  
 W poniższym przykładzie pokazano, jak utworzyć kolumnę rozpoczynającą się od wartości 200 i dodać przyrostowo w krokach 3.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataColumn>
- [Definicja schematu elementu DataTable](datatable-schema-definition.md)
- [Elementy DataTable](datatables.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
