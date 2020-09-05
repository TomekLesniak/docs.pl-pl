---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496176"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="0f24d-101">Tło zestawu wstążki jest ustawione jako przezroczyste w zlokalizowanych kompilacjach</span><span class="sxs-lookup"><span data-stu-id="0f24d-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="0f24d-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="0f24d-102">Details</span></span>

<span data-ttu-id="0f24d-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> w tle dla zlokalizowanych kompilacji zawsze jest malowany przezroczysty Pędzel, co spowodowało słabą obsługę interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0f24d-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="0f24d-104">Ten problem został rozwiązany w .NET Framework 4,7 WPF, aktualizując zlokalizowane zasoby dla <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> , które z kolei zapewniają, że wybrany jest prawidłowy pędzel.</span><span class="sxs-lookup"><span data-stu-id="0f24d-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0f24d-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="0f24d-105">Suggestion</span></span>

<span data-ttu-id="0f24d-106">Uaktualnij do .NET Framework 4,7</span><span class="sxs-lookup"><span data-stu-id="0f24d-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="0f24d-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="0f24d-107">Name</span></span>    | <span data-ttu-id="0f24d-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="0f24d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0f24d-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="0f24d-109">Scope</span></span>   |<span data-ttu-id="0f24d-110">Edge</span><span class="sxs-lookup"><span data-stu-id="0f24d-110">Edge</span></span>|
|<span data-ttu-id="0f24d-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="0f24d-111">Version</span></span>|<span data-ttu-id="0f24d-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="0f24d-112">4.6.2</span></span>|
|<span data-ttu-id="0f24d-113">Typ</span><span class="sxs-lookup"><span data-stu-id="0f24d-113">Type</span></span>|<span data-ttu-id="0f24d-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="0f24d-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0f24d-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="0f24d-115">Affected APIs</span></span>

<span data-ttu-id="0f24d-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="0f24d-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
