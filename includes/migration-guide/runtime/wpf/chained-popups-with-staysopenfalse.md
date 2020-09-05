---
ms.openlocfilehash: 7bf5f7e8a49acc2918dd0d68a1c54a5c277091b0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496145"
---
### <a name="chained-popups-with-staysopenfalse"></a><span data-ttu-id="3f14c-101">Połączone okienka podręczne z StaysOpen = false</span><span class="sxs-lookup"><span data-stu-id="3f14c-101">Chained Popups with StaysOpen=False</span></span>

#### <a name="details"></a><span data-ttu-id="3f14c-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3f14c-102">Details</span></span>

<span data-ttu-id="3f14c-103">Okno podręczne z StaysOpen = false ma być zamknięte po kliknięciu poza oknem podręcznym.</span><span class="sxs-lookup"><span data-stu-id="3f14c-103">A Popup with StaysOpen=False is supposed to close when you click outside the Popup.</span></span> <span data-ttu-id="3f14c-104">Gdy dwa lub więcej takich okien podręcznych jest łańcucha (tj. jeden zawiera inny), wystąpił wiele problemów, w tym:</span><span class="sxs-lookup"><span data-stu-id="3f14c-104">When two or more such Popups are chained (i.e. one contains another), there were many problems, including:</span></span><ul><li><span data-ttu-id="3f14c-105">Otwórz dwa poziomy, kliknij poza P2, ale wewnątrz P1.</span><span class="sxs-lookup"><span data-stu-id="3f14c-105">Open two levels, click outside P2 but inside P1.</span></span>  <span data-ttu-id="3f14c-106">Nic się nie dzieje.</span><span class="sxs-lookup"><span data-stu-id="3f14c-106">Nothing happens.</span></span></li><li><span data-ttu-id="3f14c-107">Otwórz dwa poziomy, kliknij poza P1.</span><span class="sxs-lookup"><span data-stu-id="3f14c-107">Open two levels, click outside P1.</span></span>  <span data-ttu-id="3f14c-108">Zamknij oba okna podręczne.</span><span class="sxs-lookup"><span data-stu-id="3f14c-108">Both popups close.</span></span></li><li><span data-ttu-id="3f14c-109">Otwórz i Zamknij dwa poziomy.</span><span class="sxs-lookup"><span data-stu-id="3f14c-109">Open and close two levels.</span></span>  <span data-ttu-id="3f14c-110">Następnie spróbuj ponownie otworzyć P2.</span><span class="sxs-lookup"><span data-stu-id="3f14c-110">Then try to open P2 again.</span></span>  <span data-ttu-id="3f14c-111">Nic się nie dzieje.</span><span class="sxs-lookup"><span data-stu-id="3f14c-111">Nothing happens.</span></span></li><li><span data-ttu-id="3f14c-112">Spróbuj otworzyć trzy poziomy.</span><span class="sxs-lookup"><span data-stu-id="3f14c-112">Try to open three levels.</span></span>  <span data-ttu-id="3f14c-113">Nie można.</span><span class="sxs-lookup"><span data-stu-id="3f14c-113">You can't.</span></span>  <span data-ttu-id="3f14c-114">(Nic się nie dzieje lub pierwsze dwa poziomy są zamykane, w zależności od tego, gdzie klikniesz). Te przypadki (i inne warianty) działają teraz zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="3f14c-114">(Either nothing happens or the first two levels close, depending on where you click.) These cases (and other variants) now work as expected.</span></span></li></ul>

| <span data-ttu-id="3f14c-115">Nazwa</span><span class="sxs-lookup"><span data-stu-id="3f14c-115">Name</span></span>    | <span data-ttu-id="3f14c-116">Wartość</span><span class="sxs-lookup"><span data-stu-id="3f14c-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3f14c-117">Zakres</span><span class="sxs-lookup"><span data-stu-id="3f14c-117">Scope</span></span>   |<span data-ttu-id="3f14c-118">Edge</span><span class="sxs-lookup"><span data-stu-id="3f14c-118">Edge</span></span>|
|<span data-ttu-id="3f14c-119">Wersja</span><span class="sxs-lookup"><span data-stu-id="3f14c-119">Version</span></span>|<span data-ttu-id="3f14c-120">4.7.1</span><span class="sxs-lookup"><span data-stu-id="3f14c-120">4.7.1</span></span>|
|<span data-ttu-id="3f14c-121">Typ</span><span class="sxs-lookup"><span data-stu-id="3f14c-121">Type</span></span>|<span data-ttu-id="3f14c-122">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="3f14c-122">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3f14c-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="3f14c-123">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.Popup.StaysOpen`

-->
