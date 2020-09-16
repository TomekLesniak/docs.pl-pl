---
ms.openlocfilehash: c64431fd651fd7d53fb46231c6acc10c5cb43fff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606809"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a>Akcje na przycisku i DownButton domeny WinForm są teraz zsynchronizowane

#### <a name="details"></a>Szczegóły

W .NET Framework 4.7.1 i poprzednich wersjach <xref:System.Windows.Forms.DomainUpDown> Akcja kontrolki <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> jest ignorowana, gdy jest obecny tekst kontrolki, a deweloper jest zobowiązany do używania <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> akcji na formancie przed użyciem <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> akcji. Począwszy od .NET Framework 4.7.2 obie <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> akcje i działają niezależnie w tym scenariuszu i pozostają zsynchronizowane.

#### <a name="suggestion"></a>Sugestia

Aby aplikacja mogła korzystać z tych zmian, musi ona działać na .NET Framework 4.7.2 lub nowszym. Aplikacja może korzystać z tych zmian w jeden z następujących sposobów:

- Zostanie ponownie skompilowana w celu przekierowania .NET Framework 4.7.2. Ta zmiana jest domyślnie włączona w Windows Forms aplikacjach przeznaczonych dla .NET Framework 4.7.2 lub nowszych.
- Powoduje to wypróbowanie starszego zachowania przewijania przez dodanie następującego [przełącznika AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) do `<runtime>` sekcji pliku konfiguracyjnego aplikacji i ustawienie go na `false` , jak pokazano w poniższym przykładzie.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   | Edge        |
| Wersja | 4.7.2       |
| Typ    | Przekierowanie |

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
