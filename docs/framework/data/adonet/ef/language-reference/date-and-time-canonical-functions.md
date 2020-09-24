---
title: Funkcji daty i godziny Canonical
ms.date: 03/30/2017
ms.assetid: 9628b74f-1585-436a-b385-8b02ed0cdd63
ms.openlocfilehash: 9b7650990232face3a7c3673a6fb789912acf15c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148285"
---
# <a name="date-and-time-canonical-functions"></a>Funkcji daty i godziny Canonical

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] obejmuje funkcje kanoniczne daty i godziny.  
  
## <a name="remarks"></a>Uwagi  

 W poniższej tabeli przedstawiono [!INCLUDE[esql](../../../../../../includes/esql-md.md)] funkcje kanoniczne daty i godziny. `datetime` jest <xref:System.DateTime> wartością.  
  
|Funkcja|Opis|  
|--------------|-----------------|  
|`AddNanoseconds(expression,number)`|Dodaje określoną `number` liczbę nanosekund do `expression` .<br /><br /> **Argumenty**<br /><br /> `expression`: `DateTime` , `DateTimeOffset` , lub `Time` .<br /><br /> `number`: `Int32`.<br /><br /> **Wartość zwracana**<br /><br /> Typ `expression` .|  
|`AddMicroseconds(expression,number)`|Dodaje określone `number` mikrosekundy do `expression` .<br /><br /> **Argumenty**<br /><br /> `expression`: `DateTime` , `DateTimeOffset` , lub `Time` .<br /><br /> `number`: `Int32`.<br /><br /> **Wartość zwracana**<br /><br /> Typ `expression` .|  
|`AddMilliseconds(expression,number)`|Dodaje określoną `number` liczbę milisekund do `expression` .<br /><br /> **Argumenty**<br /><br /> `expression`: `DateTime` , `DateTimeOffset` , lub `Time` .<br /><br /> `number`: `Int32`.<br /><br /> **Wartość zwracana**<br /><br /> Typ `expression` .|  
|`AddSeconds(expression,number)`|Dodaje określoną `number` liczbę sekund do `expression` .<br /><br /> **Argumenty**<br /><br /> `expression`: `DateTime` , `DateTimeOffset` , lub `Time` .<br /><br /> `number`: `Int32`.<br /><br /> **Wartość zwracana**<br /><br /> Typ `expression` .|  
|`AddMinutes(expression,number)`|Dodaje określoną `number` liczbę minut do `expression` .<br /><br /> **Argumenty**<br /><br /> `expression`: `DateTime` , `DateTimeOffset` , lub `Time` .<br /><br /> `number`: `Int32`.<br /><br /> **Wartość zwracana**<br /><br /> Typ `expression` .|  
|`AddHours(expression,number)`|Dodaje określoną `number` liczbę godzin do `expression` .<br /><br /> **Argumenty**<br /><br /> `expression`: `DateTime` , `DateTimeOffset` , lub `Time` .<br /><br /> `number`: `Int32`.<br /><br /> **Wartość zwracana**<br /><br /> Typ `expression` .|  
|`AddDays(expression,number)`|Dodaje określoną `number` liczbę dni do `expression` .<br /><br /> **Argumenty**<br /><br /> `expression`: `DateTime` lub `DateTimeOffset` .<br /><br /> `number`: `Int32`.<br /><br /> **Wartość zwracana**<br /><br /> Typ `expression` .|  
|`AddMonths(expression,number)`|Dodaje określoną `number` liczbę miesięcy do `expression` .<br /><br /> **Argumenty**<br /><br /> `expression`: `DateTime` lub `DateTimeOffset` .<br /><br /> `number`: `Int32`.<br /><br /> **Wartość zwracana**<br /><br /> Typ `expression` .|  
|`AddYears(expression,number)`|Dodaje określone `number` lata do `expression` .<br /><br /> **Argumenty**<br /><br /> `expression`: `DateTime` lub `DateTimeOffset` .<br /><br /> `number`: `Int32`.<br /><br /> **Wartość zwracana**<br /><br /> Typ `expression` .|  
|`CreateDateTime(year,month,day,hour,minute,second)`|Zwraca nową `DateTime` wartość jako bieżącą datę i godzinę serwera w strefie czasowej serwera.<br /><br /> **Argumenty**<br /><br /> `year`, `month` , `day` , `hour` , `minute` : `Int16` i `Int32` .<br /><br /> `second`: `Double`.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `DateTime`.|  
|`CreateDateTimeOffset(year,month,day,hour,minute,second,tzoffset)`|Zwraca nową `DateTimeOffset` wartość jako bieżącą datę i godzinę serwera względem uniwersalnego czasu koordynowanego (UTC).<br /><br /> **Argumenty**<br /><br /> `year`, `month`, `day`, `hour`, `minute`, `tzoffset`: `Int32`.<br /><br /> `second`: `Double`.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `DateTimeOffset`.|  
|`CreateTime(hour,minute,second)`|Zwraca nową `Time` wartość jako bieżącą godzinę.<br /><br /> **Argumenty**<br /><br /> `hour` i `minute` : `Int32` .<br /><br /> `second`: `Double`.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `Time`.|  
|`CurrentDateTime()`|Zwraca `DateTime` wartość jako bieżącą datę i godzinę serwera w strefie czasowej serwera.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `DateTime`.|  
|`CurrentDateTimeOffset()`|Zwraca bieżącą datę, godzinę i przesunięcie jako `DateTimeOffset` .<br /><br /> **Wartość zwracana**<br /><br /> Klasa `DateTimeOffset`.|  
|`CurrentUtcDateTime()`|Zwraca <xref:System.DateTime> wartość jako bieżącą datę i godzinę serwera w strefie czasowej UTS.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `DateTime`.|  
|`Day(expression)`|Zwraca część dnia z `expression` `Int32` zakresu od 1 do 31.<br /><br /> **Argumenty**<br /><br /> A `DateTime` i `DateTimeOffset` .<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 12.`<br /><br /> `Day(cast('03/12/1998' as DateTime))`|  
|`DayOfYear(expression)`|Zwraca część dnia z `expression` `Int32` przedziału od 1 do 366, gdzie 366 jest zwracany przez ostatni dzień roku przestępnego.<br /><br /> **Argumenty**<br /><br /> A `DateTime` lub `DateTimeOffset` .<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`DiffNanoseconds(startExpression,endExpression)`|Zwraca różnicę w nanosekundach, między `startExpression` i `endExpression` .<br /><br /> **Argumenty**<br /><br /> `startExpression`, `endExpression` : `DateTime` , `DateTimeOffset` lub `Time` . **Uwaga:** `startExpression` i `endExpression` muszą być tego samego typu.   <br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`DiffMilliseconds(startExpression,endExpression)`|Zwraca różnicę (w milisekundach) między `startExpression` i `endExpression` .<br /><br /> **Argumenty**<br /><br /> `startExpression`, `endExpression` : `DateTime` , `DateTimeOffset` lub `Time` . **Uwaga:** `startExpression` i `endExpression` muszą być tego samego typu.   <br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`DiffMicroseconds(startExpression,endExpression)`|Zwraca różnicę, w mikrosekundach, między `startExpression` i `endExpression` .<br /><br /> **Argumenty**<br /><br /> `startExpression`, `endExpression` : `DateTime` , `DateTimeOffset` lub `Time` . **Uwaga:** `startExpression` i `endExpression` muszą być tego samego typu.   <br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`DiffSeconds(startExpression,endExpression)`|Zwraca różnicę (w sekundach) między `startExpression` i `endExpression` .<br /><br /> **Argumenty**<br /><br /> `startExpression`, `endExpression` : `DateTime` , `DateTimeOffset` lub `Time` . **Uwaga:** `startExpression` i `endExpression` muszą być tego samego typu.   <br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`DiffMinutes(startExpression,endExpression)`|Zwraca różnicę (w minutach) między `startExpression` i `endExpression` .<br /><br /> **Argumenty**<br /><br /> `startExpression`, `endExpression` : `DateTime` , `DateTimeOffset` lub `Time` . **Uwaga:** `startExpression` i `endExpression` muszą być tego samego typu.   <br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`DiffHours(startExpression,endExpression)`|Zwraca różnicę (w godzinach) między `startExpression` i `endExpression` .<br /><br /> **Argumenty**<br /><br /> `startExpression`, `endExpression` : `DateTime` , `DateTimeOffset` lub `Time` . **Uwaga:** `startExpression` i `endExpression` muszą być tego samego typu.   <br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`DiffDays(startExpression,endExpression)`|Zwraca różnicę (w dniach) między `startExpression` i `endExpression` .<br /><br /> **Argumenty**<br /><br /> `startExpression`, `endExpression` : `DateTime` lub `DateTimeOffset` . **Uwaga:** `startExpression` i `endExpression` muszą być tego samego typu.   <br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`DiffMonths(startExpression,endExpression)`|Zwraca różnicę w miesiącach, między `startExpression` i `endExpression` .<br /><br /> **Argumenty**<br /><br /> `startExpression`, `endExpression` : `DateTime` lub `DateTimeOffset` . **Uwaga:** `startExpression` i `endExpression` muszą być tego samego typu.   <br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`DiffYears(startExpression,endExpression)`|Zwraca różnicę (w latach) między `startExpression` i `endExpression` .<br /><br /> **Argumenty**<br /><br /> `startExpression`, `endExpression` : `DateTime` lub `DateTimeOffset` . **Uwaga:** `startExpression` i `endExpression` muszą być tego samego typu.   <br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`GetTotalOffsetMinutes(datetimeoffset)`|Zwraca liczbę minut, przez jaką `datetimeoffset` jest przesunięty od GMT. Zwykle jest to między + 780 i – 780 (+ lub-13 godzin). **Uwaga:**  Ta funkcja jest obsługiwana tylko w SQL Server 2008. <br /><br /> **Argumenty**<br /><br /> Klasa `DateTimeOffset`.<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`Hour(expression)`|Zwraca część godziny z `expression` `Int32` przedziału od 0 do 23.<br /><br /> **Argumenty**<br /><br /> A `DateTime, Time` i `DateTimeOffset` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 22.`<br /><br /> `Hour(cast('22:35:5' as DateTime))`|  
|`Millisecond(expression)`|Zwraca część milisekundową z `expression` `Int32` przedziału od 0 do 999.<br /><br /> **Argumenty**<br /><br /> A `DateTime, Time` i `DateTimeOffset` .<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .|  
|`Minute(expression)`|Zwraca część minuty z `expression` `Int32` przedziału od 0 do 59.<br /><br /> **Argumenty**<br /><br /> A `DateTime, Time` lub `DateTimeOffset` .<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 35`<br /><br /> `Minute(cast('22:35:5' as DateTime))`|  
|`Month(expression)`|Zwraca część miesiąca z `expression` `Int32` przedziału od 1 do 12.<br /><br /> **Argumenty**<br /><br /> A `DateTime` lub `DateTimeOffset` .<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 3.`<br /><br /> `Month(cast('03/12/1998' as DateTime))`|  
|`Second(expression)`|Zwraca część sekund z `expression` `Int32` przedziału od 0 do 59.<br /><br /> **Argumenty**<br /><br /> A `DateTime, Time` i `DateTimeOffset` .<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 5`<br /><br /> `Second(cast('22:35:5' as DateTime))`|  
|`TruncateTime(expression)`|Zwraca wartość `expression` , która obcina wartości czasu.<br /><br /> **Argumenty**<br /><br /> A `DateTime` lub `DateTimeOffset` .<br /><br /> **Wartość zwracana**<br /><br /> Typ `expression` .|  
|`Year(expression)`|Zwraca część roku `expression` jako `Int32` `YYYY` .<br /><br /> **Argumenty**<br /><br /> A `DateTime` i `DateTimeOffset` .<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 1998.`<br /><br /> `Year(cast('03/12/1998' as DateTime))`|  
  
 Te funkcje zostaną zwrócone, `null` Jeśli dane `null` wejściowe.  
  
 Równoważne funkcje są dostępne w dostawcy zarządzanym przez klienta programu Microsoft SQL. Aby uzyskać więcej informacji, zobacz temat [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Zobacz też

- [Funkcje Canonical](canonical-functions.md)
