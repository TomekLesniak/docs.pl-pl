---
title: Przycinanie aplikacji samodzielnych
description: Dowiedz się, jak przyciąć aplikacje samodzielne w celu zmniejszenia ich rozmiaru. Platforma .NET Core udostępnia pakiet środowiska uruchomieniowego z aplikacją, która jest publikowana w sposób niezależny i ogólnie zawiera więcej informacji o środowisku uruchomieniowym.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: e3eb161b14f206723ad034af0a4a6ba8cd575578
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810615"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="e2d57-104">Przycinanie samodzielnych wdrożeń i plików wykonywalnych</span><span class="sxs-lookup"><span data-stu-id="e2d57-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="e2d57-105">[Model wdrożenia zależny od platformy](index.md#publish-framework-dependent) był najbardziej pomyślnym modelem wdrożenia od momentu rozpoczęcia działania programu .NET.</span><span class="sxs-lookup"><span data-stu-id="e2d57-105">The [framework-dependent deployment model](index.md#publish-framework-dependent) has been the most successful deployment model since the inception of .NET.</span></span> <span data-ttu-id="e2d57-106">W tym scenariuszu Deweloper aplikacji korzysta tylko z aplikacji i zestawów innych firm z oczekiwaniami, gdy środowisko uruchomieniowe platformy .NET i biblioteki struktury będą dostępne na komputerze klienckim.</span><span class="sxs-lookup"><span data-stu-id="e2d57-106">In this scenario, the application developer bundles only the application and third-party assemblies with the expectation that the .NET runtime and framework libraries will be available in the client machine.</span></span> <span data-ttu-id="e2d57-107">Ten model wdrażania jest nadal jedynym podmiotem w programie .NET Core, ale istnieją pewne scenariusze, w których model zależny od struktury nie jest optymalny.</span><span class="sxs-lookup"><span data-stu-id="e2d57-107">This deployment model continues to be the dominant one in .NET Core as well but there are some scenarios where the framework-dependent model is not optimal.</span></span> <span data-ttu-id="e2d57-108">Alternatywą jest opublikowanie [aplikacji samodzielnej](index.md#publish-self-contained), w której środowisko uruchomieniowe i struktura platformy .NET Core są powiązane ze sobą wraz z aplikacjami i zestawami innych firm.</span><span class="sxs-lookup"><span data-stu-id="e2d57-108">The alternative is to publish a [self-contained application](index.md#publish-self-contained), where the .NET Core runtime and framework are bundled together with the application and third-party assemblies.</span></span>

<span data-ttu-id="e2d57-109">Niezależny od przycinania model wdrażania to wyspecjalizowana wersja modelu wdrażania, który jest zoptymalizowany pod kątem zmniejszenia rozmiaru wdrożenia.</span><span class="sxs-lookup"><span data-stu-id="e2d57-109">The trim-self-contained deployment model is a specialized version of the self-contained deployment model that is optimized to reduce deployment size.</span></span> <span data-ttu-id="e2d57-110">Minimalizacja rozmiaru wdrożenia jest wymaganiem krytycznym dla niektórych scenariuszy po stronie klienta, takich jak aplikacje Blazor.</span><span class="sxs-lookup"><span data-stu-id="e2d57-110">Minimizing deployment size is a critical requirement for some client-side scenarios like Blazor applications.</span></span> <span data-ttu-id="e2d57-111">W zależności od złożoności aplikacji do uruchomienia aplikacji jest wymagany tylko podzestaw zestawów Framework.</span><span class="sxs-lookup"><span data-stu-id="e2d57-111">Depending on the complexity of the application, only a subset of the framework assemblies is required to run the application.</span></span> <span data-ttu-id="e2d57-112">Te nieużywane części biblioteki są zbędne i mogą być przycinane z spakowanej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e2d57-112">These unused parts of the library are unnecessary and can be trimmed from the packaged application.</span></span> <span data-ttu-id="e2d57-113">Istnieje jednak ryzyko, że analiza czasu kompilacji aplikacji może spowodować błędy w czasie wykonywania, ze względu na to, że nie jest możliwe niezawodne analizowanie różnych niezawodnych wzorców kodu (w przeważającej mierze przy użyciu odbicia).</span><span class="sxs-lookup"><span data-stu-id="e2d57-113">However, there is a risk that the build time analysis of the application can cause failures at runtime, due to not being able to reliably analyze various problematic code patterns (largely centered on reflection use).</span></span> <span data-ttu-id="e2d57-114">Ponieważ niezawodności nie można zagwarantować, ten model wdrażania jest oferowany jako funkcja w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="e2d57-114">Because reliability can't be guaranteed, this deployment model is offered as a preview feature.</span></span> <span data-ttu-id="e2d57-115">Aparat analizy czasu kompilacji zawiera ostrzeżenia dla deweloperów wzorców kodu, które są problematyczne, i oczekuje, że te wzorce kodu zostaną naprawione.</span><span class="sxs-lookup"><span data-stu-id="e2d57-115">The build time analysis engine provides warnings to the developer of code patterns that are problematic, with the expectation that these code patterns will be fixed.</span></span> <span data-ttu-id="e2d57-116">Jeśli to możliwe, zalecamy przeniesienie wszelkich zależności odbicia środowiska uruchomieniowego w aplikacji do czasu kompilowania przy użyciu kodu, który spełnia te same wymagania.</span><span class="sxs-lookup"><span data-stu-id="e2d57-116">Where possible, we recommend that you move any runtime reflection dependencies in your application to build time by using code that meets the same requirements.</span></span>

<span data-ttu-id="e2d57-117">Tryb przycinania dla aplikacji można skonfigurować za pomocą elementu TRIMMODE i domyślnie (), `copyused` Aby połączyć zestawy, które są używane w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e2d57-117">The trim mode for the applications can be configured via the TrimMode and will default (`copyused`) to bundle assemblies that are used in the application.</span></span> <span data-ttu-id="e2d57-118">Aplikacje webassembly Blazor będą używać bardziej agresywnego trybu ( `link` ), który będzie przycinał nieużywany kod w zestawach.</span><span class="sxs-lookup"><span data-stu-id="e2d57-118">Blazor WebAssembly applications will use a more aggressive mode (`link`) that will trim unused code within assemblies.</span></span> <span data-ttu-id="e2d57-119">Ostrzeżenia analizy przycinające zapewniają informacje dotyczące wzorców kodu, w których nie było możliwe przeprowadzenie analizy pełnej zależności.</span><span class="sxs-lookup"><span data-stu-id="e2d57-119">Trim analysis warnings give information on code patterns where a full dependency analysis was not possible.</span></span> <span data-ttu-id="e2d57-120">Te ostrzeżenia są domyślnie pomijane i można je włączyć, ustawiając flagę, `SuppressTrimAnalysisWarnings` na wartość false.</span><span class="sxs-lookup"><span data-stu-id="e2d57-120">These warnings are suppressed by default and can be turned on by setting the flag, `SuppressTrimAnalysisWarnings`, to false.</span></span> <span data-ttu-id="e2d57-121">Więcej informacji na temat dostępnych opcji przycinania można znaleźć na [stronie ILLinker](https://github.com/mono/linker/blob/master/docs/illink-options.md).</span><span class="sxs-lookup"><span data-stu-id="e2d57-121">More information on the trim options available can be found at the [ILLinker page](https://github.com/mono/linker/blob/master/docs/illink-options.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e2d57-122">Przycinanie jest funkcją eksperymentalną w programie .NET Core 3,1, 5,0 i jest dostępna _tylko_ dla aplikacji, które są publikowane samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="e2d57-122">Trimming is an experimental feature in .NET Core 3.1, 5.0 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="e2d57-123">Uniemożliwiaj przycinanie zestawów</span><span class="sxs-lookup"><span data-stu-id="e2d57-123">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="e2d57-124">Istnieją scenariusze, w których funkcje przycinania nie będą wykrywać odwołań.</span><span class="sxs-lookup"><span data-stu-id="e2d57-124">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="e2d57-125">Na przykład gdy odbicie jest używane w zestawie czasu wykonywania, przez aplikację lub bibliotekę, do której odwołuje się aplikacja, zestaw nie jest bezpośrednio przywoływany.</span><span class="sxs-lookup"><span data-stu-id="e2d57-125">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="e2d57-126">Przycinanie jest nieświadome tych pośrednich odwołań i wykluczają bibliotekę z opublikowanego folderu.</span><span class="sxs-lookup"><span data-stu-id="e2d57-126">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="e2d57-127">Gdy kod jest pośrednio odwołujący się do zestawu poprzez odbicie, można zapobiec przycinaniu zestawu przy użyciu tego `<TrimmerRootAssembly>` Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="e2d57-127">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="e2d57-128">Poniższy przykład pokazuje, jak zapobiec przycinaniu zestawu o nazwie `System.Security` Assembly:</span><span class="sxs-lookup"><span data-stu-id="e2d57-128">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="e2d57-129">Przytnij aplikację — interfejs wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="e2d57-129">Trim your app - CLI</span></span>

<span data-ttu-id="e2d57-130">Przytnij aplikację przy użyciu polecenia [dotnet Publish](../tools/dotnet-publish.md) .</span><span class="sxs-lookup"><span data-stu-id="e2d57-130">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="e2d57-131">Po opublikowaniu aplikacji ustaw następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="e2d57-131">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="e2d57-132">Publikuj jako samodzielną aplikację dla określonego środowiska uruchomieniowego: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="e2d57-132">Publish as a self-contained app for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="e2d57-133">Włącz przycinanie: `/p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="e2d57-133">Enable trimming: `/p:PublishTrimmed=true`</span></span>

<span data-ttu-id="e2d57-134">Poniższy przykład publikuje aplikację dla systemu Windows jako samodzielny i przycina dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="e2d57-134">The following example publishes an app for Windows as self-contained and trims the output.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

<span data-ttu-id="e2d57-135">Poniższy przykład publikuje aplikację w trybie agresywnego przycinania, w którym nieużywany kod w ramach zestawów zostanie przycięty i włączono ostrzeżenia elementu dostosowującego.</span><span class="sxs-lookup"><span data-stu-id="e2d57-135">The following example publishes an app in the aggressive trim mode where unused code within assemblies will be trimmed and trimmer warnings enabled.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

<span data-ttu-id="e2d57-136">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="e2d57-136">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="e2d57-137">Przycinanie aplikacji — Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e2d57-137">Trim your app - Visual Studio</span></span>

<span data-ttu-id="e2d57-138">Program Visual Studio tworzy Profile publikowania wielokrotnego użytku, które kontrolują sposób publikowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e2d57-138">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="e2d57-139">W okienku **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt, który chcesz opublikować.</span><span class="sxs-lookup"><span data-stu-id="e2d57-139">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="e2d57-140">Wybierz pozycję **Publikuj...**.</span><span class="sxs-lookup"><span data-stu-id="e2d57-140">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Eksplorator rozwiązań z menu po kliknięciu prawym przyciskiem myszy wyróżnianie opcji Publikuj.":::

    <span data-ttu-id="e2d57-142">Jeśli nie masz jeszcze profilu publikowania, postępuj zgodnie z instrukcjami, aby utworzyć jeden, i wybierz typ docelowy **folderu** .</span><span class="sxs-lookup"><span data-stu-id="e2d57-142">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="e2d57-143">Wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="e2d57-143">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Profil publikacji programu Visual Studio za pomocą przycisku Edytuj.":::

01. <span data-ttu-id="e2d57-145">W oknie dialogowym **Ustawienia profilu** ustaw następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="e2d57-145">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="e2d57-146">Ustaw **Tryb wdrożenia** na **własny**.</span><span class="sxs-lookup"><span data-stu-id="e2d57-146">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="e2d57-147">Ustaw **docelowy środowisko uruchomieniowe** na platformę, w której chcesz publikować.</span><span class="sxs-lookup"><span data-stu-id="e2d57-147">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="e2d57-148">Wybierz pozycję **Przytnij nieużywane zestawy (w wersji zapoznawczej)**.</span><span class="sxs-lookup"><span data-stu-id="e2d57-148">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="e2d57-149">Wybierz pozycję **Zapisz** , aby zapisać ustawienia i powrócić do okna dialogowego **Publikowanie** .</span><span class="sxs-lookup"><span data-stu-id="e2d57-149">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Opcje okna dialogowego Ustawienia profilu z trybem wdrożenia, cel środowiska uruchomieniowego i nieużywane Zestawy przycinania.":::

01. <span data-ttu-id="e2d57-151">Wybierz pozycję **Publikuj** , aby opublikować aplikację przycięty.</span><span class="sxs-lookup"><span data-stu-id="e2d57-151">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="e2d57-152">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą programu Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e2d57-152">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="e2d57-153">Przytnij aplikację — Visual Studio dla komputerów Mac</span><span class="sxs-lookup"><span data-stu-id="e2d57-153">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="e2d57-154">Visual Studio dla komputerów Mac nie udostępnia opcji przycinania aplikacji podczas publikowania.</span><span class="sxs-lookup"><span data-stu-id="e2d57-154">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="e2d57-155">Należy opublikować ręcznie, postępując zgodnie z instrukcjami podanymi w sekcji [Trim The App-CLI](#trim-your-app---cli) .</span><span class="sxs-lookup"><span data-stu-id="e2d57-155">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="e2d57-156">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="e2d57-156">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2d57-157">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e2d57-157">See also</span></span>

- <span data-ttu-id="e2d57-158">[Wdrażanie aplikacji .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="e2d57-158">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="e2d57-159">[Publikowanie aplikacji platformy .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="e2d57-159">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="e2d57-160">[Publikowanie aplikacji platformy .NET Core w programie Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e2d57-160">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="e2d57-161">[dotnet Publish polecenie](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="e2d57-161">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
