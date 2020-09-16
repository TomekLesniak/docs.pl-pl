---
ms.openlocfilehash: aadf5eb85c8736c29639d49bc8baf21545d2467c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606945"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>Platforma .NET COM pomyślnie organizowana parametry ByRef SafeArray dla zdarzeń

#### <a name="details"></a>Szczegóły

W .NET Framework 4.7.2 i starszych wersjach parametr ByRef [SAFEARRAY](/windows/desktop/api/oaidl/ns-oaidl-safearray) dla zdarzenia com nie będzie mógł zostać przekierowany z powrotem do kodu natywnego.  Po zmianie tej zmiany element [SAFEARRAY](/windows/desktop/api/oaidl/ns-oaidl-safearray) zostanie teraz skierowany pomyślnie.<ul><li>[x] Quirked</li></ul>

#### <a name="suggestion"></a>Sugestia

Jeśli poprawne kierowanie parametrów ByRef w zdarzeniach COM powoduje przerwanie wykonywania, można wyłączyć ten kod, dodając następujący przełącznik konfiguracji do konfiguracji aplikacji:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4,8|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
