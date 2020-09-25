---
title: Funkcje daty i godziny
ms.date: 03/30/2017
ms.assetid: 971762d0-663b-4b64-8c61-352a8e6d3949
ms.openlocfilehash: aa024ad748db26cb75111984abdb61fdbd538ef9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198459"
---
# <a name="date-and-time-functions"></a>Funkcje daty i godziny

.NET Framework Dostawca danych for SQL Server (SqlClient) zawiera funkcje daty i godziny, które wykonują operacje na `System.DateTime` wartości wejściowej i zwracają `string` wynik, wartość numeryczną lub `System.DateTime` wartości. Te funkcje znajdują się w przestrzeni nazw SqlServer, która jest dostępna w przypadku korzystania z programu SqlClient. Właściwość przestrzeni nazw dostawcy umożliwia Entity Framework odnajdywania prefiksu używanego przez tego dostawcę dla określonych konstrukcji, takich jak typy i funkcje. W poniższej tabeli przedstawiono funkcje daty i godziny SqlClient.  
  
|Funkcja|Opis|  
|--------------|-----------------|  
|`DATEADD(datepart, number, date)`|Zwraca nową `DateTime` wartość opartą na dodawaniu interwału do określonej daty.<br /><br /> **Argumenty**<br /><br /> `datepart`: `String` Reprezentuje część daty, w której ma zostać zwrócona nowa wartość.<br /><br /> `number`: `Int32` ,, `Int64` `Decimal` , Lub `Double` wartość używana do przyrostu `datepart` .<br /><br /> `date:` Wyrażenie zwracające wartość `DateTime` , lub lub `DateTimeOffset` `Time` z dokładnością = [0-7] lub ciągiem znaków w formacie daty.<br /><br /> **Wartość zwracana**<br /><br /> Nowa `DateTime` , lub `DateTimeOffset` lub `Time` wartość o precyzji = [0-7].<br /><br /> **Przykład**<br /><br /> `SqlServer.DATEADD('day', 22, cast('6/9/2006' as DateTime))`|  
|`DATEDIFF(datepart,startdate,enddate)`|Zwraca liczbę granic daty i godziny przekroczenia między dwoma określonymi datami.<br /><br /> **Argumenty**<br /><br /> `datepart`: `String` Reprezentuje część daty, aby obliczyć różnicę.<br /><br /> `startdate`: Data początkowa obliczenia jest wyrażeniem zwracającym `DateTime` wartość, lub `DateTimeOffset` lub `Time` z dokładnością = [0-7] lub ciągiem znaków w formacie daty.<br /><br /> `enddate:` Data końcowa obliczenia jest wyrażeniem zwracającym `DateTime` wartość, lub `DateTimeOffset` lub `Time` z dokładnością = [0-7] lub ciągiem znaków w formacie daty.<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .<br /><br /> **Przykład**<br /><br /> `SqlServer.DATEDIFF('day', cast('6/9/2006' as DateTime),`<br /><br /> `cast('6/20/2006' as DateTime))`|  
|`DATENAME(datepart, date)`|Zwraca ciąg znaków reprezentujący określoną wartość parametru datepart określonej daty.<br /><br /> **Argumenty**<br /><br /> `datepart`: `String` Reprezentuje część daty, w której ma zostać zwrócona nowa wartość.<br /><br /> `date`: Wyrażenie zwracające `DateTime,` wartość or lub `DateTimeOffset` `Time` z dokładnością = [0-7] lub ciągiem znaków w formacie daty.<br /><br /> **Wartość zwracana**<br /><br /> Ciąg znaków reprezentujący określoną wartość parametru datepart określoną datę.<br /><br /> **Przykład**<br /><br /> `SqlServer.DATENAME('year', cast('6/9/2006' as DateTime))`|  
|`DATEPART(datepart, date)`|Zwraca liczbę całkowitą reprezentującą określoną wartość parametru datepart określonej daty.<br /><br /> **Argumenty**<br /><br /> `datepart`: `String` Reprezentuje część daty, w której ma zostać zwrócona nowa wartość.<br /><br /> `date`: Wyrażenie zwracające `DateTime,` `DateTimeOffset,` wartość lub lub `Time` z dokładnością = [0-7] lub ciągiem znaków w formacie daty.<br /><br /> **Wartość zwracana**<br /><br /> Określona wartość parametru datepart określonego dnia, jako `Int32` .<br /><br /> **Przykład**<br /><br /> `SqlServer.DATEPART('year', cast('6/9/2006' as DateTime))`|  
|`DAY(date)`|Zwraca dzień z określonej daty jako liczbę całkowitą.<br /><br /> **Argumenty**<br /><br /> `date`: Wyrażenie typu `DateTime` lub `DateTimeOffset` z dokładnością = 0-7.<br /><br /> **Wartość zwracana**<br /><br /> Dzień określonego dnia jako `Int32` .<br /><br /> **Przykład**<br /><br /> `SqlServer.DAY(cast('6/9/2006' as DateTime))`|  
|`GETDATE()`|Tworzy bieżącą datę i godzinę w SQL Server wewnętrznym formacie dla wartości DateTime.<br /><br /> **Wartość zwracana**<br /><br /> Bieżąca data i godzina systemowa `DateTime` z dokładnością 3.<br /><br /> **Przykład**<br /><br /> `SqlServer.GETDATE()`|  
|`GETUTCDATE()`|Tworzy wartość DateTime w formacie UTC (uniwersalny czas koordynowany lub czas uniwersalny Greenwich).<br /><br /> **Wartość zwracana**<br /><br /> `DateTime`Wartość z dokładnością 3 w formacie UTC.<br /><br /> **Przykład**<br /><br /> `SqlServer.GETUTCDATE()`|  
|`MONTH(date)`|Zwraca miesiąc z określoną datą jako liczbę całkowitą.<br /><br /> **Argumenty**<br /><br /> `date`: Wyrażenie typu `DateTime` lub `DateTimeOffset` z dokładnością = 0-7.<br /><br /> **Wartość zwracana**<br /><br /> Miesiąc określonego dnia jako `Int32` .<br /><br /> **Przykład**<br /><br /> `SqlServer.MONTH(cast('6/9/2006' as DateTime))`|  
|`YEAR(date)`|Zwraca rok z określonej daty jako liczbę całkowitą.<br /><br /> **Argumenty**<br /><br /> `date`: Wyrażenie typu `DateTime` lub `DateTimeOffset` z dokładnością = 0-7.<br /><br /> **Wartość zwracana**<br /><br /> Rok określonego dnia jako `Int32` .<br /><br /> **Przykład**<br /><br /> `SqlServer.YEAR(cast('6/9/2006' as DateTime))`|  
|`SYSDATETIME()`|Zwraca `DateTime` wartość z dokładnością do 7.<br /><br /> **Wartość zwracana**<br /><br /> `DateTime`Wartość z dokładnością do 7.<br /><br /> **Przykład**<br /><br /> `SqlServer.SYSDATETIME()`|  
|`SYSUTCDATE()`|Tworzy wartość DateTime w formacie UTC (uniwersalny czas koordynowany lub czas uniwersalny Greenwich).<br /><br /> **Wartość zwracana**<br /><br /> `DateTime`Wartość o dokładności = 7 w formacie UTC.<br /><br /> **Przykład**<br /><br /> `SqlServer.SYSUTCDATE()`|  
|`SYSDATETIMEOFFSET()`|Zwraca `DateTimeOffset` z dokładnością do 7.<br /><br /> **Wartość zwracana**<br /><br /> `DateTimeOffset`Wartość z dokładnością 7 w formacie UTC.<br /><br /> **Przykład**<br /><br /> `SqlServer.SYSDATETIMEOFFSET()`|  
  
 Aby uzyskać więcej informacji na temat funkcji usługi Data i godzina obsługiwanych przez program SqlClient, zobacz [typy danych daty i godziny oraz funkcje (Transact-SQL)](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).
  
## <a name="see-also"></a>Zobacz też

- [Klient SQL dla funkcji programu Entity Framework](sqlclient-for-ef-functions.md)
