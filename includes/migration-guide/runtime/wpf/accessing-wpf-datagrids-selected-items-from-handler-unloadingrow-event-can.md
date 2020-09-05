---
ms.openlocfilehash: 1487e32ffca7b4bbebb5edac7efc8961ac05723b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497102"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="2bdfc-101">Dostęp do wybranych elementów programu WPF DataGrid z procedury obsługi zdarzenia UnloadingRow elementu DataGrid może spowodować wystąpienie elementu NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="2bdfc-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="2bdfc-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="2bdfc-102">Details</span></span>

<span data-ttu-id="2bdfc-103">Ze względu na usterkę w .NET Framework 4,5, obsługa zdarzeń dla <xref:System.Windows.Controls.DataGrid> zdarzeń obejmujących usunięcie wiersza może spowodować, że <xref:System.NullReferenceException?displayProperty=fullName> zostanie wygenerowany, jeśli uzyskują dostęp do <xref:System.Windows.Controls.DataGrid> <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> właściwości lub <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="2bdfc-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=fullName> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> properties.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2bdfc-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="2bdfc-104">Suggestion</span></span>

<span data-ttu-id="2bdfc-105">Ten problem został rozwiązany w .NET Framework 4,6 i może zostać rozwiązany przez uaktualnienie do tej wersji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2bdfc-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="2bdfc-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="2bdfc-106">Name</span></span>    | <span data-ttu-id="2bdfc-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="2bdfc-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2bdfc-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="2bdfc-108">Scope</span></span>   |<span data-ttu-id="2bdfc-109">Mały</span><span class="sxs-lookup"><span data-stu-id="2bdfc-109">Minor</span></span>|
|<span data-ttu-id="2bdfc-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="2bdfc-110">Version</span></span>|<span data-ttu-id="2bdfc-111">4.5</span><span class="sxs-lookup"><span data-stu-id="2bdfc-111">4.5</span></span>|
|<span data-ttu-id="2bdfc-112">Typ</span><span class="sxs-lookup"><span data-stu-id="2bdfc-112">Type</span></span>|<span data-ttu-id="2bdfc-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="2bdfc-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2bdfc-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="2bdfc-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.Controls.DataGrid.UnloadingRow`
- `E:System.Windows.Controls.DataGrid.UnloadingRowDetails`

-->
