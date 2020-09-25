---
title: Pobieranie informacji o schemacie bazy danych
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: c0aaadc82771d1c2a36d797bc157d88b8d3cacdc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177361"
---
# <a name="retrieving-database-schema-information"></a>Pobieranie informacji o schemacie bazy danych

Uzyskiwanie informacji o schemacie z bazy danych jest realizowane przy użyciu procesu odnajdywania schematu. Funkcja odnajdywania schematów umożliwia aplikacjom żądanie, że dostawcy zarządzani znajdą i zwracają informacje o schemacie bazy danych, znane także jako *metadane*, danej bazy danych. Różne elementy schematu bazy danych, takie jak tabele, kolumny i procedury składowane, są udostępniane za poorednictwem kolekcji schematów. Każda kolekcja schematów zawiera różne informacje o schemacie specyficzne dla używanego dostawcy.  
  
 Każdy z .NET Framework dostawców zarządzanych implementuje metodę **GetSchema** w klasie **Connection** , a informacje o schemacie, które są zwracane z metody **GetSchema** , mają postać <xref:System.Data.DataTable> . Metoda **GetSchema** jest przeciążoną metodą, która zapewnia parametry opcjonalne do określania kolekcji schematów do zwrócenia i ograniczając ilość zwracanych informacji.  
  
 Dostawcy danych .NET Framework dla OLE DB, ODBC, Oracle i SqlClient zapewniają metodę **Getschemaing** , która zwraca element DataTable opisujący metadane kolumn elementu **DataReader**.  
  
 Dostawca danych .NET Framework dla OLE DB udostępnia również informacje o schemacie przy użyciu <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> metody <xref:System.Data.OleDb.OleDbConnection> obiektu. Jako argumenty **GetOleDbSchemaTable** przyjmuje, <xref:System.Data.OleDb.OleDbSchemaGuid> że identyfikuje informacje o schemacie do zwrócenia i tablicę ograniczeń dla tych zwracanych kolumn. **GetOleDbSchemaTable** zwraca <xref:System.Data.DataTable> wypełniony z żądanymi informacjami o schemacie.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [GetSchema i kolekcje schematów](getschema-and-schema-collections.md)  
 Opisuje metodę **GetSchema** i sposób jej użycia do pobierania i ograniczania informacji schematu z bazy danych.  
  
 Ograniczenia schematu  
 Opisuje ograniczenia schematu, które mogą być używane z **GetSchema**.  
  
 [Typowe kolekcje schematów](common-schema-collections.md)  
 Opisuje wszystkie typowe kolekcje schematów obsługiwane przez wszystkich .NET Framework zarządzanych dostawców.  
  
 [Kolekcje schematów programu SQL Server](sql-server-schema-collections.md)  
 Opisuje kolekcję schematów obsługiwaną przez dostawcę .NET Framework dla SQL Server.  
  
 [Kolekcje schematów Oracle](oracle-schema-collections.md)  
 Opisuje kolekcję schematów obsługiwaną przez dostawcę .NET Framework dla firmy Oracle.  
  
 [Kolekcje schematów ODBC](odbc-schema-collections.md)  
 Opisuje kolekcje schematów dla sterowników ODBC.  
  
 [Kolekcje schematów OLE DB](ole-db-schema-collections.md)  
 Opisuje kolekcje schematów dla dostawców OLE DB.  
  
## <a name="reference"></a>Tematy pomocy  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Opisuje metodę **GetSchema** <xref:System.Data.Common.DbConnection> klasy.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Opisuje metodę **GetSchema** <xref:System.Data.Odbc.OdbcConnection> klasy.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Opisuje metodę **GetSchema** <xref:System.Data.OleDb.OleDbConnection> klasy.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Opisuje metodę **GetSchema** <xref:System.Data.OracleClient.OracleConnection> klasy.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Opisuje metodę **GetSchema** <xref:System.Data.SqlClient.SqlConnection> klasy.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Opisuje metodę **Getschemaing** <xref:System.Data.Common.DbDataReader> klasy.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Opisuje metodę **Getschemaing** <xref:System.Data.Odbc.OdbcDataReader> klasy.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Opisuje metodę **Getschemaing** <xref:System.Data.OleDb.OleDbDataReader> klasy.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Opisuje metodę **Getschemaing** <xref:System.Data.OracleClient.OracleDataReader> klasy.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Opisuje metodę **Getschemaing** <xref:System.Data.SqlClient.SqlDataReader> klasy.  
  
## <a name="see-also"></a>Zobacz też

- [Pobieranie i modyfikowanie danych ADO.NET](retrieving-and-modifying-data.md)
- [Omówienie ADO.NET](ado-net-overview.md)
