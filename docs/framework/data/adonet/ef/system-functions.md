---
title: Funkcje systemowe
ms.date: 03/30/2017
ms.assetid: b7c71b58-09e6-44ce-a3e5-a0fdb892fb86
ms.openlocfilehash: 0d46429ac958e6f5db4d51947669784303af783b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156501"
---
# <a name="system-functions"></a>Funkcje systemowe

Dostawca danych .NET Framework dla SQL Server (SqlClient) udostępnia następujące funkcje systemowe:  
  
|Funkcja|Opis|  
|--------------|-----------------|  
|`CHECKSUM (` `value`, [`value`, [`value`]]`)`|Zwraca wartość sumy kontrolnej. `CHECKSUM` jest przeznaczony do użycia podczas tworzenia indeksów skrótu.<br /><br /> **Argumenty**<br /><br /> `value`: A `Boolean` ,,,,,,,,, `Byte` `Int16` `Int32` `Int64` `Single` `Decimal` `Double` `DateTime` `String` , `Binary` lub `Guid` . Można określić jedną, dwie lub trzy wartości.<br /><br /> **Wartość zwracana**<br /><br /> Wartość bezwzględna określonego wyrażenia.<br /><br /> **Przykład**<br /><br /> `SqlServer.CHECKSUM(10,100,1000.0)`|  
|`CURRENT_TIMESTAMP ()`|Tworzy bieżącą datę i godzinę w SQL Server wewnętrznym formacie dla `DateTime` wartości z dokładnością 7 w SQL Server 2008 i dokładnością 3 w SQL Server 2005.<br /><br /> **Wartość zwracana**<br /><br /> Bieżąca data i godzina systemowa jako `DateTime` .<br /><br /> **Przykład**<br /><br /> `SqlServer.CURRENT_TIMESTAMP()`|  
|`CURRENT_ USER` `()`|Zwraca nazwę bieżącego użytkownika.<br /><br /> **Wartość zwracana**<br /><br /> ASCII `String` .<br /><br /> **Przykład**<br /><br /> `SqlServer.CURRENT_USER()`|  
|`DATALENGTH` `(` `expression` `)`|Zwraca liczbę bajtów użytych do reprezentowania dowolnego wyrażenia.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Boolean` ,,,,,,,,, `Byte` `Int16` `Int32` `Int64` `Single` `Decimal` `Double` `DateTime` `Time` , `DateTimeOffset` , `String` ,, `Binary` lub `Guid` .<br /><br /> **Wartość zwracana**<br /><br /> Rozmiar właściwości jako `Int32` .<br /><br /> **Przykład**<br /><br /> `SELECT VALUE SqlServer.DATALENGTH(P.Name)FROM`<br /><br /> `AdventureWorksEntities.Product AS P`|  
|`HOST_NAME()`|Zwraca nazwę stacji roboczej.<br /><br /> **Wartość zwracana**<br /><br /> Unicode `String` .<br /><br /> **Przykład**<br /><br /> `SqlServer.HOST_NAME()`|  
|`ISDATE(` `expression` `)`|Określa, czy wyrażenie wejściowe jest prawidłową datą.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Boolean` ,,,,,,,,, `Byte` `Int16` `Int32` `Int64` `Single` `Decimal` `Double` `DateTime` `Time` , `DateTimeOffset` , `String` ,, `Binary` lub `Guid` .<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` . Jeden (1), jeśli wyrażenie wejściowe jest prawidłową datą. Zero (0) w przeciwnym razie.<br /><br /> **Przykład**<br /><br /> `SqlServer.ISDATE('1/1/2006')`|  
|`ISNUMERIC(` `expression` `)`|Określa, czy wyrażenie jest prawidłowym typem liczbowym.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Boolean` ,,,,,,,,, `Byte` `Int16` `Int32` `Int64` `Single` `Decimal` `Double` `DateTime` `Time` , `DateTimeOffset` , `String` ,, `Binary` lub `Guid` .<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` . Jeden (1), jeśli wyrażenie wejściowe jest prawidłową datą. Zero (0) w przeciwnym razie.<br /><br /> **Przykład**<br /><br /> `SqlServer.ISNUMERIC('21')`|  
|`NEWID()`|Tworzy unikatową wartość typu GUID.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `Guid`.<br /><br /> **Przykład**<br /><br /> `SqlServer.NEWID()`|  
|`USER_NAME(` `id` `)`|Zwraca nazwę użytkownika bazy danych z określonego numeru identyfikacyjnego.<br /><br /> **Argumenty**<br /><br /> `expression`: `Int32` Numer identyfikacyjny skojarzony z użytkownikiem bazy danych.<br /><br /> **Wartość zwracana**<br /><br /> Unicode `String` .<br /><br /> **Przykład**<br /><br /> `SqlServer.USER_NAME(0)`|  
  
 Aby uzyskać więcej informacji o `String` funkcjach obsługiwanych przez program SqlClient, zobacz [Funkcje ciągów (Transact-SQL)](/sql/t-sql/functions/string-functions-transact-sql).
  
## <a name="see-also"></a>Zobacz też

- [Jednostki języka SQL](./language-reference/entity-sql-language.md)
- [Klient SQL dla funkcji programu Entity Framework](sqlclient-for-ef-functions.md)
