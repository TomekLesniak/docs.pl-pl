---
title: Omówienie zestawu SDK programu .NET
titleSuffix: ''
description: Dowiedz się więcej o zestawach SDK projektu .NET.
ms.date: 09/17/2020
ms.topic: conceptual
ms.openlocfilehash: 6b6651f674f09d5d0d18ddb873096037ad3b2ba5
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247579"
---
# <a name="net-project-sdks"></a><span data-ttu-id="96a11-103">Zestawy SDK projektu .NET</span><span class="sxs-lookup"><span data-stu-id="96a11-103">.NET project SDKs</span></span>

<span data-ttu-id="96a11-104">Projekty .NET Core i .NET 5,0 i nowsze są skojarzone z zestawem SDK (Software Development Kit).</span><span class="sxs-lookup"><span data-stu-id="96a11-104">.NET Core and .NET 5.0 and later projects are associated with a software development kit (SDK).</span></span> <span data-ttu-id="96a11-105">Każdy *zestaw SDK projektu* to zestaw [obiektów docelowych](/visualstudio/msbuild/msbuild-targets) programu MSBuild i skojarzonych [zadań](/visualstudio/msbuild/msbuild-tasks) , które są odpowiedzialne za kompilowanie, pakowanie i publikowanie kodu.</span><span class="sxs-lookup"><span data-stu-id="96a11-105">Each *project SDK* is a set of MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and associated [tasks](/visualstudio/msbuild/msbuild-tasks) that are responsible for compiling, packing, and publishing code.</span></span> <span data-ttu-id="96a11-106">Projekt, który odwołuje się do zestawu SDK projektu, jest czasami określany jako *projekt w stylu zestawu SDK*.</span><span class="sxs-lookup"><span data-stu-id="96a11-106">A project that references a project SDK is sometimes referred to as an *SDK-style project*.</span></span>

## <a name="available-sdks"></a><span data-ttu-id="96a11-107">Dostępne zestawy SDK</span><span class="sxs-lookup"><span data-stu-id="96a11-107">Available SDKs</span></span>

<span data-ttu-id="96a11-108">Dostępne są następujące zestawy SDK:</span><span class="sxs-lookup"><span data-stu-id="96a11-108">The following SDKs are available:</span></span>

| <span data-ttu-id="96a11-109">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="96a11-109">ID</span></span> | <span data-ttu-id="96a11-110">Opis</span><span class="sxs-lookup"><span data-stu-id="96a11-110">Description</span></span> | <span data-ttu-id="96a11-111">Repozytorium</span><span class="sxs-lookup"><span data-stu-id="96a11-111">Repo</span></span>|
| - | - | - |
| `Microsoft.NET.Sdk` | <span data-ttu-id="96a11-112">Zestaw SDK platformy .NET</span><span class="sxs-lookup"><span data-stu-id="96a11-112">The .NET SDK</span></span> | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Web` | <span data-ttu-id="96a11-113">[Zestaw SDK sieci Web](/aspnet/core/razor-pages/web-sdk) platformy .NET</span><span class="sxs-lookup"><span data-stu-id="96a11-113">The .NET [Web SDK](/aspnet/core/razor-pages/web-sdk)</span></span> | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Razor` | <span data-ttu-id="96a11-114">[Zestaw SDK Razor](/aspnet/core/razor-pages/sdk) dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="96a11-114">The .NET [Razor SDK](/aspnet/core/razor-pages/sdk)</span></span> |
| `Microsoft.NET.Sdk.Worker` | <span data-ttu-id="96a11-115">Zestaw SDK usługi programu .NET Worker</span><span class="sxs-lookup"><span data-stu-id="96a11-115">The .NET Worker Service SDK</span></span> |
| `Microsoft.NET.Sdk.WindowsDesktop` | <span data-ttu-id="96a11-116">Zestawy kontrolne i zestaw SDK WPF\*</span><span class="sxs-lookup"><span data-stu-id="96a11-116">The WinForms and WPF SDK\*</span></span> | <span data-ttu-id="96a11-117"><https://github.com/dotnet/winforms> i <https://github.com/dotnet/wpf></span><span class="sxs-lookup"><span data-stu-id="96a11-117"><https://github.com/dotnet/winforms> and <https://github.com/dotnet/wpf></span></span> |

