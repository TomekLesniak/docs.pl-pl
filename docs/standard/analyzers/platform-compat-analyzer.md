---
title: Analizator zgodności platformy
description: Analizator Roslyn, który może pomóc w wykrywaniu problemów ze zgodnością platformy w aplikacjach i bibliotekach dla wielu platform.
author: buyaa-n
ms.date: 09/17/2020
ms.openlocfilehash: 4e842e5bbe90dd5006d9b27d0365f908b6441997
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406604"
---
# <a name="platform-compatibility-analyzer"></a><span data-ttu-id="90d68-103">Analizator zgodności platformy</span><span class="sxs-lookup"><span data-stu-id="90d68-103">Platform compatibility analyzer</span></span>

<span data-ttu-id="90d68-104">Prawdopodobnie przesłuchasz motto "jeden .NET": pojedynczej, ujednoliconej platformy do tworzenia aplikacji dowolnego typu.</span><span class="sxs-lookup"><span data-stu-id="90d68-104">You've probably heard the motto of "One .NET": a single, unified platform for building any type of application.</span></span> <span data-ttu-id="90d68-105">Zestaw SDK programu .NET 5,0 zawiera ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin i ML.NET, a także doda obsługę większej liczby platform w czasie.</span><span class="sxs-lookup"><span data-stu-id="90d68-105">The .NET 5.0 SDK includes ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin, and ML.NET, and will add support for more platforms over time.</span></span> <span data-ttu-id="90d68-106">Program .NET 5,0 dokłada starań, aby zapewnić środowisko, w którym nie trzeba mieć powodów dotyczących różnych wersji platformy .NET, ale nie próbuje w pełni abstrakcji bazowego systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="90d68-106">.NET 5.0 strives to provide an experience where you don't have to reason about the different flavors of .NET, but doesn't attempt to fully abstract away the underlying operating system (OS).</span></span> <span data-ttu-id="90d68-107">Nadal będziesz mieć możliwość wywoływania interfejsów API specyficznych dla platformy, na przykład P/Invoke, WinRT lub powiązań Xamarin dla systemów iOS i Android.</span><span class="sxs-lookup"><span data-stu-id="90d68-107">You'll continue to be able to call platform-specific APIs, for example, P/Invokes, WinRT, or the Xamarin bindings for iOS and Android.</span></span>

<span data-ttu-id="90d68-108">Jednak używanie interfejsów API specyficznych dla platformy na składniku oznacza, że kod nie działa już na wszystkich platformach.</span><span class="sxs-lookup"><span data-stu-id="90d68-108">But using platform-specific APIs on a component means the code no longer works across all platforms.</span></span> <span data-ttu-id="90d68-109">Potrzebujemy sposobu na wykrycie tego rozwiązania w czasie projektowania, aby deweloperzy mogli uzyskać diagnostykę, gdy przypadkowo używają interfejsów API specyficznych dla platformy.</span><span class="sxs-lookup"><span data-stu-id="90d68-109">We needed a way to detect this at design time so developers get diagnostics when they inadvertently use platform-specific APIs.</span></span> <span data-ttu-id="90d68-110">Aby osiągnąć ten cel, w programie .NET 5,0 wprowadzono [analizatora zgodności platformy](/visualstudio/code-quality/ca1416) i uzupełniające się interfejsy API, które ułatwiają deweloperom identyfikowanie i Używanie interfejsów API specyficznych dla platformy w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="90d68-110">To achieve this goal, .NET 5.0 introduces the [platform compatibility analyzer](/visualstudio/code-quality/ca1416) and complementary APIs to help developers identify and use platform-specific APIs where appropriate.</span></span>
<span data-ttu-id="90d68-111">Nowe interfejsy API obejmują:</span><span class="sxs-lookup"><span data-stu-id="90d68-111">The new APIs include:</span></span>

