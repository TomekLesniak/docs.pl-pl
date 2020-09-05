---
ms.openlocfilehash: f50022d9a7bacd7be40fe3050ced26e7c25cf7aa
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497772"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a><span data-ttu-id="42aac-101">Awaria w selektorze podczas usuwania elementu z niestandardowej kolekcji INCC</span><span class="sxs-lookup"><span data-stu-id="42aac-101">Crash in Selector when removing an item from a custom INCC collection</span></span>

#### <a name="details"></a><span data-ttu-id="42aac-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="42aac-102">Details</span></span>

<span data-ttu-id="42aac-103"><code>T:System.InvalidOperationException</code>Może wystąpić w następującym scenariuszu:</span><span class="sxs-lookup"><span data-stu-id="42aac-103">An <code>T:System.InvalidOperationException</code> can occur in the following scenario:</span></span><ul><li><span data-ttu-id="42aac-104">ItemsSource dla elementu <code>T:System.Windows.Controls.Primitives.Selector</code> to kolekcja z niestandardową implementacją programu <code>T:System.Collections.Specialized.INotifyCollectionChanged</code> .</span><span class="sxs-lookup"><span data-stu-id="42aac-104">The ItemsSource for a <code>T:System.Windows.Controls.Primitives.Selector</code> is a collection with a custom implementation of <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</span></span></li><li><span data-ttu-id="42aac-105">Wybrany element zostanie usunięty z kolekcji.</span><span class="sxs-lookup"><span data-stu-id="42aac-105">The selected item is removed from the collection.</span></span></li><li><span data-ttu-id="42aac-106"><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code>Ma <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> =-1 (wskazuje nieznaną pozycję).</span><span class="sxs-lookup"><span data-stu-id="42aac-106">The <code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> has <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (indicating an unknown position).</span></span></li></ul><span data-ttu-id="42aac-107">Stosu wywołań wyjątku rozpoczyna się od system. Windows. Threading. Dyspozytor. VerifyAccess () w System. Windows. DependencyObject. GetValue (DependencyProperty dp) w System. Windows. Controls. elementy pierwotne. Selector. GetIsSelected (DependencyObject element) ten wyjątek może wystąpić w .NET Framework 4,5, jeśli aplikacja ma więcej niż jeden wątek dyspozytora.</span><span class="sxs-lookup"><span data-stu-id="42aac-107">The exception's callstack begins at System.Windows.Threading.Dispatcher.VerifyAccess() at System.Windows.DependencyObject.GetValue(DependencyProperty dp) at System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element)This exception can occur in .NET Framework 4.5 if the application has more than one Dispatcher thread.</span></span> <span data-ttu-id="42aac-108">W .NET Framework 4,7 wyjątek może wystąpić również w aplikacjach z pojedynczym wątkiem dyspozytora.</span><span class="sxs-lookup"><span data-stu-id="42aac-108">In .NET Framework 4.7 the exception can also occur in applications with a single Dispatcher thread.</span></span> <span data-ttu-id="42aac-109">Problem został rozwiązany w .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="42aac-109">The issue is fixed in .NET Framework 4.7.1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="42aac-110">Sugestia</span><span class="sxs-lookup"><span data-stu-id="42aac-110">Suggestion</span></span>

<span data-ttu-id="42aac-111">Uaktualnij do .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="42aac-111">Upgrade to .NET Framework 4.7.1.</span></span>

| <span data-ttu-id="42aac-112">Nazwa</span><span class="sxs-lookup"><span data-stu-id="42aac-112">Name</span></span>    | <span data-ttu-id="42aac-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="42aac-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="42aac-114">Zakres</span><span class="sxs-lookup"><span data-stu-id="42aac-114">Scope</span></span>   |<span data-ttu-id="42aac-115">Mały</span><span class="sxs-lookup"><span data-stu-id="42aac-115">Minor</span></span>|
|<span data-ttu-id="42aac-116">Wersja</span><span class="sxs-lookup"><span data-stu-id="42aac-116">Version</span></span>|<span data-ttu-id="42aac-117">4,7</span><span class="sxs-lookup"><span data-stu-id="42aac-117">4.7</span></span>|
|<span data-ttu-id="42aac-118">Typ</span><span class="sxs-lookup"><span data-stu-id="42aac-118">Type</span></span>|<span data-ttu-id="42aac-119">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="42aac-119">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="42aac-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="42aac-120">Affected APIs</span></span>

<span data-ttu-id="42aac-121">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="42aac-121">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
