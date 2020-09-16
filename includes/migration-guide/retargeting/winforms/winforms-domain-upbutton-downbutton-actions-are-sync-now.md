---
ms.openlocfilehash: c64431fd651fd7d53fb46231c6acc10c5cb43fff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606809"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a><span data-ttu-id="3a2c8-101">Akcje na przycisku i DownButton domeny WinForm są teraz zsynchronizowane</span><span class="sxs-lookup"><span data-stu-id="3a2c8-101">WinForm's Domain upbutton and downbutton actions are in sync now</span></span>

#### <a name="details"></a><span data-ttu-id="3a2c8-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3a2c8-102">Details</span></span>

<span data-ttu-id="3a2c8-103">W .NET Framework 4.7.1 i poprzednich wersjach <xref:System.Windows.Forms.DomainUpDown> Akcja kontrolki <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> jest ignorowana, gdy jest obecny tekst kontrolki, a deweloper jest zobowiązany do używania <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> akcji na formancie przed użyciem <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> akcji.</span><span class="sxs-lookup"><span data-stu-id="3a2c8-103">In the .NET Framework 4.7.1 and previous versions the <xref:System.Windows.Forms.DomainUpDown> control's <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action is ignored when control text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before using <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="3a2c8-104">Począwszy od .NET Framework 4.7.2 obie <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> akcje i działają niezależnie w tym scenariuszu i pozostają zsynchronizowane.</span><span class="sxs-lookup"><span data-stu-id="3a2c8-104">Starting with the .NET Framework 4.7.2 both the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> actions work independently in this scenario and remain in sync.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3a2c8-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="3a2c8-105">Suggestion</span></span>

<span data-ttu-id="3a2c8-106">Aby aplikacja mogła korzystać z tych zmian, musi ona działać na .NET Framework 4.7.2 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="3a2c8-106">In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="3a2c8-107">Aplikacja może korzystać z tych zmian w jeden z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="3a2c8-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="3a2c8-108">Zostanie ponownie skompilowana w celu przekierowania .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="3a2c8-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="3a2c8-109">Ta zmiana jest domyślnie włączona w Windows Forms aplikacjach przeznaczonych dla .NET Framework 4.7.2 lub nowszych.</span><span class="sxs-lookup"><span data-stu-id="3a2c8-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="3a2c8-110">Powoduje to wypróbowanie starszego zachowania przewijania przez dodanie następującego [przełącznika AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) do `<runtime>` sekcji pliku konfiguracyjnego aplikacji i ustawienie go na `false` , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="3a2c8-110">It opts out of the legacy scrolling behavior by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="3a2c8-111">Nazwa</span><span class="sxs-lookup"><span data-stu-id="3a2c8-111">Name</span></span>    | <span data-ttu-id="3a2c8-112">Wartość</span><span class="sxs-lookup"><span data-stu-id="3a2c8-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3a2c8-113">Zakres</span><span class="sxs-lookup"><span data-stu-id="3a2c8-113">Scope</span></span>   | <span data-ttu-id="3a2c8-114">Edge</span><span class="sxs-lookup"><span data-stu-id="3a2c8-114">Edge</span></span>        |
| <span data-ttu-id="3a2c8-115">Wersja</span><span class="sxs-lookup"><span data-stu-id="3a2c8-115">Version</span></span> | <span data-ttu-id="3a2c8-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="3a2c8-116">4.7.2</span></span>       |
| <span data-ttu-id="3a2c8-117">Typ</span><span class="sxs-lookup"><span data-stu-id="3a2c8-117">Type</span></span>    | <span data-ttu-id="3a2c8-118">Przekierowanie</span><span class="sxs-lookup"><span data-stu-id="3a2c8-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3a2c8-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="3a2c8-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
