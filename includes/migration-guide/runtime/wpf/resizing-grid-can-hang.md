---
ms.openlocfilehash: 8dc1b4d94d01813a8124d1340b50fa78a9b157f8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497435"
---
### <a name="resizing-a-grid-can-hang"></a><span data-ttu-id="7ce68-101">Zmienianie rozmiarów siatki może się zawiesić</span><span class="sxs-lookup"><span data-stu-id="7ce68-101">Resizing a Grid can hang</span></span>

#### <a name="details"></a><span data-ttu-id="7ce68-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="7ce68-102">Details</span></span>

<span data-ttu-id="7ce68-103">Pętla nieskończona może wystąpić podczas układu w <code>T:System.Windows.Controls.Grid</code> następujących okolicznościach:</span><span class="sxs-lookup"><span data-stu-id="7ce68-103">An infinite loop can occur during layout of a <code>T:System.Windows.Controls.Grid</code> under the following circumstances:</span></span><ul><li><span data-ttu-id="7ce68-104">Definicje wierszy zawierają dwa \* wiersze, deklarując MinHeight i MaxHeight.</span><span class="sxs-lookup"><span data-stu-id="7ce68-104">Row definitions contain two \*-rows, both declaring a MinHeight and a MaxHeight.</span></span></li><li><span data-ttu-id="7ce68-105">Zawartość \* wierszy nie przekracza odpowiedniego MaxHeight</span><span class="sxs-lookup"><span data-stu-id="7ce68-105">Content of the \*-rows doesn't exceed the corresponding MaxHeight</span></span></li><li><span data-ttu-id="7ce68-106">Dostępna wysokość siatki jest przekraczana przez pierwszy MinHeight (plus wszystkie inne stałe lub autowiersze)</span><span class="sxs-lookup"><span data-stu-id="7ce68-106">The Grid's available height is exceeded by the first MinHeight (plus any other fixed or Auto rows)</span></span></li><li><span data-ttu-id="7ce68-107">Aplikacja jest przeznaczona dla .NET Framework 4,7 lub jest docelowa do algorytmu alokacji 4,7 przez ustawienie <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></span><span class="sxs-lookup"><span data-stu-id="7ce68-107">The app targets .NET Framework 4.7, or opts in to the 4.7 allocation algorithm by setting <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></span></span></li></ul><span data-ttu-id="7ce68-108">Pętla również występuje z więcej niż dwoma wierszami lub analogicznie do kolumn.</span><span class="sxs-lookup"><span data-stu-id="7ce68-108">The loop would also happen with more than two rows, or in the analogous case for columns.</span></span> <span data-ttu-id="7ce68-109">Problem został rozwiązany w .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="7ce68-109">The issue is fixed in .NET Framework 4.7.1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7ce68-110">Sugestia</span><span class="sxs-lookup"><span data-stu-id="7ce68-110">Suggestion</span></span>

<span data-ttu-id="7ce68-111">Uaktualnij do .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="7ce68-111">Upgrade to .NET Framework 4.7.1.</span></span>  <span data-ttu-id="7ce68-112">Alternatywnie, jeśli nie jest potrzebny algorytm alokacji 4,7, można użyć następującego ustawienia konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="7ce68-112">Alternatively, if you don't need the 4.7 allocation algorithm you can use the following configuration setting:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="7ce68-113">Nazwa</span><span class="sxs-lookup"><span data-stu-id="7ce68-113">Name</span></span>    | <span data-ttu-id="7ce68-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="7ce68-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7ce68-115">Zakres</span><span class="sxs-lookup"><span data-stu-id="7ce68-115">Scope</span></span>   |<span data-ttu-id="7ce68-116">Edge</span><span class="sxs-lookup"><span data-stu-id="7ce68-116">Edge</span></span>|
|<span data-ttu-id="7ce68-117">Wersja</span><span class="sxs-lookup"><span data-stu-id="7ce68-117">Version</span></span>|<span data-ttu-id="7ce68-118">4,7</span><span class="sxs-lookup"><span data-stu-id="7ce68-118">4.7</span></span>|
|<span data-ttu-id="7ce68-119">Typ</span><span class="sxs-lookup"><span data-stu-id="7ce68-119">Type</span></span>|<span data-ttu-id="7ce68-120">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="7ce68-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7ce68-121">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="7ce68-121">Affected APIs</span></span>

<span data-ttu-id="7ce68-122">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="7ce68-122">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
