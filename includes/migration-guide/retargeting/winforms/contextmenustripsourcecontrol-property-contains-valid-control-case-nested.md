---
ms.openlocfilehash: 5529b8379c5cb9f1bc525e0c2340f6b885e35822
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606170"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>Właściwość ContextMenuStrip. SourceControl zawiera prawidłową kontrolkę w przypadku zagnieżdżonych kontrolki ToolStripMenuItems

#### <a name="details"></a>Szczegóły

W .NET Framework 4.7.1 i poprzednich wersjach <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> Właściwość nieprawidłowo zwraca wartość null, jeśli użytkownik otworzy menu z formantów zagnieżdżonych <xref:System.Windows.Forms.ToolStripMenuItem> . W .NET Framework 4.7.2 i nowszych <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> Właściwość jest zawsze ustawiana na rzeczywistą kontrolę źródła.

#### <a name="suggestion"></a>Sugestia

**Jak wybrać lub wycofać te zmiany** Aby aplikacja mogła korzystać z tych zmian, musi ona działać na .NET Framework 4.7.2 lub nowszym. Aplikacja może korzystać z tych zmian w jeden z następujących sposobów:

- Jest ona przeznaczona dla .NET Framework 4.7.2. Ta zmiana jest domyślnie włączona w Windows Forms aplikacjach przeznaczonych dla .NET Framework 4.7.2 lub nowszych.
- Jest ona przeznaczona dla .NET Framework 4.7.1 lub wcześniejszej wersji i [wyłączają](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) się ze starszych zachowań ułatwień dostępu, dodając następujący `<runtime>` przykład AppContext do sekcji pliku app.config i ustawiając go na `false` , jak pokazano w poniższym przykładzie.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

Aplikacje ukierunkowane na .NET Framework 4.7.2 lub nowsze i chcą zachować starsze zachowanie mogą zrezygnować z używania wartości kontroli źródła starszej przez jawne ustawienie tego przełącznika AppContext na `true` .

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   | Edge        |
| Wersja | 4.7.2       |
| Typ    | Przekierowanie |

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
