---
title: System.TimeSpan, metody
ms.date: 03/30/2017
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
ms.openlocfilehash: 15b6c8bd5c9cce8e6d1bac030c6b7f6b40df6cd4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155591"
---
# <a name="systemtimespan-methods"></a>System.TimeSpan, metody

Obsługa elementów członkowskich <xref:System.TimeSpan?displayProperty=nameWithType> znacznie zależy od wersji .NET Framework i Microsoft SQL Server, z których korzystasz.  
  
 Gdy metoda, operator lub właściwość jest nieobsługiwana; oznacza to, że LINQ to SQL nie może przetłumaczyć elementu członkowskiego na wykonanie na SQL Server. Nadal możesz korzystać z tych elementów członkowskich w kodzie. Jednak muszą być oceniane przed przekazaniem zapytania do języka Transact-SQL lub po pobraniu wyników z bazy danych.  
  
## <a name="previous-limitations"></a>Poprzednie ograniczenia  

 W przypadku korzystania z LINQ to SQL z wersjami .NET Framework przed .NET Framework 3,5 SP1 nie można mapować SQL Server pól bazy danych na <xref:System.TimeSpan?displayProperty=nameWithType> . Jednak operacje na <xref:System.TimeSpan> są obsługiwane, ponieważ <xref:System.TimeSpan> wartości mogą być zwracane z <xref:System.DateTime> odejmowania lub wprowadzane do wyrażenia jako literału lub zmiennej powiązanej.  
  
## <a name="supported-systemtimespan-member-support"></a>Obsługiwane wsparcie składowej system. TimeSpan

 Poniższe LINQ to SQL-obsługiwane metody, operatory i właściwości są dostępne do użycia w zapytaniach LINQ to SQL. Po zmapowaniu w modelu obiektów lub zewnętrznym pliku mapowania LINQ to SQL umożliwia wywoływanie wielu <xref:System.TimeSpan?displayProperty=nameWithType> elementów członkowskich wewnątrz zapytań LINQ to SQL.  
  
|Obsługiwane <xref:System.TimeSpan> metody|Obsługiwane <xref:System.TimeSpan> Operatory|Obsługiwane <xref:System.TimeSpan> właściwości|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<xref:System.TimeSpan.MinValue>|  
  
> [!NOTE]
> Możliwość mapowania <xref:System.TimeSpan?displayProperty=nameWithType> do `TIME` kolumny SQL z LINQ to SQL wymaga .NET Framework 3,5 z dodatkiem SP1 i poza nią. `TIME`Typ danych SQL jest dostępny tylko w Microsoft SQL Server 2008 i więcej.  
  
### <a name="addition-and-subtraction"></a>Dodawanie i odejmowanie  

 Chociaż typ CLR obsługuje <xref:System.TimeSpan?displayProperty=nameWithType> Dodawanie i odejmowanie, typ SQL nie `TIME` jest. W związku z tym zapytania LINQ to SQL generują błędy, jeśli spróbują Dodawanie i odejmowanie, gdy są one mapowane na typ SQL `TIME` . Inne zagadnienia dotyczące pracy z typami dat i godzin SQL można znaleźć w [mapowaniu typu SQL-CLR](sql-clr-type-mapping.md).  
  
## <a name="see-also"></a>Zobacz też

- [Pojęcia dotyczące zapytań](query-concepts.md)
- [Tworzenie modelu obiektu](creating-the-object-model.md)
- [Mapowania typów środowiska SQL-CLR](sql-clr-type-mapping.md)
- [Typy danych i funkcje](data-types-and-functions.md)
