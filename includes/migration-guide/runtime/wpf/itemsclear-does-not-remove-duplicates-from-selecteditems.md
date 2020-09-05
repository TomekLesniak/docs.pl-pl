---
ms.openlocfilehash: 25ce391f917bd270d4d9a75f608e4a8ec763d15c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496910"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a><span data-ttu-id="5accb-101">Elementy. Clear nie usuwa duplikatów z SelectedItems</span><span class="sxs-lookup"><span data-stu-id="5accb-101">Items.Clear does not remove duplicates from SelectedItems</span></span>

#### <a name="details"></a><span data-ttu-id="5accb-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="5accb-102">Details</span></span>

<span data-ttu-id="5accb-103">Załóżmy, że selektor (z włączoną obsługą wielu zaznaczeń) ma duplikaty w <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> kolekcji — ten sam element występuje więcej niż jeden raz.</span><span class="sxs-lookup"><span data-stu-id="5accb-103">Suppose a Selector (with multiple selection enabled) has duplicates in its <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> collection - the same item appears more than once.</span></span>  <span data-ttu-id="5accb-104">Usunięcie tych elementów ze źródła danych (np. przez wywoływanie elementów. Clear) nie powiodło się usunięcie ich z <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> ; tylko pierwsze wystąpienie zostanie usunięte.</span><span class="sxs-lookup"><span data-stu-id="5accb-104">Removing those items from the data source (e.g. by calling Items.Clear) fails to remove them from <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; only the first instance is removed.</span></span> <span data-ttu-id="5accb-105">Ponadto kolejne użycie <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (np. SelectedItems. Clear ()) może napotkać problemy, takie jak <xref:System.ArgumentException?displayProperty=fullName> , ponieważ <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> zawiera elementy, które nie znajdują się już w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="5accb-105">Furthermore, subsequent use of <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (e.g. SelectedItems.Clear()) can encounter problems such as <xref:System.ArgumentException?displayProperty=fullName>, because <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contains items that are no longer in the data source.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5accb-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="5accb-106">Suggestion</span></span>

<span data-ttu-id="5accb-107">Uaktualnij, jeśli to możliwe, aby .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="5accb-107">Upgrade if possible to .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="5accb-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="5accb-108">Name</span></span>    | <span data-ttu-id="5accb-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="5accb-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5accb-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="5accb-110">Scope</span></span>   |<span data-ttu-id="5accb-111">Mały</span><span class="sxs-lookup"><span data-stu-id="5accb-111">Minor</span></span>|
|<span data-ttu-id="5accb-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="5accb-112">Version</span></span>|<span data-ttu-id="5accb-113">4.5</span><span class="sxs-lookup"><span data-stu-id="5accb-113">4.5</span></span>|
|<span data-ttu-id="5accb-114">Typ</span><span class="sxs-lookup"><span data-stu-id="5accb-114">Type</span></span>|<span data-ttu-id="5accb-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="5accb-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="5accb-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="5accb-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.MultiSelector.SelectedItems`

-->
