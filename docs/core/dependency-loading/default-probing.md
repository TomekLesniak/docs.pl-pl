---
title: Domyślna sondowanie — .NET Core
description: Omówienie elementu System. Runtime. Loader. AssemblyLoadContext. default sondowania w celu lokalizowania zależności.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 13ce4c7de5f6ce1b76b2e61db810c0f19717540f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608415"
---
# <a name="default-probing"></a><span data-ttu-id="1b3c6-103">Domyślna sonda</span><span class="sxs-lookup"><span data-stu-id="1b3c6-103">Default probing</span></span>

<span data-ttu-id="1b3c6-104"><xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>Wystąpienie jest odpowiedzialne za lokalizowanie zależności zestawu.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="1b3c6-105">W tym artykule opisano <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> logikę sondowania wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="1b3c6-106">Host skonfigurował właściwości sondowania</span><span class="sxs-lookup"><span data-stu-id="1b3c6-106">Host configured probing properties</span></span>

<span data-ttu-id="1b3c6-107">Po uruchomieniu środowiska uruchomieniowego host środowiska uruchomieniowego udostępnia zestaw nazwanych właściwości, które konfigurują <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> ścieżki sondy.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="1b3c6-108">Każda właściwość sondowania jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-108">Each probing property is optional.</span></span> <span data-ttu-id="1b3c6-109">Jeśli jest obecny, Każda właściwość jest wartością ciągu, która zawiera rozdzielaną listę ścieżek bezwzględnych.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="1b3c6-110">Ogranicznik to ";" w systemie Windows i ":" na wszystkich innych platformach.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="1b3c6-111">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="1b3c6-111">Property Name</span></span>                 |<span data-ttu-id="1b3c6-112">Opis</span><span class="sxs-lookup"><span data-stu-id="1b3c6-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="1b3c6-113">Lista ścieżek plików zestawu platformy i aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="1b3c6-114">Lista ścieżek katalogów do wyszukiwania zestawów zasobów satelity.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="1b3c6-115">Lista ścieżek katalogów do wyszukiwania niezarządzanych (natywnych) bibliotek.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="1b3c6-116">Lista ścieżek katalogów do wyszukiwania zestawów zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="1b3c6-117">Lista ścieżek katalogów do wyszukiwania natywnych obrazów zestawów zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="1b3c6-118">Jak są wypełniane właściwości?</span><span class="sxs-lookup"><span data-stu-id="1b3c6-118">How are the properties populated?</span></span>

<span data-ttu-id="1b3c6-119">Istnieją dwa główne scenariusze wypełniania właściwości w zależności od tego, czy \* \<myapp>.deps.jsw\* pliku istnieje.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="1b3c6-120">Gdy \* \*.deps.jsw\* pliku jest obecny, jest analizowany w celu wypełnienia właściwości sondowania.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="1b3c6-121">Gdy \* \*.deps.jsw\* pliku nie istnieje, zakłada się, że katalog aplikacji zawiera wszystkie zależności.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="1b3c6-122">Zawartość katalogu służy do wypełniania właściwości sondowania.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="1b3c6-123">Ponadto \* \*.deps.jsw\* plikach dla dowolnych struktur, do których istnieją odwołania, są podobnie analizowane.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="1b3c6-124">Na koniec zmienna środowiskowa `ADDITIONAL_DEPS` może służyć do dodawania dodatkowych zależności.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>  <span data-ttu-id="1b3c6-125">`dotnet.exe` zawiera również `--additional-deps` opcjonalny parametr, aby ustawić tę wartość przy uruchamianiu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-125">`dotnet.exe` also contains an `--additional-deps` optional parameter to set this value on application startup.</span></span>

<span data-ttu-id="1b3c6-126">`APP_PATHS`Właściwości i `APP_NI_PATHS` nie są domyślnie wypełniane i pomijane w przypadku większości aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-126">The `APP_PATHS` and `APP_NI_PATHS` properties are not populated by default and are omitted for most applications.</span></span>