<span data-ttu-id="96a11-118">Zestaw SDK platformy .NET jest podstawowym zestawem SDK dla platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="96a11-118">The .NET SDK is the base SDK for .NET.</span></span> <span data-ttu-id="96a11-119">Inne zestawy SDK odwołują się do zestawu .NET SDK i projekty, które są skojarzone z innymi zestawami SDK, mają wszystkie dostępne dla nich właściwości.</span><span class="sxs-lookup"><span data-stu-id="96a11-119">The other SDKs reference the .NET SDK, and projects that are associated with the other SDKs have all the .NET SDK properties available to them.</span></span> <span data-ttu-id="96a11-120">Zestaw SDK sieci Web, na przykład, zależy od zestawu .NET SDK i zestawu Razor SDK.</span><span class="sxs-lookup"><span data-stu-id="96a11-120">The Web SDK, for example, depends on both the .NET SDK and the Razor SDK.</span></span>

<span data-ttu-id="96a11-121">Możesz również utworzyć własny zestaw SDK, który może być dystrybuowany za pośrednictwem programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="96a11-121">You can also author your own SDK that can be distributed via NuGet.</span></span>

<span data-ttu-id="96a11-122">\* Począwszy od platformy .NET 5,0, projekty Windows Forms i Windows Presentation Foundation (WPF) powinny określać zestaw .NET SDK ( `Microsoft.NET.Sdk` ), a nie `Microsoft.NET.Sdk.WindowsDesktop` .</span><span class="sxs-lookup"><span data-stu-id="96a11-122">\* Starting in .NET 5.0, Windows Forms and Windows Presentation Foundation (WPF) projects should specify the .NET SDK (`Microsoft.NET.Sdk`) instead of `Microsoft.NET.Sdk.WindowsDesktop`.</span></span> <span data-ttu-id="96a11-123">W przypadku tych projektów ustawienie `TargetFramework` dla opcji `net5.0-windows` i `UseWPF` lub `UseWindowsForms` na `true` spowoduje automatyczne zaimportowanie zestawu Windows Desktop SDK.</span><span class="sxs-lookup"><span data-stu-id="96a11-123">For these projects, setting `TargetFramework` to `net5.0-windows` and `UseWPF` or `UseWindowsForms` to `true` will automatically import the Windows desktop SDK.</span></span> <span data-ttu-id="96a11-124">Jeśli projekt jest przeznaczony dla programu .NET 5,0 lub nowszego i określa `Microsoft.NET.Sdk.WindowsDesktop` zestaw SDK, uzyskasz NETSDK1137 z ostrzeżeniem dotyczącym kompilacji.</span><span class="sxs-lookup"><span data-stu-id="96a11-124">If your project targets .NET 5.0 or later and specifies the `Microsoft.NET.Sdk.WindowsDesktop` SDK, you'll get build warning NETSDK1137.</span></span>

## <a name="project-files"></a><span data-ttu-id="96a11-125">Pliki projektu</span><span class="sxs-lookup"><span data-stu-id="96a11-125">Project files</span></span>

<span data-ttu-id="96a11-126">Projekty platformy .NET są oparte na formacie programu [MSBuild](/visualstudio/msbuild/msbuild) .</span><span class="sxs-lookup"><span data-stu-id="96a11-126">.NET projects are based on the [MSBuild](/visualstudio/msbuild/msbuild) format.</span></span> <span data-ttu-id="96a11-127">Pliki projektu, które mają rozszerzenia, takie jak *. csproj* dla projektów C# i *. fsproj* dla projektów F #, są w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="96a11-127">Project files, which have extensions like *.csproj* for C# projects and *.fsproj* for F# projects, are in XML format.</span></span> <span data-ttu-id="96a11-128">Głównym elementem pliku projektu MSBuild jest element [projektu](/visualstudio/msbuild/project-element-msbuild) .</span><span class="sxs-lookup"><span data-stu-id="96a11-128">The root element of an MSBuild project file is the [Project](/visualstudio/msbuild/project-element-msbuild) element.</span></span> <span data-ttu-id="96a11-129">`Project`Element ma opcjonalny `Sdk` atrybut, który określa zestaw SDK (i wersję) do użycia.</span><span class="sxs-lookup"><span data-stu-id="96a11-129">The `Project` element has an optional `Sdk` attribute that specifies which SDK (and version) to use.</span></span> <span data-ttu-id="96a11-130">Aby użyć narzędzi .NET i skompilować swój kod, należy ustawić `Sdk` atrybut na jeden z identyfikatorów w tabeli [dostępnych zestawów SDK](#available-sdks) .</span><span class="sxs-lookup"><span data-stu-id="96a11-130">To use the .NET tools and build your code, set the `Sdk` attribute to one of the IDs in the [Available SDKs](#available-sdks) table.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

