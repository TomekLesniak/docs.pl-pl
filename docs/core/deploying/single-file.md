---
title: Aplikacja pojedynczego pliku
description: Dowiedz się, co to jest aplikacja z pojedynczym plikiem i dlaczego należy rozważyć użycie tego modelu wdrażania aplikacji.
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: b7693d6c119d00a798ef03ed1019f2f04c1828cf
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654655"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="f3133-103">Wdrażanie i wykonywanie przy użyciu jednego pliku</span><span class="sxs-lookup"><span data-stu-id="f3133-103">Single file deployment and executable</span></span>

<span data-ttu-id="f3133-104">Zgrupowanie wszystkich plików zależnych od aplikacji do jednego pliku binarnego zapewnia deweloperowi aplikacji z opcją atrakcyjną w celu wdrożenia i dystrybucji aplikacji jako pojedynczy plik.</span><span class="sxs-lookup"><span data-stu-id="f3133-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="f3133-105">Ten model wdrażania został udostępniony od platformy .NET Core 3,0 i został ulepszony w programie .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="f3133-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="f3133-106">Wcześniej w programie .NET Core 3,0, gdy użytkownik uruchamia aplikację z jednym plikiem, host .NET Core najpierw wyodrębnia wszystkie pliki do katalogu tymczasowego przed uruchomieniem aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f3133-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="f3133-107">Program .NET 5,0 podnosi to środowisko, bezpośrednio uruchamiając kod bez konieczności wyodrębniania plików z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f3133-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="f3133-108">Wdrożenie pojedynczego pliku jest dostępne zarówno dla [modelu wdrażania zależnego od platformy](index.md#publish-framework-dependent) , jak i [aplikacji samodzielnych](index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="f3133-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="f3133-109">Rozmiar pojedynczego pliku w aplikacji samodzielnej jest duży, ponieważ będzie obejmował środowisko uruchomieniowe i biblioteki struktury.</span><span class="sxs-lookup"><span data-stu-id="f3133-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="f3133-110">Opcja wdrożenia pojedynczego pliku może być łączona z [ReadyToRun](../tools/dotnet-publish.md) i [Trim (funkcja eksperymentalna w programie .NET 5,0)](trim-self-contained.md) opcje publikowania.</span><span class="sxs-lookup"><span data-stu-id="f3133-110">The single file deployment option can be combined with [ReadyToRun](../tools/dotnet-publish.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

## <a name="api-incompatibility"></a><span data-ttu-id="f3133-111">Niezgodność interfejsu API</span><span class="sxs-lookup"><span data-stu-id="f3133-111">API incompatibility</span></span>

<span data-ttu-id="f3133-112">Niektóre interfejsy API nie są zgodne z wdrożeniem pojedynczego pliku, a aplikacje mogą wymagać modyfikacji, jeśli korzystają z tych interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="f3133-112">Some APIs are not compatible with single-file deployment and applications may require modification if they use these APIs.</span></span> <span data-ttu-id="f3133-113">Jeśli używasz struktury lub pakietu innej firmy, istnieje możliwość, że mogą one również korzystać z jednego z tych interfejsów API i wymagać modyfikacji.</span><span class="sxs-lookup"><span data-stu-id="f3133-113">If you use a third-party framework or package, it's possible that they may also use one of these APIs and need modification.</span></span> <span data-ttu-id="f3133-114">Najczęstsze przyczyny problemów są zależne od ścieżek plików plików lub bibliotek DLL dostarczanych z aplikacją.</span><span class="sxs-lookup"><span data-stu-id="f3133-114">The most common cause of problems is dependence on file paths for files or DLLs shipped with the application.</span></span>

<span data-ttu-id="f3133-115">W poniższej tabeli znajdują się odpowiednie szczegóły interfejsu API biblioteki środowiska uruchomieniowego dotyczące użycia pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="f3133-115">The table below has the relevant runtime library API details for single-file use.</span></span>

| <span data-ttu-id="f3133-116">Interfejs API</span><span class="sxs-lookup"><span data-stu-id="f3133-116">API</span></span>                            | <span data-ttu-id="f3133-117">Uwaga</span><span class="sxs-lookup"><span data-stu-id="f3133-117">Note</span></span>                                                                   |
|--------------------------------|------------------------------------------------------------------------|
| `Assembly.Location`            | <span data-ttu-id="f3133-118">Zwraca pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="f3133-118">Returns an empty string.</span></span>                                               |
| `Module.FullyQualifiedName`    | <span data-ttu-id="f3133-119">Zwraca ciąg z wartością `<Unknown>` lub zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="f3133-119">Returns a string with the value of `<Unknown>` or throws an exception.</span></span> |
| `Module.Name`                  | <span data-ttu-id="f3133-120">Zwraca ciąg o wartości `<Unknown>` .</span><span class="sxs-lookup"><span data-stu-id="f3133-120">Returns a string with the value of `<Unknown>`.</span></span>                        |
| `Assembly.GetFile`             | <span data-ttu-id="f3133-121">Zgłasza <xref:System.IO.IOException> .</span><span class="sxs-lookup"><span data-stu-id="f3133-121">Throws <xref:System.IO.IOException>.</span></span>                                   |
| `Assembly.GetFiles`            | <span data-ttu-id="f3133-122">Zgłasza <xref:System.IO.IOException> .</span><span class="sxs-lookup"><span data-stu-id="f3133-122">Throws <xref:System.IO.IOException>.</span></span>                                   |
| `Assembly.CodeBase`            | <span data-ttu-id="f3133-123">Zgłasza <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="f3133-123">Throws <xref:System.PlatformNotSupportedException>.</span></span>                    |
| `Assembly.EscapedCodeBase`     | <span data-ttu-id="f3133-124">Zgłasza <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="f3133-124">Throws <xref:System.PlatformNotSupportedException>.</span></span>                    |
| `AssemblyName.CodeBase`        | <span data-ttu-id="f3133-125">Zwraca wartość `null`.</span><span class="sxs-lookup"><span data-stu-id="f3133-125">Returns `null`.</span></span>                                                        |
| `AssemblyName.EscapedCodeBase` | <span data-ttu-id="f3133-126">Zwraca wartość `null`.</span><span class="sxs-lookup"><span data-stu-id="f3133-126">Returns `null`.</span></span>                                                        |

<span data-ttu-id="f3133-127">Mamy pewne zalecenia dotyczące rozwiązywania typowych scenariuszy:</span><span class="sxs-lookup"><span data-stu-id="f3133-127">We have some recommendations for fixing common scenarios:</span></span>

* <span data-ttu-id="f3133-128">Aby uzyskać dostęp do plików obok pliku wykonywalnego, użyj programu <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3133-128">To access files next to the executable, use <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="f3133-129">Aby znaleźć nazwę pliku wykonywalnego, użyj pierwszego elementu <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3133-129">To find the file name of the executable, use the first element of <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="f3133-130">Aby uniknąć całkowitego wysyłania luźnych plików, należy rozważyć użycie [zasobów osadzonych](../../framework/resources/creating-resource-files-for-desktop-apps.md).</span><span class="sxs-lookup"><span data-stu-id="f3133-130">To avoid shipping loose files entirely, consider using [embedded resources](../../framework/resources/creating-resource-files-for-desktop-apps.md).</span></span>

## <a name="other-considerations"></a><span data-ttu-id="f3133-131">Inne zagadnienia</span><span class="sxs-lookup"><span data-stu-id="f3133-131">Other considerations</span></span>

<span data-ttu-id="f3133-132">Pojedynczy plik domyślnie nie obsługuje bibliotek natywnych.</span><span class="sxs-lookup"><span data-stu-id="f3133-132">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="f3133-133">W systemie Linux wstępnie łączymy środowisko uruchomieniowe z pakietem i tylko biblioteki natywne aplikacji są wdrażane w tym samym katalogu, w którym znajduje się aplikacja Jednoplikowa.</span><span class="sxs-lookup"><span data-stu-id="f3133-133">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="f3133-134">W systemie Windows połączymy tylko kod hostingu, a biblioteki natywne środowiska uruchomieniowego i aplikacji są wdrażane w tym samym katalogu, w którym znajduje się aplikacja pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="f3133-134">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="f3133-135">Jest to konieczne w celu zapewnienia dobrego środowiska debugowania, które wymaga wykluczenia plików natywnych z pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="f3133-135">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="f3133-136">Istnieje możliwość ustawienia flagi, `IncludeNativeLibrariesForSelfExtract` Aby uwzględnić biblioteki natywne w pojedynczym zbiorze plików, ale te pliki zostaną wyodrębnione do katalogu tymczasowego na komputerze klienckim po uruchomieniu aplikacji pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="f3133-136">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

<span data-ttu-id="f3133-137">Aplikacja Jednoplikowa będzie zawierała wszystkie powiązane pliki PDB obok niej i nie zostanie domyślnie zawiązana.</span><span class="sxs-lookup"><span data-stu-id="f3133-137">Single-file application will have all related PDB files alongside it and will not be bundled by default.</span></span> <span data-ttu-id="f3133-138">Jeśli chcesz uwzględnić plików pdb wewnątrz zestawu dla projektów, które tworzysz, ustaw polecenie `DebugType` na zgodnie z `embedded` [poniższym](#include-pdb-files-inside-the-bundle) opisem.</span><span class="sxs-lookup"><span data-stu-id="f3133-138">If you want to include PDBs inside the assembly for projects you build, set the `DebugType` to `embedded` as described [below](#include-pdb-files-inside-the-bundle) in detail.</span></span>

<span data-ttu-id="f3133-139">Zarządzane składniki języka C++ nie są dobrze dopasowane do wdrożenia jednoplikowego i zalecamy zapisanie aplikacji w języku C# lub innym niezarządzanym języku C++ w celu zapewnienia zgodności z pojedynczym plikiem.</span><span class="sxs-lookup"><span data-stu-id="f3133-139">Managed C++ components aren't well suited for single-file deployment and we recommend that you write applications in C# or another non-managed C++ language to be single-file compatible.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="f3133-140">Wykluczanie plików z osadzania</span><span class="sxs-lookup"><span data-stu-id="f3133-140">Exclude files from being embedded</span></span>

<span data-ttu-id="f3133-141">Niektóre pliki można jawnie wykluczyć z osadzania w pojedynczym pliku przez ustawienie następujących metadanych:</span><span class="sxs-lookup"><span data-stu-id="f3133-141">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="f3133-142">Na przykład w celu umieszczenia niektórych plików w katalogu publikowania, ale nie są one powiązane z pojedynczym plikiem:</span><span class="sxs-lookup"><span data-stu-id="f3133-142">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="include-pdb-files-inside-the-bundle"></a><span data-ttu-id="f3133-143">Uwzględnij pliki PDB wewnątrz pakietu</span><span class="sxs-lookup"><span data-stu-id="f3133-143">Include PDB files inside the bundle</span></span>

<span data-ttu-id="f3133-144">Plik PDB zestawu może być osadzony w samym zestawie ( `.dll` ) przy użyciu poniższego ustawienia.</span><span class="sxs-lookup"><span data-stu-id="f3133-144">The PDB file for an assembly can be embedded into the assembly itself (the `.dll`) using the setting below.</span></span> <span data-ttu-id="f3133-145">Ponieważ symbole są częścią zestawu, będą również częścią aplikacji jednoplikowej:</span><span class="sxs-lookup"><span data-stu-id="f3133-145">Since the symbols are part of the assembly, they will be part of the single-file application as well:</span></span>

```xml
<DebugType>embedded</DebugType>
```

<span data-ttu-id="f3133-146">Na przykład Dodaj następującą właściwość do pliku projektu zestawu, aby osadzić plik PDB w tym zestawie:</span><span class="sxs-lookup"><span data-stu-id="f3133-146">For example, add the following property to the project file of an assembly to embed the PDB file to that assembly:</span></span>

```xml
<PropertyGroup>
  <DebugType>embedded</DebugType>
</PropertyGroup>
```

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="f3133-147">Publikowanie pojedynczego pliku aplikacji — interfejs wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="f3133-147">Publish a single file app - CLI</span></span>

<span data-ttu-id="f3133-148">Opublikuj aplikację pojedynczego pliku przy użyciu polecenia [dotnet Publish](../tools/dotnet-publish.md) .</span><span class="sxs-lookup"><span data-stu-id="f3133-148">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="f3133-149">Po opublikowaniu aplikacji ustaw następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="f3133-149">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="f3133-150">Publikuj dla określonego środowiska uruchomieniowego: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="f3133-150">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="f3133-151">Publikuj jako pojedynczy plik: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="f3133-151">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="f3133-152">W poniższym przykładzie jest publikowana aplikacja dla systemu Windows jako samodzielna aplikacja pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="f3133-152">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="f3133-153">Poniższy przykład umożliwia opublikowanie aplikacji dla systemu Linux jako zależnej od struktury aplikacji pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="f3133-153">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="f3133-154">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="f3133-154">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="f3133-155">Publikowanie aplikacji pojedynczego pliku — Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3133-155">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="f3133-156">Program Visual Studio tworzy Profile publikowania wielokrotnego użytku, które kontrolują sposób publikowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f3133-156">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="f3133-157">W okienku **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt, który chcesz opublikować.</span><span class="sxs-lookup"><span data-stu-id="f3133-157">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="f3133-158">Kliknij pozycję **Opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="f3133-158">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Eksplorator rozwiązań z menu po kliknięciu prawym przyciskiem myszy wyróżnianie opcji Publikuj.":::

    <span data-ttu-id="f3133-160">Jeśli nie masz jeszcze profilu publikowania, postępuj zgodnie z instrukcjami, aby utworzyć jeden, i wybierz typ docelowy **folderu** .</span><span class="sxs-lookup"><span data-stu-id="f3133-160">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="f3133-161">Wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="f3133-161">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Eksplorator rozwiązań z menu po kliknięciu prawym przyciskiem myszy wyróżnianie opcji Publikuj.":::

01. <span data-ttu-id="f3133-163">W oknie dialogowym **Ustawienia profilu** ustaw następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="f3133-163">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="f3133-164">Ustaw **Tryb wdrożenia** na **własny**.</span><span class="sxs-lookup"><span data-stu-id="f3133-164">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="f3133-165">Ustaw **docelowy środowisko uruchomieniowe** na platformę, w której chcesz publikować.</span><span class="sxs-lookup"><span data-stu-id="f3133-165">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="f3133-166">Wybierz pozycję **Wygeneruj pojedynczy plik**.</span><span class="sxs-lookup"><span data-stu-id="f3133-166">Select **Produce single file**.</span></span>

    <span data-ttu-id="f3133-167">Wybierz pozycję **Zapisz** , aby zapisać ustawienia i powrócić do okna dialogowego **Publikowanie** .</span><span class="sxs-lookup"><span data-stu-id="f3133-167">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Eksplorator rozwiązań z menu po kliknięciu prawym przyciskiem myszy wyróżnianie opcji Publikuj.":::

01. <span data-ttu-id="f3133-169">Wybierz pozycję **Publikuj** , aby opublikować aplikację jako pojedynczy plik.</span><span class="sxs-lookup"><span data-stu-id="f3133-169">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="f3133-170">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą programu Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f3133-170">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="f3133-171">Publikowanie aplikacji pojedynczego pliku — Visual Studio dla komputerów Mac</span><span class="sxs-lookup"><span data-stu-id="f3133-171">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="f3133-172">Visual Studio dla komputerów Mac nie udostępnia opcji publikowania aplikacji jako pojedynczego pliku.</span><span class="sxs-lookup"><span data-stu-id="f3133-172">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="f3133-173">Należy opublikować ręcznie, postępując zgodnie z instrukcjami zawartymi w sekcji [Publikowanie pojedynczego pliku App-CLI](#publish-a-single-file-app---cli) .</span><span class="sxs-lookup"><span data-stu-id="f3133-173">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="f3133-174">Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="f3133-174">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3133-175">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f3133-175">See also</span></span>

- <span data-ttu-id="f3133-176">[Wdrażanie aplikacji .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="f3133-176">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="f3133-177">[Publikowanie aplikacji platformy .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="f3133-177">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="f3133-178">[Publikowanie aplikacji platformy .NET Core w programie Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f3133-178">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="f3133-179">[ `dotnet publish` polecenie](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="f3133-179">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
