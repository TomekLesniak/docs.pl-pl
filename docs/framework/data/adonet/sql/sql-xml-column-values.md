---
title: Wartości kolumny SQL XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: cd55e2263d4b71fe62910ac918e331ebe37833eb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177283"
---
# <a name="sql-xml-column-values"></a>Wartości kolumny SQL XML

SQL Server obsługuje `xml` Typ danych, a deweloperzy mogą pobierać zestawy wyników, w tym typ, przy użyciu standardowego zachowania <xref:System.Data.SqlClient.SqlCommand> klasy. `xml`Kolumnę można pobrać tylko w przypadku pobrania dowolnej kolumny ( <xref:System.Data.SqlClient.SqlDataReader> na przykład), ale jeśli chcesz korzystać z zawartości kolumny jako XML, musisz użyć <xref:System.Xml.XmlReader> .  
  
## <a name="example"></a>Przykład  

 Poniższa Aplikacja konsolowa wybiera dwa wiersze, `xml` z których każda zawiera kolumnę, z tabeli **Sales. Store** w bazie danych **AdventureWorks** do <xref:System.Data.SqlClient.SqlDataReader> wystąpienia. Dla każdego wiersza wartość `xml` kolumny jest odczytywana przy użyciu <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> metody <xref:System.Data.SqlClient.SqlDataReader> . Wartość jest przechowywana w <xref:System.Xml.XmlReader> . Należy pamiętać, że należy użyć <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> zamiast <xref:System.Data.IDataRecord.GetValue%2A> metody, jeśli chcesz ustawić zawartość dla <xref:System.Data.SqlTypes.SqlXml> zmiennej; <xref:System.Data.IDataRecord.GetValue%2A> zwraca wartość `xml` kolumny jako ciąg.  
  
> [!NOTE]
> Przykładowa baza danych **AdventureWorks** nie jest instalowana domyślnie podczas instalowania SQL Server. Można go zainstalować, uruchamiając Instalatora SQL Server.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.SqlTypes.SqlXml>
- [Dane XML w programie SQL Server](xml-data-in-sql-server.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
