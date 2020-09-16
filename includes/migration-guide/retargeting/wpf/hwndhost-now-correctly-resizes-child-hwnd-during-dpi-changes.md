---
ms.openlocfilehash: 77e231f8ef1dde8a263b8622311099a4a404062d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606661"
---
### <a name="hwndhost-now-correctly-resizes-child-hwnd-during-dpi-changes"></a><span data-ttu-id="96de1-101">HwndHost teraz prawidłowo zmienia rozmiar elementu podrzędnego (HWND) podczas zmiany DPI</span><span class="sxs-lookup"><span data-stu-id="96de1-101">HwndHost now correctly resizes child-HWND during DPI changes</span></span>

#### <a name="details"></a><span data-ttu-id="96de1-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="96de1-102">Details</span></span>

<span data-ttu-id="96de1-103">W .NET Framework 4.7.2 i starszych wersjach, gdy WPF była uruchamiana w trybie z uwzględnieniem monitora, formanty hostowane w ramach <xref:System.Windows.Interop.HwndHost> nie zostały poprawnie dopasowane po zmianie dpi, na przykład podczas przesuwania aplikacji z jednego monitora na inny.</span><span class="sxs-lookup"><span data-stu-id="96de1-103">In .NET Framework 4.7.2 and earlier versions, when WPF was run in Per-Monitor Aware mode, controls hosted within <xref:System.Windows.Interop.HwndHost> were not sized correctly after DPI changes, such as when moving applications from one monitor to another.</span></span> <span data-ttu-id="96de1-104">Ta poprawka zapewnia odpowiednie rozmiary formantów hostowanych.</span><span class="sxs-lookup"><span data-stu-id="96de1-104">This fix ensures that hosted controls are sized appropriately.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="96de1-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="96de1-105">Suggestion</span></span>

<span data-ttu-id="96de1-106">Aby aplikacja mogła korzystać z tych zmian, musi ona zostać uruchomiona w .NET Framework 4.7.2 lub nowszym, a następnie musi wybrać następujący [przełącznik AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) w `<runtime>` sekcji pliku konfiguracji aplikacji do `false` , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="96de1-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later, and it must opt-in to this behavior by setting the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the `<runtime>` section of the app config file to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="96de1-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="96de1-107">Name</span></span>    | <span data-ttu-id="96de1-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="96de1-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="96de1-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="96de1-109">Scope</span></span>   | <span data-ttu-id="96de1-110">Duży</span><span class="sxs-lookup"><span data-stu-id="96de1-110">Major</span></span>       |
| <span data-ttu-id="96de1-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="96de1-111">Version</span></span> | <span data-ttu-id="96de1-112">4,8</span><span class="sxs-lookup"><span data-stu-id="96de1-112">4.8</span></span>         |
| <span data-ttu-id="96de1-113">Typ</span><span class="sxs-lookup"><span data-stu-id="96de1-113">Type</span></span>    | <span data-ttu-id="96de1-114">Przekierowanie</span><span class="sxs-lookup"><span data-stu-id="96de1-114">Retargeting</span></span> |
