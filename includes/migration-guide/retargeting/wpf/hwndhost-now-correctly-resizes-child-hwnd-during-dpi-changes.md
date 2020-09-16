---
ms.openlocfilehash: 77e231f8ef1dde8a263b8622311099a4a404062d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606661"
---
### <a name="hwndhost-now-correctly-resizes-child-hwnd-during-dpi-changes"></a>HwndHost teraz prawidłowo zmienia rozmiar elementu podrzędnego (HWND) podczas zmiany DPI

#### <a name="details"></a>Szczegóły

W .NET Framework 4.7.2 i starszych wersjach, gdy WPF była uruchamiana w trybie z uwzględnieniem monitora, formanty hostowane w ramach <xref:System.Windows.Interop.HwndHost> nie zostały poprawnie dopasowane po zmianie dpi, na przykład podczas przesuwania aplikacji z jednego monitora na inny. Ta poprawka zapewnia odpowiednie rozmiary formantów hostowanych.

#### <a name="suggestion"></a>Sugestia

Aby aplikacja mogła korzystać z tych zmian, musi ona zostać uruchomiona w .NET Framework 4.7.2 lub nowszym, a następnie musi wybrać następujący [przełącznik AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) w `<runtime>` sekcji pliku konfiguracji aplikacji do `false` , jak pokazano w poniższym przykładzie.

<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   | Duży       |
| Wersja | 4,8         |
| Typ    | Przekierowanie |
