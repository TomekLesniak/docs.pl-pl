---
ms.openlocfilehash: 961ca545560a53fc2c1d52722b68ae460de66877
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496896"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a><span data-ttu-id="7057b-101">DataGridCellsPanel. BringIndexIntoView zgłasza wyjątku ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="7057b-101">DataGridCellsPanel.BringIndexIntoView throws ArgumentOutOfRangeException</span></span>

#### <a name="details"></a><span data-ttu-id="7057b-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="7057b-102">Details</span></span>

<span data-ttu-id="7057b-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> działa asynchronicznie, gdy Wirtualizacja kolumny jest włączona, ale szerokość kolumn nie została jeszcze ustalona.</span><span class="sxs-lookup"><span data-stu-id="7057b-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> will work asynchronously when column virtualization is enabled but the column widths have not yet been determined.</span></span>  <span data-ttu-id="7057b-104">Jeśli kolumny zostaną usunięte przed wykonaniem asynchronicznej pracy, <xref:System.ArgumentOutOfRangeException?displayProperty=fullName> może wystąpić.</span><span class="sxs-lookup"><span data-stu-id="7057b-104">If columns are removed before the asynchronous work happens, an <xref:System.ArgumentOutOfRangeException?displayProperty=fullName> can occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7057b-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="7057b-105">Suggestion</span></span>

<span data-ttu-id="7057b-106">Jeden z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="7057b-106">Any one of the following:</span></span><ol><li><span data-ttu-id="7057b-107">Uaktualnij do .NET Framework 4,7.</span><span class="sxs-lookup"><span data-stu-id="7057b-107">Upgrade to .NET Framework 4.7.</span></span></li><li><span data-ttu-id="7057b-108">Zainstaluj najnowszą poprawkę obsługi dla .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="7057b-108">Install the latest servicing patch for .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="7057b-109">Należy unikać usuwania kolumn do momentu ukończenia asynchronicznej odpowiedzi <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> .</span><span class="sxs-lookup"><span data-stu-id="7057b-109">Avoid removing columns until the asynchronous response to <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> has completed.</span></span></li></ol>

| <span data-ttu-id="7057b-110">Nazwa</span><span class="sxs-lookup"><span data-stu-id="7057b-110">Name</span></span>    | <span data-ttu-id="7057b-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="7057b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7057b-112">Zakres</span><span class="sxs-lookup"><span data-stu-id="7057b-112">Scope</span></span>   |<span data-ttu-id="7057b-113">Edge</span><span class="sxs-lookup"><span data-stu-id="7057b-113">Edge</span></span>|
|<span data-ttu-id="7057b-114">Wersja</span><span class="sxs-lookup"><span data-stu-id="7057b-114">Version</span></span>|<span data-ttu-id="7057b-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="7057b-115">4.6.2</span></span>|
|<span data-ttu-id="7057b-116">Typ</span><span class="sxs-lookup"><span data-stu-id="7057b-116">Type</span></span>|<span data-ttu-id="7057b-117">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="7057b-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7057b-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="7057b-118">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)`
- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)`

-->
