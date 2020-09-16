---
ms.openlocfilehash: 6ee290f6722480778381376f588e16877894f232
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606751"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a>PrivateFontCollection. AddFontFile — metoda zwalnia zasoby czcionek

#### <a name="details"></a>Szczegóły

W .NET Framework 4.7.1 i poprzednich wersjach <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> Klasa nie zwolni zasobów czcionki GDI+ po usunięciu <xref:System.Drawing.Text.PrivateFontCollection> <xref:System.Drawing.Font> obiektów, które są dodawane do tej kolekcji przy użyciu <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> metody. W .NET Framework 4.7.2 i nowszych <xref:System.Drawing.Text.FontCollection.Dispose%2A> wersji czcionki GDI+, które zostały dodane do kolekcji jako pliki.

#### <a name="suggestion"></a>Sugestia

**Jak wybrać lub wycofać te zmiany** Aby aplikacja mogła korzystać z tych zmian, musi ona działać na .NET Framework 4.7.2 lub nowszym. Aplikacja może korzystać z tych zmian w jeden z następujących sposobów:

- Zostanie ponownie skompilowana w celu przekierowania .NET Framework 4.7.2. Ta zmiana jest domyślnie włączona w Windows Forms aplikacjach przeznaczonych dla .NET Framework 4.7.2 lub nowszych.
- Jest ona przeznaczona dla .NET Framework 4.7.1 lub wcześniejszej wersji i [wyłączają](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) się ze starszych zachowań ułatwień dostępu, dodając następujący `<runtime>` przykład AppContext do sekcji pliku app.config i ustawiając go na `false` , jak pokazano w poniższym przykładzie.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

Aplikacje ukierunkowane na .NET Framework 4.7.2 lub nowsze i chcą zachować starsze zachowanie mogą zrezygnować z niezwolnienia zasobów czcionki przez jawne ustawienie tego przełącznika AppContext na `true` .

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   | Edge        |
| Wersja | 4.7.2       |
| Typ    | Przekierowanie |

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>