- <span data-ttu-id="90d68-112"><xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> Dodawanie adnotacji do interfejsów API jako specyficznych dla platformy i <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> Dodawanie adnotacji do interfejsów API jako nieobsługiwanych w określonym systemie operacyjnym.</span><span class="sxs-lookup"><span data-stu-id="90d68-112"><xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> to annotate APIs as being platform-specific and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> to annotate APIs as being unsupported on a particular OS.</span></span> <span data-ttu-id="90d68-113">Te atrybuty mogą opcjonalnie zawierać numer wersji i zostały już zastosowane do niektórych interfejsów API specyficznych dla platformy w podstawowych bibliotekach platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="90d68-113">These attributes can optionally include the version number, and have already been applied to some platform-specific APIs in the core .NET libraries.</span></span>
- <span data-ttu-id="90d68-114">`Is<Platform>()` i `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` metody statyczne w <xref:System.OperatingSystem?displayProperty=nameWithType> klasie w celu bezpiecznego wywoływania interfejsów API specyficznych dla platformy.</span><span class="sxs-lookup"><span data-stu-id="90d68-114">`Is<Platform>()` and `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` static methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class for safely calling platform-specific APIs.</span></span> <span data-ttu-id="90d68-115">Na przykład <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> może służyć do ochrony wywołania interfejsu API specyficznego dla systemu Windows, a <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType> () może służyć do ochrony wywołania interfejsu API specyficznego dla systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="90d68-115">For example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> can be used to guard a call to a Windows-specific API, and <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>() can be used to guard a versioned Windows-specific API call.</span></span> <span data-ttu-id="90d68-116">Zapoznaj się z tymi [przykładami](#guard-platform-specific-apis-with-guard-methods) , jak te metody mogą być używane jako osłony odwołań do interfejsów API specyficznych dla platformy.</span><span class="sxs-lookup"><span data-stu-id="90d68-116">See these [examples](#guard-platform-specific-apis-with-guard-methods) of how these methods can be used as guards of platform-specific API references.</span></span>

> [!TIP]
> <span data-ttu-id="90d68-117">Analizator zgodności platformy uaktualnia i zastępuje funkcję [odnajdywania problemów między platformami](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) w [analizatorze interfejsu API platformy .NET](../../standard/analyzers/api-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="90d68-117">The platform compatibility analyzer upgrades and replaces the [Discovering cross-platform issues](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) feature of the [.NET API analyzer](../../standard/analyzers/api-analyzer.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="90d68-118">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="90d68-118">Prerequisites</span></span>

<span data-ttu-id="90d68-119">Analizator zgodności platformy jest jednym z Roslynjących analiz jakości kodu.</span><span class="sxs-lookup"><span data-stu-id="90d68-119">The platform compatibility analyzer is one of the Roslyn code quality analyzers.</span></span> <span data-ttu-id="90d68-120">Począwszy od platformy .NET 5,0, analizatory te są [dołączone do zestawu .NET SDK](../../fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="90d68-120">Starting in .NET 5.0, these analyzers are [included with the .NET SDK](../../fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="90d68-121">Analizator zgodności platformy jest domyślnie włączony tylko w przypadku projektów docelowych `net5.0` lub nowszych.</span><span class="sxs-lookup"><span data-stu-id="90d68-121">The platform compatibility analyzer is enabled by default only for projects that target `net5.0` or a later version.</span></span> <span data-ttu-id="90d68-122">Można go jednak [włączyć](/visualstudio/code-quality/ca1416.md#configurability) dla projektów przeznaczonych dla innych platform.</span><span class="sxs-lookup"><span data-stu-id="90d68-122">However, you can [enable](/visualstudio/code-quality/ca1416.md#configurability) it for projects that target other frameworks.</span></span>

## <a name="how-the-analyzer-determines-platform-dependency"></a><span data-ttu-id="90d68-123">Jak Analizator określa zależność platformy</span><span class="sxs-lookup"><span data-stu-id="90d68-123">How the analyzer determines platform dependency</span></span>

- <span data-ttu-id="90d68-124">**Nieprzypisany interfejs API** jest uznawany za działający na **wszystkich platformach systemu operacyjnego**.</span><span class="sxs-lookup"><span data-stu-id="90d68-124">An **unattributed API** is considered to work on **all OS platforms**.</span></span>
- <span data-ttu-id="90d68-125">Interfejs API oznaczony jako with `[SupportedOSPlatform("platform")]` jest traktowany jako przenośny tylko w określonym systemie operacyjnym `platform` .</span><span class="sxs-lookup"><span data-stu-id="90d68-125">An API marked with `[SupportedOSPlatform("platform")]` is considered only portable to the specified OS `platform`.</span></span>
  - <span data-ttu-id="90d68-126">Ten atrybut można zastosować wiele razy, aby wskazać **obsługę wielu platform** ( `[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]` ).</span><span class="sxs-lookup"><span data-stu-id="90d68-126">The attribute can be applied multiple times to indicate **multiple platform support** (`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`).</span></span>
  - <span data-ttu-id="90d68-127">Analizator wyświetli **Ostrzeżenie** , jeśli do interfejsów API specyficznych dla platformy są przywoływane bez odpowiedniego **kontekstu platformy**:</span><span class="sxs-lookup"><span data-stu-id="90d68-127">The analyzer will produce a **warning** if platform-specific APIs are referenced without a proper **platform context**:</span></span>
    - <span data-ttu-id="90d68-128">**Ostrzega** , jeśli projekt nie jest celem obsługiwanej platformy (na przykład wywołania interfejsu API określonego dla systemu Windows i obiektów docelowych projektu `<TargetFramework>net5.0-ios14.0</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="90d68-128">**Warns** if the project doesn't target the supported platform (for example, a Windows-specific API call and the project targets `<TargetFramework>net5.0-ios14.0</TargetFramework>`).</span></span>
    - <span data-ttu-id="90d68-129">**Ostrzega** , jeśli projekt jest przeznaczony do wielowymiarowego ( `<TargetFramework>net5.0</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="90d68-129">**Warns** if the project is multi-targeted (`<TargetFramework>net5.0</TargetFramework>`).</span></span>
    - <span data-ttu-id="90d68-130">**Nie ostrzega** o tym, czy w ramach projektu, który jest przeznaczony dla określonych **platform** (na przykład dla wywołania interfejsu API określonego dla systemu Windows i elementów docelowych projektu), jest przywoływany interfejs API specyficzny dla platformy `<TargetFramework>net5.0-windows</TargetFramework>` .</span><span class="sxs-lookup"><span data-stu-id="90d68-130">**Doesn't warn** if the platform-specific API is referenced within a project that targets any of the **specified platforms** (for example, for a Windows-specific API call and the project targets `<TargetFramework>net5.0-windows</TargetFramework>`).</span></span>
    - <span data-ttu-id="90d68-131">**Nie ostrzega** , jeśli wywołanie interfejsu API specyficzne dla platformy jest chronione przez odpowiednie metody sprawdzania platformy (na przykład `if(OperatingSystem.IsWindows())` ).</span><span class="sxs-lookup"><span data-stu-id="90d68-131">**Doesn't warn** if the platform-specific API call is guarded by corresponding platform-check methods (for example, `if(OperatingSystem.IsWindows())`).</span></span>
    - <span data-ttu-id="90d68-132">**Nie ostrzega** , jeśli interfejs API specyficzny dla platformy jest przywoływany z tego samego kontekstu specyficznego dla platformy (**połączenie jest również przypisane** do `[SupportedOSPlatform("platform")` ).</span><span class="sxs-lookup"><span data-stu-id="90d68-132">**Doesn't warn** if the platform-specific API is referenced from the same platform-specific context (**call site also attributed** with `[SupportedOSPlatform("platform")`).</span></span>
- <span data-ttu-id="90d68-133">Interfejs API oznaczony za pomocą `[UnsupportedOSPlatform("platform")]` jest uznawany za nieobsługiwany tylko w określonym systemie operacyjnym, `platform` ale jest obsługiwany przez wszystkie inne platformy.</span><span class="sxs-lookup"><span data-stu-id="90d68-133">An API marked with `[UnsupportedOSPlatform("platform")]` is considered unsupported only on the specified OS `platform` but supported for all other platforms.</span></span>
  - <span data-ttu-id="90d68-134">Ten atrybut może być stosowany wiele razy z różnymi platformami, na przykład `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]` .</span><span class="sxs-lookup"><span data-stu-id="90d68-134">The attribute can be applied multiple times with different platforms, for example, `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`.</span></span>
  - <span data-ttu-id="90d68-135">Analizator generuje **Ostrzeżenie** tylko wtedy, gdy `platform` jest skuteczny dla witryny wywołania:</span><span class="sxs-lookup"><span data-stu-id="90d68-135">The analyzer produces a **warning** only if the `platform` is effective for the call site:</span></span>
    - <span data-ttu-id="90d68-136">**Ostrzega** , jeśli projekt jest przeznaczony dla platformy, która jest przypisana jako nieobsługiwana (na przykład jeśli interfejs API jest przypisany do `[UnsupportedOSPlatform("windows")]` i dla obiektów docelowych lokacji wywołania `<TargetFramework>net5.0-windows</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="90d68-136">**Warns** if the project targets the platform that's attributed as unsupported (for example, if the API is attributed with `[UnsupportedOSPlatform("windows")]` and the call site targets `<TargetFramework>net5.0-windows</TargetFramework>`).</span></span>
    - <span data-ttu-id="90d68-137">**Ostrzega** o tym, czy projekt jest przeznaczony do wielowymiarowego i `platform` znajduje się w domyślnej grupie elementów programu [ `<SupportedPlatform>` MSBuild](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) , czy też `platform` jest zawarty ręcznie w `MSBuild` \<SupportedPlatform> grupie Items:</span><span class="sxs-lookup"><span data-stu-id="90d68-137">**Warns** if the project is multi-targeted and the `platform` is included in the default [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) items group, or the `platform` is manually included within the `MSBuild` \<SupportedPlatform> items group:</span></span>

      ```XML
      <ItemGroup>
          <SupportedPlatform Include="platform" />
      </ItemGroup>
      ```

    - <span data-ttu-id="90d68-138">**Nie ostrzega** w przypadku kompilowania aplikacji, która nie jest przeznaczona dla nieobsługiwanej platformy lub ma wiele obiektów docelowych, a platforma nie jest uwzględniona w domyślnej grupie elementów programu [MSBuild `<SupportedPlatform>` ](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) .</span><span class="sxs-lookup"><span data-stu-id="90d68-138">**Doesn't warn** if you're building an app that doesn't target the unsupported platform or is multi-targeted and the platform is not included in the default [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) items group.</span></span>
- <span data-ttu-id="90d68-139">Oba atrybuty mogą być tworzone z numerami wersji lub bez nich w ramach nazwy platformy.</span><span class="sxs-lookup"><span data-stu-id="90d68-139">Both attributes can be instantiated with or without version numbers as part of the platform name.</span></span>
  - <span data-ttu-id="90d68-140">Numery wersji są `major.minor[.build[.revision]]` `major.minor` wymagane, a `build` `revision` części i są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="90d68-140">Version numbers are in the format of `major.minor[.build[.revision]]`; `major.minor` is required and the `build` and `revision` parts are optional.</span></span> <span data-ttu-id="90d68-141">Na przykład "system Windows 7.0" wskazuje system Windows w wersji 7,0, ale "Windows" jest interpretowany jako Windows 0,0.</span><span class="sxs-lookup"><span data-stu-id="90d68-141">For example, "Windows7.0" indicates Windows version 7.0, but "Windows" is interpreted as Windows 0.0.</span></span>

<span data-ttu-id="90d68-142">Aby uzyskać więcej informacji, zobacz [przykłady działania atrybutów i ich przyczyny](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).</span><span class="sxs-lookup"><span data-stu-id="90d68-142">For more information, see [examples of how the attributes work and what diagnostics they cause](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).</span></span>

### <a name="advanced-scenarios-for-combining-attributes"></a><span data-ttu-id="90d68-143">Zaawansowane scenariusze łączenia atrybutów</span><span class="sxs-lookup"><span data-stu-id="90d68-143">Advanced scenarios for combining attributes</span></span>

- <span data-ttu-id="90d68-144">Jeśli istnieją kombinacje `[SupportedOSPlatform]` i `[UnsupportedOSPlatform]` atrybuty, wszystkie atrybuty są pogrupowane według identyfikatora platformy systemu operacyjnego:</span><span class="sxs-lookup"><span data-stu-id="90d68-144">If a combination of `[SupportedOSPlatform]` and `[UnsupportedOSPlatform]` attributes are present, all attributes are grouped by OS platform identifier:</span></span>
  - <span data-ttu-id="90d68-145">**Tylko obsługiwana lista**.</span><span class="sxs-lookup"><span data-stu-id="90d68-145">**Supported only list**.</span></span> <span data-ttu-id="90d68-146">Jeśli najniższa wersja dla każdej platformy systemu operacyjnego jest `[SupportedOSPlatform]` atrybutem, interfejs API jest uznawany za obsługiwany przez wymienione platformy i nieobsługiwany przez wszystkie inne platformy.</span><span class="sxs-lookup"><span data-stu-id="90d68-146">If the lowest version for each OS platform is a `[SupportedOSPlatform]` attribute, the API is considered to only be supported by the listed platforms and unsupported by all other platforms.</span></span> <span data-ttu-id="90d68-147">Atrybuty opcjonalne `[UnsupportedOSPlatform]` dla każdej platformy mogą mieć tylko wyższą wersję minimalnej obsługiwanej wersji, co oznacza, że interfejs API zostanie usunięty od określonej wersji.</span><span class="sxs-lookup"><span data-stu-id="90d68-147">The optional `[UnsupportedOSPlatform]` attributes for each platform can only have higher version of the minimum supported version, which denotes that the API is removed starting from the specified version.</span></span>

    ```csharp
    // The API only supported on Windows 8.0 and later, not supported for all other.
    // The API is removed/unsupported from version 10.0.19041.0.
    [SupportedOSPlatform("windows8.0")]
    [UnsupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows80SupportFromCertainVersion();
    ```

  - <span data-ttu-id="90d68-148">**Nieobsługiwana lista**.</span><span class="sxs-lookup"><span data-stu-id="90d68-148">**Unsupported only list**.</span></span> <span data-ttu-id="90d68-149">Jeśli najniższa wersja dla każdej platformy systemu operacyjnego jest `[UnsupportedOSPlatform]` atrybutem, interfejs API jest uznawany za nieobsługiwany przez wymienione platformy i obsługiwany przez wszystkie inne platformy.</span><span class="sxs-lookup"><span data-stu-id="90d68-149">If the lowest version for each OS platform is an `[UnsupportedOSPlatform]` attribute, then the API is considered to only be unsupported by the listed platforms and supported by all other platforms.</span></span> <span data-ttu-id="90d68-150">Lista może mieć `[SupportedOSPlatform]` atrybut o tej samej platformie, ale wyższej wersji, co oznacza, że interfejs API jest obsługiwany w tej wersji.</span><span class="sxs-lookup"><span data-stu-id="90d68-150">The list could have `[SupportedOSPlatform]` attribute with the same platform but a higher version, which denotes that the API is supported starting from that version.</span></span>
  
    ```csharp
    // The API was unsupported on Windows until version 10.0.19041.0.
    // The API is considered supported everywhere else without constraints.
    [UnsupportedOSPlatform("windows")]
    [SupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows8UnsupportFromWindows10();
    ```

  - <span data-ttu-id="90d68-151">**Niespójna lista**.</span><span class="sxs-lookup"><span data-stu-id="90d68-151">**Inconsistent list**.</span></span> <span data-ttu-id="90d68-152">Jeśli najniższa wersja dla niektórych platform jest inna niż w przypadku `[SupportedOSPlatform]` `[UnsupportedOSPlatform]` innych platform, jest traktowana jako niespójna, co nie jest obsługiwane przez analizator.</span><span class="sxs-lookup"><span data-stu-id="90d68-152">If the lowest version for some platforms is `[SupportedOSPlatform]` while it is `[UnsupportedOSPlatform]` for other platforms, is considered inconsistent, which is not supported for the analyzer.</span></span>
  - <span data-ttu-id="90d68-153">Jeśli najmniejsze wersje `[SupportedOSPlatform]` i `[UnsupportedOSPlatform]` atrybuty są równe, Analizator traktuje platformę jako część **obsługiwanej listy**.</span><span class="sxs-lookup"><span data-stu-id="90d68-153">If the lowest versions of `[SupportedOSPlatform]` and `[UnsupportedOSPlatform]` attributes are equal, the analyzer considers the platform as part of the **Supported only list**.</span></span>
- <span data-ttu-id="90d68-154">Atrybuty platformy można stosować do typów, elementów członkowskich (metod, pól, właściwości i zdarzeń) i zestawów z inną nazwą platformy i/lub wersją.</span><span class="sxs-lookup"><span data-stu-id="90d68-154">Platform attributes can be applied to types, members (methods, fields, properties, and events) and assemblies with different platform name and / or version.</span></span>
  - <span data-ttu-id="90d68-155">Atrybuty zastosowane na najwyższym poziomie `target` mają wpływ na wszystkie jej składowe i typy.</span><span class="sxs-lookup"><span data-stu-id="90d68-155">Attributes applied at the top level `target` affect all of its members and types.</span></span>
  - <span data-ttu-id="90d68-156">Atrybuty poziomu podrzędnego są stosowane tylko wtedy, gdy są zgodne z regułą "adnotacje potomne mogą zawęzić obsługę platform, ale nie mogą ich poszerzyć".</span><span class="sxs-lookup"><span data-stu-id="90d68-156">Child level attributes only apply if they adhere to the rule "child annotations can narrow the platforms support, but they cannot widen it".</span></span>
    - <span data-ttu-id="90d68-157">Gdy element nadrzędny ma **obsługiwaną tylko** listę, a następnie podrzędne atrybuty elementu członkowskiego nie mogą dodać nowej obsługi platformy, która mogłaby rozszerzać wsparcie nadrzędne, Nowa obsługa platformy może zostać dodana tylko do samego siebie.</span><span class="sxs-lookup"><span data-stu-id="90d68-157">When parent has **Supported only** list, then child member attributes could not add a new platform support as that would be extending parent support, a new platform support can only added to the parent itself.</span></span> <span data-ttu-id="90d68-158">Ale może mieć `Supported` atrybut dla tej samej platformy z nowszymi wersjami, co spowoduje zawężenie obsługi.</span><span class="sxs-lookup"><span data-stu-id="90d68-158">But it can have `Supported` attribute for same platform with later versions as that will narrow the support.</span></span> <span data-ttu-id="90d68-159">Ponadto może mieć `Unsupported` atrybut o tej samej platformie, co spowoduje również zawężenie nadrzędnego wsparcia.</span><span class="sxs-lookup"><span data-stu-id="90d68-159">Also it can have `Unsupported` attribute with same platform as that will also narrow parent support.</span></span>
    - <span data-ttu-id="90d68-160">Gdy element nadrzędny ma **nieobsługiwaną** listę, wówczas atrybuty elementu członkowskiego podrzędnego mogą dodać nową obsługę platformy, która spowodowałaby zawężenie obsługi nadrzędnej, ale nie może mieć `Supported` atrybutu dla tej samej platformy jak w elemencie nadrzędnym, który mógłby zwiększyć obsługę elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="90d68-160">When parent has **Unsupported only** list, then child member attributes could add a new platform support as that would be narrowing parent support, but it cannot have `Supported` attribute for same platform as in the parent, that would extend parent support.</span></span> <span data-ttu-id="90d68-161">Pomoc techniczną dla tej samej platformy można dodać tylko do poziomu nadrzędnego, w którym `Unsupported` zastosowano oryginalny atrybut.</span><span class="sxs-lookup"><span data-stu-id="90d68-161">Support for the same platform can be added only to parent level where the original `Unsupported` attribute applied.</span></span>
  - <span data-ttu-id="90d68-162">Jeśli `[SupportedOSPlatform("platformVersion")]` zastosowano więcej niż jeden raz dla interfejsu API o tej samej `platform` nazwie tylko ten z minimalną wersją jest uznawany przez analizatora.</span><span class="sxs-lookup"><span data-stu-id="90d68-162">If `[SupportedOSPlatform("platformVersion")]` is applied more than once for an API with the same `platform` name only the one with minimum version is considered by the analyzer.</span></span>
  - <span data-ttu-id="90d68-163">Jeśli `[UnsupportedOSPlatform("platformVersion")]` zastosowano więcej niż dwa razy dla interfejsu API o tej samej `platform` nazwie, Analizator jest traktowany jako tylko dwa z najwcześniejszymi wersjami.</span><span class="sxs-lookup"><span data-stu-id="90d68-163">If `[UnsupportedOSPlatform("platformVersion")]` is applied more than twice for an API with the same `platform` name, only the two with earliest versions are considered by the analyzer.</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="90d68-164">Nie oczekuje się, że interfejs API, który był obsługiwany początkowo, ale nie jest obsługiwany (usunięty) w nowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="90d68-164">An API that was supported initially but unsupported (removed) in a later version is not expected to get resupported in an even later version.</span></span>

### <a name="examples-of-how-the-attributes-work-and-what-diagnostics-they-produce"></a><span data-ttu-id="90d68-165">Przykłady działania atrybutów i ich diagnostyki</span><span class="sxs-lookup"><span data-stu-id="90d68-165">Examples of how the attributes work and what diagnostics they produce</span></span>

  ```csharp
  // An API supported only on Windows.
  [SupportedOSPlatform("Windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  public void Caller()
  {
      WindowsOnlyApi(); // warns: 'WindowsOnlyApi' is supported on 'windows'

      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Windows'
      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Linux'
      SupportedOnWindowsAndLinuxOnly();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 8.0 and later  
      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // for same platform analyzer only warn for the latest version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  public void Caller2()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'android'

      // warns:'StartedWindowsSupportFromVersion8' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFromVersion8' is supported on 'windows' 8.0 and later
      StartedWindowsSupportFromVersion8();

      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is supported on 'windows' 8.0 and later
      // even there were 3 diagnostics found analyzer warn only for the first 2.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

## <a name="handle-reported-warnings"></a><span data-ttu-id="90d68-166">Obsługa ostrzeżeń raportowanych</span><span class="sxs-lookup"><span data-stu-id="90d68-166">Handle reported warnings</span></span>

<span data-ttu-id="90d68-167">Zalecanym sposobem postępowania z tą diagnostyką jest upewnienie się, że interfejsy API specyficzne dla platformy są wywoływane tylko w przypadku uruchamiania na odpowiedniej platformie.</span><span class="sxs-lookup"><span data-stu-id="90d68-167">The recommended way to deal with these diagnostics is to make sure you only call platform-specific APIs when running on an appropriate platform.</span></span> <span data-ttu-id="90d68-168">Poniżej przedstawiono opcje, których można użyć do rozwiązywania ostrzeżeń; Wybierz opcję, która jest najbardziej odpowiednia dla danej sytuacji:</span><span class="sxs-lookup"><span data-stu-id="90d68-168">Following are the options you can use to address the warnings; choose whichever is most appropriate for your situation:</span></span>

- <span data-ttu-id="90d68-169">**Ochrona wywołania**.</span><span class="sxs-lookup"><span data-stu-id="90d68-169">**Guard the call**.</span></span> <span data-ttu-id="90d68-170">Można to osiągnąć, warunkowo wywołując kod w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="90d68-170">You can achieve this by conditionally calling the code at run time.</span></span> <span data-ttu-id="90d68-171">Sprawdź, czy pracujesz w żądanym `Platform` miejscu przy użyciu jednej z metod sprawdzania platformy, na przykład `OperatingSystem.Is<Platform>()` lub `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` .</span><span class="sxs-lookup"><span data-stu-id="90d68-171">Check whether you’re running on a desired `Platform` by using one of platform-check methods, for example, `OperatingSystem.Is<Platform>()` or `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`.</span></span>

- <span data-ttu-id="90d68-172">**Oznacz lokację wywołania jako specyficzną dla platformy**.</span><span class="sxs-lookup"><span data-stu-id="90d68-172">**Mark the call site as platform-specific**.</span></span> <span data-ttu-id="90d68-173">Możesz także oznaczyć własne interfejsy API jako charakterystyczne dla danej platformy, co skutecznie tylko przekazuje wymagania do obiektów wywołujących.</span><span class="sxs-lookup"><span data-stu-id="90d68-173">You can also choose to mark your own APIs as being platform-specific, thus effectively just forwarding the requirements to your callers.</span></span> <span data-ttu-id="90d68-174">Oznacz zawierającą metodę lub typ lub cały zestaw z tymi samymi atrybutami, co odwołanie zależne od platformy.</span><span class="sxs-lookup"><span data-stu-id="90d68-174">Mark the containing method or type or the entire assembly with the same attributes as the referenced platform-dependent call.</span></span> <span data-ttu-id="90d68-175">[Przykłady](#mark-call-site-as-platform-specific).</span><span class="sxs-lookup"><span data-stu-id="90d68-175">[Examples](#mark-call-site-as-platform-specific).</span></span>

- <span data-ttu-id="90d68-176">**Potwierdź witrynę wywołania przy użyciu sprawdzenia platformy**.</span><span class="sxs-lookup"><span data-stu-id="90d68-176">**Assert the call site with platform check**.</span></span> <span data-ttu-id="90d68-177">Jeśli nie chcesz obciążać dodatkowej `if` instrukcji w czasie wykonywania, użyj <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="90d68-177">If you don't want the overhead of an additional `if` statement at run time, use <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="90d68-178">[Przykład](#assert-the-call-site-with-platform-check).</span><span class="sxs-lookup"><span data-stu-id="90d68-178">[Example](#assert-the-call-site-with-platform-check).</span></span>

- <span data-ttu-id="90d68-179">**Usuń kod**.</span><span class="sxs-lookup"><span data-stu-id="90d68-179">**Delete the code**.</span></span> <span data-ttu-id="90d68-180">Na ogół nie jest to potrzebne, ponieważ oznacza to utratę wierności, gdy kod jest używany przez użytkowników systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="90d68-180">Generally not what you want because it means you lose fidelity when your code is used by Windows users.</span></span> <span data-ttu-id="90d68-181">W przypadku, gdy istnieje alternatywa dla wielu platform, najlepiej jest ją używać w przypadku interfejsów API specyficznych dla platformy.</span><span class="sxs-lookup"><span data-stu-id="90d68-181">For cases where a cross-platform alternative exists, you’re likely better off using that over platform-specific APIs.</span></span>

- <span data-ttu-id="90d68-182">**Pomiń ostrzeżenie**.</span><span class="sxs-lookup"><span data-stu-id="90d68-182">**Suppress the warning**.</span></span> <span data-ttu-id="90d68-183">Można również po prostu pominąć ostrzeżenie, za pośrednictwem editor.config lub `#pragma warning disable ca1416` .</span><span class="sxs-lookup"><span data-stu-id="90d68-183">You can also simply suppress the warning, either via editor.config or `#pragma warning disable ca1416`.</span></span> <span data-ttu-id="90d68-184">Jednak ta opcja powinna być ostatnią możliwością w przypadku korzystania z interfejsów API specyficznych dla platformy.</span><span class="sxs-lookup"><span data-stu-id="90d68-184">However, this option should be a last resort when using platform-specific APIs.</span></span>

### <a name="guard-platform-specific-apis-with-guard-methods"></a><span data-ttu-id="90d68-185">Ochrona interfejsów API specyficznych dla platformy przy użyciu metod Guard</span><span class="sxs-lookup"><span data-stu-id="90d68-185">Guard platform-specific APIs with guard methods</span></span>

<span data-ttu-id="90d68-186">Nazwa platformy metody Guard powinna być zgodna z nazwą platformy interfejsu API zależnej od platformy wywołującej.</span><span class="sxs-lookup"><span data-stu-id="90d68-186">The guard method's platform name should match with the calling platform-dependent API platform name.</span></span> <span data-ttu-id="90d68-187">Jeśli ciąg platformy wywołującego interfejsu API zawiera wersję:</span><span class="sxs-lookup"><span data-stu-id="90d68-187">If the platform string of the calling API includes the version:</span></span>

- <span data-ttu-id="90d68-188">Dla `[SupportedOSPlatform("platformVersion")]` atrybutu platforma metody Guard `version` powinna być większa lub równa platformie wywołującej `Version` .</span><span class="sxs-lookup"><span data-stu-id="90d68-188">For the `[SupportedOSPlatform("platformVersion")]` attribute, the guard method platform `version` should be greater than or equal to the calling platform's `Version`.</span></span>
- <span data-ttu-id="90d68-189">Dla `[UnsupportedOSPlatform("platformVersion")]` atrybutu platforma metody Guard `version` powinna być mniejsza lub równa platformie wywołującej `Version` .</span><span class="sxs-lookup"><span data-stu-id="90d68-189">For the `[UnsupportedOSPlatform("platformVersion")]` attribute, the guard method's platform `version` should be less than or equal to the calling platform's `Version`.</span></span>

  ```csharp
  public void CallingSupportedOnlyApis() // Allow list calls
  {
      if (OperatingSystem.IsWindows())
      {
          WindowsOnlyApi(); // will not warn
      }

      if (OperatingSystem.IsLinux())
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn, within one of the supported context
      }

      // Can use &&, || logical operators to guard combined attributes
      if (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10.0.19041)))
      {
          ApiSupportedFromWindows8UnsupportFromWindows10();
      }

      if (OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903))
      {
          AssemblySupportedOnWindowsApiSupportedFromWindows10(); // Only need to check latest supported version
      }
  }

  public void CallingUnsupportedApis()
  {
      if (!OperatingSystem.IsAndroid())
      {
          DoesNotWorkOnAndroid(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || OperatingSystem.IsWindowsVersionAtLeast(8))
      {
          StartedWindowsSupportFromVersion8(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || // supported all other platforms
         (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903)))
      {
          StartedWindowsSupportFrom8UnsupportedFrom10(); // will not warn
      }
  }
  ```

- <span data-ttu-id="90d68-190">Jeśli musisz chronić kod, który jest przeznaczony dla standardu lub netcoreapp, gdzie nowe <xref:System.OperatingSystem> interfejsy API nie są dostępne <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> , może być używany przez analizator.</span><span class="sxs-lookup"><span data-stu-id="90d68-190">if you need to guard a code that targets netstandard or netcoreapp where new <xref:System.OperatingSystem> APIs are not available <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> API can be used and will be respected by the analyzer.</span></span> <span data-ttu-id="90d68-191">Ale nie jest tak zoptymalizowany jak nowe interfejsy API dodane w programie <xref:System.OperatingSystem> .</span><span class="sxs-lookup"><span data-stu-id="90d68-191">But it's not as optimized as the new APIs added in <xref:System.OperatingSystem>.</span></span> <span data-ttu-id="90d68-192">W przypadku, gdy platforma nie jest obsługiwana w <xref:System.Runtime.InteropServices.OSPlatform> strukturze, można użyć <xref:System.Runtime.InteropServices.OSPlatform.Create%2A?displayProperty=nameWithType> ("platforma"), która jest również przestrzegana przez analizator.</span><span class="sxs-lookup"><span data-stu-id="90d68-192">In case the platform is not supported in <xref:System.Runtime.InteropServices.OSPlatform> struct, you can use <xref:System.Runtime.InteropServices.OSPlatform.Create%2A?displayProperty=nameWithType>("platform") which is also respected by the analyzer.</span></span>

  ```csharp
  public void CallingSupportedOnlyApis()
  {
      if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn
      }

      if (RuntimeInformation.IsOSPlatform(OSPlatform.Create("browser")))
      {
          ApiOnlySupportedOnBrowser(); // call of browser specific API
      }
  }
  ```

### <a name="mark-call-site-as-platform-specific"></a><span data-ttu-id="90d68-193">Oznacz lokację wywołania jako specyficzną dla platformy</span><span class="sxs-lookup"><span data-stu-id="90d68-193">Mark call site as platform-specific</span></span>

<span data-ttu-id="90d68-194">Nazwy platform powinny być zgodne z interfejsem API zależnym od platformy wywołującej.</span><span class="sxs-lookup"><span data-stu-id="90d68-194">Platform names should match the calling platform-dependent API.</span></span> <span data-ttu-id="90d68-195">Jeśli ciąg platformy zawiera wersję:</span><span class="sxs-lookup"><span data-stu-id="90d68-195">If the platform string includes a version:</span></span>

- <span data-ttu-id="90d68-196">Dla `[SupportedOSPlatform("platformVersion")]` atrybutu platforma lokacji wywołania `version` powinna być większa lub równa platformie wywołującej `Version`</span><span class="sxs-lookup"><span data-stu-id="90d68-196">For the `[SupportedOSPlatform("platformVersion")]` attribute, the call site platform `version` should be greater than or equal to the calling platform's `Version`</span></span>
- <span data-ttu-id="90d68-197">Dla `[UnsupportedOSPlatform("platformVersion")]` atrybutu platforma lokacji wywołania `version` powinna być mniejsza lub równa platformie wywołującej `Version`</span><span class="sxs-lookup"><span data-stu-id="90d68-197">For the `[UnsupportedOSPlatform("platformVersion")]` attribute, the call site platform `version` should be less than or equal to the calling platform's `Version`</span></span>

  ```csharp
  // an API supported only on Windows.
  [SupportedOSPlatform("windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  [SupportedOSPlatform("windows8.0")] // call site attributed Windows 8.0 or above.
  public void Caller()
  {
      WindowsOnlyApi(); // will not warn as call site is for Windows.

      // will not warn as call site is for Windows.
      SupportedOnWindowsAndLinuxOnly();

      // will not warn for the API's [SupportedOSPlatform("windows8.0")] attribute.
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // as the call site version is lower than calling version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows11.0")] // call site attributed with windows 11.0 or above.
  public void Caller2()
  {
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // will not warn as call site version higher than calling API.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")] // call site supports Windows from version 8.0 to 10.0.19041.0.
  public void Caller3()
  {
      // will not warn as caller has exact same attributes.
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // As call site stopped support from that version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on Android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  [UnsupportedOSPlatform("windows")] // Caller no support Windows for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'Android'.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }

  [UnsupportedOSPlatform("windows")]
  [UnsupportedOSPlatform("android")] // Caller not support Windows and Android for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // will not warn as call site not supports Android.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

### <a name="assert-the-call-site-with-platform-check"></a><span data-ttu-id="90d68-198">Zapoznaj się z sprawdzeniem połączenia z platformą</span><span class="sxs-lookup"><span data-stu-id="90d68-198">Assert the call-site with platform check</span></span>

<span data-ttu-id="90d68-199">Jako warunek dla programu można również użyć wszystkich testów warunkowych użytych w [przykładach funkcji ochrony platformy](#guard-platform-specific-apis-with-guard-methods) <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="90d68-199">All the conditional checks used in the [platform guard examples](#guard-platform-specific-apis-with-guard-methods) can also be used as the condition for <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span></span>

  ```csharp
  // An API supported only on Linux.
  [SupportedOSPlatform("linux")]
  public void LinuxOnlyApi() { }

  public void Caller()
  {
      Debug.Assert(OperatingSystem.IsLinux());

      LinuxOnlyApi(); // will not warn
  }
  ```

## <a name="see-also"></a><span data-ttu-id="90d68-200">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="90d68-200">See also</span></span>

- [<span data-ttu-id="90d68-201">Nazwy platformy docelowej w programie .NET 5</span><span class="sxs-lookup"><span data-stu-id="90d68-201">Target Framework Names in .NET 5</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [<span data-ttu-id="90d68-202">Dodawanie adnotacji do interfejsów API specyficznych dla platformy i wykrywanie ich użycia</span><span class="sxs-lookup"><span data-stu-id="90d68-202">Annotating platform-specific APIs and detecting its use</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-checks/platform-checks.md)
- [<span data-ttu-id="90d68-203">Dodawanie adnotacji do interfejsów API jako nieobsługiwanych na określonych platformach</span><span class="sxs-lookup"><span data-stu-id="90d68-203">Annotating APIs as unsupported on specific platforms</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-exclusion/platform-exclusion.md)
- [<span data-ttu-id="90d68-204">Analizator zgodności platformy CA1416</span><span class="sxs-lookup"><span data-stu-id="90d68-204">CA1416 Platform compatibility analyzer</span></span>](/visualstudio/code-quality/ca1416)
- [<span data-ttu-id="90d68-205">Analizator interfejsów API platformy .NET</span><span class="sxs-lookup"><span data-stu-id="90d68-205">.NET API analyzer</span></span>](../../standard/analyzers/api-analyzer.md)
