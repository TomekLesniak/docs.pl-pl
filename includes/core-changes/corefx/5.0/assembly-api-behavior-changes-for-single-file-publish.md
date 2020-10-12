---
ms.openlocfilehash: 0d6847b7a937094f36efae70ae450cc37824221d
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955563"
---
### <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a><span data-ttu-id="34bcc-101">Zmiany zachowania interfejsu API związane z zestawem dla formatu publikowania pojedynczego pliku</span><span class="sxs-lookup"><span data-stu-id="34bcc-101">Assembly-related API behavior changes for single-file publishing format</span></span>

<span data-ttu-id="34bcc-102">Wiele interfejsów API związanych z lokalizacją pliku zestawu ma zmiany zachowania, gdy są wywoływane w formacie publikowania pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="34bcc-102">Multiple APIs related to an assembly's file location have behavior changes when they're invoked in a single-file publishing format.</span></span>

#### <a name="change-description"></a><span data-ttu-id="34bcc-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="34bcc-103">Change description</span></span>

<span data-ttu-id="34bcc-104">W przypadku publikowania jednoplikowego dla programu .NET 5,0 i nowszych wersji zestawy powiązane są ładowane z pamięci zamiast wyodrębniane na dysk.</span><span class="sxs-lookup"><span data-stu-id="34bcc-104">In single-file publishing for .NET 5.0 and later versions, bundled assemblies are loaded from memory instead of extracted to disk.</span></span> <span data-ttu-id="34bcc-105">W przypadku aplikacji publikowanych jednoplikowo oznacza to, że niektóre interfejsy API powiązane z lokalizacją zwracają różne wartości na platformie .NET 5,0 i nowszych niż w poprzednich wersjach programu .NET.</span><span class="sxs-lookup"><span data-stu-id="34bcc-105">For single-file published apps, this means that certain location-related APIs return different values on .NET 5.0 and later than on previous versions of .NET.</span></span> <span data-ttu-id="34bcc-106">Zmiany są następujące:</span><span class="sxs-lookup"><span data-stu-id="34bcc-106">The changes are as follows:</span></span>

| <span data-ttu-id="34bcc-107">Interfejs API</span><span class="sxs-lookup"><span data-stu-id="34bcc-107">API</span></span> | <span data-ttu-id="34bcc-108">Poprzednie wersje</span><span class="sxs-lookup"><span data-stu-id="34bcc-108">Previous versions</span></span> | <span data-ttu-id="34bcc-109">.NET 5,0 i nowsze</span><span class="sxs-lookup"><span data-stu-id="34bcc-109">.NET 5.0 and later</span></span> |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | <span data-ttu-id="34bcc-110">Zwraca wyodrębnioną ścieżkę pliku DLL</span><span class="sxs-lookup"><span data-stu-id="34bcc-110">Returns extracted DLL file path</span></span> | <span data-ttu-id="34bcc-111">Zwraca pusty ciąg dla zestawów w pakiecie</span><span class="sxs-lookup"><span data-stu-id="34bcc-111">Returns empty string for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | <span data-ttu-id="34bcc-112">Zwraca wyodrębnioną ścieżkę pliku DLL</span><span class="sxs-lookup"><span data-stu-id="34bcc-112">Returns extracted DLL file path</span></span> | <span data-ttu-id="34bcc-113">Zgłasza wyjątek dla zestawów w pakiecie</span><span class="sxs-lookup"><span data-stu-id="34bcc-113">Throws exception for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | <span data-ttu-id="34bcc-114">Zwraca `null` dla zestawów w pakiecie</span><span class="sxs-lookup"><span data-stu-id="34bcc-114">Returns `null` for bundled assemblies</span></span> | <span data-ttu-id="34bcc-115">Zgłasza wyjątek dla zestawów w pakiecie</span><span class="sxs-lookup"><span data-stu-id="34bcc-115">Throws exception for bundled assemblies</span></span> |
| `Environment.GetCommandLineArgs()[0]` | <span data-ttu-id="34bcc-116">Wartość to nazwa biblioteki DLL punktu wejścia</span><span class="sxs-lookup"><span data-stu-id="34bcc-116">Value is the name of the entry point DLL</span></span> | <span data-ttu-id="34bcc-117">Wartość jest nazwą pliku wykonywalnego hosta</span><span class="sxs-lookup"><span data-stu-id="34bcc-117">Value is the name of the host executable</span></span> |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | <span data-ttu-id="34bcc-118">Wartość jest katalogiem tymczasowym wyodrębniania</span><span class="sxs-lookup"><span data-stu-id="34bcc-118">Value is the temporary extraction directory</span></span> | <span data-ttu-id="34bcc-119">Wartość jest katalogiem zawierającym plik wykonywalny hosta</span><span class="sxs-lookup"><span data-stu-id="34bcc-119">Value is the containing directory of the host executable</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="34bcc-120">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="34bcc-120">Version introduced</span></span>

<span data-ttu-id="34bcc-121">5,0</span><span class="sxs-lookup"><span data-stu-id="34bcc-121">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="34bcc-122">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="34bcc-122">Recommended action</span></span>

<span data-ttu-id="34bcc-123">Należy unikać zależności między lokalizacją pliku zestawów podczas publikowania jako pojedynczy plik.</span><span class="sxs-lookup"><span data-stu-id="34bcc-123">Avoid dependencies on the file location of assemblies when publishing as a single file.</span></span>

#### <a name="category"></a><span data-ttu-id="34bcc-124">Kategoria</span><span class="sxs-lookup"><span data-stu-id="34bcc-124">Category</span></span>

- <span data-ttu-id="34bcc-125">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="34bcc-125">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="34bcc-126">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="34bcc-126">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
