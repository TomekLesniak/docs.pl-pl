---
ms.openlocfilehash: c78122a2fe69c78625d6cb7fa9ddf41c49c2e737
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497449"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="6efac-101">Wywołanie elementu DataGrid. CommitEdit z obsługi CellEditEnding powoduje odrzucenie fokusu</span><span class="sxs-lookup"><span data-stu-id="6efac-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

#### <a name="details"></a><span data-ttu-id="6efac-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="6efac-102">Details</span></span>

<span data-ttu-id="6efac-103">Wywołanie <xref:System.Windows.Controls.DataGrid.CommitEdit> z jednego z <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> programów obsługi zdarzeń powoduje <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> utratę fokusu.</span><span class="sxs-lookup"><span data-stu-id="6efac-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> to lose focus.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6efac-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="6efac-104">Suggestion</span></span>

<span data-ttu-id="6efac-105">Ta usterka została rozwiązana w .NET Framework 4.5.2, dlatego można ją uniknąć, uaktualniając .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6efac-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="6efac-106">Alternatywnie można to uniknąć przez jawne ponowne wybranie polecenia <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> po wywołaniu <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="6efac-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span></span>

| <span data-ttu-id="6efac-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="6efac-107">Name</span></span>    | <span data-ttu-id="6efac-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="6efac-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6efac-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="6efac-109">Scope</span></span>   |<span data-ttu-id="6efac-110">Edge</span><span class="sxs-lookup"><span data-stu-id="6efac-110">Edge</span></span>|
|<span data-ttu-id="6efac-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="6efac-111">Version</span></span>|<span data-ttu-id="6efac-112">4.5</span><span class="sxs-lookup"><span data-stu-id="6efac-112">4.5</span></span>|
|<span data-ttu-id="6efac-113">Typ</span><span class="sxs-lookup"><span data-stu-id="6efac-113">Type</span></span>|<span data-ttu-id="6efac-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="6efac-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6efac-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="6efac-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.CommitEdit`
- `M:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)`

-->
