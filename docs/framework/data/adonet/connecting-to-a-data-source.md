---
title: Nawiązywanie połączenia ze źródłem danych
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: b9e69b029ad37c583e51c219f87ff9d7d8e7315c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203777"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Nawiązywanie połączenia ze źródłem danych w ADO.NET

W programie ADO.NET do łączenia się z określonym źródłem danych jest używany obiekt **połączenia** , dostarczając wymagane informacje o uwierzytelnianiu w parametrach połączenia. Używany obiekt **połączenia** zależy od typu źródła danych.  
  
 Każdy dostawca danych .NET Framework dołączony do .NET Framework ma <xref:System.Data.Common.DbConnection> obiekt: Dostawca danych .NET Framework dla OLE DB zawiera obiekt, .NET Framework dostawca danych dla <xref:System.Data.OleDb.OleDbConnection> SQL Server zawiera obiekt <xref:System.Data.SqlClient.SqlConnection> , .NET Framework dostawca danych dla ODBC zawiera obiekt, a .NET Framework dostawca danych <xref:System.Data.Odbc.OdbcConnection> dla programu Oracle zawiera <xref:System.Data.OracleClient.OracleConnection> obiekt.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Nawiązywanie połączenia](establishing-the-connection.md)\
 Opisuje sposób użycia obiektu **połączenia** w celu nawiązania połączenia ze źródłem danych.  
  
 [Zdarzenia połączenia](connection-events.md)\
 Opisuje sposób użycia zdarzenia **InfoMessage** do pobierania komunikatów informacyjnych ze źródła danych.  
  
## <a name="see-also"></a>Zobacz też

- [Parametry połączenia](connection-strings.md)
- [Pula połączeń](connection-pooling.md)
- [Polecenia i parametry](commands-and-parameters.md)
- [Elementy DataAdapter i DataReader](dataadapters-and-datareaders.md)
- [Transakcje i współbieżność](transactions-and-concurrency.md)
- [Omówienie ADO.NET](ado-net-overview.md)
