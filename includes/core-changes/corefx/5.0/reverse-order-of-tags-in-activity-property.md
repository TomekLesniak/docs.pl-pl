---
ms.openlocfilehash: 24b88b3ba1b6cfe9fb9fb1f6398a6daeb57596a9
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756116"
---
### <a name="order-of-tags-in-activitytags-is-reversed"></a>Kolejność tagów w działaniu. Tagi są odwrócone

<xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> teraz przechowuje elementy na liście zgodnie z kolejnością, w której zostały dodane, czyli pierwszy dodany element znajduje się na liście. Ta zmiana została wprowadzona w celu dopasowania do [specyfikacji atrybutów OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET program <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> przechowuje elementy w odwrotnej kolejności, z której są dodawane. Oznacza to, że pierwszy dodany element jest ostatni na liście. Począwszy od platformy .NET 5,0, kolejność elementów jest odwracana, a pierwszy dodany element jest zawsze na liście.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="recommended-action"></a>Zalecana akcja

Jeśli aplikacja ma zależność od <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> kolejności listy i uaktualniasz do programu .net 5,0 lub nowszego, musisz zmienić tę część kodu.

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
