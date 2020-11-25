---
title: 'Zmiana podziału: kolejność tagów w działaniu. Tagi są odwrócone'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w podstawowych bibliotekach .NET, w których działanie. Tagi zawierają teraz elementy na liście zgodnie z kolejnością, w której zostały dodane.
ms.date: 11/01/2020
ms.openlocfilehash: 1ff14dc1a4f7a0bf8cf9e79f3750b819f4d4a5ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761496"
---
# <a name="order-of-tags-in-activitytags-is-reversed"></a>Kolejność tagów w działaniu. Tagi są odwrócone

<xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> teraz przechowuje elementy na liście zgodnie z kolejnością, w której zostały dodane, czyli pierwszy dodany element znajduje się na liście. Ta zmiana została wprowadzona w celu dopasowania do [specyfikacji atrybutów OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET program <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> przechowuje elementy w odwrotnej kolejności, z której są dodawane. Oznacza to, że pierwszy dodany element jest ostatni na liście. Począwszy od platformy .NET 5,0, kolejność elementów jest odwracana, a pierwszy dodany element jest zawsze na liście.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

Jeśli aplikacja ma zależność od <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> kolejności listy i uaktualniasz do programu .net 5,0 lub nowszego, musisz zmienić tę część kodu.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
