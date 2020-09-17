---
ms.openlocfilehash: 8c739d8f355ffa6a6e09cbe4c531b188acede5bd
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720309"
---
### <a name="osplatform-attributes-renamed-or-removed"></a><span data-ttu-id="79b67-101">Atrybuty OSPlatform zostały zmienione lub usunięte</span><span class="sxs-lookup"><span data-stu-id="79b67-101">OSPlatform attributes renamed or removed</span></span>

<span data-ttu-id="79b67-102">Następujące atrybuty wprowadzone w programie .NET 5,0 Preview 8 zostały usunięte lub zmieniono ich nazwy: `MinimumOSPlatformAttribute` , `RemovedInOSPlatformAttribute` , i `ObsoletedInOSPlatformAttribute` .</span><span class="sxs-lookup"><span data-stu-id="79b67-102">The following attributes that were introduced in .NET 5.0 Preview 8 have been removed or renamed: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute`, and `ObsoletedInOSPlatformAttribute`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="79b67-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="79b67-103">Change description</span></span>

<span data-ttu-id="79b67-104">W programie .NET 5,0 w wersji zapoznawczej 8 wprowadzono następujące atrybuty w <xref:System.Runtime.Versioning> przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="79b67-104">.NET 5.0 Preview 8 introduced the following attributes in the <xref:System.Runtime.Versioning> namespace:</span></span>

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

<span data-ttu-id="79b67-105">W programie .NET 5,0 w wersji zapoznawczej 8, gdy projekt jest przeznaczony dla programu .NET 5 specyficzny dla systemu operacyjnego, przy użyciu [monikera platformy docelowej](../../../../docs/standard/frameworks.md) , takiej jak `net5.0-windows` , kompilacja dodaje atrybut na poziomie zestawu `System.Runtime.Versioning.MinimumOSPlatformAttribute` .</span><span class="sxs-lookup"><span data-stu-id="79b67-105">In .NET 5.0 Preview 8, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../docs/standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level `System.Runtime.Versioning.MinimumOSPlatformAttribute` attribute.</span></span>

<span data-ttu-id="79b67-106">W programie .NET 5,0 RC1 program `ObsoletedInOSPlatformAttribute` został usunięty i `MinimumOSPlatformAttribute` `RemovedInOSPlatformAttribute` zmieniono jego nazwę w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="79b67-106">In .NET 5.0 RC1, the `ObsoletedInOSPlatformAttribute` has been removed, and `MinimumOSPlatformAttribute` and `RemovedInOSPlatformAttribute` have been renamed as follows:</span></span>

| <span data-ttu-id="79b67-107">Wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="79b67-107">Preview 8 name</span></span> | <span data-ttu-id="79b67-108">RC1 i nowsze nazwy</span><span class="sxs-lookup"><span data-stu-id="79b67-108">RC1 and later name</span></span> |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

<span data-ttu-id="79b67-109">W programie .NET 5,0 w wersji RC1 lub nowszej, gdy projekt jest przeznaczony dla programu .NET 5 specyficzny dla systemu operacyjnego, przy użyciu [monikera platformy docelowej](../../../../docs/standard/frameworks.md) , takiej jak `net5.0-windows` , kompilacja dodaje atrybut na poziomie zestawu <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> .</span><span class="sxs-lookup"><span data-stu-id="79b67-109">In .NET 5.0 RC1 and later, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../docs/standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> attribute.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="79b67-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="79b67-110">Reason for change</span></span>

<span data-ttu-id="79b67-111">Program .NET 5,0 w wersji zapoznawczej 8 wprowadza atrybuty w <xref:System.Runtime.Versioning> celu określenia obsługiwanych platform dla interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="79b67-111">.NET 5.0 Preview 8 introduced attributes in <xref:System.Runtime.Versioning> to specify supported platforms for APIs.</span></span> <span data-ttu-id="79b67-112">Atrybuty są używane przez [analizatora zgodności platformy](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) do tworzenia ostrzeżeń kompilacji, gdy interfejsy API specyficzne dla platformy są używane na platformach, które nie obsługują tych interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="79b67-112">The attributes are consumed by the [Platform compatibility analyzer](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) to produce build warnings when platform-specific APIs are consumed on platforms that don't supported those APIs.</span></span>

<span data-ttu-id="79b67-113">W przypadku platformy .NET 5,0 RC1 dodano do analizatora zgodności platformy dodatkową funkcję umożliwiającą wykluczenie platformy.</span><span class="sxs-lookup"><span data-stu-id="79b67-113">For .NET 5.0 RC1, an additional feature was added to the platform compatibility analyzer for platform exclusion.</span></span> <span data-ttu-id="79b67-114">Funkcja umożliwia oznaczenie interfejsów API jako całkowicie nieobsługiwanych na platformach systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="79b67-114">The feature allows APIs to be marked as entirely unsupported on OS platforms.</span></span> <span data-ttu-id="79b67-115">Ta funkcja monituje o wprowadzenie zmian w atrybutach, w tym przy użyciu bardziej odpowiednich nazw.</span><span class="sxs-lookup"><span data-stu-id="79b67-115">That feature prompted changes to the attributes, including using more suitable names.</span></span> <span data-ttu-id="79b67-116">`ObsoletedInOSPlatformAttribute`Zostało usunięte, ponieważ nie było już potrzebne.</span><span class="sxs-lookup"><span data-stu-id="79b67-116">The `ObsoletedInOSPlatformAttribute` was removed because it was no longer needed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="79b67-117">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="79b67-117">Version introduced</span></span>

<span data-ttu-id="79b67-118">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="79b67-118">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="79b67-119">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="79b67-119">Recommended action</span></span>

<span data-ttu-id="79b67-120">Po przekierowaniu projektu z programu .NET 5,0 w wersji zapoznawczej 8 do programu .NET 5,0 RC1 mogą wystąpić błędy kompilacji lub czasu wykonania z powodu tych zmian.</span><span class="sxs-lookup"><span data-stu-id="79b67-120">When you retarget your project from .NET 5.0 Preview 8 to .NET 5.0 RC1, you might encounter build or run-time errors due to these changes.</span></span> <span data-ttu-id="79b67-121">Na przykład zmiana nazwy `MinimumOSPlatformAttribute` może spowodować błędy, ponieważ atrybut jest stosowany do zestawów specyficznych dla platformy w czasie kompilacji, a stare artefakty kompilacji nadal odwołują się do starej nazwy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="79b67-121">For example, the renaming of `MinimumOSPlatformAttribute` is likely to produce errors, because the attribute is applied to platform-specific assemblies at build time, and old build artifacts will still reference the old API name.</span></span>

<span data-ttu-id="79b67-122">Przykładowe błędy czasu kompilacji:</span><span class="sxs-lookup"><span data-stu-id="79b67-122">Example build-time errors:</span></span>

- <span data-ttu-id="79b67-123">**błąd CS0246: nie można znaleźć nazwy typu lub przestrzeni nazw "MinimumOSPlatformAttribute" (czy nie brakuje dyrektywy using lub odwołania do zestawu?)**</span><span class="sxs-lookup"><span data-stu-id="79b67-123">**error CS0246: The type or namespace name 'MinimumOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="79b67-124">**błąd CS0246: nie można znaleźć nazwy typu lub przestrzeni nazw "RemovedInOSPlatformAttribute" (czy nie brakuje dyrektywy using lub odwołania do zestawu?)**</span><span class="sxs-lookup"><span data-stu-id="79b67-124">**error CS0246: The type or namespace name 'RemovedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="79b67-125">**błąd CS0246: nie można znaleźć nazwy typu lub przestrzeni nazw "ObsoletedInOSPlatformAttribute" (czy nie brakuje dyrektywy using lub odwołania do zestawu?)**</span><span class="sxs-lookup"><span data-stu-id="79b67-125">**error CS0246: The type or namespace name 'ObsoletedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="79b67-126">Przykładowy błąd czasu wykonywania:</span><span class="sxs-lookup"><span data-stu-id="79b67-126">Example run-time error:</span></span>

<span data-ttu-id="79b67-127">**Nieobsługiwany wyjątek. System. TypeLoadException: nie można załadować typu "System. Runtime. Versioning. MinimumOSPlatformAttribute" z zestawu "System. Runtime, Version = 5.0.0.0, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a".**</span><span class="sxs-lookup"><span data-stu-id="79b67-127">**Unhandled exception. System.TypeLoadException: Could not load type 'System.Runtime.Versioning.MinimumOSPlatformAttribute' from assembly 'System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a'.**</span></span>

<span data-ttu-id="79b67-128">Aby rozwiązać te błędy:</span><span class="sxs-lookup"><span data-stu-id="79b67-128">To resolve these errors:</span></span>

- <span data-ttu-id="79b67-129">Zaktualizuj wszystkie odwołania `MinimumOSPlatformAttribute` do <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> .</span><span class="sxs-lookup"><span data-stu-id="79b67-129">Update any references of `MinimumOSPlatformAttribute` to <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="79b67-130">Zaktualizuj wszystkie odwołania `RemovedInOSPlatformAttribute` do <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> .</span><span class="sxs-lookup"><span data-stu-id="79b67-130">Update any references of `RemovedInOSPlatformAttribute` to <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="79b67-131">Usuń wszystkie odwołania do `ObsoletedInOSPlatformAttribute` .</span><span class="sxs-lookup"><span data-stu-id="79b67-131">Remove any references to `ObsoletedInOSPlatformAttribute`.</span></span>
- <span data-ttu-id="79b67-132">Skompiluj ponownie projekt (lub wykonaj czyszczenie + kompilację), aby usunąć stare artefakty kompilacji.</span><span class="sxs-lookup"><span data-stu-id="79b67-132">Rebuild your project (or perform clean + build) to delete old build artifacts.</span></span>

#### <a name="category"></a><span data-ttu-id="79b67-133">Kategoria</span><span class="sxs-lookup"><span data-stu-id="79b67-133">Category</span></span>

<span data-ttu-id="79b67-134">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="79b67-134">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="79b67-135">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="79b67-135">Affected APIs</span></span>

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

#### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->