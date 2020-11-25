---
title: Tabele konwersji typów na platformie .NET
ms.date: 03/30/2017
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET], type conversions
- data types [.NET], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
ms.openlocfilehash: dc98a326155273805e3157d99755de2e97f83a46
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730217"
---
# <a name="type-conversion-tables-in-net"></a>Tabele konwersji typów na platformie .NET

Konwersja rozszerzająca występuje, gdy wartość jednego typu jest konwertowana na inny typ o równym lub większym rozmiarze. Konwersja zawęża występuje, gdy wartość jednego typu jest konwertowana na wartość innego typu o mniejszym rozmiarze. Tabele w tym temacie ilustrują zachowania w obu typach konwersji.  
  
## <a name="widening-conversions"></a>Poszerzenie konwersji  

 W poniższej tabeli opisano konwersje rozszerzające, które mogą być wykonywane bez utraty informacji.  
  
|Typ|Mogą być konwertowane bez utraty danych|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.SByte>|<xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int16>|<xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt16>|<xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Char>|<xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int32>|<xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt32>|<xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 Niektóre rozszerzone konwersje na <xref:System.Single> lub <xref:System.Double> mogą spowodować utratę precyzji. W poniższej tabeli opisano konwersje rozszerzające, które czasami powodują utratę informacji.  
  
|Typ|Można przekonwertować na|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## <a name="narrowing-conversions"></a>Konwersje zawężające  

 Zawężanie konwersji na <xref:System.Single> lub <xref:System.Double> może spowodować utratę informacji. Jeśli typ docelowy nie może prawidłowo przedstawić wielkości źródła, typ wyniku jest ustawiony na stałą `PositiveInfinity` lub `NegativeInfinity` . `PositiveInfinity` wyniki dzielenia liczby dodatniej przez zero i są zwracane, gdy wartość <xref:System.Single> lub <xref:System.Double> przekracza wartość `MaxValue` pola. `NegativeInfinity` wyniki dzielenia ujemnej liczby przez zero i są zwracane, gdy wartość <xref:System.Single> lub <xref:System.Double> spadnie poniżej wartości `MinValue` pola. Konwersja z do a <xref:System.Double> <xref:System.Single> może skutkować `PositiveInfinity` lub `NegativeInfinity` .  
  
 Zawężanie konwersji może również spowodować utratę informacji dla innych typów danych. Jednak <xref:System.OverflowException> jest zgłaszany, jeśli wartość konwertowanego typu wykracza poza zakres określony przez typ docelowy `MaxValue` i `MinValue` pola, a konwersja jest sprawdzana przez środowisko uruchomieniowe, aby upewnić się, że wartość typu docelowego nie przekracza jego `MaxValue` lub `MinValue` . Konwersje wykonywane z <xref:System.Convert?displayProperty=nameWithType> klasą są zawsze sprawdzane w ten sposób.  
  
 W poniższej tabeli wymieniono konwersje, które generują <xref:System.OverflowException> użycie <xref:System.Convert?displayProperty=nameWithType> lub wszelką sprawdzoną konwersję, jeśli wartość konwertowanego typu jest poza zdefiniowanym zakresem typu zwracanego.  
  
|Typ|Można przekonwertować na|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>|  
|<xref:System.Int16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16>|  
|<xref:System.UInt16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>|  
|<xref:System.Int32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32>|  
|<xref:System.UInt32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>|  
|<xref:System.Int64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64>|  
|<xref:System.UInt64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>|  
|<xref:System.Decimal>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Single>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Double>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Convert?displayProperty=nameWithType>
- [Konwersja typów w programie .NET](type-conversion.md)
