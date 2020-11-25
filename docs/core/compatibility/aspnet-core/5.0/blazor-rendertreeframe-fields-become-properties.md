---
title: 'Zmiana podziału: Blazor: RenderTreeFrame pola publiczne ReadOnly mają właściwości'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Blazor: RenderTreeFrame pola publiczne ReadOnly mają właściwości'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e9da9c538cc0a8ed4f138ef64ece0c7d144f28d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761355"
---
# <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a><span data-ttu-id="ee0a5-103">Blazor: RenderTreeFrame pola publiczne ReadOnly mają właściwości</span><span class="sxs-lookup"><span data-stu-id="ee0a5-103">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>

<span data-ttu-id="ee0a5-104">W ASP.NET Core 3,0 i 3,1, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> Struktura uwidacznia różne `readonly public` pola, w tym <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType> , <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence> i innych.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-104">In ASP.NET Core 3.0 and 3.1, the <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> struct exposed various `readonly public` fields, including <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence>, and others.</span></span> <span data-ttu-id="ee0a5-105">W ASP.NET Core 5,0 RC1 i nowszych wersjach wszystkie `readonly public` pola zostały zmienione na `readonly public` właściwości.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-105">In ASP.NET Core 5.0 RC1 and later versions, all the `readonly public` fields changed to `readonly public` properties.</span></span>

<span data-ttu-id="ee0a5-106">Ta zmiana nie wpłynie na wielu deweloperów, ponieważ:</span><span class="sxs-lookup"><span data-stu-id="ee0a5-106">This change won't affect many developers because:</span></span>

* <span data-ttu-id="ee0a5-107">Każda aplikacja lub biblioteka, która po prostu używa `.razor` plików (lub nawet wywołań ręcznych <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> ) w celu zdefiniowania jej składników, nie będzie bezpośrednio odwoływać się do tego typu.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-107">Any app or library that simply uses `.razor` files (or even manual <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> calls) to define its components wouldn't be referencing this type directly.</span></span>
* <span data-ttu-id="ee0a5-108">`RenderTreeFrame`Sam typ jest traktowany jako szczegóły implementacji, nie jest przeznaczony do użycia poza platformą.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-108">The `RenderTreeFrame` type itself is regarded as an implementation detail, not intended for use outside of the framework.</span></span> <span data-ttu-id="ee0a5-109">ASP.NET Core 3,0 i nowsze zawierają Analizator, który wystawia ostrzeżenia kompilatora, jeśli typ jest używany bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-109">ASP.NET Core 3.0 and later includes an analyzer that issues compiler warnings if the type is being used directly.</span></span>
* <span data-ttu-id="ee0a5-110">Nawet w przypadku bezpośredniego odwoływania `RenderTreeFrame` się do tej zmiany są rozdzieleniem danych binarnych, ale nie ze źródłem.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-110">Even if you reference `RenderTreeFrame` directly, this change is binary-breaking but not source-breaking.</span></span> <span data-ttu-id="ee0a5-111">Oznacza to, że istniejący kod źródłowy będzie kompilować i działać prawidłowo.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-111">That is, your existing source code will compile and behave properly.</span></span> <span data-ttu-id="ee0a5-112">Wystąpi problem tylko w przypadku kompilowania z platformą .NET Core 3. x, a następnie uruchamiania tych plików binarnych dla architektury .NET 5,0 RC1 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-112">You'll only encounter an issue if compiling against a .NET Core 3.x framework and then running those binaries against the .NET 5.0 RC1 and later framework.</span></span>

