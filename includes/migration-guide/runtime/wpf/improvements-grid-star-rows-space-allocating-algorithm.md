---
ms.openlocfilehash: 415eb1960c20fb662469e126560d6f366309eb0d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496146"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="a8b7e-101">Ulepszenia siatki z gwiazdkami — przydzielenie algorytmu w przestrzeni wierszy</span><span class="sxs-lookup"><span data-stu-id="a8b7e-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="a8b7e-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="a8b7e-102">Details</span></span>

<span data-ttu-id="a8b7e-103">Rozwiązano usterkę w [algorytmie przydzielania rozmiarów do](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)programu w ramach <xref:System.Windows.Controls.Grid> wprowadzenia w .NET Framework 4,7.</span><span class="sxs-lookup"><span data-stu-id="a8b7e-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="a8b7e-104">W niektórych przypadkach, takich jak siatka <code>Height=&quot;Auto&quot;</code> zawierająca puste wiersze, wiersze były ułożone w niewłaściwej pozycji, prawdopodobnie poza siatką.</span><span class="sxs-lookup"><span data-stu-id="a8b7e-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a8b7e-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="a8b7e-105">Suggestion</span></span>

<span data-ttu-id="a8b7e-106">Aby aplikacja mogła korzystać z tych zmian, należy ją uruchomić w .NET Framework 4,8 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="a8b7e-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="a8b7e-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="a8b7e-107">Name</span></span>    | <span data-ttu-id="a8b7e-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="a8b7e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a8b7e-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="a8b7e-109">Scope</span></span>   |<span data-ttu-id="a8b7e-110">Duży</span><span class="sxs-lookup"><span data-stu-id="a8b7e-110">Major</span></span>|
|<span data-ttu-id="a8b7e-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="a8b7e-111">Version</span></span>|<span data-ttu-id="a8b7e-112">4,8</span><span class="sxs-lookup"><span data-stu-id="a8b7e-112">4.8</span></span>|
|<span data-ttu-id="a8b7e-113">Typ</span><span class="sxs-lookup"><span data-stu-id="a8b7e-113">Type</span></span>|<span data-ttu-id="a8b7e-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="a8b7e-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a8b7e-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a8b7e-115">Affected APIs</span></span>

<span data-ttu-id="a8b7e-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="a8b7e-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
