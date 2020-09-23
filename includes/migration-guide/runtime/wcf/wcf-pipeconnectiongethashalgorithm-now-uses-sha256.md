---
ms.openlocfilehash: 9f5f238e3d4222af1da3a1713e1b3e65de6e6f49
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "91024900"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>Funkcja WCF PipeConnection. GetHashAlgorithm używa teraz SHA256

#### <a name="details"></a>Szczegóły

Rozpoczynając od .NET Framework 4.7.1, Windows Communication Foundation używa skrótu SHA256 do generowania losowych nazw dla nazwanych potoków. W .NET Framework 4,7 i starszych wersjach użyto skrótu SHA1.

#### <a name="suggestion"></a>Sugestia

Jeśli wystąpi problem ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszym, możesz go wycofać, dodając następujący wiersz do `<runtime>` sekcji pliku app.config:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
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
