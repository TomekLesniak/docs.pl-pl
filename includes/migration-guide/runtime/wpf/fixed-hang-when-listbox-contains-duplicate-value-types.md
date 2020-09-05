---
ms.openlocfilehash: 7637c2d96aef93b4cf8f2314c1dd1edba51d553c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496237"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a><span data-ttu-id="c302c-101">Naprawiono zawieszenie, gdy pole listy zawiera zduplikowane typy wartości</span><span class="sxs-lookup"><span data-stu-id="c302c-101">Fixed a hang when ListBox contains duplicate value-types</span></span>

#### <a name="details"></a><span data-ttu-id="c302c-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="c302c-102">Details</span></span>

<span data-ttu-id="c302c-103">Rozwiązano problem polegający na tym, że wirtualizacja <xref:System.Windows.Controls.ItemsControl> może się zawiesić podczas przewijania, gdy kolekcja elementów zawiera zduplikowane obiekty z typem wartości.</span><span class="sxs-lookup"><span data-stu-id="c302c-103">Fixed a problem where a virtualizing<xref:System.Windows.Controls.ItemsControl> can hang during scrolling when its Items collection contains duplicate value-typed objects.</span></span>

| <span data-ttu-id="c302c-104">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c302c-104">Name</span></span>    | <span data-ttu-id="c302c-105">Wartość</span><span class="sxs-lookup"><span data-stu-id="c302c-105">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c302c-106">Zakres</span><span class="sxs-lookup"><span data-stu-id="c302c-106">Scope</span></span>   |<span data-ttu-id="c302c-107">Duży</span><span class="sxs-lookup"><span data-stu-id="c302c-107">Major</span></span>|
|<span data-ttu-id="c302c-108">Wersja</span><span class="sxs-lookup"><span data-stu-id="c302c-108">Version</span></span>|<span data-ttu-id="c302c-109">4,8</span><span class="sxs-lookup"><span data-stu-id="c302c-109">4.8</span></span>|
|<span data-ttu-id="c302c-110">Typ</span><span class="sxs-lookup"><span data-stu-id="c302c-110">Type</span></span>|<span data-ttu-id="c302c-111">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="c302c-111">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c302c-112">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="c302c-112">Affected APIs</span></span>

<span data-ttu-id="c302c-113">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="c302c-113">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
