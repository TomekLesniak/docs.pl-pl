---
title: Przycinanie aplikacji samodzielnych
description: Dowiedz się, jak przyciąć aplikacje samodzielne w celu zmniejszenia ich rozmiaru. Platforma .NET Core udostępnia pakiet środowiska uruchomieniowego z aplikacją, która jest publikowana w sposób niezależny i ogólnie zawiera więcej informacji o środowisku uruchomieniowym.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 9c2994c98a2ebe6f45b056256c2bda28db017fbf
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465484"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="a16b4-104">Przycinanie samodzielnych wdrożeń i plików wykonywalnych</span><span class="sxs-lookup"><span data-stu-id="a16b4-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="a16b4-105">[Model wdrożenia zależny od platformy](index.md#publish-framework-dependent) był najbardziej pomyślnym modelem wdrożenia od momentu rozpoczęcia działania programu .NET.</span><span class="sxs-lookup"><span data-stu-id="a16b4-105">The [framework-dependent deployment model](index.md#publish-framework-dependent) has been the most successful deployment model since the inception of .NET.</span></span> <span data-ttu-id="a16b4-106">W tym scenariuszu Deweloper aplikacji korzysta tylko z aplikacji i zestawów innych firm z oczekiwaniami, gdy środowisko uruchomieniowe platformy .NET i biblioteki struktury będą dostępne na komputerze klienckim.</span><span class="sxs-lookup"><span data-stu-id="a16b4-106">In this scenario, the application developer bundles only the application and third-party assemblies with the expectation that the .NET runtime and framework libraries will be available in the client machine.</span></span> <span data-ttu-id="a16b4-107">Ten model wdrażania jest nadal jedynym podmiotem w programie .NET Core, ale istnieją pewne scenariusze, w których model zależny od struktury nie jest optymalny.</span><span class="sxs-lookup"><span data-stu-id="a16b4-107">This deployment model continues to be the dominant one in .NET Core as well but there are some scenarios where the framework-dependent model is not optimal.</span></span> <span data-ttu-id="a16b4-108">Alternatywą jest opublikowanie [aplikacji samodzielnej](index.md#publish-self-contained), w której środowisko uruchomieniowe i struktura platformy .NET Core są powiązane ze sobą wraz z aplikacjami i zestawami innych firm.</span><span class="sxs-lookup"><span data-stu-id="a16b4-108">The alternative is to publish a [self-contained application](index.md#publish-self-contained), where the .NET Core runtime and framework are bundled together with the application and third-party assemblies.</span></span>

<span data-ttu-id="a16b4-109">Niezależny od przycinania model wdrażania to wyspecjalizowana wersja modelu wdrażania, który jest zoptymalizowany pod kątem zmniejszenia rozmiaru wdrożenia.</span><span class="sxs-lookup"><span data-stu-id="a16b4-109">The trim-self-contained deployment model is a specialized version of the self-contained deployment model that is optimized to reduce deployment size.</span></span> <span data-ttu-id="a16b4-110">Minimalizacja rozmiaru wdrożenia jest wymaganiem krytycznym dla niektórych scenariuszy po stronie klienta, takich jak aplikacje Blazor.</span><span class="sxs-lookup"><span data-stu-id="a16b4-110">Minimizing deployment size is a critical requirement for some client-side scenarios like Blazor applications.</span></span> <span data-ttu-id="a16b4-111">W zależności od złożoności aplikacji przywoływany jest tylko podzestaw zestawów Framework, a podzestaw kodu w każdym zestawie jest wymagany do uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a16b4-111">Depending on the complexity of the application, only a subset of the framework assemblies are referenced, and a subset of the code within each assembly is required to run the application.</span></span> <span data-ttu-id="a16b4-112">Nieużywane części bibliotek są zbędne i mogą być przycinane z spakowanej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a16b4-112">The unused parts of the libraries are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="a16b4-113">Istnieje jednak ryzyko, że analiza czasu kompilacji aplikacji może spowodować błędy w czasie wykonywania, ze względu na to, że nie jest możliwe niezawodne analizowanie różnych niezawodnych wzorców kodu (w przeważającej mierze przy użyciu odbicia).</span><span class="sxs-lookup"><span data-stu-id="a16b4-113">However, there is a risk that the build time analysis of the application can cause failures at runtime, due to not being able to reliably analyze various problematic code patterns (largely centered on reflection use).</span></span> <span data-ttu-id="a16b4-114">Ponieważ niezawodności nie można zagwarantować, ten model wdrażania jest oferowany jako funkcja w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="a16b4-114">Because reliability can't be guaranteed, this deployment model is offered as a preview feature.</span></span>

<span data-ttu-id="a16b4-115">Aparat analizy czasu kompilacji zawiera ostrzeżenia dla deweloperów wzorców kodu, które są problematyczne w celu wykrycia, który inny kod jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="a16b4-115">The build time analysis engine provides warnings to the developer of code patterns that are problematic to detect which other code is required.</span></span> <span data-ttu-id="a16b4-116">Do kodu można dodawać adnotacje z atrybutami, aby poznać element dostosowujący, który ma zostać uwzględniony.</span><span class="sxs-lookup"><span data-stu-id="a16b4-116">Code can be annotated with attributes to tell the trimmer what else to include.</span></span> <span data-ttu-id="a16b4-117">Wiele wzorców odbicia można zamienić na generowanie kodu w czasie kompilacji przy użyciu [generatorów źródeł](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).</span><span class="sxs-lookup"><span data-stu-id="a16b4-117">Many reflection patterns can be replaced with build-time code generation using [Source Generators](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).</span></span>

<span data-ttu-id="a16b4-118">Tryb przycinania dla aplikacji jest konfigurowany przy użyciu `TrimMode` Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="a16b4-118">The trim mode for the applications is configured with the `TrimMode` setting.</span></span> <span data-ttu-id="a16b4-119">Wartość domyślna to `copyused` i pakiety, do których odwołują się zestawy z aplikacją.</span><span class="sxs-lookup"><span data-stu-id="a16b4-119">The default value is `copyused` and bundles referenced assemblies with the application.</span></span> <span data-ttu-id="a16b4-120">Ta `link` wartość jest używana z aplikacjami Webassembly Blazor i przycina nieużywany kod w zestawach.</span><span class="sxs-lookup"><span data-stu-id="a16b4-120">The `link` value is used with Blazor WebAssembly applications and trims unused code within assemblies.</span></span> <span data-ttu-id="a16b4-121">Ostrzeżenia analizy przycinające zapewniają informacje dotyczące wzorców kodu, w których nie było możliwe przeprowadzenie analizy pełnej zależności.</span><span class="sxs-lookup"><span data-stu-id="a16b4-121">Trim analysis warnings give information on code patterns where a full dependency analysis was not possible.</span></span> <span data-ttu-id="a16b4-122">Te ostrzeżenia są domyślnie pomijane i można je włączyć, ustawiając flagę `SuppressTrimAnalysisWarnings` na `false` .</span><span class="sxs-lookup"><span data-stu-id="a16b4-122">These warnings are suppressed by default and can be turned on by setting the flag `SuppressTrimAnalysisWarnings` to `false`.</span></span> <span data-ttu-id="a16b4-123">Aby uzyskać więcej informacji na temat dostępnych opcji przycinania, zobacz [Opcje przycinania](trimming-options.md).</span><span class="sxs-lookup"><span data-stu-id="a16b4-123">For more information about the trim options available, see [Trimming options](trimming-options.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a16b4-124">Przycinanie jest funkcją eksperymentalną w programie .NET Core 3,1, 5,0 i jest dostępna _tylko_ dla aplikacji, które są publikowane samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="a16b4-124">Trimming is an experimental feature in .NET Core 3.1, 5.0 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="a16b4-125">Uniemożliwiaj przycinanie zestawów</span><span class="sxs-lookup"><span data-stu-id="a16b4-125">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="a16b4-126">Istnieją scenariusze, w których funkcje przycinania nie będą wykrywać odwołań.</span><span class="sxs-lookup"><span data-stu-id="a16b4-126">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="a16b4-127">Na przykład gdy odbicie jest używane w zestawie czasu wykonywania, przez aplikację lub bibliotekę, do której odwołuje się aplikacja, zestaw nie jest bezpośrednio przywoływany.</span><span class="sxs-lookup"><span data-stu-id="a16b4-127">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="a16b4-128">Przycinanie jest nieświadome tych pośrednich odwołań i wykluczają bibliotekę z opublikowanego folderu.</span><span class="sxs-lookup"><span data-stu-id="a16b4-128">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="a16b4-129">Gdy kod jest pośrednio odwołujący się do zestawu poprzez odbicie, można zapobiec przycinaniu zestawu przy użyciu tego `<TrimmerRootAssembly>` Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="a16b4-129">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="a16b4-130">Poniższy przykład pokazuje, jak zapobiec przycinaniu zestawu o nazwie `System.Security` Assembly:</span><span class="sxs-lookup"><span data-stu-id="a16b4-130">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="a16b4-131">Przytnij aplikację — interfejs wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="a16b4-131">Trim your app - CLI</span></span>

<span data-ttu-id="a16b4-132">Przytnij aplikację przy użyciu polecenia [dotnet Publish](../tools/dotnet-publish.md) .</span><span class="sxs-lookup"><span data-stu-id="a16b4-132">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="a16b4-133">Po opublikowaniu aplikacji ustaw następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="a16b4-133">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="a16b4-134">Publikuj jako samodzielną aplikację dla określonego środowiska uruchomieniowego: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="a16b4-134">Publish as a self-contained app for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="a16b4-135">Włącz przycinanie: `/p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="a16b4-135">Enable trimming: `/p:PublishTrimmed=true`</span></span>

<span data-ttu-id="a16b4-136">Poniższy przykład publikuje aplikację dla systemu Windows jako samodzielny i przycina dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="a16b4-136">The following example publishes an app for Windows as self-contained and trims the output.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

<span data-ttu-id="a16b4-137">Poniższy przykład publikuje aplikację w trybie agresywnego przycinania, w którym nieużywany kod w ramach zestawów zostanie przycięty i włączono ostrzeżenia elementu dostosowującego.</span><span class="sxs-lookup"><span data-stu-id="a16b4-137">The following example publishes an app in the aggressive trim mode where unused code within assemblies will be trimmed and trimmer warnings enabled.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

<span data-ttu-id="a16b4-138">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="a16b4-138">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="a16b4-139">Przycinanie aplikacji — Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a16b4-139">Trim your app - Visual Studio</span></span>

<span data-ttu-id="a16b4-140">Program Visual Studio tworzy Profile publikowania wielokrotnego użytku, które kontrolują sposób publikowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a16b4-140">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="a16b4-141">W okienku **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt, który chcesz opublikować.</span><span class="sxs-lookup"><span data-stu-id="a16b4-141">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="a16b4-142">Wybierz pozycję **Publikuj...**.</span><span class="sxs-lookup"><span data-stu-id="a16b4-142">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Eksplorator rozwiązań z menu po kliknięciu prawym przyciskiem myszy wyróżnianie opcji Publikuj.":::

    <span data-ttu-id="a16b4-144">Jeśli nie masz jeszcze profilu publikowania, postępuj zgodnie z instrukcjami, aby utworzyć jeden, i wybierz typ docelowy **folderu** .</span><span class="sxs-lookup"><span data-stu-id="a16b4-144">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="a16b4-145">Wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="a16b4-145">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Profil publikacji programu Visual Studio za pomocą przycisku Edytuj.":::

01. <span data-ttu-id="a16b4-147">W oknie dialogowym **Ustawienia profilu** ustaw następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="a16b4-147">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="a16b4-148">Ustaw **Tryb wdrożenia** na **własny**.</span><span class="sxs-lookup"><span data-stu-id="a16b4-148">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="a16b4-149">Ustaw **docelowy środowisko uruchomieniowe** na platformę, w której chcesz publikować.</span><span class="sxs-lookup"><span data-stu-id="a16b4-149">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="a16b4-150">Wybierz pozycję **Przytnij nieużywane zestawy (w wersji zapoznawczej)**.</span><span class="sxs-lookup"><span data-stu-id="a16b4-150">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="a16b4-151">Wybierz pozycję **Zapisz** , aby zapisać ustawienia i powrócić do okna dialogowego **Publikowanie** .</span><span class="sxs-lookup"><span data-stu-id="a16b4-151">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Opcje okna dialogowego Ustawienia profilu z trybem wdrożenia, cel środowiska uruchomieniowego i nieużywane Zestawy przycinania.":::

01. <span data-ttu-id="a16b4-153">Wybierz pozycję **Publikuj** , aby opublikować aplikację przycięty.</span><span class="sxs-lookup"><span data-stu-id="a16b4-153">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="a16b4-154">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą programu Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="a16b4-154">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="a16b4-155">Przytnij aplikację — Visual Studio dla komputerów Mac</span><span class="sxs-lookup"><span data-stu-id="a16b4-155">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="a16b4-156">Visual Studio dla komputerów Mac nie udostępnia opcji przycinania aplikacji podczas publikowania.</span><span class="sxs-lookup"><span data-stu-id="a16b4-156">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="a16b4-157">Należy opublikować ręcznie, postępując zgodnie z instrukcjami podanymi w sekcji [Trim The App-CLI](#trim-your-app---cli) .</span><span class="sxs-lookup"><span data-stu-id="a16b4-157">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="a16b4-158">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="a16b4-158">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a16b4-159">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a16b4-159">See also</span></span>

- <span data-ttu-id="a16b4-160">[Wdrażanie aplikacji .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="a16b4-160">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="a16b4-161">[Publikowanie aplikacji platformy .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="a16b4-161">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="a16b4-162">[Publikowanie aplikacji platformy .NET Core w programie Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="a16b4-162">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="a16b4-163">[dotnet Publish polecenie](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="a16b4-163">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
