---
title: Dodawanie elementów DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 5fe2bd45e0abada1f9ec7071e3863da853479b51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202386"
---
# <a name="adding-datarelations"></a>Dodawanie elementów DataRelation

W przypadku <xref:System.Data.DataSet> z wieloma <xref:System.Data.DataTable> obiektami można użyć obiektów, <xref:System.Data.DataRelation> Aby powiązać jedną tabelę z inną, aby nawigować przez tabele i zwracać elementy podrzędne lub nadrzędne z powiązanej tabeli.  
  
 Argumenty wymagane do utworzenia **relacji** datarelationship są nazwami **tworzonego elementu** datarelationship i tablicą zawierającą co najmniej jedno <xref:System.Data.DataColumn> odwołanie do kolumn, które pełnią rolę kolumn nadrzędnych i podrzędnych w relacji. Po utworzeniu **relacji**można jej używać do nawigowania między tabelami i pobierania wartości.  
  
 Dodawanie **relacji** do dodawania <xref:System.Data.DataSet> , domyślnie, <xref:System.Data.UniqueConstraint> do tabeli nadrzędnej i <xref:System.Data.ForeignKeyConstraint> do tabeli podrzędnej. Aby uzyskać więcej informacji o tych domyślnych ograniczeniach, zobacz temat [ograniczenia DataTable](datatable-constraints.md).  
  
 Poniższy przykład kodu tworzy **relację** danych przy użyciu dwóch <xref:System.Data.DataTable> obiektów w <xref:System.Data.DataSet> . Każda <xref:System.Data.DataTable> z nich zawiera kolumnę o nazwie **CustId**, która służy jako link między dwoma <xref:System.Data.DataTable> obiektami. Przykład dodaje pojedyncze **powiązanie** do kolekcji **relacji** <xref:System.Data.DataSet> . Pierwszy argument w przykładzie określa nazwę tworzonego **powiązania** . Drugi argument ustawia nadrzędną **kolumnę** danych, a trzeci argument ustawia podrzędną **kolumnę**danych.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 **Relacja** danych ma również **zagnieżdżoną** właściwość, która po ustawieniu na **wartość true**powoduje, że wiersze z tabeli podrzędnej będą zagnieżdżone w skojarzonym wierszu z tabeli nadrzędnej, gdy są zapisywane jako elementy XML przy użyciu <xref:System.Data.DataSet.WriteXml%2A> . Aby uzyskać więcej informacji, zobacz [Używanie języka XML w zestawie danych](using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>Zobacz też

- [Elementy DataSet, DataTable i DataView](index.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
