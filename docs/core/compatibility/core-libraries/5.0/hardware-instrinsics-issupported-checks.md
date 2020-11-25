---
title: 'Nieprzerwana zmiana: wewnętrzne testy nieobsługiwane przez sprzęt mogą się różnić w zależności od typów zagnieżdżonych'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których jest sprawdzana wersja Funkcja issupport dla elementów wewnętrznych sprzętu może teraz generować inny wynik.
ms.date: 11/01/2020
ms.openlocfilehash: 9acef15860de76a9743621cb4c5edba5aac3931c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761555"
---
# <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a>Wewnętrzne testy nieobsługiwane sprzętowo mogą się różnić w zależności od typów zagnieżdżonych

Sprawdzanie `<Isa>.X64.IsSupported` , gdzie `<Isa>` odwołuje się do klas w <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> przestrzeni nazw, może teraz generować różne wyniki do poprzednich wersji platformy .NET.

> [!TIP]
> Program *ISA* jest przeznaczony dla standardowej architektury branżowej.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET niektóre <xref:System.Runtime.Intrinsics.X86> Typy sprzętu — na przykład, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType> nie uwidaczniają klasy zagnieżdżonej `X64` . W przypadku tych typów wywoływanie `<Isa>.X64.IsSupported` został rozwiązany z `IsSupported` właściwością `X64` klasy zagnieżdżonej klasy nadrzędnej `<Isa>` . Oznacza to, że właściwość może zwrócić `true` nawet wtedy, gdy `<Isa>.IsSupported` zwraca `false` .

W programie .NET 5,0 i jego nowszych wersjach wszystkie <xref:System.Runtime.Intrinsics.X86> typy uwidaczniają zagnieżdżoną `X64` klasę, która odpowiednio obsługuje raporty. Dzięki temu ogólna hierarchia jest poprawna, a w `<Isa>.X64.IsSupported` przypadku `true` , gdy jest, `<Isa>.IsSupported` można również przyjąć, że jest to możliwe `true` .

## <a name="reason-for-change"></a>Przyczyna zmiany

Miało to `<Isa>.X64.IsSupported` `true` na celu, że `<Isa>.IsSupported` jest również implikowane `true` . Jednak ze względu na sposób, w jaki rozpoznawanie elementów członkowskich działa w języku C#, klasy, które nie miały klasy zagnieżdżonej, `X64` uwidaczniają sytuację, w której to nigdy nie było tak samo, i doprowadziło do błędów w kodzie użytkownika.

## <a name="recommended-action"></a>Zalecana akcja

W razie potrzeby dostosuj kod, który sprawdza, czy `IsSupported` ma być sprawdzana odpowiednia wartość ISA.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
