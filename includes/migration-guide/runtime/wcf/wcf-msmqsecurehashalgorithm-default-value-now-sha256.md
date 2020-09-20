---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770848"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>Wartość domyślna MsmqSecureHashAlgorithm WCF jest teraz SHA256

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4.7.1, domyślny algorytm podpisywania komunikatów w programie WCF dla komunikatów usługi MSMQ to SHA256. W .NET Framework 4,7 i wcześniejszych wersjach domyślny algorytm podpisywania wiadomości to SHA1.

#### <a name="suggestion"></a>Sugestia

W przypadku wystąpienia problemów ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszym można zrezygnować z zmiany, dodając następujący wiersz do `<runtime>` sekcji pliku app.config:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| Nazwa    | Wartość   |
|:--------|:--------|
| Zakres   | Mały   |
| Wersja | 4.7.1   |
| Typ    | Środowisko uruchomieniowe |

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
