---
ms.openlocfilehash: bca76daca6e9c424377a80aa56e1a5ff191be5ca
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496695"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a><span data-ttu-id="d018b-101">Sporadycznie nie można przewijać do ostatniego elementu w ItemsControls (na przykład ListBox i DataGrid) przy użyciu niestandardowych szablonów datatemplates</span><span class="sxs-lookup"><span data-stu-id="d018b-101">Intermittently unable to scroll to bottom item in ItemsControls (like ListBox and DataGrid) when using custom DataTemplates</span></span>

#### <a name="details"></a><span data-ttu-id="d018b-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="d018b-102">Details</span></span>

<span data-ttu-id="d018b-103">W niektórych przypadkach usterka w .NET Framework 4,5 powoduje, że w <xref:System.Windows.Controls.ListBox?displayProperty=fullName> <xref:System.Windows.Controls.ComboBox?displayProperty=fullName> <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> przypadku korzystania z niestandardowych szablonów datatemplates ItemsControls (np., itp.).</span><span class="sxs-lookup"><span data-stu-id="d018b-103">In some instances, a bug in the .NET Framework 4.5 is causing ItemsControls (like <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>, etc.) to not scroll to their bottom item when using custom DataTemplates.</span></span> <span data-ttu-id="d018b-104">W przypadku próby przeprowadzenia przewijania po raz drugi (po przeprowadzeniu przewijania kopii zapasowej) działanie zostanie wykonane.</span><span class="sxs-lookup"><span data-stu-id="d018b-104">If the scrolling is attempted a second time (after scrolling back up), it will work then.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d018b-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="d018b-105">Suggestion</span></span>

<span data-ttu-id="d018b-106">Ten problem został rozwiązany w .NET Framework 4.5.2 i może zostać rozwiązany przez uaktualnienie do tej wersji (lub nowszej) .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d018b-106">This issue has been fixed in the .NET Framework 4.5.2 and may be addressed by upgrading to that version (or a later version) of the .NET Framework.</span></span> <span data-ttu-id="d018b-107">Alternatywnie użytkownicy nadal mogą przeciągać paski przewijania do elementów końcowych w tych kolekcjach, ale może być konieczne dwukrotne wykonanie tej czynności.</span><span class="sxs-lookup"><span data-stu-id="d018b-107">Alternatively, users can still drag scroll bars to the final items in these collections, but may need to try twice to do so successfully.</span></span>

| <span data-ttu-id="d018b-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="d018b-108">Name</span></span>    | <span data-ttu-id="d018b-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="d018b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d018b-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="d018b-110">Scope</span></span>   |<span data-ttu-id="d018b-111">Mały</span><span class="sxs-lookup"><span data-stu-id="d018b-111">Minor</span></span>|
|<span data-ttu-id="d018b-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="d018b-112">Version</span></span>|<span data-ttu-id="d018b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d018b-113">4.5</span></span>|
|<span data-ttu-id="d018b-114">Typ</span><span class="sxs-lookup"><span data-stu-id="d018b-114">Type</span></span>|<span data-ttu-id="d018b-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="d018b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d018b-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d018b-116">Affected APIs</span></span>

<span data-ttu-id="d018b-117">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="d018b-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