<span data-ttu-id="96a11-131">Aby określić zestaw SDK pochodzący z programu NuGet, należy dołączyć wersję na końcu nazwy lub określić nazwę i wersję w *global.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="96a11-131">To specify an SDK that comes from NuGet, include the version at the end of the name, or specify the name and version in the *global.json* file.</span></span>

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

<span data-ttu-id="96a11-132">Innym sposobem określenia zestawu SDK jest element najwyższego poziomu [zestawu SDK](/visualstudio/msbuild/sdk-element-msbuild) :</span><span class="sxs-lookup"><span data-stu-id="96a11-132">Another way to specify the SDK is with the top-level [Sdk](/visualstudio/msbuild/sdk-element-msbuild) element:</span></span>

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

<span data-ttu-id="96a11-133">Odwołanie do zestawu SDK w jednym z tych sposobów znacznie upraszcza pliki projektu dla platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="96a11-133">Referencing an SDK in one of these ways greatly simplifies project files for .NET.</span></span> <span data-ttu-id="96a11-134">Podczas oceniania projektu, MSBuild dodaje niejawne Importy w `Sdk.props` górnej części pliku projektu i `Sdk.targets` w dolnej części.</span><span class="sxs-lookup"><span data-stu-id="96a11-134">While evaluating the project, MSBuild adds implicit imports for `Sdk.props` at the top of the project file and `Sdk.targets` at the bottom.</span></span>

