---
ms.openlocfilehash: 3244913e06a744dafc4440f824ebe6bed25b8dd1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497393"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="2ae62-101">ObjectDisposedException zgłoszone przez program sprawdzania pisowni WPF</span><span class="sxs-lookup"><span data-stu-id="2ae62-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="2ae62-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="2ae62-102">Details</span></span>

<span data-ttu-id="2ae62-103">Aplikacje WPF sporadycznie uległy awarii podczas zamykania aplikacji za pomocą modułu <xref:System.ObjectDisposedException?displayProperty=fullName> sprawdzania pisowni.</span><span class="sxs-lookup"><span data-stu-id="2ae62-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="2ae62-104">Jest to rozwiązane w 4,7 .NET Frameworkj platformie WPF przez obsługę wyjątku i w ten sposób, dzięki czemu nie ma już negatywnego wpływ na aplikacje.</span><span class="sxs-lookup"><span data-stu-id="2ae62-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="2ae62-105">Należy zauważyć, że sporadyczne wyjątki pierwszej szansy byłyby nadal przestrzegane w aplikacjach uruchamianych w ramach debugera.</span><span class="sxs-lookup"><span data-stu-id="2ae62-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2ae62-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="2ae62-106">Suggestion</span></span>

<span data-ttu-id="2ae62-107">Uaktualnij do .NET Framework 4,7</span><span class="sxs-lookup"><span data-stu-id="2ae62-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="2ae62-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="2ae62-108">Name</span></span>    | <span data-ttu-id="2ae62-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="2ae62-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2ae62-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="2ae62-110">Scope</span></span>   |<span data-ttu-id="2ae62-111">Edge</span><span class="sxs-lookup"><span data-stu-id="2ae62-111">Edge</span></span>|
|<span data-ttu-id="2ae62-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="2ae62-112">Version</span></span>|<span data-ttu-id="2ae62-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="2ae62-113">4.6.1</span></span>|
|<span data-ttu-id="2ae62-114">Typ</span><span class="sxs-lookup"><span data-stu-id="2ae62-114">Type</span></span>|<span data-ttu-id="2ae62-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="2ae62-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2ae62-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="2ae62-116">Affected APIs</span></span>

<span data-ttu-id="2ae62-117">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="2ae62-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
