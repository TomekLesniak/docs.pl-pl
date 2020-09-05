---
ms.openlocfilehash: d23d7821e19b9d7f2db13a6bfdf868a8414cf721
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497346"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a><span data-ttu-id="0cefe-101">Element — przewijanie płaskiej listy z elementami o różnej wysokości pikseli</span><span class="sxs-lookup"><span data-stu-id="0cefe-101">Item-scrolling a flat list with items of different pixel-height</span></span>

#### <a name="details"></a><span data-ttu-id="0cefe-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="0cefe-102">Details</span></span>

<span data-ttu-id="0cefe-103">Gdy <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> zostanie wyświetlona kolekcja używająca wirtualizacji ( <code>IsVirtualizing=true</code> ) i przewijania elementów ( <code>ScrollUnit=Item</code> ) i gdy kontrolka przewinie się w celu wyświetlenia elementu, którego wysokość w pikselach różni się od sąsiadów, <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> wykonuje iterację wszystkich elementów w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="0cefe-103">When an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> displays a collection using virtualization (<code>IsVirtualizing=true</code>) and item- scrolling (<code>ScrollUnit=Item</code>), and when the control scrolls to display an item whose height in pixels differs from its neighbors, the <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> iterates over all items in the collection.</span></span> <span data-ttu-id="0cefe-104">Interfejs użytkownika nie odpowiada podczas tej iteracji; Jeśli kolekcja jest duża, może to być postrzegane jako zawieszenie.</span><span class="sxs-lookup"><span data-stu-id="0cefe-104">The UI is unresponsive during this iteration; if the collection is large, this can be perceived as a hang.</span></span> <span data-ttu-id="0cefe-105">Iteracja występuje w innych sytuacjach, nawet w poprzednich wersjach .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0cefe-105">The iteration occurs in other circumstances, even in previous .NET Framework releases.</span></span> <span data-ttu-id="0cefe-106">Na przykład występuje w przypadku przewijania do pikseli () w przypadku <code>ScrollUnit=Pixel</code> napotkania elementu o różnej wysokości pikseli, a po przejściu danych hierarchicznych (takich jak <xref:System.Windows.Controls.TreeView?displayProperty=fullName> lub <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> z włączonym grupowaniem) w przypadku napotkania elementu z inną liczbą elementów podrzędnych niż jego sąsiedzi. W przypadku przewijania elementów i o różnej wysokości pikseli iteracja została wprowadzona w .NET Framework 4.6.1, aby naprawić błędy w układzie danych hierarchicznych.</span><span class="sxs-lookup"><span data-stu-id="0cefe-106">For example, it occurs when pixel-scrolling (<code>ScrollUnit=Pixel</code>) upon encountering an item with different pixel height, and when item-scrolling hierarchical data (such as a <xref:System.Windows.Controls.TreeView?displayProperty=fullName> or an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> with grouping enabled) upon encountering an item with a different number of descendant items than its neighbors.For the case of item-scrolling and different pixel height, the iteration was introduced in .NET Framework 4.6.1 to fix bugs in the layout of hierarchical data.</span></span>  <span data-ttu-id="0cefe-107">Nie jest to konieczne, jeśli dane są płaskie (bez hierarchii), a .NET Framework 4.6.2 nie robi w tym przypadku.</span><span class="sxs-lookup"><span data-stu-id="0cefe-107">It is not needed if the data is flat (no hierarchy), and .NET Framework 4.6.2 does not do it in that case.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0cefe-108">Sugestia</span><span class="sxs-lookup"><span data-stu-id="0cefe-108">Suggestion</span></span>

<span data-ttu-id="0cefe-109">Jeśli iteracja występuje w .NET Framework 4.6.1, ale nie w starszych wersjach — to oznacza, że jeśli <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> element jest przewijaną listą z elementami o różnej wysokości pikseli — istnieją dwie metody zaradcze:</span><span class="sxs-lookup"><span data-stu-id="0cefe-109">If the iteration occurs in .NET Framework 4.6.1 but not in earlier releases - that is, if the <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> is item- scrolling a flat list with items of different pixel height - there are two remedies:</span></span><ol><li><span data-ttu-id="0cefe-110">Zainstaluj .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="0cefe-110">Install .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="0cefe-111">Zainstaluj poprawkę HR 1605 dla .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="0cefe-111">Install hotfix HR 1605 for .NET Framework 4.6.1.</span></span></li></ol>

| <span data-ttu-id="0cefe-112">Nazwa</span><span class="sxs-lookup"><span data-stu-id="0cefe-112">Name</span></span>    | <span data-ttu-id="0cefe-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="0cefe-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0cefe-114">Zakres</span><span class="sxs-lookup"><span data-stu-id="0cefe-114">Scope</span></span>   |<span data-ttu-id="0cefe-115">Mały</span><span class="sxs-lookup"><span data-stu-id="0cefe-115">Minor</span></span>|
|<span data-ttu-id="0cefe-116">Wersja</span><span class="sxs-lookup"><span data-stu-id="0cefe-116">Version</span></span>|<span data-ttu-id="0cefe-117">4.6.1</span><span class="sxs-lookup"><span data-stu-id="0cefe-117">4.6.1</span></span>|
|<span data-ttu-id="0cefe-118">Typ</span><span class="sxs-lookup"><span data-stu-id="0cefe-118">Type</span></span>|<span data-ttu-id="0cefe-119">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="0cefe-119">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0cefe-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="0cefe-120">Affected APIs</span></span>

- <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.VirtualizingStackPanel`

-->