```xml
<Project>
  <!-- Implicit top import -->
  <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
  ...
  <!-- Implicit bottom import -->
  <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

> [!TIP]
> <span data-ttu-id="96a11-135">Na komputerze z systemem Windows pliki *SDK. props* i *SDK. targets* można znaleźć w folderze *%ProgramFiles%\dotnet\sdk \\ [wersja] \Sdks\Microsoft.NET.Sdk\Sdk* .</span><span class="sxs-lookup"><span data-stu-id="96a11-135">On a Windows machine, the *Sdk.props* and *Sdk.targets* files can be found in the *%ProgramFiles%\dotnet\sdk\\[version]\Sdks\Microsoft.NET.Sdk\Sdk* folder.</span></span>

### <a name="preprocess-the-project-file"></a><span data-ttu-id="96a11-136">Wstępnie przetwórz plik projektu</span><span class="sxs-lookup"><span data-stu-id="96a11-136">Preprocess the project file</span></span>

<span data-ttu-id="96a11-137">Można zobaczyć w pełni rozwinięty projekt, gdy program MSBuild widzi go po zestawie SDK i jego obiektach docelowych za pomocą `dotnet msbuild -preprocess` polecenia.</span><span class="sxs-lookup"><span data-stu-id="96a11-137">You can see the fully expanded project as MSBuild sees it after the SDK and its targets are included by using the `dotnet msbuild -preprocess` command.</span></span> <span data-ttu-id="96a11-138">Przełącznik [preprocesora](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) [`dotnet msbuild`](../tools/dotnet-msbuild.md) polecenia pokazuje, które pliki są importowane, ich źródła i ich wkłady do kompilacji bez faktycznego kompilowania projektu.</span><span class="sxs-lookup"><span data-stu-id="96a11-138">The [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) switch of the [`dotnet msbuild`](../tools/dotnet-msbuild.md) command shows which files are imported, their sources, and their contributions to the build without actually building the project.</span></span>

<span data-ttu-id="96a11-139">Jeśli projekt ma wiele platform docelowych, należy skoncentrować wyniki polecenia tylko dla jednej struktury, określając ją jako właściwość programu MSBuild.</span><span class="sxs-lookup"><span data-stu-id="96a11-139">If the project has multiple target frameworks, focus the results of the command on only one framework by specifying it as an MSBuild property.</span></span> <span data-ttu-id="96a11-140">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="96a11-140">For example:</span></span>

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a><span data-ttu-id="96a11-141">Domyślna kompilacja obejmuje</span><span class="sxs-lookup"><span data-stu-id="96a11-141">Default compilation includes</span></span>

<span data-ttu-id="96a11-142">Wartość domyślna to include i Exclude dla elementów kompilowania, zasobów osadzonych i `None` elementów zdefiniowanych w zestawie SDK.</span><span class="sxs-lookup"><span data-stu-id="96a11-142">The default includes and excludes for compile items, embedded resources, and `None` items are defined in the SDK.</span></span> <span data-ttu-id="96a11-143">W przeciwieństwie do projektów .NET Framework nie należących do zestawu SDK, nie trzeba określać tych elementów w pliku projektu, ponieważ ustawienia domyślne obejmują najczęściej spotykane przypadki użycia.</span><span class="sxs-lookup"><span data-stu-id="96a11-143">Unlike non-SDK .NET Framework projects, you don't need to specify these items in your project file, because the defaults cover most common use cases.</span></span> <span data-ttu-id="96a11-144">Sprawia to, że plik projektu jest mniejszy i łatwiejszy do zrozumienia i edycji, w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="96a11-144">This makes the project file smaller and easier to understand and edit by hand, if needed.</span></span>

<span data-ttu-id="96a11-145">W poniższej tabeli pokazano, które elementy i które [elementy globalne](https://en.wikipedia.org/wiki/Glob_(programming)) są uwzględnione i wykluczone w zestawie SDK platformy .NET:</span><span class="sxs-lookup"><span data-stu-id="96a11-145">The following table shows which elements and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are included and excluded in the .NET SDK:</span></span>

| <span data-ttu-id="96a11-146">Element</span><span class="sxs-lookup"><span data-stu-id="96a11-146">Element</span></span>           | <span data-ttu-id="96a11-147">Uwzględnij globalizowania</span><span class="sxs-lookup"><span data-stu-id="96a11-147">Include glob</span></span>                              | <span data-ttu-id="96a11-148">Wyklucz globalizowania</span><span class="sxs-lookup"><span data-stu-id="96a11-148">Exclude glob</span></span>                                                  | <span data-ttu-id="96a11-149">Usuń globalizowania</span><span class="sxs-lookup"><span data-stu-id="96a11-149">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| <span data-ttu-id="96a11-150">Opracowania</span><span class="sxs-lookup"><span data-stu-id="96a11-150">Compile</span></span>           | <span data-ttu-id="96a11-151">\*\*/\*. cs (lub inne rozszerzenia językowe)</span><span class="sxs-lookup"><span data-stu-id="96a11-151">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="96a11-152">\*\*/\*Użytkownicy  \*\*/\*.\* proj  \*\*/\*. sln  \*\*/\*. vssscc</span><span class="sxs-lookup"><span data-stu-id="96a11-152">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="96a11-153">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="96a11-153">N/A</span></span>                      |
| <span data-ttu-id="96a11-154">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="96a11-154">EmbeddedResource</span></span>  | <span data-ttu-id="96a11-155">\*\*/\*. resx</span><span class="sxs-lookup"><span data-stu-id="96a11-155">\*\*/\*.resx</span></span>                              | <span data-ttu-id="96a11-156">\*\*/\*Użytkownicy \*\*/\*.\* proj \*\*/\*. sln \*\*/\*. vssscc</span><span class="sxs-lookup"><span data-stu-id="96a11-156">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="96a11-157">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="96a11-157">N/A</span></span>                      |
| <span data-ttu-id="96a11-158">Brak</span><span class="sxs-lookup"><span data-stu-id="96a11-158">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="96a11-159">\*\*/\*Użytkownicy \*\*/\*.\* proj \*\*/\*. sln \*\*/\*. vssscc</span><span class="sxs-lookup"><span data-stu-id="96a11-159">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="96a11-160">\*\*/\*Rejestr \*\*/\*. resx</span><span class="sxs-lookup"><span data-stu-id="96a11-160">\*\*/\*.cs; \*\*/\*.resx</span></span> |

> [!NOTE]
> <span data-ttu-id="96a11-161">`./bin`Foldery i `./obj` , które są reprezentowane przez `$(BaseOutputPath)` właściwości i programu `$(BaseIntermediateOutputPath)` MSBuild, są domyślnie wykluczone z elementy globalne.</span><span class="sxs-lookup"><span data-stu-id="96a11-161">The `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, are excluded from the globs by default.</span></span> <span data-ttu-id="96a11-162">Wykluczenia są reprezentowane przez właściwość `$(DefaultItemExcludes)` .</span><span class="sxs-lookup"><span data-stu-id="96a11-162">Excludes are represented by the property `$(DefaultItemExcludes)`.</span></span>

