---
ms.openlocfilehash: 61749f59f9379a6d18bb013b2612a07cb7822b3a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497649"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="f0ec7-101">Nowe wartości wyliczeniowe w PageRangeSelection WPF</span><span class="sxs-lookup"><span data-stu-id="f0ec7-101">New enum values in WPF's PageRangeSelection</span></span>

#### <a name="details"></a><span data-ttu-id="f0ec7-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f0ec7-102">Details</span></span>

<span data-ttu-id="f0ec7-103">Dodano dwóch nowych członków ( <xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> i <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName> ) do <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="f0ec7-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> enum.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f0ec7-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="f0ec7-104">Suggestion</span></span>

<span data-ttu-id="f0ec7-105">W większości przypadków te zmiany nie wpłyną na kod użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f0ec7-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="f0ec7-106">Kod, który zależy od określonej liczby elementów istniejących w <xref:System.Enum.GetNames(System.Type)> lub <xref:System.Enum.GetValues(System.Type)> wywołania <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> typu należy zmodyfikować, chociaż.</span><span class="sxs-lookup"><span data-stu-id="f0ec7-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> type should be modified, though.</span></span>

| <span data-ttu-id="f0ec7-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="f0ec7-107">Name</span></span>    | <span data-ttu-id="f0ec7-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="f0ec7-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f0ec7-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="f0ec7-109">Scope</span></span>   |<span data-ttu-id="f0ec7-110">Edge</span><span class="sxs-lookup"><span data-stu-id="f0ec7-110">Edge</span></span>|
|<span data-ttu-id="f0ec7-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="f0ec7-111">Version</span></span>|<span data-ttu-id="f0ec7-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f0ec7-112">4.5</span></span>|
|<span data-ttu-id="f0ec7-113">Typ</span><span class="sxs-lookup"><span data-stu-id="f0ec7-113">Type</span></span>|<span data-ttu-id="f0ec7-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="f0ec7-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f0ec7-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f0ec7-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.PageRangeSelection`

-->
