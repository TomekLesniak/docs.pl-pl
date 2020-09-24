---
title: Mapowanie typu danych Oracle
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: 71a85f82ea3535cf7aec8dd92fbda6726a36fb81
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166576"
---
# <a name="oracle-data-type-mappings"></a>Mapowanie typu danych Oracle

Poniższa tabela zawiera listę typów danych Oracle i ich mapowania na <xref:System.Data.OracleClient.OracleDataReader> .  
  
|Typ danych Oracle|Typ danych .NET Framework zwracany przez OracleDataReader. GetValue|OracleClient typ danych zwrócony przez OracleDataReader. GetOracleValue|Uwagi|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**DOTYCZĄCE**|**Byte []**|<xref:System.Data.OracleClient.OracleBFile>||  
|**TWORZENIA**|**Byte []**|<xref:System.Data.OracleClient.OracleLob>||  
|**DELIKATN**|**Ciąg**|<xref:System.Data.OracleClient.OracleString>||  
|**OBIEKTÓW CLOB**|**Ciąg**|<xref:System.Data.OracleClient.OracleLob>||  
|**DNIU**|**Data/godzina**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Dokładności**|<xref:System.Data.OracleClient.OracleNumber>|Ten typ danych jest aliasem dla typu danych **Number** i został zaprojektowany tak, aby <xref:System.Data.OracleClient.OracleDataReader> zwracał wartość **System. Decimal** lub <xref:System.Data.OracleClient.OracleNumber> zamiast wartości zmiennoprzecinkowej. Użycie .NET Frameworkgo typu danych może spowodować przepełnienie.|  
|**CAŁKOWITĄ**|**Dokładności**|<xref:System.Data.OracleClient.OracleNumber>|Ten typ danych jest aliasem dla typu danych **Number (38)** i został zaprojektowany tak, aby <xref:System.Data.OracleClient.OracleDataReader> zwracał wartość **System. Decimal** lub <xref:System.Data.OracleClient.OracleNumber> zamiast wartości całkowitej. Użycie .NET Frameworkgo typu danych może spowodować przepełnienie.|  
|**INTERWAŁ OD ROKU DO MIESIĄCA**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERWAŁ OD DNIA DO SEKUNDY**|**Czasu**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**DŁUGO**|**Ciąg**|<xref:System.Data.OracleClient.OracleString>||  
|**DŁUGI NIEPRZETWORZONY**|**Byte []**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**Ciąg**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**Ciąg**|<xref:System.Data.OracleClient.OracleLob>||  
|**Liczba**|**Dokładności**|<xref:System.Data.OracleClient.OracleNumber>|Użycie .NET Frameworkgo typu danych może spowodować przepełnienie.|  
|**NVARCHAR2**|**Ciąg**|<xref:System.Data.OracleClient.OracleString>||  
|**SUROWCÓW**|**Byte []**|<xref:System.Data.OracleClient.OracleBinary>||  
|**WSKAŹNIK REF**|||Typ danych **kursora ref** firmy Oracle nie jest obsługiwany przez <xref:System.Data.OracleClient.OracleDataReader> obiekt.|  
|**Właściwość**|**Ciąg**|<xref:System.Data.OracleClient.OracleString>||  
|**ZNACZNIK czasu**|**Data/godzina**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**SYGNATURA CZASOWA Z LOKALNĄ STREFĄ CZASOWĄ**|**Data/godzina**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**SYGNATURA CZASOWA ZE STREFĄ CZASOWĄ**|**Data/godzina**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**LICZBA CAŁKOWITA BEZ ZNAKU**|**Liczba**|<xref:System.Data.OracleClient.OracleNumber>|Ten typ danych jest aliasem dla typu danych **Number (38)** i został zaprojektowany tak, aby <xref:System.Data.OracleClient.OracleDataReader> zwracał wartość **System. Decimal** lub <xref:System.Data.OracleClient.OracleNumber> zamiast niepodpisanej wartości całkowitej. Użycie .NET Frameworkgo typu danych może spowodować przepełnienie.|  
|**VARCHAR2**|**Ciąg**|<xref:System.Data.OracleClient.OracleString>||  
  
 W poniższej tabeli przedstawiono typy danych Oracle i typy danych .NET Framework (**System. Data. DbType** i <xref:System.Data.OracleClient.OracleType> ), które mają być używane podczas wiązania ich jako parametry.  
  
