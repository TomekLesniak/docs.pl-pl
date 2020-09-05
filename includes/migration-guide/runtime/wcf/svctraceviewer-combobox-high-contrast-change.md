---
ms.openlocfilehash: 6a6c0af9cc0f3e5d1bbc3a4462a9ff7eaa748a5f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496169"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Zmiana wysokiego kontrastu ComboBox svcTraceViewer

#### <a name="details"></a>Szczegóły

W [narzędziu Podgląd śledzenia usług firmy Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)kontrolki ComboBox nie były wyświetlane w prawidłowym kolorze w niektórych motywach o dużym kontraście. Problem został rozwiązany w .NET Framework 4.7.2. Jednak ze względu na wymagania zgodności z zestawem SDK .NET Framework, poprawka nie była domyślnie widoczna dla klientów. Program .NET 4,8 wyświetla tę zmianę, dodając następujące [przełączniki konfiguracji AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) do pliku svcTraceViewer.exe.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a>Sugestia

<ul><li>Jak zrezygnować z zmiany, jeśli nie chcesz mieć zmiany zachowania dużego kontrastu, możesz ją wyłączyć, usuwając następującą sekcję z pliku svcTraceViewer.exe.config:</li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4,8|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