#### <a name="build-errors"></a><span data-ttu-id="96a11-163">Błędy kompilacji</span><span class="sxs-lookup"><span data-stu-id="96a11-163">Build errors</span></span>

<span data-ttu-id="96a11-164">Jeśli jawnie zdefiniujesz dowolny z tych elementów w pliku projektu, możesz uzyskać błąd kompilacji "NETSDK1022" podobny do poniższego:</span><span class="sxs-lookup"><span data-stu-id="96a11-164">If you explicitly define any of these items in your project file, you're likely to get a "NETSDK1022" build error similar to the following:</span></span>

  > <span data-ttu-id="96a11-165">Uwzględniono zduplikowane elementy "Kompiluj".</span><span class="sxs-lookup"><span data-stu-id="96a11-165">Duplicate 'Compile' items were included.</span></span> <span data-ttu-id="96a11-166">Zestaw SDK platformy .NET domyślnie zawiera elementy "Kompiluj" z katalogu projektu.</span><span class="sxs-lookup"><span data-stu-id="96a11-166">The .NET SDK includes 'Compile' items from your project directory by default.</span></span> <span data-ttu-id="96a11-167">Możesz usunąć te elementy z pliku projektu lub ustawić właściwość "EnableDefaultCompileItems" na wartość "false", jeśli chcesz jawnie uwzględnić je w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="96a11-167">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

  > <span data-ttu-id="96a11-168">Uwzględniono zduplikowane elementy "EmbeddedResource".</span><span class="sxs-lookup"><span data-stu-id="96a11-168">Duplicate 'EmbeddedResource' items were included.</span></span> <span data-ttu-id="96a11-169">Zestaw SDK platformy .NET domyślnie zawiera elementy "EmbeddedResource" z katalogu projektu.</span><span class="sxs-lookup"><span data-stu-id="96a11-169">The .NET SDK includes 'EmbeddedResource' items from your project directory by default.</span></span> <span data-ttu-id="96a11-170">Możesz usunąć te elementy z pliku projektu lub ustawić właściwość "EnableDefaultEmbeddedResourceItems" na wartość "false", jeśli chcesz jawnie uwzględnić je w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="96a11-170">You can either remove these items from your project file, or set the 'EnableDefaultEmbeddedResourceItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="96a11-171">Aby rozwiązać te błędy, wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="96a11-171">To resolve the errors, do one of the following:</span></span>

- <span data-ttu-id="96a11-172">Usuń jawne `Compile` , `EmbeddedResource` lub elementy, `None` które są zgodne z niejawnymi wymienionymi w poprzedniej tabeli.</span><span class="sxs-lookup"><span data-stu-id="96a11-172">Remove the explicit `Compile`, `EmbeddedResource`, or `None` items that match the implicit ones listed on the previous table.</span></span>

- <span data-ttu-id="96a11-173">Ustaw `EnableDefaultItems` Właściwość na `false` , aby wyłączyć wszystkie niejawne dołączenie do pliku:</span><span class="sxs-lookup"><span data-stu-id="96a11-173">Set the `EnableDefaultItems` property to `false` to disable all implicit file inclusion:</span></span>

  ```xml
  <PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
  </PropertyGroup>
  ```

  <span data-ttu-id="96a11-174">Jeśli chcesz określić pliki do opublikowania w aplikacji, nadal możesz użyć znanych mechanizmów programu MSBuild dla tego elementu, na przykład `Content` .</span><span class="sxs-lookup"><span data-stu-id="96a11-174">If you want to specify files to be published with your app, you can still use the known MSBuild mechanisms for that, for example, the `Content` element.</span></span>

- <span data-ttu-id="96a11-175">Selektywnie Wyłącz tylko `Compile` , `EmbeddedResource` lub `None` elementy globalne, ustawiając `EnableDefaultCompileItems` Właściwość, `EnableDefaultEmbeddedResourceItems` , lub `EnableDefaultNoneItems` na `false` :</span><span class="sxs-lookup"><span data-stu-id="96a11-175">Selectively disable only `Compile`, `EmbeddedResource`, or `None` globs by setting the `EnableDefaultCompileItems`, `EnableDefaultEmbeddedResourceItems`, or `EnableDefaultNoneItems` property to `false`:</span></span>

  ```xml
  <PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
    <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
  </PropertyGroup>
  ```

  <span data-ttu-id="96a11-176">Jeśli wyłączysz tylko `Compile` elementy globalne, Eksplorator rozwiązań w programie Visual Studio nadal pokazuje \* elementy CS jako część projektu, uwzględnione jako `None` elementy.</span><span class="sxs-lookup"><span data-stu-id="96a11-176">If you only disable `Compile` globs, Solution Explorer in Visual Studio still shows \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="96a11-177">Aby wyłączyć niejawną `None` globalizowania, ustaw `EnableDefaultNoneItems` ją na wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="96a11-177">To disable the implicit `None` glob, set `EnableDefaultNoneItems` to `false` too.</span></span>

