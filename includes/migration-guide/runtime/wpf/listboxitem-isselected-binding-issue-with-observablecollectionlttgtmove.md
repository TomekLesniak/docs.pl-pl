---
ms.openlocfilehash: 196b6a13d32c7767b858d6d68ca775eb49324805
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497106"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a><span data-ttu-id="ff748-101">Problem z powiązaniem IsSelected ListBoxItem z ObservableCollection &lt; T &gt; . Przenieś</span><span class="sxs-lookup"><span data-stu-id="ff748-101">ListBoxItem IsSelected binding issue with ObservableCollection&lt;T&gt;.Move</span></span>

#### <a name="details"></a><span data-ttu-id="ff748-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ff748-102">Details</span></span>

<span data-ttu-id="ff748-103">Wywołanie <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> lub <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> w kolekcji powiązanej <xref:System.Windows.Controls.ListBox?displayProperty=fullName> z zaznaczonymi elementami może prowadzić do nieprawidłowych zachowań z przyszłym wyborem lub usunięciem zaznaczenia <xref:System.Windows.Controls.ListBox?displayProperty=fullName> elementów.</span><span class="sxs-lookup"><span data-stu-id="ff748-103">Calling <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> or <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> on a collection bound to a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> with items selected can lead to erratic behavior with future selection or unselection of <xref:System.Windows.Controls.ListBox?displayProperty=fullName> items.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ff748-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="ff748-104">Suggestion</span></span>

<span data-ttu-id="ff748-105">Wywołanie <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> i <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> zamiast obejścia <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> tego problemu.</span><span class="sxs-lookup"><span data-stu-id="ff748-105">Calling <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> and <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> instead of <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> will work around this issue.</span></span> <span data-ttu-id="ff748-106">Alternatywnie ten problem został rozwiązany w .NET Framework 4,6 i może zostać rozwiązany przez uaktualnienie do tej wersji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff748-106">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="ff748-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="ff748-107">Name</span></span>    | <span data-ttu-id="ff748-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="ff748-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ff748-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="ff748-109">Scope</span></span>   |<span data-ttu-id="ff748-110">Mały</span><span class="sxs-lookup"><span data-stu-id="ff748-110">Minor</span></span>|
|<span data-ttu-id="ff748-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="ff748-111">Version</span></span>|<span data-ttu-id="ff748-112">4.5</span><span class="sxs-lookup"><span data-stu-id="ff748-112">4.5</span></span>|
|<span data-ttu-id="ff748-113">Typ</span><span class="sxs-lookup"><span data-stu-id="ff748-113">Type</span></span>|<span data-ttu-id="ff748-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="ff748-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ff748-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ff748-115">Affected APIs</span></span>

- <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.ObjectModel.ObservableCollection`1.Move(System.Int32,System.Int32)``
- ``M:System.Collections.ObjectModel.ObservableCollection`1.MoveItem(System.Int32,System.Int32)``

-->
