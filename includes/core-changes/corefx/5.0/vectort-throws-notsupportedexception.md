---
ms.openlocfilehash: 43ebb37124b8efe077b9f81fe5351bd7db2c72f7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302721"
---
### <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a>Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów

<xref:System.Numerics.Vector%601?displayProperty=nameWithType>teraz zawsze jest zgłaszany <xref:System.NotSupportedException> dla nieobsługiwanych parametrów typu.

#### <a name="change-description"></a>Zmień opis

Wcześniej elementy członkowskie <xref:System.Numerics.Vector%601> nie zawsze zgłaszają <xref:System.NotSupportedException> `T` [nieobsługiwany typ](#unsupported-types). Wyjątek nie został zawsze wygenerowany ze względu na ścieżki kodu obsługujące przyspieszenie sprzętowe. Na przykład `Vector<bool> + Vector<bool>` `default` zamiast zgłaszać wyjątek na platformach, które nie mają przyspieszenia sprzętowego, takiego jak ARM32. W przypadku nieobsługiwanych typów <xref:System.Numerics.Vector%601> elementy członkowskie wykazują niespójne zachowanie na różnych platformach i konfiguracjach sprzętu.

Począwszy od platformy .NET 5,0, <xref:System.Numerics.Vector%601> członkowie zawsze zgłaszają <xref:System.NotSupportedException> wszystkie konfiguracje sprzętu, gdy `T` nie jest to obsługiwanego typu.

##### <a name="unsupported-types"></a>Nieobsługiwane typy

Obsługiwane typy dla parametru typu <xref:System.Numerics.Vector%601> są:

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

Obsługiwane typy nie uległy zmianie, ale mogą ulec zmianie w przyszłości.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

#### <a name="recommended-action"></a>Zalecana akcja

Nie używaj nieobsługiwanego typu dla parametru typu <xref:System.Numerics.Vector%601> .

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Numerics.Vector%601?displayProperty=fullName>i wszystkie jej elementy członkowskie

<!--

#### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
