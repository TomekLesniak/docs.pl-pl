---
title: 'Zmiana podziału: Blazor: nieznaczące odstępy są obcinane ze składników w czasie kompilacji'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Blazor: nieznaczące odstępy są obcinane ze składników w czasie kompilacji'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 92a961bb377bedd27b793c77d4be31ce52179ee2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761660"
---
# <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a><span data-ttu-id="01919-103">Blazor: nieznaczące odstępy są obcinane ze składników w czasie kompilacji</span><span class="sxs-lookup"><span data-stu-id="01919-103">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>

<span data-ttu-id="01919-104">Począwszy od ASP.NET Core 5,0 w wersji zapoznawczej 7 kompilator Razor pomija nieznaczące odstępy w składnikach Blazor (pliki *Razor* ) w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="01919-104">Starting with ASP.NET Core 5.0 Preview 7, the Razor compiler omits insignificant whitespace in Blazor components (*.razor* files) at compile time.</span></span> <span data-ttu-id="01919-105">Aby zapoznać się z omówieniem, zobacz temat Issue [dotnet/aspnetcore # 23568](https://github.com/dotnet/aspnetcore/issues/23568).</span><span class="sxs-lookup"><span data-stu-id="01919-105">For discussion, see issue [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="01919-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="01919-106">Version introduced</span></span>

<span data-ttu-id="01919-107">5,0 wersja zapoznawcza 7</span><span class="sxs-lookup"><span data-stu-id="01919-107">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="01919-108">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="01919-108">Old behavior</span></span>

<span data-ttu-id="01919-109">W 3. x wersjach Blazor Server i Blazor webassembly biały znak jest uznawany za kod źródłowy składnika.</span><span class="sxs-lookup"><span data-stu-id="01919-109">In 3.x versions of Blazor Server and Blazor WebAssembly, whitespace is honored in a component's source code.</span></span> <span data-ttu-id="01919-110">Odstępy — tylko węzły tekstowe są renderowane w Document Object Model przeglądarki (DOM), nawet jeśli nie ma efektów wizualnych.</span><span class="sxs-lookup"><span data-stu-id="01919-110">Whitespace-only text nodes render in the browser's Document Object Model (DOM) even when there's no visual effect.</span></span>

<span data-ttu-id="01919-111">Rozważmy następujący kod składnika Blazor:</span><span class="sxs-lookup"><span data-stu-id="01919-111">Consider the following Blazor component code:</span></span>

```razor
<ul>
    @foreach (var item in Items)
    {
        <li>
            @item.Text
        </li>
    }
</ul>
```

<span data-ttu-id="01919-112">W poprzednim przykładzie renderowane są dwa węzły odstępu:</span><span class="sxs-lookup"><span data-stu-id="01919-112">The preceding example renders two whitespace nodes:</span></span>

* <span data-ttu-id="01919-113">Poza `@foreach` blokiem kodu.</span><span class="sxs-lookup"><span data-stu-id="01919-113">Outside of the `@foreach` code block.</span></span>
* <span data-ttu-id="01919-114">Wokół `<li>` elementu.</span><span class="sxs-lookup"><span data-stu-id="01919-114">Around the `<li>` element.</span></span>
* <span data-ttu-id="01919-115">Wokół `@item.Text` danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="01919-115">Around the `@item.Text` output.</span></span>

<span data-ttu-id="01919-116">Lista zawierająca 100 elementów skutkuje w węzłach o 402.</span><span class="sxs-lookup"><span data-stu-id="01919-116">A list containing 100 items results in 402 whitespace nodes.</span></span> <span data-ttu-id="01919-117">Jest to ponad połowę wszystkich wyrenderowanych węzłów, nawet jeśli żaden z węzłów odstępu nie ma wizualnie wpływu na renderowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="01919-117">That's over half of all nodes rendered, even though none of the whitespace nodes visually affect the rendered output.</span></span>

<span data-ttu-id="01919-118">Podczas renderowania statycznego kodu HTML dla składników, odstęp wewnątrz tagu nie został zachowany.</span><span class="sxs-lookup"><span data-stu-id="01919-118">When rendering static HTML for components, whitespace inside a tag wasn't preserved.</span></span> <span data-ttu-id="01919-119">Na przykład Wyświetl źródło następującego składnika:</span><span class="sxs-lookup"><span data-stu-id="01919-119">For example, view the source of the following component:</span></span>

```razor
<foo        bar="baz"     />
```

<span data-ttu-id="01919-120">Biały znak nie jest zachowywany.</span><span class="sxs-lookup"><span data-stu-id="01919-120">Whitespace isn't preserved.</span></span> <span data-ttu-id="01919-121">Wstępnie renderowane dane wyjściowe to:</span><span class="sxs-lookup"><span data-stu-id="01919-121">The pre-rendered output is:</span></span>

```razor
<foo bar="baz" />
```

## <a name="new-behavior"></a><span data-ttu-id="01919-122">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="01919-122">New behavior</span></span>

<span data-ttu-id="01919-123">O ile `@preservewhitespace` dyrektywa nie jest używana z wartością `true` , węzły odstępu są usuwane, jeśli:</span><span class="sxs-lookup"><span data-stu-id="01919-123">Unless the `@preservewhitespace` directive is used with value `true`, whitespace nodes are removed if they:</span></span>

* <span data-ttu-id="01919-124">Są wiodące lub końcowe w obrębie elementu.</span><span class="sxs-lookup"><span data-stu-id="01919-124">Are leading or trailing within an element.</span></span>
* <span data-ttu-id="01919-125">Są wiodące lub końcowe w obrębie `RenderFragment` parametru.</span><span class="sxs-lookup"><span data-stu-id="01919-125">Are leading or trailing within a `RenderFragment` parameter.</span></span> <span data-ttu-id="01919-126">Na przykład zawartość podrzędna jest przesyłana do innego składnika.</span><span class="sxs-lookup"><span data-stu-id="01919-126">For example, child content being passed to another component.</span></span>
* <span data-ttu-id="01919-127">Należy użyć bloku kodu w języku C#, takiego jak `@if` i `@foreach` .</span><span class="sxs-lookup"><span data-stu-id="01919-127">Precede or follow a C# code block such as `@if` and `@foreach`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="01919-128">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="01919-128">Reason for change</span></span>

<span data-ttu-id="01919-129">Celem Blazor w ASP.NET Core 5,0 jest poprawa wydajności renderowania i różnicowania.</span><span class="sxs-lookup"><span data-stu-id="01919-129">A goal for Blazor in ASP.NET Core 5.0 is to improve the performance of rendering and diffing.</span></span> <span data-ttu-id="01919-130">Nieznaczące węzły drzewa odstępów zużywają do 40% czasu renderowania w testach porównawczych.</span><span class="sxs-lookup"><span data-stu-id="01919-130">Insignificant whitespace tree nodes consumed up to 40 percent of the rendering time in benchmarks.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="01919-131">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="01919-131">Recommended action</span></span>

<span data-ttu-id="01919-132">W większości przypadków nie ma to żadnego oddziaływania na układ wizualizacji renderowanego składnika.</span><span class="sxs-lookup"><span data-stu-id="01919-132">In most cases, the visual layout of the rendered component is unaffected.</span></span> <span data-ttu-id="01919-133">Jednak usunięcie odstępu może mieć wpływ na renderowane dane wyjściowe w przypadku używania reguły CSS, takiej jak `white-space: pre` .</span><span class="sxs-lookup"><span data-stu-id="01919-133">However, the whitespace removal might affect the rendered output when using a CSS rule like `white-space: pre`.</span></span> <span data-ttu-id="01919-134">Aby wyłączyć tę optymalizację wydajności i zachować odstęp, wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="01919-134">To disable this performance optimization and preserve the whitespace, take one of the following actions:</span></span>

* <span data-ttu-id="01919-135">Dodaj `@preservewhitespace true` dyrektywę w górnej części pliku *Razor* , aby zastosować preferencję do określonego składnika.</span><span class="sxs-lookup"><span data-stu-id="01919-135">Add the `@preservewhitespace true` directive at the top of the *.razor* file to apply the preference to a specific component.</span></span>
* <span data-ttu-id="01919-136">Dodaj `@preservewhitespace true` dyrektywę wewnątrz pliku *_Imports. Razor* , aby zastosować preferencję do całego podkatalogu lub całego projektu.</span><span class="sxs-lookup"><span data-stu-id="01919-136">Add the `@preservewhitespace true` directive inside an *_Imports.razor* file to apply the preference to an entire subdirectory or the entire project.</span></span>

<span data-ttu-id="01919-137">W większości przypadków żadna akcja nie jest wymagana, ponieważ aplikacje zwykle nadal zachowują się normalnie (ale szybciej).</span><span class="sxs-lookup"><span data-stu-id="01919-137">In most cases, no action is required, as applications will typically continue to behave normally (but faster).</span></span> <span data-ttu-id="01919-138">W przypadku wyłączania odstępów powoduje wszelkie problemy dotyczące określonego składnika, użyj `@preservewhitespace true` w tym składniku, aby wyłączyć tę optymalizację.</span><span class="sxs-lookup"><span data-stu-id="01919-138">If the whitespace stripping causes any problems for a particular component, use `@preservewhitespace true` in that component to disable this optimization.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="01919-139">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="01919-139">Affected APIs</span></span>

<span data-ttu-id="01919-140">Brak</span><span class="sxs-lookup"><span data-stu-id="01919-140">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
