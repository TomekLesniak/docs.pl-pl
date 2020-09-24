---
title: Klient SQL dla typów programu Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: bca2cc0e0d9f43c51c66080f3bd38c245ce94381
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156592"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>Klient SQL dla typów programu Entity Framework

Plik manifestu dostawcy programu .NET Framework Dostawca danych for SQL Server (SqlClient) zawiera listę typów pierwotnych dostawcy, zestawów reguł dla każdego typu, mapowania między typami pierwotnymi modelu koncepcyjnego i magazynu oraz reguły podnoszenia i konwersji między typami pierwotnymi modelu koncepcyjnego i magazynu.  
  
 Poniższa tabela zawiera opis typów dla SQL Server 2008, SQL Server 2005 i SQL Server 2000 baz danych oraz tego, jak te typy są mapowane na typy modelu koncepcyjnego. Niektóre nowe typy zostały wprowadzone w nowszych wersjach SQL Server nie są obsługiwane we wcześniejszych wersjach SQL Server. Te typy są wymienione w poniższej tabeli.  
  
|Typ dostawcy<br /><br /> name|Typ dostawcy<br /><br /> atrybuty|`EDMSimpleType`<br /><br /> name|Aspekty|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|nie dotyczy|`Edm.Boolean`|nie dotyczy|  
|`tinyint`|nie dotyczy|`Edm.Byte`|nie dotyczy|  
|`smallint`|nie dotyczy|`Edm.Int16`|nie dotyczy|  
|`int`|nie dotyczy|`Edm.Int32`|nie dotyczy|  
|`bigint`|nie dotyczy|`Edm.Int64`|nie dotyczy|  
|`float`|nie dotyczy|`Edm.Double`|nie dotyczy|  
|`real`|nie dotyczy|`Edm.Double`|nie dotyczy|  
|`decimal`|nie dotyczy|`Edm.Decimal`|Dokładne<br /><br /> -Minimum: 1<br /><br /> -Maksimum: 38<br /><br /> -Domyślnie: 18<br /><br /> -Stała: FAŁSZ<br /><br /> Zasięgu<br /><br /> -Minimum: 0<br /><br /> -Maksimum: 38<br /><br /> -Wartość domyślna: 0<br /><br /> -Stała: FAŁSZ|  
|`numeric`|nie dotyczy|`Edm.Decimal`|Dokładne<br /><br /> -Minimum: 1<br /><br /> -Maksimum: 38<br /><br /> -Domyślnie: 18<br /><br /> -Stała: FAŁSZ<br /><br /> Zasięgu<br /><br /> -Minimum: 0<br /><br /> -Maksimum: 38<br /><br /> -Wartość domyślna: 0<br /><br /> -Stała: FAŁSZ|  
|`smallmoney`|nie dotyczy|`Edm.Decimal`|Dokładne<br /><br /> -Domyślnie: 10<br /><br /> -Stała: prawda<br /><br /> Zasięgu<br /><br /> -Domyślnie: 4<br /><br /> -Stała: prawda|  
|`money`|nie dotyczy|`Edm.Decimal`|Dokładne<br /><br /> -Domyślnie: 19<br /><br /> -Stała: prawda<br /><br /> Zasięgu<br /><br /> -Domyślnie: 4<br /><br /> -Stała: prawda|  
|`binary`|nie dotyczy|`Edm.Binary`|MaxLength<br /><br /> -Minimum: 1<br /><br /> -Maksimum: 8000<br /><br /> -Wartość domyślna: 8000<br /><br /> -Stała: FAŁSZ<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: prawda<br /><br /> -Stała: prawda|  
|`varbinary`|nie dotyczy|`Edm.Binary`|MaxLength<br /><br /> -Minimum: 1<br /><br /> -Maksimum: 8000<br /><br /> -Wartość domyślna: 8000<br /><br /> -Stała: FAŁSZ<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda|  
|`varbinary(max)`<br /><br /> Uwaga: ten typ nie jest obsługiwany w SQL Server 2000.|nie dotyczy|`Edm.Binary`|MaxLength<br /><br /> -Wartość domyślna: 214748364780<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda|  
|`image`|nie dotyczy|`Edm.Binary`|MaxLength<br /><br /> -Wartość domyślna: 2147483647<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda|  
|`timestamp`|nie dotyczy|`Edm.Binary`|MaxLength<br /><br /> -Domyślnie: 8<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: prawda<br /><br /> -Stała: prawda|  
|`rowversion`|nie dotyczy|`Edm.Binary`|MaxLength<br /><br /> -Domyślnie: 8<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: prawda<br /><br /> -Stała: prawda|  
|`smalldatetime`|nie dotyczy|`Edm.DateTime`|Dokładne<br /><br /> -Wartość domyślna: 0<br /><br /> -Stała: prawda|  
|`datetime`|nie dotyczy|`Edm.DateTime`|Dokładne<br /><br /> -Wartość domyślna: 3<br /><br /> -Stała: prawda|  
|`date`<br /><br /> Uwaga: ten typ nie jest obsługiwany w SQL Server 2005 i SQL Server 2000.|nie dotyczy|`Edm.DateTime`|Dokładne<br /><br /> -Wartość domyślna: 0<br /><br /> -Stała: FAŁSZ|  
|`time`<br /><br /> Uwaga: ten typ nie jest obsługiwany w SQL Server 2005 i SQL Server 2000.|nie dotyczy|`Edm.Time`|Dokładne<br /><br /> -Domyślnie: 7<br /><br /> -Stała: FAŁSZ|  
|`datetime2`<br /><br /> Uwaga: ten typ nie jest obsługiwany w SQL Server 2005 i SQL Server 2000.|nie dotyczy|`Edm.DateTime`|Dokładne<br /><br /> -Domyślnie: 7<br /><br /> -Stała: FAŁSZ|  
|`datetimeoffset`<br /><br /> Uwaga: ten typ nie jest obsługiwany w SQL Server 2005 i SQL Server 2000.|nie dotyczy|`Edm.DateTimeOffset`|Dokładne<br /><br /> -Domyślnie: 7<br /><br /> -Stała: FAŁSZ|  
|`nvarchar`<br /><br /> Uwaga: ten typ nie jest obsługiwany w SQL Server 2000.|nie dotyczy|`Edm.String`|MaxLength<br /><br /> -Minimum: 1<br /><br /> -Maksimum: 4000<br /><br /> -Wartość domyślna: 4000<br /><br /> -Stała: FAŁSZ<br /><br /> Unicode:<br /><br /> -Wartość domyślna: prawda<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda|  
|`varchar`<br /><br /> Uwaga: ten typ nie jest obsługiwany w SQL Server 2000.|nie dotyczy|`Edm.String`|MaxLength<br /><br /> -Minimum: 1<br /><br /> -Maksimum: 8000<br /><br /> -Wartość domyślna: 8000<br /><br /> -Stała: FAŁSZ<br /><br /> Unicode:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda|  
|`char`|nie dotyczy|`Edm.String`|MaxLength<br /><br /> -Minimum: 1<br /><br /> -Maksimum: 8000<br /><br /> -Wartość domyślna: 8000<br /><br /> -Stała: FAŁSZ<br /><br /> Unicode:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: prawda<br /><br /> -Stała: prawda|  
|`nchar`|nie dotyczy|`Edm.String`|MaxLength<br /><br /> -Minimum: 1<br /><br /> -Maksimum: 4000<br /><br /> -Wartość domyślna: 4000<br /><br /> -Stała: FAŁSZ<br /><br /> Unicode:<br /><br /> -Wartość domyślna: prawda<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: prawda<br /><br /> -Stała: prawda|  
|`varchar`(`max`)|nie dotyczy|`Edm.String`|MaxLength<br /><br /> -Wartość domyślna: 2147483647<br /><br /> -Stała: prawda<br /><br /> Unicode:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda|  
|`nvarchar`(`max`)|nie dotyczy|`Edm.String`|MaxLength<br /><br /> -Wartość domyślna: 1073741823<br /><br /> -Stała: prawda<br /><br /> Unicode:<br /><br /> -Wartość domyślna: prawda<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda|  
|`ntext`|Równe porównywalne: FAŁSZ<br /><br /> Zamówienie porównywalne: FAŁSZ|`Edm.String`|MaxLength<br /><br /> -Wartość domyślna: 1073741823<br /><br /> -Stała: prawda<br /><br /> Unicode:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda|  
|`text`|Równe porównywalne: FAŁSZ<br /><br /> Zamówienie porównywalne: FAŁSZ|`Edm.String`|MaxLength<br /><br /> -Wartość domyślna: 2147483647<br /><br /> -Stała: prawda<br /><br /> Unicode:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda|  
|`Unique`<br /><br /> `identifier`|Równe porównywalne: prawda<br /><br /> Zamówienie porównywalne: prawda|`Edm.Guid`|nie dotyczy|  
|`xml`|Równe porównywalne: FAŁSZ<br /><br /> Zamówienie porównywalne: FAŁSZ|`Edm.String`|MaxLength<br /><br /> -Wartość domyślna: 1073741823<br /><br /> -Stała: prawda<br /><br /> Unicode:<br /><br /> -Wartość domyślna: prawda<br /><br /> -Stała: prawda<br /><br /> FixedLength:<br /><br /> -Wartość domyślna: false<br /><br /> -Stała: prawda|  
  
## <a name="see-also"></a>Zobacz też

- [Specyfikacje CSDL, SSDL i MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
