---
ms.openlocfilehash: 5529b8379c5cb9f1bc525e0c2340f6b885e35822
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606170"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a><span data-ttu-id="7adb5-101">Właściwość ContextMenuStrip. SourceControl zawiera prawidłową kontrolkę w przypadku zagnieżdżonych kontrolki ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="7adb5-101">ContextMenuStrip.SourceControl property contains a valid control in the case of nested ToolStripMenuItems</span></span>

#### <a name="details"></a><span data-ttu-id="7adb5-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="7adb5-102">Details</span></span>

<span data-ttu-id="7adb5-103">W .NET Framework 4.7.1 i poprzednich wersjach <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> Właściwość nieprawidłowo zwraca wartość null, jeśli użytkownik otworzy menu z formantów zagnieżdżonych <xref:System.Windows.Forms.ToolStripMenuItem> .</span><span class="sxs-lookup"><span data-stu-id="7adb5-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property incorrectly returns null when the user opens the menu from nested <xref:System.Windows.Forms.ToolStripMenuItem> controls.</span></span> <span data-ttu-id="7adb5-104">W .NET Framework 4.7.2 i nowszych <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> Właściwość jest zawsze ustawiana na rzeczywistą kontrolę źródła.</span><span class="sxs-lookup"><span data-stu-id="7adb5-104">In the .NET Framework 4.7.2 and later, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> property is always set to the actual source control.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7adb5-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="7adb5-105">Suggestion</span></span>

<span data-ttu-id="7adb5-106">**Jak wybrać lub wycofać te zmiany** Aby aplikacja mogła korzystać z tych zmian, musi ona działać na .NET Framework 4.7.2 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="7adb5-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="7adb5-107">Aplikacja może korzystać z tych zmian w jeden z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="7adb5-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="7adb5-108">Jest ona przeznaczona dla .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="7adb5-108">It targets the .NET Framework 4.7.2.</span></span> <span data-ttu-id="7adb5-109">Ta zmiana jest domyślnie włączona w Windows Forms aplikacjach przeznaczonych dla .NET Framework 4.7.2 lub nowszych.</span><span class="sxs-lookup"><span data-stu-id="7adb5-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="7adb5-110">Jest ona przeznaczona dla .NET Framework 4.7.1 lub wcześniejszej wersji i [wyłączają](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) się ze starszych zachowań ułatwień dostępu, dodając następujący `<runtime>` przykład AppContext do sekcji pliku app.config i ustawiając go na `false` , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="7adb5-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

<span data-ttu-id="7adb5-111">Aplikacje ukierunkowane na .NET Framework 4.7.2 lub nowsze i chcą zachować starsze zachowanie mogą zrezygnować z używania wartości kontroli źródła starszej przez jawne ustawienie tego przełącznika AppContext na `true` .</span><span class="sxs-lookup"><span data-stu-id="7adb5-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to the use of the legacy source control value by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="7adb5-112">Nazwa</span><span class="sxs-lookup"><span data-stu-id="7adb5-112">Name</span></span>    | <span data-ttu-id="7adb5-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="7adb5-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7adb5-114">Zakres</span><span class="sxs-lookup"><span data-stu-id="7adb5-114">Scope</span></span>   | <span data-ttu-id="7adb5-115">Edge</span><span class="sxs-lookup"><span data-stu-id="7adb5-115">Edge</span></span>        |
| <span data-ttu-id="7adb5-116">Wersja</span><span class="sxs-lookup"><span data-stu-id="7adb5-116">Version</span></span> | <span data-ttu-id="7adb5-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="7adb5-117">4.7.2</span></span>       |
| <span data-ttu-id="7adb5-118">Typ</span><span class="sxs-lookup"><span data-stu-id="7adb5-118">Type</span></span>    | <span data-ttu-id="7adb5-119">Przekierowanie</span><span class="sxs-lookup"><span data-stu-id="7adb5-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="7adb5-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="7adb5-120">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