## <a name="customize-the-build"></a><span data-ttu-id="96a11-178">Dostosuj kompilację</span><span class="sxs-lookup"><span data-stu-id="96a11-178">Customize the build</span></span>

<span data-ttu-id="96a11-179">Istnieją różne sposoby [dostosowywania kompilacji](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="96a11-179">There are various ways to [customize a build](/visualstudio/msbuild/customize-your-build).</span></span> <span data-ttu-id="96a11-180">Możesz chcieć przesłonić Właściwość przez przekazanie jej jako argumentu do polecenia [MSBuild](/visualstudio/msbuild/msbuild-command-line-reference) lub [dotnet](../tools/index.md) .</span><span class="sxs-lookup"><span data-stu-id="96a11-180">You may want to override a property by passing it as an argument to an [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) or [dotnet](../tools/index.md) command.</span></span> <span data-ttu-id="96a11-181">Możesz również dodać właściwość do pliku projektu lub do pliku *Directory. Build. props* .</span><span class="sxs-lookup"><span data-stu-id="96a11-181">You can also add the property to the project file or to a *Directory.Build.props* file.</span></span> <span data-ttu-id="96a11-182">Aby uzyskać listę przydatnych właściwości projektów .NET, zobacz [Dokumentacja programu MSBuild dla projektów zestawu SDK platformy .NET](msbuild-props.md).</span><span class="sxs-lookup"><span data-stu-id="96a11-182">For a list of useful properties for .NET projects, see [MSBuild reference for .NET SDK projects](msbuild-props.md).</span></span>

### <a name="custom-targets"></a><span data-ttu-id="96a11-183">Niestandardowe elementy docelowe</span><span class="sxs-lookup"><span data-stu-id="96a11-183">Custom targets</span></span>

<span data-ttu-id="96a11-184">Projekty platformy .NET mogą spakować niestandardowe cele programu MSBuild i właściwości do użycia przez projekty korzystające z pakietu.</span><span class="sxs-lookup"><span data-stu-id="96a11-184">.NET projects can package custom MSBuild targets and properties for use by projects that consume the package.</span></span> <span data-ttu-id="96a11-185">Użyj tego typu rozszerzalności, gdy chcesz:</span><span class="sxs-lookup"><span data-stu-id="96a11-185">Use this type of extensibility when you want to:</span></span>

- <span data-ttu-id="96a11-186">Rozwiń proces kompilacji.</span><span class="sxs-lookup"><span data-stu-id="96a11-186">Extend the build process.</span></span>
- <span data-ttu-id="96a11-187">Dostęp do artefaktów procesu kompilacji, takich jak wygenerowane pliki.</span><span class="sxs-lookup"><span data-stu-id="96a11-187">Access artifacts of the build process, such as generated files.</span></span>
- <span data-ttu-id="96a11-188">Sprawdź konfigurację, pod którą jest wywoływana kompilacja.</span><span class="sxs-lookup"><span data-stu-id="96a11-188">Inspect the configuration under which the build is invoked.</span></span>

<span data-ttu-id="96a11-189">Dodawanie niestandardowych elementów docelowych kompilacji lub właściwości przez umieszczenie plików w formularzu `<package_id>.targets` lub `<package_id>.props` (na przykład `Contoso.Utility.UsefulStuff.targets` ) w folderze *Build* projektu.</span><span class="sxs-lookup"><span data-stu-id="96a11-189">You add custom build targets or properties by placing files in the form `<package_id>.targets` or `<package_id>.props` (for example, `Contoso.Utility.UsefulStuff.targets`) in the *build* folder of the project.</span></span>

<span data-ttu-id="96a11-190">Poniższy kod XML to fragment z pliku *. csproj* , który instruuje [`dotnet pack`](../tools/dotnet-pack.md) polecenie do pakowania.</span><span class="sxs-lookup"><span data-stu-id="96a11-190">The following XML is a snippet from a *.csproj* file that instructs the [`dotnet pack`](../tools/dotnet-pack.md) command what to package.</span></span> <span data-ttu-id="96a11-191">`<ItemGroup Label="dotnet pack instructions">`Element umieszcza pliki docelowe w folderze *kompilacji* wewnątrz pakietu.</span><span class="sxs-lookup"><span data-stu-id="96a11-191">The `<ItemGroup Label="dotnet pack instructions">` element places the targets files into the *build* folder inside the package.</span></span> <span data-ttu-id="96a11-192">`<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">`Element umieszcza zestawy i pliki *JSON* w folderze *Build* .</span><span class="sxs-lookup"><span data-stu-id="96a11-192">The `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` element places the assemblies and *.json* files into the *build* folder.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  ...
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  ...
  
</Project>
```

<span data-ttu-id="96a11-193">Aby użyć niestandardowego obiektu docelowego w projekcie, Dodaj element wskazujący `PackageReference` pakiet i jego wersję.</span><span class="sxs-lookup"><span data-stu-id="96a11-193">To consume a custom target in your project, add a `PackageReference` element that points to the package and its version.</span></span> <span data-ttu-id="96a11-194">W przeciwieństwie do narzędzi, pakiet Custom targets jest uwzględniany w zamknięciu zależności projektu zużywanego.</span><span class="sxs-lookup"><span data-stu-id="96a11-194">Unlike the tools, the custom targets package is included in the consuming project's dependency closure.</span></span>

<span data-ttu-id="96a11-195">Można skonfigurować sposób używania niestandardowego obiektu docelowego.</span><span class="sxs-lookup"><span data-stu-id="96a11-195">You can configure how to use the custom target.</span></span> <span data-ttu-id="96a11-196">Ponieważ jest to element docelowy programu MSBuild, może on zależeć od danego elementu docelowego, działać po innym elemencie docelowym lub być wywoływana ręcznie przy użyciu `dotnet msbuild -t:<target-name>` polecenia.</span><span class="sxs-lookup"><span data-stu-id="96a11-196">Since it's an MSBuild target, it can depend on a given target, run after another target, or be manually invoked by using the `dotnet msbuild -t:<target-name>` command.</span></span> <span data-ttu-id="96a11-197">Aby jednak zapewnić lepsze środowisko użytkownika, można połączyć narzędzia dla poszczególnych projektów i niestandardowe elementy docelowe.</span><span class="sxs-lookup"><span data-stu-id="96a11-197">However, to provide a better user experience, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="96a11-198">W tym scenariuszu narzędzie dla projektu akceptuje wszelkie parametry, które są potrzebne, i tłumaczy je na wymagane [`dotnet msbuild`](../tools/dotnet-msbuild.md) wywołanie, które wykonuje miejsce docelowe.</span><span class="sxs-lookup"><span data-stu-id="96a11-198">In this scenario, the per-project tool accepts whatever parameters are needed and translates that into the required [`dotnet msbuild`](../tools/dotnet-msbuild.md) invocation that executes the target.</span></span> <span data-ttu-id="96a11-199">Możesz zobaczyć przykład tego rodzaju synergii w repozytorium [przykładów Hackathonych](https://github.com/dotnet/MVPSummitHackathon2016) w projekcie programu 2016 MVP [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) .</span><span class="sxs-lookup"><span data-stu-id="96a11-199">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="see-also"></a><span data-ttu-id="96a11-200">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96a11-200">See also</span></span>

- [<span data-ttu-id="96a11-201">Instalowanie programu .NET Core</span><span class="sxs-lookup"><span data-stu-id="96a11-201">Install .NET Core</span></span>](../install/index.yml)
- [<span data-ttu-id="96a11-202">Jak używać zestawów SDK projektu MSBuild</span><span class="sxs-lookup"><span data-stu-id="96a11-202">How to use MSBuild project SDKs</span></span>](/visualstudio/msbuild/how-to-use-project-sdk)
- [<span data-ttu-id="96a11-203">Pakowanie niestandardowych elementów docelowych programu MSBuild i ich właściwości przy użyciu narzędzia NuGet</span><span class="sxs-lookup"><span data-stu-id="96a11-203">Package custom MSBuild targets and props with NuGet</span></span>](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
