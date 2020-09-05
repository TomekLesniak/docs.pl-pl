---
ms.openlocfilehash: e47a24239872e3fe86ff6902f66b38daaa106598
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497055"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>Odbiornika obcina ciągi z osadzonymi wartościami null

#### <a name="details"></a>Szczegóły

<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> obcina ciągi z osadzonymi wartościami null. Klasa nie obsługuje znaków o wartości null <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> . Zmiana ta dotyczy tylko aplikacji, które używają <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> do odczytu <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> danych w procesie i używania znaków null jako ograniczników.

#### <a name="suggestion"></a>Sugestia

<xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> dane powinny być aktualizowane, jeśli jest to możliwe, nie mogą być używane w osadzonych znakach null.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Diagnostics.Tracing.EventListener.%23ctor>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.#ctor`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})`

-->
