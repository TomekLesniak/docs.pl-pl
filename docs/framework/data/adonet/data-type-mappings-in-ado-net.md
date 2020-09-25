---
title: Mapowanie typu danych
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 52e64714a17448cd94723bdc216d8ea069fc5eef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177751"
---
# <a name="data-type-mappings-in-adonet"></a>Mapowanie typu danych w ADO.NET

.NET Framework opiera się na wspólnym typie systemu, który definiuje, w jaki sposób typy są zadeklarowane, używane i zarządzane w czasie wykonywania. Składa się z obu typów wartości i typów referencyjnych, które pochodzą z <xref:System.Object> typu podstawowego. Podczas pracy ze źródłem danych typ danych jest wnioskowany od dostawcy danych, jeśli nie został jawnie określony. Na przykład <xref:System.Data.DataSet> obiekt jest niezależny od określonego źródła danych. Dane z programu `DataSet` są pobierane ze źródła danych, a zmiany są utrwalane w źródle danych przy użyciu `DataAdapter` . Oznacza to, że `DataAdapter` w przypadku wypełniania <xref:System.Data.DataTable> wartości z `DataSet` wartościami ze źródła danych, typy danych w kolumnach `DataTable` są .NET Framework typy, a nie typy specyficzne dla .NET Framework dostawcy danych, który jest używany do nawiązywania połączenia ze źródłem danych.  
  
 Podobnie, gdy `DataReader` zwraca wartość ze źródła danych, wynikowa wartość jest przechowywana w zmiennej lokalnej, która ma typ .NET Framework. Dla `Fill` operacji `DataAdapter` i `Get` metod `DataReader` , typ .NET Framework jest wywnioskowany na podstawie wartości zwróconej przez dostawcę danych .NET Framework.  
  
 Zamiast polegać na wywnioskowanym typie danych, można użyć typów metod dostępu typu w `DataReader` przypadku, gdy wiadomo, że określony typ zwracanej wartości. Wpisywane metody dostępu zapewniają lepszą wydajność, zwracając wartość jako określony typ .NET Framework, co eliminuje konieczność stosowania dodatkowej konwersji typu.  
  
> [!NOTE]
> Wartości null dla typów danych .NET Framework dostawcy danych są reprezentowane przez `DBNull.Value` .  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Mapowanie typu danych serwera SQL](sql-server-data-type-mappings.md)  
 Wyświetla listę odroczonych mapowań typu danych i metod dostępu do danych dla programu <xref:System.Data.SqlClient> .  
  
 [Mapowanie typu danych OLE DB](ole-db-data-type-mappings.md)  
 Wyświetla listę odroczonych mapowań typu danych i metod dostępu do danych dla programu <xref:System.Data.OleDb> .  
  
 [Mapowanie typu danych ODBC](odbc-data-type-mappings.md)  
 Wyświetla listę odroczonych mapowań typu danych i metod dostępu do danych dla programu <xref:System.Data.Odbc> .  
  
 [Mapowanie typu danych Oracle](oracle-data-type-mappings.md)  
 Wyświetla listę odroczonych mapowań typu danych i metod dostępu do danych dla programu <xref:System.Data.OracleClient> .  
  
 [Liczby zmiennoprzecinkowe](floating-point-numbers.md)  
 Opisuje problemy, które deweloperzy często napotykają podczas pracy z liczbami zmiennoprzecinkowymi.  
  
## <a name="see-also"></a>Zobacz też

- [Typy danych programu SQL Server i ADO.NET](./sql/sql-server-data-types.md)
- [Konfigurowanie parametrów i typów danych parametrów](configuring-parameters-and-parameter-data-types.md)
- [Pobieranie informacji o schemacie bazy danych](retrieving-database-schema-information.md)
- [Wspólny system typów](../../../standard/base-types/common-type-system.md)
- [Konwertowanie typów](/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [Omówienie ADO.NET](ado-net-overview.md)
