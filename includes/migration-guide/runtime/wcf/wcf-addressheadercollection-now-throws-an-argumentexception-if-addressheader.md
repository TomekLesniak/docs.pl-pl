---
ms.openlocfilehash: 200c22a1b83149d833a083365ebb65d0e80bc31a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497480"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a>Funkcja WCF AddressHeaderCollection teraz generuje ArgumentException, jeśli element addressHeader ma wartość null

#### <a name="details"></a>Szczegóły

Rozpoczynając od .NET Framework 4.7.1, <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> Konstruktor zgłasza, <xref:System.ArgumentException> Jeśli jeden z elementów jest <code>null</code> . W .NET Framework 4,7 i wcześniejszych wersjach nie jest zgłaszany żaden wyjątek.

#### <a name="suggestion"></a>Sugestia

Jeśli wystąpią problemy ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszej wersji, możesz zrezygnować z niej, dodając następujący wiersz do <code>&lt;runtime&gt;</code> sekcji pliku app.config::<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.7.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
