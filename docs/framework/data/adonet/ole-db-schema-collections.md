---
title: Kolekcje schematów OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 90899a123b3dafcd47a50ef8f6eb003938b22a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186942"
---
# <a name="ole-db-schema-collections"></a>Kolekcje schematów OLE DB

W tej sekcji omówiono obsługę kolekcji schematów dla OLE DB dostawców dla Microsoft SQL Server, Oracle i Microsoft Jet.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Dostawca OLE DB Microsoft SQL Server  

 Sterownik OLE DB Microsoft SQL Server obsługuje następujące kolekcje schematów oprócz wspólnych kolekcji schematów:  
  
- Tabele  
  
- Kolumny  
  
- Procedury  
  
- ProcedureParameters  
  
- Wykaz  
  
- Indeksy  
  
### <a name="tables"></a>Tabele  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|TABLE_TYPE|String|  
|TABLE_GUID|Guid (identyfikator GUID)|  
|OPIS|String|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Kolumny  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid (identyfikator GUID)|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|String|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid (identyfikator GUID)|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|String|  
|CHARACTER_SET_SCHEMA|String|  
|CHARACTER_SET_NAME|String|  
|COLLATION_CATALOG|String|  
|COLLATION_SCHEMA|String|  
|COLLATION_NAME|String|  
|DOMAIN_CATALOG|String|  
|DOMAIN_SCHEMA|String|  
|DOMAIN_NAME|String|  
|OPIS|String|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte []|  
|IS_COMPUTED|Boolean|  
  
### <a name="procedures"></a>Procedury  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|PROCEDURE_CATALOG|String|  
|PROCEDURE_SCHEMA|String|  
|PROCEDURE_NAME|String|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|String|  
|OPIS|String|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|PROCEDURE_CATALOG|String|  
|PROCEDURE_SCHEMA|String|  
|PROCEDURE_NAME|String|  
|PARAMETER_NAME|String|  
|ORDINAL_POSITION|Int32|  
|PARAMETER_TYPE|Int32|  
|PARAMETER_HASDEFAULT|Boolean|  
|PARAMETER_DEFAULT|String|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|OPIS|String|  
|TYPE_NAME|String|  
|LOCAL_TYPE_NAME|String|  
  
### <a name="catalog"></a>Wykaz  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|CATALOG_NAME|String|  
|OPIS|String|  
  
### <a name="indexes"></a>Indeksy  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|INDEX_CATALOG|String|  
|INDEX_SCHEMA|String|  
|INDEX_NAME|String|  
|PRIMARY_KEY|Boolean|  
|UNIKATOWY|Boolean|  
|CLUSTERED|Boolean|  
|TYP|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULL — Wartości|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid (identyfikator GUID)|  
|COLUMN_PROPID|Int64|  
|SORTOWANIE|Int16|  
|KARDYNALNOŚCI|Liczba dziesiętna|  
|Page|Int32|  
|FILTER_CONDITION|String|  
|ZINTEGROWANE|Boolean|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Dostawca OLE DB Microsoft Oracle  

 Sterownik programu Microsoft Oracle OLE DB obsługuje następujące wybrane kolekcje schematów oprócz wspólnych kolekcji schematów:  
  
- Tabele  
  
- Kolumny  
  
- Procedury  
  
- ProcedureColumns  
  
- ProcedureParameters  
  
- Widoki  
  
- Indeksy  
  
### <a name="tables"></a>Tabele  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|TABLE_TYPE|String|  
|TABLE_GUID|Guid (identyfikator GUID)|  
|OPIS|String|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Kolumny  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid (identyfikator GUID)|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|String|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid (identyfikator GUID)|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|String|  
|CHARACTER_SET_SCHEMA|String|  
|CHARACTER_SET_NAME|String|  
|COLLATION_CATALOG|String|  
|COLLATION_SCHEMA|String|  
|COLLATION_NAME|String|  
|DOMAIN_CATALOG|String|  
|DOMAIN_SCHEMA|String|  
|DOMAIN_NAME|String|  
|OPIS|String|  
  
### <a name="procedures"></a>Procedury  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|PROCEDURE_CATALOG|String|  
|PROCEDURE_SCHEMA|String|  
|PROCEDURE_NAME|String|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|String|  
|OPIS|String|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|PROCEDURE_CATALOG|String|  
|PROCEDURE_SCHEMA|String|  
|PROCEDURE_NAME|String|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid (identyfikator GUID)|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid (identyfikator GUID)|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|OPIS|String|  
|WYSTĘPUJĄ|Int16|  
  
### <a name="views"></a>Widoki  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|VIEW_DEFINITION|String|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|OPIS|String|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indeksy  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|INDEX_CATALOG|String|  
|INDEX_SCHEMA|String|  
|INDEX_NAME|String|  
|PRIMARY_KEY|Boolean|  
|UNIKATOWY|Boolean|  
|CLUSTERED|Boolean|  
|TYP|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULL — Wartości|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid (identyfikator GUID)|  
|COLUMN_PROPID|Int64|  
|SORTOWANIE|Int16|  
|KARDYNALNOŚCI|Liczba dziesiętna|  
|Page|Int32|  
|FILTER_CONDITION|String|  
|ZINTEGROWANE|Boolean|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Dostawca OLE DB Microsoft Jet  

 Sterownik programu Microsoft Jet OLE DB obsługuje następujące kolekcje schematów oprócz wspólnych kolekcji schematów:  
  
- Tabele  
  
- Kolumny  
  
- Procedury  
  
- Widoki  
  
- Indeksy  
  
### <a name="tables"></a>Tabele  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|TABLE_TYPE|String|  
|TABLE_GUID|Guid (identyfikator GUID)|  
|OPIS|String|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Kolumny  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid (identyfikator GUID)|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|String|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid (identyfikator GUID)|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|String|  
|CHARACTER_SET_SCHEMA|String|  
|CHARACTER_SET_NAME|String|  
|COLLATION_CATALOG|String|  
|COLLATION_SCHEMA|String|  
|COLLATION_NAME|String|  
|DOMAIN_CATALOG|String|  
|DOMAIN_SCHEMA|String|  
|DOMAIN_NAME|String|  
|OPIS|String|  
  
### <a name="procedures"></a>Procedury  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|PROCEDURE_CATALOG|String|  
|PROCEDURE_SCHEMA|String|  
|PROCEDURE_NAME|String|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|String|  
|OPIS|String|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="views"></a>Widoki  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|VIEW_DEFINITION|String|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|OPIS|String|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indeksy  
  
|nazwa_kolumny|typ_danych|  
|----------------|--------------|  
|TABLE_CATALOG|String|  
|TABLE_SCHEMA|String|  
|TABLE_NAME|String|  
|INDEX_CATALOG|String|  
|INDEX_SCHEMA|String|  
|INDEX_NAME|String|  
|PRIMARY_KEY|Boolean|  
|UNIKATOWY|Boolean|  
|CLUSTERED|Boolean|  
|TYP|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULL — Wartości|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|String|  
|COLUMN_GUID|Guid (identyfikator GUID)|  
|COLUMN_PROPID|Int64|  
|SORTOWANIE|Int16|  
|KARDYNALNOŚCI|Liczba dziesiętna|  
|Page|Int32|  
|FILTER_CONDITION|String|  
|ZINTEGROWANE|Boolean|  
  
## <a name="see-also"></a>Zobacz też

- [Omówienie ADO.NET](ado-net-overview.md)
