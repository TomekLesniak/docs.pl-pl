---
ms.openlocfilehash: 6a6c0af9cc0f3e5d1bbc3a4462a9ff7eaa748a5f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496169"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="f37b0-101">Zmiana wysokiego kontrastu ComboBox svcTraceViewer</span><span class="sxs-lookup"><span data-stu-id="f37b0-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="f37b0-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f37b0-102">Details</span></span>

<span data-ttu-id="f37b0-103">W [narzędziu Podgląd śledzenia usług firmy Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)kontrolki ComboBox nie były wyświetlane w prawidłowym kolorze w niektórych motywach o dużym kontraście.</span><span class="sxs-lookup"><span data-stu-id="f37b0-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="f37b0-104">Problem został rozwiązany w .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="f37b0-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="f37b0-105">Jednak ze względu na wymagania zgodności z zestawem SDK .NET Framework, poprawka nie była domyślnie widoczna dla klientów.</span><span class="sxs-lookup"><span data-stu-id="f37b0-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="f37b0-106">Program .NET 4,8 wyświetla tę zmianę, dodając następujące [przełączniki konfiguracji AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) do pliku svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="f37b0-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a><span data-ttu-id="f37b0-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="f37b0-107">Suggestion</span></span>

<ul><li><span data-ttu-id="f37b0-108">Jak zrezygnować z zmiany, jeśli nie chcesz mieć zmiany zachowania dużego kontrastu, możesz ją wyłączyć, usuwając następującą sekcję z pliku svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="f37b0-108">How to opt out of the change If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span></li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f37b0-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="f37b0-109">Name</span></span>    | <span data-ttu-id="f37b0-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="f37b0-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f37b0-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="f37b0-111">Scope</span></span>   |<span data-ttu-id="f37b0-112">Edge</span><span class="sxs-lookup"><span data-stu-id="f37b0-112">Edge</span></span>|
|<span data-ttu-id="f37b0-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="f37b0-113">Version</span></span>|<span data-ttu-id="f37b0-114">4,8</span><span class="sxs-lookup"><span data-stu-id="f37b0-114">4.8</span></span>|
|<span data-ttu-id="f37b0-115">Typ</span><span class="sxs-lookup"><span data-stu-id="f37b0-115">Type</span></span>|<span data-ttu-id="f37b0-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="f37b0-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f37b0-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f37b0-117">Affected APIs</span></span>

<span data-ttu-id="f37b0-118">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="f37b0-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
