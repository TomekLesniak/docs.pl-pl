---
ms.openlocfilehash: 31ada197db36be192317e32a37a353d375d9cc65
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496527"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="b38ff-101">Przewijanie drzewa WPF lub zgrupowane pole listy w VirtualizingStackPanel może spowodować zawieszenie</span><span class="sxs-lookup"><span data-stu-id="b38ff-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

#### <a name="details"></a><span data-ttu-id="b38ff-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="b38ff-102">Details</span></span>

<span data-ttu-id="b38ff-103">W .NET Framework v 4.5, przewinięcie WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> w zwirtualizowanym panelu stosu może spowodować zawieszenie, jeśli w okienku ekranu pojawią się marginesy (między elementami na <xref:System.Windows.Controls.TreeView?displayProperty=fullName> przykład lub w elemencie ItemsPresenter).</span><span class="sxs-lookup"><span data-stu-id="b38ff-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="b38ff-104">Ponadto w niektórych przypadkach różne elementy w widoku mogą spowodować niestabilność nawet wtedy, gdy nie ma marginesów.</span><span class="sxs-lookup"><span data-stu-id="b38ff-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b38ff-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="b38ff-105">Suggestion</span></span>

<span data-ttu-id="b38ff-106">Tę usterkę można uniknąć przez uaktualnienie do .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="b38ff-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="b38ff-107">Alternatywnie marginesy mogą być usuwane z kolekcji widoku (na przykład <xref:System.Windows.Controls.TreeView?displayProperty=fullName> s) w zwirtualizowanych panelach stosu, jeśli wszystkie zawarte elementy mają ten sam rozmiar.</span><span class="sxs-lookup"><span data-stu-id="b38ff-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=fullName>s) within virtualized stack panels if all contained items are the same size.</span></span>

| <span data-ttu-id="b38ff-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b38ff-108">Name</span></span>    | <span data-ttu-id="b38ff-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="b38ff-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b38ff-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="b38ff-110">Scope</span></span>   |<span data-ttu-id="b38ff-111">Duży</span><span class="sxs-lookup"><span data-stu-id="b38ff-111">Major</span></span>|
|<span data-ttu-id="b38ff-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="b38ff-112">Version</span></span>|<span data-ttu-id="b38ff-113">4.5</span><span class="sxs-lookup"><span data-stu-id="b38ff-113">4.5</span></span>|
|<span data-ttu-id="b38ff-114">Typ</span><span class="sxs-lookup"><span data-stu-id="b38ff-114">Type</span></span>|<span data-ttu-id="b38ff-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="b38ff-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b38ff-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b38ff-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)`

-->
