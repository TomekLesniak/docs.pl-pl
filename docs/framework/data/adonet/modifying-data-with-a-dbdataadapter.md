---
title: Modyfikowanie danych za pomocą obiektu DbDataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e35c7f9e-648b-4fcc-9361-d365c3e42c9a
ms.openlocfilehash: 5272a53ae0b3ac1888d01dc2a59778c6c7231619
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150768"
---
# <a name="modifying-data-with-a-dbdataadapter"></a>Modyfikowanie danych za pomocą obiektu DbDataAdapter

<xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A>Metoda <xref:System.Data.Common.DbProviderFactory> obiektu daje <xref:System.Data.Common.DbDataAdapter> obiekt, który jest silnie wpisana do źródłowego dostawcy danych określonego podczas tworzenia fabryki. Następnie można użyć programu, <xref:System.Data.Common.DbCommandBuilder> Aby utworzyć polecenia do wstawiania, aktualizowania i usuwania danych ze <xref:System.Data.DataSet> źródła danych.  
  
## <a name="retrieving-data-with-a-dbdataadapter"></a>Pobieranie danych przy użyciu DbDataAdapter  

 W tym przykładzie pokazano, jak utworzyć silnie wpisaną `DbDataAdapter` na podstawie nazwy dostawcy i parametrów połączenia. Kod używa <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> metody <xref:System.Data.Common.DbProviderFactory> do utworzenia <xref:System.Data.Common.DbConnection> . Następnie kod używa <xref:System.Data.Common.DbProviderFactory.CreateCommand%2A> metody do tworzenia <xref:System.Data.Common.DbCommand> i wybierania danych przez ustawienie `CommandText` `Connection` właściwości i. Na koniec kod tworzy <xref:System.Data.Common.DbDataAdapter> Obiekt przy użyciu <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> metody i ustawia jego `SelectCommand` Właściwość. `Fill`Metoda `DbDataAdapter` ładowania danych do <xref:System.Data.DataTable> .  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/VB/source.vb#1)]  
  
## <a name="modifying-data-with-a-dbdataadapter"></a>Modyfikowanie danych za pomocą obiektu DbDataAdapter  

 W tym przykładzie pokazano, jak modyfikować dane przy `DataTable` użyciu a za <xref:System.Data.Common.DbDataAdapter> pomocą programu, <xref:System.Data.Common.DbCommandBuilder> Aby generować polecenia wymagane do aktualizowania danych w źródle danych. <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> `DbDataAdapter` Jest ustawiony na pobieranie wartości CustomerID i NazwaFirmy z tabeli Customers. <xref:System.Data.Common.DbCommandBuilder.GetInsertCommand%2A>Metoda jest używana do ustawiania <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> właściwości, <xref:System.Data.Common.DbCommandBuilder.GetUpdateCommand%2A> Metoda jest używana do ustawiania <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> właściwości, a <xref:System.Data.Common.DbCommandBuilder.GetDeleteCommand%2A> Metoda jest używana do ustawiania <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> właściwości. Kod dodaje nowy wiersz do tabeli Customers i aktualizuje źródło danych. Kod następnie lokalizuje dodany wiersz, wyszukując identyfikator IDKlienta, który jest kluczem podstawowym zdefiniowanym dla tabeli Customers. Zmienia on NazwaFirmy i aktualizuje źródło danych. Na koniec kod usuwa wiersz.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/VB/source.vb#1)]  
  
## <a name="handling-parameters"></a>Obsługa parametrów  

 Dostawcy danych .NET Framework obsługują nazewnictwo i Określanie parametrów i symboli zastępczych parametrów w różny sposób. Ta składnia jest dostosowana do określonego źródła danych, zgodnie z opisem w poniższej tabeli.  
  
|Dostawca danych|Składnia nazewnictwa parametrów|  
|-------------------|-----------------------------|  
|`SqlClient`|Używa nazwanych parametrów w formacie `@` *ParameterName*.|  
|`OracleClient`|Używa nazwanych parametrów w formacie `:` *parmname* (lub *parmname*).|  
|`OleDb`|Używa znaczników parametrów pozycyjnych wskazanych przez znak zapytania ( `?` ).|  
|`Odbc`|Używa znaczników parametrów pozycyjnych wskazanych przez znak zapytania ( `?` ).|  
  
 Model fabryki nie ułatwia tworzenia sparametryzowanych `DbCommand` i `DbDataAdapter` obiektów. Musisz rozgałęzić w kodzie, aby utworzyć parametry, które są dostosowane do dostawcy danych.  
  
> [!IMPORTANT]
> Unikanie parametrów specyficznych dla dostawcy całkowicie przy użyciu łączenia ciągów do konstruowania bezpośrednich instrukcji SQL nie jest zalecane ze względów bezpieczeństwa. Używanie łączenia ciągów zamiast parametrów pozostawia aplikację narażoną na ataki z iniekcją SQL.  
  
## <a name="see-also"></a>Zobacz też

- [DbProviderFactories](dbproviderfactories.md)
- [Uzyskiwanie DbProviderFactory](obtaining-a-dbproviderfactory.md)
- [DbConnection, DbCommand i DbException](dbconnection-dbcommand-and-dbexception.md)
- [Omówienie ADO.NET](ado-net-overview.md)