<span data-ttu-id="ee0a5-113">Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 25727](https://github.com/dotnet/aspnetcore/issues/25727).</span><span class="sxs-lookup"><span data-stu-id="ee0a5-113">For discussion, see GitHub issue [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ee0a5-114">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="ee0a5-114">Version introduced</span></span>

<span data-ttu-id="ee0a5-115">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="ee0a5-115">5.0 RC1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="ee0a5-116">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="ee0a5-116">Old behavior</span></span>

<span data-ttu-id="ee0a5-117">Publiczne składowe w programie `RenderTreeFrame` są zdefiniowane jako pola.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-117">Public members on `RenderTreeFrame` are defined as fields.</span></span> <span data-ttu-id="ee0a5-118">Przykład: `renderTreeFrame.Sequence` i `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-118">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="ee0a5-119">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="ee0a5-119">New behavior</span></span>

<span data-ttu-id="ee0a5-120">Publiczne składowe w `RenderTreeFrame` programie są zdefiniowane jako właściwości o takich samych nazwach jak poprzednio.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-120">Public members on `RenderTreeFrame` are defined as properties with the same names as before.</span></span> <span data-ttu-id="ee0a5-121">Przykład: `renderTreeFrame.Sequence` i `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-121">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

<span data-ttu-id="ee0a5-122">Jeśli starszy wstępnie skompilowany kod nie został ponownie skompilowany od tej zmiany, może zgłosić wyjątek podobny do *MissingFieldException: nie znaleziono pola: "Microsoft. AspNetCore. Components. RenderTree. RenderTreeFrame. FrameType"*.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-122">If older precompiled code hasn't been recompiled since this change, it may throw an exception similar to *MissingFieldException: Field not found: 'Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType'*.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ee0a5-123">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="ee0a5-123">Reason for change</span></span>

<span data-ttu-id="ee0a5-124">Ta zmiana była niezbędna do zaimplementowania ulepszeń wydajności o dużym wpływie na renderowanie składników Blazor w ASP.NET Core 5,0.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-124">This change was necessary to implement high-impact performance improvements in Blazor component rendering in ASP.NET Core 5.0.</span></span> <span data-ttu-id="ee0a5-125">Te same poziomy bezpieczeństwa i hermetyzacji są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-125">The same levels of safety and encapsulation are maintained.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ee0a5-126">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="ee0a5-126">Recommended action</span></span>

<span data-ttu-id="ee0a5-127">Ta zmiana nie dotyczy większości deweloperów Blazor.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-127">Most Blazor developers are unaffected by this change.</span></span> <span data-ttu-id="ee0a5-128">Zmiana jest prawdopodobnie niekorzystnie wpływać na bibliotekę i autorów pakietów, ale tylko w rzadkich przypadkach.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-128">The change is more likely to affect library and package authors, but only in rare cases.</span></span> <span data-ttu-id="ee0a5-129">W przypadku tworzenia:</span><span class="sxs-lookup"><span data-stu-id="ee0a5-129">Specifically, if you're developing:</span></span>

* <span data-ttu-id="ee0a5-130">Aplikacja i używanie ASP.NET Core 3. x lub uaktualniania do 5,0 RC1 lub nowszego, nie musisz zmieniać własnego kodu.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-130">An app and using ASP.NET Core 3.x or upgrading to 5.0 RC1 or later, you don't need to change your own code.</span></span> <span data-ttu-id="ee0a5-131">Jeśli jednak zależą od biblioteki uaktualnionej do konta dla tej zmiany, należy zaktualizować ją do nowszej wersji tej biblioteki.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-131">However, if you depend on a library that upgraded to account for this change, then you need to update to a newer version of that library.</span></span>
* <span data-ttu-id="ee0a5-132">Biblioteka i chce obsługiwać tylko ASP.NET Core 5,0 RC1 lub nowszy, nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-132">A library and want to support only ASP.NET Core 5.0 RC1 or later, no action is needed.</span></span> <span data-ttu-id="ee0a5-133">Upewnij się, że plik projektu deklaruje `<TargetFramework>` wartość `net5.0` lub nowszą wersję.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-133">Just ensure that your project file declares a `<TargetFramework>` value of `net5.0` or a later version.</span></span>
* <span data-ttu-id="ee0a5-134">Biblioteka i chcesz obsługiwać oba ASP.NET Core 3. x *i* 5,0, ustal, czy kod odczytuje wszelkich `RenderTreeFrame` członków.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-134">A library and want to support both ASP.NET Core 3.x *and* 5.0, determine whether your code reads any `RenderTreeFrame` members.</span></span> <span data-ttu-id="ee0a5-135">Na przykład Ocena `someRenderTreeFrame.FrameType` .</span><span class="sxs-lookup"><span data-stu-id="ee0a5-135">For example, evaluating `someRenderTreeFrame.FrameType`.</span></span>
  * <span data-ttu-id="ee0a5-136">Większość bibliotek nie odczytuje `RenderTreeFrame` elementów członkowskich, w tym bibliotek zawierających `.razor` składniki.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-136">Most libraries won't read `RenderTreeFrame` members, including libraries that contain `.razor` components.</span></span> <span data-ttu-id="ee0a5-137">W takim przypadku nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-137">In this case, no action is needed.</span></span>
  * <span data-ttu-id="ee0a5-138">Jeśli jednak Twoja biblioteka działa, musisz mieć wiele obiektów docelowych, aby obsługiwać jednocześnie `netstandard2.1` i `net5.0` .</span><span class="sxs-lookup"><span data-stu-id="ee0a5-138">However, if your library does that, you'll need to multi-target to support both `netstandard2.1` and `net5.0`.</span></span> <span data-ttu-id="ee0a5-139">Zastosuj następujące zmiany w pliku projektu:</span><span class="sxs-lookup"><span data-stu-id="ee0a5-139">Apply the following changes in your project file:</span></span>
    * <span data-ttu-id="ee0a5-140">Zamień istniejący `<TargetFramework>` element na `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>` .</span><span class="sxs-lookup"><span data-stu-id="ee0a5-140">Replace the existing `<TargetFramework>` element with `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span></span>
    * <span data-ttu-id="ee0a5-141">Użyj `Microsoft.AspNetCore.Components` odwołania do pakietu warunkowego do konta dla obu wersji, które mają być obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="ee0a5-141">Use a conditional `Microsoft.AspNetCore.Components` package reference to account for both versions you wish to support.</span></span> <span data-ttu-id="ee0a5-142">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="ee0a5-142">For example:</span></span>

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

<span data-ttu-id="ee0a5-143">Aby uzyskać więcej wyjaśnień, zobacz to [porównanie pokazuje, jak @jsakamoto już uaktualniono `Toolbelt.Blazor.HeadElement` bibliotekę](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span><span class="sxs-lookup"><span data-stu-id="ee0a5-143">For further clarification, see this [diff showing how @jsakamoto already upgraded the `Toolbelt.Blazor.HeadElement` library](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ee0a5-144">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ee0a5-144">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
