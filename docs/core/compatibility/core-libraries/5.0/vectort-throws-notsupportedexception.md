---
title: 'Istotna zmiana: wektor <T> zgłasza NotSupportedException'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których wektor <T> zawsze zgłasza wyjątek dla nieobsługiwanych parametrów typu.
ms.date: 11/01/2020
ms.openlocfilehash: 63db7c6b720735b180ed11098227b31a14008f74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761516"
---
# <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a>Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów

<xref:System.Numerics.Vector%601?displayProperty=nameWithType> teraz zawsze jest zgłaszany <xref:System.NotSupportedException> dla nieobsługiwanych parametrów typu.

## <a name="change-description"></a>Zmień opis

Wcześniej elementy członkowskie <xref:System.Numerics.Vector%601> nie zawsze zgłaszają <xref:System.NotSupportedException> `T` [nieobsługiwany typ](#unsupported-types). Wyjątek nie został zawsze wygenerowany ze względu na ścieżki kodu obsługujące przyspieszenie sprzętowe. Na przykład `Vector<bool> + Vector<bool>` `default` zamiast zgłaszać wyjątek na platformach, które nie mają przyspieszenia sprzętowego, takiego jak ARM32. W przypadku nieobsługiwanych typów <xref:System.Numerics.Vector%601> elementy członkowskie wykazują niespójne zachowanie na różnych platformach i konfiguracjach sprzętu.

Począwszy od platformy .NET 5,0, <xref:System.Numerics.Vector%601> członkowie zawsze zgłaszają <xref:System.NotSupportedException> wszystkie konfiguracje sprzętu, gdy `T` nie jest to obsługiwanego typu.

### <a name="unsupported-types"></a>Nieobsługiwane typy

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

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

Nie używaj nieobsługiwanego typu dla parametru typu <xref:System.Numerics.Vector%601> .

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Numerics.Vector%601?displayProperty=fullName> i wszystkie jej elementy członkowskie

<!--

#### Category

Core .NET libraries

### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
