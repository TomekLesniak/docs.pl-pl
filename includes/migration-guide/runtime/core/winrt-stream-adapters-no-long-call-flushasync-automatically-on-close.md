---
ms.openlocfilehash: 2b4f35fe15f806897e5e4d85ee774b2e4572d974
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497292"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>Karty strumienia WinRT nie są długie wywołania FlushAsync automatycznie przy zamykaniu

#### <a name="details"></a>Szczegóły

W aplikacjach ze sklepu Windows środowisko wykonawcze systemu Windows karty usługi Stream nie wywołują już metody FlushAsync z metody Dispose.

#### <a name="suggestion"></a>Sugestia

Ta zmiana powinna być niewidoczna. Deweloperzy mogą przywrócić poprzednie zachowanie, pisząc kod podobny do tego:<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Przezroczyste|
|Wersja|4.5.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
