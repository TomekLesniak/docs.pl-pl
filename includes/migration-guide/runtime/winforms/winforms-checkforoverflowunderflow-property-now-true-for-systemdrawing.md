---
ms.openlocfilehash: 68b0c4bb032b9744ef585eaef3d68e31afebee24
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496125"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="3f08d-101">Właściwość CheckForOverflowUnderflow kontrolki WinForm jest teraz prawdziwa dla elementu System. Drawing</span><span class="sxs-lookup"><span data-stu-id="3f08d-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="3f08d-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3f08d-102">Details</span></span>

<span data-ttu-id="3f08d-103">Właściwość CheckForOverflowUnderflow zestawu System.Drawing.dll ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="3f08d-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3f08d-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="3f08d-104">Suggestion</span></span>

<span data-ttu-id="3f08d-105">Poprzednio po wystąpieniu przepełnienia wynik zostałby dyskretnie obcięty.</span><span class="sxs-lookup"><span data-stu-id="3f08d-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="3f08d-106">Zostanie <xref:System.OverflowException?displayProperty=fullName> zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="3f08d-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="3f08d-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="3f08d-107">Name</span></span>    | <span data-ttu-id="3f08d-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="3f08d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3f08d-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="3f08d-109">Scope</span></span>   |<span data-ttu-id="3f08d-110">Edge</span><span class="sxs-lookup"><span data-stu-id="3f08d-110">Edge</span></span>|
|<span data-ttu-id="3f08d-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="3f08d-111">Version</span></span>|<span data-ttu-id="3f08d-112">4.5</span><span class="sxs-lookup"><span data-stu-id="3f08d-112">4.5</span></span>|
|<span data-ttu-id="3f08d-113">Typ</span><span class="sxs-lookup"><span data-stu-id="3f08d-113">Type</span></span>|<span data-ttu-id="3f08d-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="3f08d-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3f08d-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="3f08d-115">Affected APIs</span></span>

<span data-ttu-id="3f08d-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="3f08d-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