|Typ danych Oracle|Wyliczenie DbType do powiązania jako parametr|Wyliczenie OracleType do powiązania jako parametr|Uwagi|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**DOTYCZĄCE**||**Dotyczące**|W **przypadku programu Oracle** można powiązać **tylko parametr bInformacje** . Program .NET Dostawca danych for Oracle nie konstruuje się automatycznie, jeśli spróbujesz powiązać wartość inną niż**bInformacje** , taką jak **Byte []** lub <xref:System.Data.OracleClient.OracleBinary> .|  
|**TWORZENIA**||**Obiekt blob**|Oracle pozwala tylko na powiązanie **obiektu BLOB** jako parametru **obiektu BLOB** . Program .NET Dostawca danych for Oracle nie konstruuje się automatycznie, jeśli spróbujesz powiązać wartość inną niż**obiekt BLOB** , taką jak **Byte []** lub <xref:System.Data.OracleClient.OracleBinary> .|  
|**DELIKATN**|**AnsiStringFixedLength**|**Delikatn**||  
|**OBIEKTÓW CLOB**||**Obiektów CLOB**|Firma Oracle umożliwia powiązanie **obiektów CLOB** jako parametru **obiektów CLOB** . Program .NET Dostawca danych for Oracle nie konstruuje go automatycznie, jeśli podejmiesz próbę powiązania wartości innej niż**obiektów CLOB** , takiej jak **System. String** lub <xref:System.Data.OracleClient.OracleString> .|  
|**DNIU**|**Data/godzina**|**Data/godzina**||  
|**FLOAT**|**Pojedyncza, podwójna, dziesiętna**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Określa **System. Data. DbType** i <xref:System.Data.OracleClient.OracleType> .|  
|**CAŁKOWITĄ**|**Wartość =, Int16, Int32, Int64, Decimal**|**Wartość =, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Określa **System. Data. DbType** i <xref:System.Data.OracleClient.OracleType> .|  
|**INTERWAŁ OD ROKU DO MIESIĄCA**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> jest dostępny tylko w przypadku korzystania z oprogramowania klienckiego Oracle 9i i serwera.|  
|**INTERWAŁ OD DNIA DO SEKUNDY**|**Stream**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> jest dostępny tylko w przypadku korzystania z oprogramowania klienckiego Oracle 9i i serwera.|  
|**DŁUGO**|**AnsiString**|**LongVarChar**||  
|**DŁUGI NIEPRZETWORZONY**|**Binarne**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Firma Oracle umożliwia powiązanie **NCLOB** jako parametru **NCLOB** . Program .NET Dostawca danych for Oracle nie konstruuje go automatycznie, jeśli podejmiesz próbę powiązania wartości innej niż**NCLOB** , takiej jak **System. String** lub <xref:System.Data.OracleClient.OracleString> .|  
|**Liczba**|**VarNumeric**|**Liczba**||  
|**NVARCHAR2**|**Ciąg**|**NVarChar**||  
|**SUROWCÓW**|**Binarne**|**Nieprzetworzone**||  
|**WSKAŹNIK REF**||**Biera**|Aby uzyskać więcej informacji, zobacz [kursory ref Oracle](oracle-ref-cursors.md).|  
|**Właściwość**|**AnsiString**|**Właściwość**||  
|**ZNACZNIK czasu**|**Data/godzina**|**Timestamp**|<xref:System.Data.OracleClient.OracleType> jest dostępny tylko w przypadku korzystania z oprogramowania klienckiego Oracle 9i i serwera.|  
|**SYGNATURA CZASOWA Z LOKALNĄ STREFĄ CZASOWĄ**|**Data/godzina**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> jest dostępny tylko w przypadku korzystania z oprogramowania klienckiego Oracle 9i i serwera.|  
|**SYGNATURA CZASOWA ZE STREFĄ CZASOWĄ**|**Data/godzina**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> jest dostępny tylko w przypadku korzystania z oprogramowania klienckiego Oracle 9i i serwera.|  
|**LICZBA CAŁKOWITA BEZ ZNAKU**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, UInt32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Określa **System. Data. DbType** i <xref:System.Data.OracleClient.OracleType> .|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Wartości **InputOutput**, **Output**i **ReturnValue** **ParameterDirection** używane przez <xref:System.Data.OracleClient.OracleParameter.Value%2A> Właściwość <xref:System.Data.OracleClient.OracleParameter> obiektu są .NET Framework typami danych, chyba że wartość wejściowa jest typem danych Oracle (na przykład <xref:System.Data.OracleClient.OracleNumber> lub <xref:System.Data.OracleClient.OracleString> ). Nie ma to zastosowania do typów danych **kursora ref**, **bInformacje**i **LOB** .  
  
## <a name="see-also"></a>Zobacz też

- [Oracle i ADO.NET](oracle-and-adonet.md)
- [Omówienie ADO.NET](ado-net-overview.md)
