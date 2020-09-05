---
ms.openlocfilehash: 9baca45de1c8994f610815e84fdee8ba3930eb04
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497681"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>Wartość domyślna MsmqSecureHashAlgorithm WCF jest teraz SHA256

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4.7.1, domyślny algorytm podpisywania komunikatów w programie WCF dla komunikatów usługi MSMQ to SHA256. W .NET Framework 4,7 i wcześniejszych wersjach domyślny algorytm podpisywania wiadomości to SHA1.

#### <a name="suggestion"></a>Sugestia

W przypadku wystąpienia problemów ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszym można zrezygnować z zmiany, dodając następujący wiersz do <code>&lt;runtime&gt;</code> sekcji pliku app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

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
