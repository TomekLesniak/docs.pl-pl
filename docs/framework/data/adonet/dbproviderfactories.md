---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: b5f2dbb687348afac98247cb21bae831dea26bfe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183315"
---
# <a name="dbproviderfactories"></a>DbProviderFactories

<xref:System.Data.Common>Przestrzeń nazw zawiera klasy służące do tworzenia <xref:System.Data.Common.DbProviderFactory> wystąpień do pracy z określonymi źródłami danych. Po utworzeniu <xref:System.Data.Common.DbProviderFactory> wystąpienia i przejściu do niego informacji o dostawcy danych `DbProviderFactory` można określić poprawny obiekt połączenia o jednoznacznie określonym typie, który ma zostać zwrócony na podstawie dostarczonych informacji.  
  
 Począwszy od .NET Framework w wersji 4, dostawcy danych, takie jak <xref:System.Data.Odbc> ,, <xref:System.Data.OleDb> <xref:System.Data.SqlClient> i <xref:System.Data.OracleClient> nie są już wymienione w pliku machine.config, ale Dostawcy niestandardowi nadal będą wyświetlani w tym miejscu.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Omówienie modelu fabryki](factory-model-overview.md)  
 Zawiera omówienie wzorca projektowego i interfejsu programowania.  
  
 [Uzyskiwanie DbProviderFactory](obtaining-a-dbproviderfactory.md)  
 Pokazuje, jak wyświetlić listę zainstalowanych dostawców danych i utworzyć <xref:System.Data.Common.DbConnection> z programu `DbProviderFactory` .  
  
 [DbConnection, DbCommand i DbException](dbconnection-dbcommand-and-dbexception.md)  
 Pokazuje, jak utworzyć <xref:System.Data.Common.DbCommand> i i <xref:System.Data.Common.DbDataReader> jak obsługiwać błędy danych przy użyciu programu <xref:System.Data.Common.DbException> .  
  
 [Modyfikowanie danych za pomocą obiektu DbDataAdapter](modifying-data-with-a-dbdataadapter.md)  
 Pokazuje, w jaki sposób używać elementu <xref:System.Data.Common.DbCommandBuilder> with a, <xref:System.Data.Common.DbDataAdapter> Aby pobierać i modyfikować dane.  
  
## <a name="see-also"></a>Zobacz też

- [Pobieranie i modyfikowanie danych ADO.NET](retrieving-and-modifying-data.md)
- [Omówienie ADO.NET](ado-net-overview.md)
