---
title: Aplikacja pojedynczego pliku
description: Dowiedz się, co to jest aplikacja z pojedynczym plikiem i dlaczego należy rozważyć użycie tego modelu wdrażania aplikacji.
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 795ea98a9fd9d672b199eb2d9b24151340ef8246
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495800"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="a07ff-103">Wdrożenie pojedynczego pliku i plik wykonywalny</span><span class="sxs-lookup"><span data-stu-id="a07ff-103">Single file deployment and executable</span></span>

<span data-ttu-id="a07ff-104">Zgrupowanie wszystkich plików zależnych od aplikacji do jednego pliku binarnego zapewnia deweloperowi aplikacji z opcją atrakcyjną w celu wdrożenia i dystrybucji aplikacji jako pojedynczy plik.</span><span class="sxs-lookup"><span data-stu-id="a07ff-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="a07ff-105">Ten model wdrażania został udostępniony od platformy .NET Core 3,0 i został ulepszony w programie .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="a07ff-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="a07ff-106">Wcześniej w programie .NET Core 3,0, gdy użytkownik uruchamia aplikację z jednym plikiem, host .NET Core najpierw wyodrębnia wszystkie pliki do katalogu tymczasowego przed uruchomieniem aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a07ff-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="a07ff-107">Program .NET 5,0 podnosi to środowisko, bezpośrednio uruchamiając kod bez konieczności wyodrębniania plików z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a07ff-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="a07ff-108">Wdrożenie pojedynczego pliku jest dostępne zarówno dla [modelu wdrażania zależnego od platformy](index.md#publish-framework-dependent) , jak i [aplikacji samodzielnych](index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="a07ff-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="a07ff-109">Rozmiar pojedynczego pliku w aplikacji samodzielnej jest duży, ponieważ będzie obejmował środowisko uruchomieniowe i biblioteki struktury.</span><span class="sxs-lookup"><span data-stu-id="a07ff-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="a07ff-110">Opcja wdrożenia pojedynczego pliku może być łączona z [ReadyToRun](../tools/dotnet-publish.md) i [Trim (funkcja eksperymentalna w programie .NET 5,0)](trim-self-contained.md) opcje publikowania.</span><span class="sxs-lookup"><span data-stu-id="a07ff-110">The single file deployment option can be combined with [ReadyToRun](../tools/dotnet-publish.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

<span data-ttu-id="a07ff-111">Istnieją pewne ograniczenia, które należy wziąć pod uwagę przy użyciu pojedynczych plików, przy czym najpierw są używane informacje o ścieżce do lokalizowania plików względem lokalizacji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a07ff-111">There are some caveats that you need to be aware for single-file use, first of which is the use of path information to locate a file relative to the location of your application.</span></span> <span data-ttu-id="a07ff-112"><xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>Interfejs API zwróci pusty ciąg, który jest domyślnym zachowaniem dla zestawów ładowanych z pamięci.</span><span class="sxs-lookup"><span data-stu-id="a07ff-112">The <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> API will return an empty string, which is the default behavior for assemblies loaded from memory.</span></span> <span data-ttu-id="a07ff-113">Kompilator wyświetli ostrzeżenie dla tego interfejsu API w czasie kompilacji, aby poinformować dewelopera o określonym zachowaniu.</span><span class="sxs-lookup"><span data-stu-id="a07ff-113">The compiler will give a warning for this API during build time to alert the developer to the specific behavior.</span></span> <span data-ttu-id="a07ff-114">Jeśli wymagana jest ścieżka do katalogu aplikacji, <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> interfejs API zwróci katalog, w którym znajduje się AppHost (sam pakiet pojedynczego pliku).</span><span class="sxs-lookup"><span data-stu-id="a07ff-114">If the path to the application directory is needed, the <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> API will return the directory where the AppHost (the single-file bundle itself) resides.</span></span> <span data-ttu-id="a07ff-115">Zarządzane aplikacje C++ nie są dobrze dopasowane do wdrożenia jednoplikowego i zalecamy zapisanie aplikacji w języku C# w celu zapewnienia zgodności z pojedynczym plikiem.</span><span class="sxs-lookup"><span data-stu-id="a07ff-115">Managed C++ applications aren't well suited for single-file deployment and we recommend that you write applications in C# to be single-file compatible.</span></span>

<span data-ttu-id="a07ff-116">Pojedynczy plik domyślnie nie obsługuje bibliotek natywnych.</span><span class="sxs-lookup"><span data-stu-id="a07ff-116">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="a07ff-117">W systemie Linux wstępnie łączymy środowisko uruchomieniowe z pakietem i tylko biblioteki natywne aplikacji są wdrażane w tym samym katalogu, w którym znajduje się aplikacja Jednoplikowa.</span><span class="sxs-lookup"><span data-stu-id="a07ff-117">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="a07ff-118">W systemie Windows połączymy tylko kod hostingu, a biblioteki natywne środowiska uruchomieniowego i aplikacji są wdrażane w tym samym katalogu, w którym znajduje się aplikacja pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="a07ff-118">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="a07ff-119">Jest to konieczne w celu zapewnienia dobrego środowiska debugowania, które wymaga wykluczenia plików natywnych z pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="a07ff-119">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="a07ff-120">Istnieje możliwość ustawienia flagi, `IncludeNativeLibrariesForSelfExtract` Aby uwzględnić biblioteki natywne w pojedynczym zbiorze plików, ale te pliki zostaną wyodrębnione do katalogu tymczasowego na komputerze klienckim po uruchomieniu aplikacji pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="a07ff-120">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="a07ff-121">Wykluczanie plików z osadzania</span><span class="sxs-lookup"><span data-stu-id="a07ff-121">Exclude files from being embedded</span></span>

<span data-ttu-id="a07ff-122">Niektóre pliki można jawnie wykluczyć z osadzania w pojedynczym pliku przez ustawienie następujących metadanych:</span><span class="sxs-lookup"><span data-stu-id="a07ff-122">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="a07ff-123">Na przykład w celu umieszczenia niektórych plików w katalogu publikowania, ale nie są one powiązane z pojedynczym plikiem:</span><span class="sxs-lookup"><span data-stu-id="a07ff-123">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="a07ff-124">Publikowanie pojedynczego pliku aplikacji — interfejs wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="a07ff-124">Publish a single file app - CLI</span></span>

<span data-ttu-id="a07ff-125">Opublikuj aplikację pojedynczego pliku przy użyciu polecenia [dotnet Publish](../tools/dotnet-publish.md) .</span><span class="sxs-lookup"><span data-stu-id="a07ff-125">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="a07ff-126">Po opublikowaniu aplikacji ustaw następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="a07ff-126">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="a07ff-127">Publikuj dla określonego środowiska uruchomieniowego: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="a07ff-127">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="a07ff-128">Publikuj jako pojedynczy plik: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="a07ff-128">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="a07ff-129">W poniższym przykładzie jest publikowana aplikacja dla systemu Windows jako samodzielna aplikacja pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="a07ff-129">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="a07ff-130">Poniższy przykład umożliwia opublikowanie aplikacji dla systemu Linux jako zależnej od struktury aplikacji pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="a07ff-130">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="a07ff-131">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="a07ff-131">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="a07ff-132">Publikowanie aplikacji pojedynczego pliku — Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a07ff-132">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="a07ff-133">Program Visual Studio tworzy Profile publikowania wielokrotnego użytku, które kontrolują sposób publikowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a07ff-133">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="a07ff-134">W okienku **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt, który chcesz opublikować.</span><span class="sxs-lookup"><span data-stu-id="a07ff-134">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="a07ff-135">Kliknij pozycję **Opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="a07ff-135">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Eksplorator rozwiązań z menu po kliknięciu prawym przyciskiem myszy wyróżnianie opcji Publikuj.":::

    <span data-ttu-id="a07ff-137">Jeśli nie masz jeszcze profilu publikowania, postępuj zgodnie z instrukcjami, aby utworzyć jeden, i wybierz typ docelowy **folderu** .</span><span class="sxs-lookup"><span data-stu-id="a07ff-137">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="a07ff-138">Wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="a07ff-138">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Profil publikacji programu Visual Studio za pomocą przycisku Edytuj.":::

01. <span data-ttu-id="a07ff-140">W oknie dialogowym **Ustawienia profilu** ustaw następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="a07ff-140">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="a07ff-141">Ustaw **Tryb wdrożenia** na **własny**.</span><span class="sxs-lookup"><span data-stu-id="a07ff-141">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="a07ff-142">Ustaw **docelowy środowisko uruchomieniowe** na platformę, w której chcesz publikować.</span><span class="sxs-lookup"><span data-stu-id="a07ff-142">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="a07ff-143">Wybierz pozycję **Wygeneruj pojedynczy plik**.</span><span class="sxs-lookup"><span data-stu-id="a07ff-143">Select **Produce single file**.</span></span>

    <span data-ttu-id="a07ff-144">Wybierz pozycję **Zapisz** , aby zapisać ustawienia i powrócić do okna dialogowego **Publikowanie** .</span><span class="sxs-lookup"><span data-stu-id="a07ff-144">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Okno dialogowe ustawień profilu z trybem wdrożenia, docelowym środowiskiem uruchomieniowym i opcją pojedynczego pliku.":::

01. <span data-ttu-id="a07ff-146">Wybierz pozycję **Publikuj** , aby opublikować aplikację jako pojedynczy plik.</span><span class="sxs-lookup"><span data-stu-id="a07ff-146">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="a07ff-147">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą programu Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="a07ff-147">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="a07ff-148">Publikowanie aplikacji pojedynczego pliku — Visual Studio dla komputerów Mac</span><span class="sxs-lookup"><span data-stu-id="a07ff-148">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="a07ff-149">Visual Studio dla komputerów Mac nie udostępnia opcji publikowania aplikacji jako pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="a07ff-149">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="a07ff-150">Należy opublikować ręcznie, postępując zgodnie z instrukcjami zawartymi w sekcji [Publikowanie pojedynczego pliku App-CLI](#publish-a-single-file-app---cli) .</span><span class="sxs-lookup"><span data-stu-id="a07ff-150">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="a07ff-151">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="a07ff-151">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a07ff-152">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a07ff-152">See also</span></span>

- <span data-ttu-id="a07ff-153">[Wdrażanie aplikacji .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="a07ff-153">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="a07ff-154">[Publikowanie aplikacji platformy .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="a07ff-154">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="a07ff-155">[Publikowanie aplikacji platformy .NET Core w programie Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="a07ff-155">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="a07ff-156">[ `dotnet publish` polecenie](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="a07ff-156">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
