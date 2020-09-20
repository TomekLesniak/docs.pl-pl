---
ms.openlocfilehash: 4bc8db52efdfe483acb4f6b6e33c4fa7716e0b79
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770889"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="47ea5-101">Zmiana wysokiego kontrastu ComboBox svcTraceViewer</span><span class="sxs-lookup"><span data-stu-id="47ea5-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="47ea5-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="47ea5-102">Details</span></span>

<span data-ttu-id="47ea5-103">W [narzędziu Podgląd śledzenia usług firmy Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)kontrolki ComboBox nie były wyświetlane w prawidłowym kolorze w niektórych motywach o dużym kontraście.</span><span class="sxs-lookup"><span data-stu-id="47ea5-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="47ea5-104">Problem został rozwiązany w .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="47ea5-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="47ea5-105">Jednak ze względu na wymagania zgodności z zestawem SDK .NET Framework, poprawka nie była domyślnie widoczna dla klientów.</span><span class="sxs-lookup"><span data-stu-id="47ea5-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="47ea5-106">Program .NET 4,8 wyświetla tę zmianę, dodając następujące [przełączniki konfiguracji AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) do pliku svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="47ea5-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

#### <a name="suggestion"></a><span data-ttu-id="47ea5-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="47ea5-107">Suggestion</span></span>

<span data-ttu-id="47ea5-108">Jeśli nie chcesz zmieniać zachowania dużego kontrastu, możesz je wyłączyć, usuwając następującą sekcję z pliku svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="47ea5-108">If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

| <span data-ttu-id="47ea5-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="47ea5-109">Name</span></span>    | <span data-ttu-id="47ea5-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="47ea5-110">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="47ea5-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="47ea5-111">Scope</span></span>   | <span data-ttu-id="47ea5-112">Edge</span><span class="sxs-lookup"><span data-stu-id="47ea5-112">Edge</span></span>    |
| <span data-ttu-id="47ea5-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="47ea5-113">Version</span></span> | <span data-ttu-id="47ea5-114">4,8</span><span class="sxs-lookup"><span data-stu-id="47ea5-114">4.8</span></span>     |
| <span data-ttu-id="47ea5-115">Typ</span><span class="sxs-lookup"><span data-stu-id="47ea5-115">Type</span></span>    | <span data-ttu-id="47ea5-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="47ea5-116">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="47ea5-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="47ea5-117">Affected APIs</span></span>

<span data-ttu-id="47ea5-118">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="47ea5-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
