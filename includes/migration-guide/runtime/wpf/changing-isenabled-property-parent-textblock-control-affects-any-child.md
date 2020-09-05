---
ms.openlocfilehash: 12a26030a9a336d887ae9d53994a9daf13356618
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496376"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="520b5-101">Zmiana właściwości IsEnabled elementu nadrzędnego formantu TextBlock ma wpływ na wszystkie kontrolki podrzędne</span><span class="sxs-lookup"><span data-stu-id="520b5-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

#### <a name="details"></a><span data-ttu-id="520b5-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="520b5-102">Details</span></span>

<span data-ttu-id="520b5-103">Począwszy od .NET Framework 4.6.2, zmiana <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> właściwości elementu nadrzędnego <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> formantu ma wpływ na wszystkie kontrolki podrzędne (takie jak hiperłącza i przyciski) <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> formantu. W .NET Framework 4.6.1 i starszych wersji, formanty wewnątrz <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> nie zawsze odzwierciedlają stan <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> właściwości <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="520b5-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> parent.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="520b5-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="520b5-104">Suggestion</span></span>

<span data-ttu-id="520b5-105">Brak.</span><span class="sxs-lookup"><span data-stu-id="520b5-105">None.</span></span> <span data-ttu-id="520b5-106">Ta zmiana jest zgodna z oczekiwanym zachowaniem formantów wewnątrz <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> kontrolki.</span><span class="sxs-lookup"><span data-stu-id="520b5-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.</span></span>

| <span data-ttu-id="520b5-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="520b5-107">Name</span></span>    | <span data-ttu-id="520b5-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="520b5-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="520b5-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="520b5-109">Scope</span></span>   |<span data-ttu-id="520b5-110">Mały</span><span class="sxs-lookup"><span data-stu-id="520b5-110">Minor</span></span>|
|<span data-ttu-id="520b5-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="520b5-111">Version</span></span>|<span data-ttu-id="520b5-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="520b5-112">4.6.2</span></span>|
|<span data-ttu-id="520b5-113">Typ</span><span class="sxs-lookup"><span data-stu-id="520b5-113">Type</span></span>|<span data-ttu-id="520b5-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="520b5-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="520b5-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="520b5-115">Affected APIs</span></span>

- <xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.UIElement.IsEnabled`

-->
