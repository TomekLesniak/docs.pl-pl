---
title: Tworzenie elementu DataTable
description: Dowiedz się, jak utworzyć element DataTable w ADO.NET, który reprezentuje jedną tabelę danych relacyjnych w pamięci, która będzie używana niezależnie lub przez inne obiekty .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 75c9bcf0e0b6180030825b4d1e7dd9e1f9686712
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198642"
---
# <a name="creating-a-datatable"></a>Tworzenie elementu DataTable

A <xref:System.Data.DataTable> , który reprezentuje jedną tabelę danych relacyjnych w pamięci, może być tworzony i używany niezależnie lub może być używany przez inne obiekty .NET Framework, najczęściej jako element członkowski <xref:System.Data.DataSet> .  
  
 Obiekt **DataTable** można utworzyć przy użyciu odpowiedniego konstruktora **DataTable** . Możesz dodać go do **zestawu danych** za pomocą metody **Add** , aby dodać go do kolekcji **tabel** obiektu **DataTable** .  
  
 Można również tworzyć obiekty **DataTable** w ramach **zestawu danych** przy użyciu metod **Fill** lub **FillSchema** obiektu **DataAdapter** lub ze wstępnie zdefiniowanego lub wywnioskowanego schematu XML przy użyciu metod **ReadXml**, **ReadXmlSchema**lub **InferXmlSchema** **zestawu danych**. Należy pamiętać, że po dodaniu **DataTable** jako członka kolekcji **tabel** jednego **zestawu danych**nie można dodać go do kolekcji tabel innego **zestawu danych**.  
  
 Podczas pierwszej tworzenia **elementu DataTable**nie ma schematu (czyli struktury). Aby zdefiniować schemat tabeli, należy utworzyć i dodać <xref:System.Data.DataColumn> obiekty do kolekcji **kolumn** tabeli. Istnieje również możliwość zdefiniowania kolumny klucza podstawowego dla tabeli oraz utworzenia i dodania obiektów **ograniczeń** do kolekcji **ograniczenia** tabeli. Po zdefiniowaniu schematu dla **elementu DataTable**można dodać wiersze danych do tabeli przez dodanie obiektów **DataRow** do kolekcji **Rows** tabeli.  
  
 Nie trzeba podawać wartości <xref:System.Data.DataTable.TableName%2A> właściwości podczas tworzenia **elementu DataTable**; można określić właściwość w innym czasie lub pozostawić ją pustą. Jednak po dodaniu tabeli bez wartości **TableName** do **zestawu danych**w tabeli zostanie nadana przyrostowa domyślna nazwa tabeli*N*, rozpoczynając od "Tabela" dla TABLE0.  
  
> [!NOTE]
> Zalecamy uniknięcie konwencji nazewnictwa "Table*N*" w przypadku podania wartości **TableName** , ponieważ wprowadzona nazwa może powodować konflikt z istniejącą domyślną nazwą tabeli w **zestawie danych**. Jeśli podana nazwa już istnieje, zgłaszany jest wyjątek.  
  
 Poniższy przykład tworzy wystąpienie obiektu **DataTable** i przypisuje mu nazwę "Customers".  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 Poniższy przykład tworzy wystąpienie **elementu DataTable** przez dodanie go do kolekcji **Tables** **zestawu danych**.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [Elementy DataTable](datatables.md)
- [Wypełnianie zestawu danych z elementu DataAdapter](../populating-a-dataset-from-a-dataadapter.md)
- [Ładowanie elementu DataSet z pliku XML](loading-a-dataset-from-xml.md)
- [Ładowanie informacji o schemacie elementu DataSet z pliku XML](loading-dataset-schema-information-from-xml.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
