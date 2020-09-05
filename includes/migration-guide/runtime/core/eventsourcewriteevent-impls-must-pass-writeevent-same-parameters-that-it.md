---
ms.openlocfilehash: 99a7fa0fcfce6d490a182f85709b5dd0e0e8c86f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496496"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>Element EventSource. metody WriteEvent Impls musi przekazać metody WriteEvent te same parametry, które otrzymały (plus ID)

#### <a name="details"></a>Szczegóły

Środowisko wykonawcze wymusza teraz kontrakt, który określa następujące elementy: Klasa pochodna <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> , która definiuje metodę zdarzenia ETW, musi wywołać metodę klasy bazowej <code>EventSource.WriteEvent</code> z identyfikatorem zdarzenia, po którym następują te same argumenty, które zostały przekazane przez metodę zdarzenia ETW.

#### <a name="suggestion"></a>Sugestia

<xref:System.IndexOutOfRangeException?displayProperty=fullName>Wyjątek jest generowany, jeśli <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> dane są odczytywane <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> w procesie dla źródła zdarzenia, które narusza ten kontrakt.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
