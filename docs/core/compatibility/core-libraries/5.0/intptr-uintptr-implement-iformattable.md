---
title: 'Zmiana podziału: IntPtr i UIntPtr Implementuj IFormattable'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których IntPtr i UIntPtr implementują teraz IFormattable.
ms.date: 11/01/2020
ms.openlocfilehash: 0684652cdc2b8cf1d237074263bf0809082b0dcd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761640"
---
# <a name="intptr-and-uintptr-implement-iformattable"></a>IntPtr i UIntPtr Implementuj IFormattable

<xref:System.IntPtr> i <xref:System.UIntPtr> teraz implementowane <xref:System.IFormattable> . Funkcje, które sprawdzają <xref:System.IFormattable> obsługę, mogą teraz zwracać różne wyniki dla tych typów, ponieważ mogą one być przekazywane specyfikatorem formatu i kulturą.

## <a name="change-description"></a>Zmień opis

We wcześniejszych wersjach programu .NET <xref:System.IntPtr> i <xref:System.UIntPtr> nie należy implementować programu <xref:System.IFormattable> . Funkcje, które sprawdzają, mogą powracać <xref:System.IFormattable> do samego wywołania <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> lub <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType> , co oznacza, że specyfikatory formatu i kultury nie są przestrzegane.

W programie .NET 5,0 i jego nowszych wersjach <xref:System.IntPtr> i <xref:System.UIntPtr> implementacji <xref:System.IFormattable> . Funkcje, które sprawdzają <xref:System.IFormattable> obsługę, mogą teraz zwracać różne wyniki dla tych typów, ponieważ mogą one być przekazywane specyfikatorem formatu i kulturą.

Ta zmiana ma wpływ na scenariusze, takie jak interpolowane ciągi i <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> , między innymi.

## <a name="reason-for-change"></a>Przyczyna zmiany

<xref:System.IntPtr><xref:System.UIntPtr>Język C# obsługuje teraz `nint` `nuint` słowa kluczowe i. Typy kopii zapasowych zostały zaktualizowane, aby zapewnić bliską parzystość (tam, gdzie to możliwe) funkcje udostępniane przez inne typy pierwotne, na przykład <xref:System.Int32?displayProperty=nameWithType> .

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

Jeśli nie chcesz używać specyfikatora formatu lub kultury niestandardowej, która ma być używana podczas wyświetlania wartości tych typów, możesz wywołać <xref:System.IntPtr.ToString?displayProperty=nameWithType> i <xref:System.UIntPtr.ToString?displayProperty=nameWithType> przeciążenia `ToString()` .

## <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

### Category

Core .NET libraries

### Affected APIs

Not detectable via API analysis.

-->
