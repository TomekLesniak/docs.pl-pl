---
ms.openlocfilehash: bba9659b92e5aabc276c585929c99898316036c5
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359141"
---
### <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a>Wewnętrzne testy nieobsługiwane sprzętowo mogą się różnić w zależności od typów zagnieżdżonych

Sprawdzanie `<Isa>.X64.IsSupported` , gdzie `<Isa>` odwołuje się do klas w <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> przestrzeni nazw, może teraz generować różne wyniki do poprzednich wersji platformy .NET.

> [!TIP]
> Program *ISA* jest przeznaczony dla standardowej architektury branżowej.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET niektóre <xref:System.Runtime.Intrinsics.X86> Typy sprzętu — na przykład, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType> nie uwidaczniają klasy zagnieżdżonej `X64` . W przypadku tych typów wywoływanie `<Isa>.X64.IsSupported` został rozwiązany z `IsSupported` właściwością `X64` klasy zagnieżdżonej klasy nadrzędnej `<Isa>` . Oznacza to, że właściwość może zwrócić `true` nawet wtedy, gdy `<Isa>.IsSupported` zwraca `false` .

W programie .NET 5,0 i jego nowszych wersjach wszystkie <xref:System.Runtime.Intrinsics.X86> typy uwidaczniają zagnieżdżoną `X64` klasę, która odpowiednio obsługuje raporty. Dzięki temu ogólna hierarchia jest poprawna, a w `<Isa>.X64.IsSupported` przypadku `true` , gdy jest, `<Isa>.IsSupported` można również przyjąć, że jest to możliwe `true` .

#### <a name="reason-for-change"></a>Przyczyna zmiany

Miało to `<Isa>.X64.IsSupported` `true` na celu, że `<Isa>.IsSupported` jest również implikowane `true` . Jednak ze względu na sposób, w jaki rozpoznawanie elementów członkowskich działa w języku C#, klasy, które nie miały klasy zagnieżdżonej, `X64` uwidaczniają sytuację, w której to nigdy nie było tak samo, i doprowadziło do błędów w kodzie użytkownika.

#### <a name="recommended-action"></a>Zalecana akcja

W razie potrzeby dostosuj kod, który sprawdza, czy `IsSupported` ma być sprawdzana odpowiednia wartość ISA.

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
