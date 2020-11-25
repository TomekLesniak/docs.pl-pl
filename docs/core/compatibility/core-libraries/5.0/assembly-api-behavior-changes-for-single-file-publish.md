---
title: 'Istotna zmiana: zmiany zachowania interfejsu API związane z zestawem dla formatu publikowania pojedynczego pliku'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których wiele interfejsów API związanych z lokalizacją pliku zestawu ma zmiany zachowania, gdy są wywoływane w formacie publikowania pojedynczego pliku.
ms.date: 11/01/2020
ms.openlocfilehash: d77e30318040c8298065073a41caab56f2ca3875
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761528"
---
# <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a><span data-ttu-id="4c726-103">Zmiany zachowania interfejsu API związane z zestawem dla formatu publikowania pojedynczego pliku</span><span class="sxs-lookup"><span data-stu-id="4c726-103">Assembly-related API behavior changes for single-file publishing format</span></span>

<span data-ttu-id="4c726-104">Wiele interfejsów API związanych z lokalizacją pliku zestawu ma zmiany zachowania, gdy są wywoływane w formacie publikowania pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="4c726-104">Multiple APIs related to an assembly's file location have behavior changes when they're invoked in a single-file publishing format.</span></span>

## <a name="change-description"></a><span data-ttu-id="4c726-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="4c726-105">Change description</span></span>

<span data-ttu-id="4c726-106">W przypadku publikowania jednoplikowego dla programu .NET 5,0 i nowszych wersji zestawy powiązane są ładowane z pamięci zamiast wyodrębniane na dysk.</span><span class="sxs-lookup"><span data-stu-id="4c726-106">In single-file publishing for .NET 5.0 and later versions, bundled assemblies are loaded from memory instead of extracted to disk.</span></span> <span data-ttu-id="4c726-107">W przypadku aplikacji publikowanych jednoplikowo oznacza to, że niektóre interfejsy API powiązane z lokalizacją zwracają różne wartości na platformie .NET 5,0 i nowszych niż w poprzednich wersjach programu .NET.</span><span class="sxs-lookup"><span data-stu-id="4c726-107">For single-file published apps, this means that certain location-related APIs return different values on .NET 5.0 and later than on previous versions of .NET.</span></span> <span data-ttu-id="4c726-108">Zmiany są następujące:</span><span class="sxs-lookup"><span data-stu-id="4c726-108">The changes are as follows:</span></span>

| <span data-ttu-id="4c726-109">Interfejs API</span><span class="sxs-lookup"><span data-stu-id="4c726-109">API</span></span> | <span data-ttu-id="4c726-110">Poprzednie wersje</span><span class="sxs-lookup"><span data-stu-id="4c726-110">Previous versions</span></span> | <span data-ttu-id="4c726-111">.NET 5,0 i nowsze</span><span class="sxs-lookup"><span data-stu-id="4c726-111">.NET 5.0 and later</span></span> |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | <span data-ttu-id="4c726-112">Zwraca wyodrębnioną ścieżkę pliku DLL</span><span class="sxs-lookup"><span data-stu-id="4c726-112">Returns extracted DLL file path</span></span> | <span data-ttu-id="4c726-113">Zwraca pusty ciąg dla zestawów w pakiecie</span><span class="sxs-lookup"><span data-stu-id="4c726-113">Returns empty string for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | <span data-ttu-id="4c726-114">Zwraca wyodrębnioną ścieżkę pliku DLL</span><span class="sxs-lookup"><span data-stu-id="4c726-114">Returns extracted DLL file path</span></span> | <span data-ttu-id="4c726-115">Zgłasza wyjątek dla zestawów w pakiecie</span><span class="sxs-lookup"><span data-stu-id="4c726-115">Throws exception for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | <span data-ttu-id="4c726-116">Zwraca `null` dla zestawów w pakiecie</span><span class="sxs-lookup"><span data-stu-id="4c726-116">Returns `null` for bundled assemblies</span></span> | <span data-ttu-id="4c726-117">Zgłasza wyjątek dla zestawów w pakiecie</span><span class="sxs-lookup"><span data-stu-id="4c726-117">Throws exception for bundled assemblies</span></span> |
| `Environment.GetCommandLineArgs()[0]` | <span data-ttu-id="4c726-118">Wartość to nazwa biblioteki DLL punktu wejścia</span><span class="sxs-lookup"><span data-stu-id="4c726-118">Value is the name of the entry point DLL</span></span> | <span data-ttu-id="4c726-119">Wartość jest nazwą pliku wykonywalnego hosta</span><span class="sxs-lookup"><span data-stu-id="4c726-119">Value is the name of the host executable</span></span> |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | <span data-ttu-id="4c726-120">Wartość jest katalogiem tymczasowym wyodrębniania</span><span class="sxs-lookup"><span data-stu-id="4c726-120">Value is the temporary extraction directory</span></span> | <span data-ttu-id="4c726-121">Wartość jest katalogiem zawierającym plik wykonywalny hosta</span><span class="sxs-lookup"><span data-stu-id="4c726-121">Value is the containing directory of the host executable</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="4c726-122">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="4c726-122">Version introduced</span></span>

<span data-ttu-id="4c726-123">5,0</span><span class="sxs-lookup"><span data-stu-id="4c726-123">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4c726-124">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="4c726-124">Recommended action</span></span>

<span data-ttu-id="4c726-125">Należy unikać zależności między lokalizacją pliku zestawów podczas publikowania jako pojedynczy plik.</span><span class="sxs-lookup"><span data-stu-id="4c726-125">Avoid dependencies on the file location of assemblies when publishing as a single file.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4c726-126">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="4c726-126">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
