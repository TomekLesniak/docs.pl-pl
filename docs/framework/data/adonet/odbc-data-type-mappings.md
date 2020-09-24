---
title: Mapowanie typu danych ODBC
ms.date: 03/30/2017
ms.assetid: 43c35d32-831d-480f-a150-78f7e869d17f
ms.openlocfilehash: b08c649c148aacf4050c1f7ebcc17f79d1305e0c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150716"
---
# <a name="odbc-data-type-mappings"></a>Mapowanie typu danych ODBC

W poniższej tabeli przedstawiono wywnioskowany typ .NET Framework dla typów danych z .NET Framework Dostawca danych dla ODBC ( <xref:System.Data.Odbc> ). Wymienione metody dostępu <xref:System.Data.Odbc.OdbcDataReader> są również wyświetlane.  
  
|Typ ODBC|Typ programu .NET Framework|Metoda dostępu typu .NET Framework|  
|---------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|SQL_BIGINT|Int64|GetInt64 ()|  
|SQL_BINARY|Byte []|GetBytes ()|  
|SQL_BIT|Boolean|GetBoolean ()|  
|SQL_CHAR|String<br /><br /> Char []|GetString ()<br /><br /> GetChars ()|  
|SQL_DECIMAL|Liczba dziesiętna|GetDecimal ()|  
|SQL_DOUBLE|Double|GetDouble ()|  
|SQL_GUID|Guid (identyfikator GUID)|GetGuid ()|  
|SQL_INTEGER|Int32|GetInt32 ()|  
|SQL_LONG_VARCHAR|String<br /><br /> Char []|GetString ()<br /><br /> GetChars ()|  
|SQL_LONGVARBINARY|Byte []|GetBytes ()|  
|SQL_NUMERIC|Liczba dziesiętna|GetDecimal ()|  
|SQL_REAL|Pojedynczy|GetFloat ()|  
|SQL_SMALLINT|Int16|GetInt16 ()|  
|SQL_TINYINT|Byte|GetByte ()|  
|SQL_TYPE_TIMES|DateTime|GetDateTime ()|  
|SQL_TYPE_TIMESTAMP|DateTime|GetDateTime ()|  
|SQL_VARBINARY|Byte []|GetBytes ()|  
|SQL_WCHAR|String<br /><br /> Char []|GetString ()<br /><br /> GetChars ()|  
|SQL_WLONGVARCHAR|String<br /><br /> Char []|GetString ()<br /><br /> GetChars ()|  
|SQL_WVARCHAR|String<br /><br /> Char []|GetString ()<br /><br /> GetChars ()|  
  
## <a name="see-also"></a>Zobacz też

- [Pobieranie i modyfikowanie danych ADO.NET](retrieving-and-modifying-data.md)
- [Omówienie ADO.NET](ado-net-overview.md)
