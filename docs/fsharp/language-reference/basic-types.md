---
title: Typy podstawowe
description: 'Znajdź podstawowe typy podstawowe, które są używane w języku F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 659ac8424c62985affcca1741e1b2a74c9c3ee8d
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557701"
---
# <a name="basic-types"></a>Typy podstawowe

W tym temacie wymieniono podstawowe typy, które są zdefiniowane w języku F #. Te typy są najbardziej podstawowe w języku F #, co jest podstawą niemal każdego programu w języku F #. Są one nadzbiorem typów pierwotnych platformy .NET.

|Typ|Typ .NET|Opis|Przykład|
|----|---------|-----------|-------|
|`bool`|<xref:System.Boolean>|Możliwe wartości to `true` i `false` .|`true`/`false`|
|`byte`|<xref:System.Byte>|Wartości od 0 do 255.|`1uy`|
|`sbyte`|<xref:System.SByte>|Wartości od-128 do 127.|`1y`|
|`int16`|<xref:System.Int16>|Wartości od-32768 do 32767.|`1s`|
|`uint16`|<xref:System.UInt16>|Wartości od 0 do 65535.|`1us`|
|`int`|<xref:System.Int32>|Wartości od-2 147 483 648 do 2 147 483 647.|`1`|
|`uint`|<xref:System.UInt32>|Wartości od 0 do 4 294 967 295.|`1u`|
|`int64`|<xref:System.Int64>|Wartości z-zakresu od do 9 223 372 036 854 775 807.|`1L`|
|`uint64`|<xref:System.UInt64>|Wartości od 0 do 18446744073709551615 są.|`1UL`|
|`nativeint`|<xref:System.IntPtr>|Natywny wskaźnik jako liczbę całkowitą ze znakiem.|`nativeint 1`|
|`unativeint`|<xref:System.UIntPtr>|Natywny wskaźnik jako liczbę całkowitą bez znaku.|`unativeint 1`|
|`decimal`|<xref:System.Decimal>|Zmiennoprzecinkowy typ danych, który ma co najmniej 28 znaczących cyfr.|`1.0`|
|`float`, `double`|<xref:System.Double>|64-bitowy typ zmiennoprzecinkowy.|`1.0`|
|`float32`, `single`|<xref:System.Single>|32-bitowy typ zmiennoprzecinkowy.|`1.0f`|
|`char`|<xref:System.Char>|Wartości znaków Unicode.|`'c'`|
|`string`|<xref:System.String>|Tekst Unicode.|`"str"`|
|`unit`|nie dotyczy|Wskazuje brak wartości rzeczywistej. Typ ma tylko jedną wartość formalną, która jest oznaczona `()` . Wartość jednostki, `()` ,, jest często używana jako symbol zastępczy, gdzie wartość jest wymagana, ale żadna wartość rzeczywista nie jest dostępna lub nie ma sensu.|`()`|

> [!NOTE]
> Za pomocą typu [bigint](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-bigint.html) można wykonać obliczenia z liczbą całkowitą za dużą dla typu 64-bitowego liczby całkowitej. `bigint` nie jest uznawany za typ podstawowy; jest to skrót dla `System.Numerics.BigInteger` .

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