<span data-ttu-id="1b3c6-127">Do listy wszystkich \* \*.deps.js\* plików używanych w aplikacji można uzyskać dostęp za pośrednictwem programu `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")` .</span><span class="sxs-lookup"><span data-stu-id="1b3c6-127">The list of all *\*.deps.json* files used by the application can be accessed via `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")`.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="1b3c6-128">Jak mogę wyświetlić właściwości sondowania z kodu zarządzanego?</span><span class="sxs-lookup"><span data-stu-id="1b3c6-128">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="1b3c6-129">Każda właściwość jest dostępna przez wywołanie <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> funkcji z nazwą właściwości z powyższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-129">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="1b3c6-130">Jak mogę debugować konstrukcję właściwości sondowania?</span><span class="sxs-lookup"><span data-stu-id="1b3c6-130">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="1b3c6-131">Host środowiska uruchomieniowego platformy .NET Core będzie wyprowadzać przydatne komunikaty śledzenia, gdy są włączone pewne zmienne środowiskowe:</span><span class="sxs-lookup"><span data-stu-id="1b3c6-131">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="1b3c6-132">Zmienna środowiskowa</span><span class="sxs-lookup"><span data-stu-id="1b3c6-132">Environment Variable</span></span>        |<span data-ttu-id="1b3c6-133">Opis</span><span class="sxs-lookup"><span data-stu-id="1b3c6-133">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="1b3c6-134">Włącza śledzenie.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-134">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="1b3c6-135">Ślady do ścieżki pliku zamiast wartości domyślnej `stderr` .</span><span class="sxs-lookup"><span data-stu-id="1b3c6-135">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="1b3c6-136">Ustawia poziom szczegółowości od 1 (najniższy) do 4 (najwyższy).</span><span class="sxs-lookup"><span data-stu-id="1b3c6-136">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="1b3c6-137">Domyślna sondowanie zestawu zarządzanego</span><span class="sxs-lookup"><span data-stu-id="1b3c6-137">Managed assembly default probing</span></span>

<span data-ttu-id="1b3c6-138">Podczas sondowania w celu zlokalizowania zestawu zarządzanego <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> wygląd wygląda następująco:</span><span class="sxs-lookup"><span data-stu-id="1b3c6-138">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="1b3c6-139">Pliki pasujące do programu <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> `TRUSTED_PLATFORM_ASSEMBLIES` (po usunięciu rozszerzeń plików).</span><span class="sxs-lookup"><span data-stu-id="1b3c6-139">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="1b3c6-140">Pliki zestawu obrazów natywnych w programie `APP_NI_PATHS` ze wspólnymi rozszerzeniami plików.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-140">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="1b3c6-141">Pliki zestawów w programie `APP_PATHS` ze wspólnymi rozszerzeniami plików.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-141">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="1b3c6-142">Sonda zestawu (zasobów) dla satelity</span><span class="sxs-lookup"><span data-stu-id="1b3c6-142">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="1b3c6-143">Aby znaleźć zestaw satelicki dla określonej kultury, należy utworzyć zestaw ścieżek plików.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-143">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="1b3c6-144">Dla każdej ścieżki w, `PLATFORM_RESOURCE_ROOTS` a następnie `APP_PATHS` Dołącz <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> ciąg, separator katalogu, <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> ciąg i rozszerzenie ". dll".</span><span class="sxs-lookup"><span data-stu-id="1b3c6-144">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="1b3c6-145">Jeśli istnieje odpowiedni plik, spróbuj załadować i zwrócić go.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-145">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="1b3c6-146">Badanie biblioteki niezarządzanej (natywnej)</span><span class="sxs-lookup"><span data-stu-id="1b3c6-146">Unmanaged (native) library probing</span></span>

<span data-ttu-id="1b3c6-147">Podczas sondowania w celu zlokalizowania biblioteki niezarządzanej `NATIVE_DLL_SEARCH_DIRECTORIES` są one przeszukiwane w poszukiwaniu zgodnej biblioteki.</span><span class="sxs-lookup"><span data-stu-id="1b3c6-147">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>
