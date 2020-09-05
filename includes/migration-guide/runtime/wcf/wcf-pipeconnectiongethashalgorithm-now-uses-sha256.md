---
ms.openlocfilehash: d32725b0d3063d3320b73e02039ff567090da932
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496359"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>Funkcja WCF PipeConnection. GetHashAlgorithm używa teraz SHA256

#### <a name="details"></a>Szczegóły

Rozpoczynając od .NET Framework 4.7.1, Windows Communication Foundation używa skrótu SHA256 do generowania losowych nazw dla nazwanych potoków. W .NET Framework 4,7 i starszych wersjach użyto skrótu SHA1.

#### <a name="suggestion"></a>Sugestia

Jeśli wystąpi problem ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszym, możesz go wycofać, dodając następujący wiersz do <code>&lt;runtime&gt;</code> sekcji pliku app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.7.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
