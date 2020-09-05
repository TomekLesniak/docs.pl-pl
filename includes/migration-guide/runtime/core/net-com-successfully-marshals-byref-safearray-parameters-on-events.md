---
ms.openlocfilehash: 1907c9b82c9685899d328f67da8001c0fa4fb697
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497062"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>Platforma .NET COM pomyślnie organizowana parametry ByRef SafeArray dla zdarzeń

#### <a name="details"></a>Szczegóły

W .NET Framework 4.7.2 i starszych wersjach parametr ByRef [SAFEARRAY](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) dla zdarzenia com nie będzie mógł zostać przekierowany z powrotem do kodu natywnego.  Po zmianie tej zmiany element [SAFEARRAY](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) zostanie teraz skierowany pomyślnie.<ul><li>[x] Quirked</li></ul>

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
