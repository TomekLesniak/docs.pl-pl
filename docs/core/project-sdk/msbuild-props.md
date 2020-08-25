---
title: Właściwości programu MSBuild dla Microsoft. NET. Sdk
description: Odwołanie do właściwości i elementów programu MSBuild, które są zrozumiałe dla zestaw .NET Core SDK.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 39cbd18121d2b8659b2f5270f39624798f4ebbdc
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810526"
---
# <a name="msbuild-reference-for-net-core-sdk-projects"></a><span data-ttu-id="da953-103">Dokumentacja programu MSBuild dla projektów zestaw .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="da953-103">MSBuild reference for .NET Core SDK projects</span></span>

<span data-ttu-id="da953-104">Ta strona jest odwołaniem do właściwości i elementów programu MSBuild, których można użyć do konfigurowania projektów platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="da953-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="da953-105">Ta strona jest w toku i nie wyświetla wszystkich przydatnych właściwości programu MSBuild dla zestaw .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="da953-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="da953-106">Aby zapoznać się z listą typowych właściwości programu MSBuild, zobacz [typowe właściwości programu MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="da953-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="da953-107">Właściwości struktury</span><span class="sxs-lookup"><span data-stu-id="da953-107">Framework properties</span></span>

- [<span data-ttu-id="da953-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="da953-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="da953-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="da953-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="da953-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="da953-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="da953-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="da953-111">TargetFramework</span></span>

<span data-ttu-id="da953-112">`TargetFramework`Właściwość określa wersję platformy docelowej dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="da953-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="da953-113">Aby zapoznać się z listą prawidłowych monikerów platformy docelowej, zobacz [platformę docelową w projektach w stylu zestawu SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="da953-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="da953-114">Aby uzyskać więcej informacji, zobacz [Platformy docelowe w projektach w stylu zestawu SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="da953-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="da953-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="da953-115">TargetFrameworks</span></span>

<span data-ttu-id="da953-116">Użyj `TargetFrameworks` właściwości, jeśli chcesz, aby aplikacja była przeznaczona dla wielu platform.</span><span class="sxs-lookup"><span data-stu-id="da953-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="da953-117">Aby zapoznać się z listą prawidłowych monikerów platformy docelowej, zobacz [platformę docelową w projektach w stylu zestawu SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="da953-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="da953-118">Ta właściwość jest ignorowana, jeśli `TargetFramework` określono (pojedynczo).</span><span class="sxs-lookup"><span data-stu-id="da953-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="da953-119">Aby uzyskać więcej informacji, zobacz [Platformy docelowe w projektach w stylu zestawu SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="da953-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="da953-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="da953-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="da953-121">Ta właściwość ma zastosowanie tylko do projektów korzystających z programu `netstandard1.x` .</span><span class="sxs-lookup"><span data-stu-id="da953-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="da953-122">Nie dotyczy to projektów, które używają `netstandard2.x` .</span><span class="sxs-lookup"><span data-stu-id="da953-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="da953-123">Użyj `NetStandardImplicitPackageVersion` właściwości, aby określić wersję platformy, która jest starsza niż wersja pakietu.</span><span class="sxs-lookup"><span data-stu-id="da953-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="da953-124">Plik projektu w poniższym przykładzie docelowym `netstandard1.3` , ale używa wersji 1.6.0 `NETStandard.Library` .</span><span class="sxs-lookup"><span data-stu-id="da953-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="da953-125">Właściwości pakietu</span><span class="sxs-lookup"><span data-stu-id="da953-125">Package properties</span></span>

<span data-ttu-id="da953-126">Można określić właściwości, takie jak `PackageId` ,,, `PackageVersion` `PackageIcon` `Title` i, `Description` aby opisać pakiet, który zostanie utworzony na podstawie projektu.</span><span class="sxs-lookup"><span data-stu-id="da953-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="da953-127">Aby uzyskać informacje o tych i innych właściwościach, zobacz [pakiet Target](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="da953-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="da953-128">Publikowanie właściwości i elementów</span><span class="sxs-lookup"><span data-stu-id="da953-128">Publish properties and items</span></span>

- [<span data-ttu-id="da953-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="da953-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="da953-130">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="da953-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="da953-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="da953-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="da953-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="da953-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="da953-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="da953-133">RuntimeIdentifier</span></span>

<span data-ttu-id="da953-134">`RuntimeIdentifier`Właściwość umożliwia określenie pojedynczego [identyfikatora środowiska uruchomieniowego (RID)](../rid-catalog.md) dla projektu.</span><span class="sxs-lookup"><span data-stu-id="da953-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="da953-135">Identyfikator RID umożliwia publikowanie samodzielnego wdrożenia.</span><span class="sxs-lookup"><span data-stu-id="da953-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="da953-136">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="da953-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="da953-137">`RuntimeIdentifiers`Właściwość pozwala określić rozdzielaną średnikami listę [identyfikatorów środowiska uruchomieniowego (RID)](../rid-catalog.md) dla projektu.</span><span class="sxs-lookup"><span data-stu-id="da953-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="da953-138">Użyj tej właściwości, jeśli chcesz opublikować dla wielu środowisk uruchomieniowych.</span><span class="sxs-lookup"><span data-stu-id="da953-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="da953-139">`RuntimeIdentifiers` jest używany podczas przywracania, aby upewnić się, że odpowiednie zasoby znajdują się na wykresie.</span><span class="sxs-lookup"><span data-stu-id="da953-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="da953-140">`RuntimeIdentifier` (pojedyncze) może zapewnić szybsze kompilacje, gdy wymagane jest tylko jedno środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="da953-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="da953-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="da953-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="da953-142">`TrimmerRootAssembly`Element umożliwia wykluczenie zestawu z [*przycinania*](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="da953-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="da953-143">Przycinanie jest procesem usuwania nieużywanych części środowiska uruchomieniowego z spakowanej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="da953-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="da953-144">W niektórych przypadkach przycinanie może niepoprawnie usunąć wymagane odwołania.</span><span class="sxs-lookup"><span data-stu-id="da953-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="da953-145">Poniższy kod XML wyklucza `System.Security` zestaw z przycinania.</span><span class="sxs-lookup"><span data-stu-id="da953-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="da953-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="da953-146">UseAppHost</span></span>

<span data-ttu-id="da953-147">`UseAppHost`Właściwość została wprowadzona w wersji 2.1.400 zestaw .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="da953-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="da953-148">Określa, czy dla wdrożenia jest tworzony natywny plik wykonywalny.</span><span class="sxs-lookup"><span data-stu-id="da953-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="da953-149">Natywny plik wykonywalny jest wymagany w przypadku wdrożeń samodzielnych.</span><span class="sxs-lookup"><span data-stu-id="da953-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="da953-150">W programie .NET Core 3,0 i jego nowszych wersjach domyślnie tworzony jest plik wykonywalny zależny od platformy.</span><span class="sxs-lookup"><span data-stu-id="da953-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="da953-151">Ustaw `UseAppHost` Właściwość na `false` , aby wyłączyć generowanie pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="da953-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="da953-152">Aby uzyskać więcej informacji na temat wdrażania, zobacz [wdrażanie aplikacji .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="da953-152">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="da953-153">Kompiluj właściwości</span><span class="sxs-lookup"><span data-stu-id="da953-153">Compile properties</span></span>

- [<span data-ttu-id="da953-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="da953-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="da953-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="da953-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="da953-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="da953-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="da953-157">`EmbeddedResourceUseDependentUponConvention`Właściwość określa, czy nazwy plików manifestu zasobów są generowane na podstawie informacji o typie w plikach źródłowych, które znajdują się w plikach zasobów.</span><span class="sxs-lookup"><span data-stu-id="da953-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="da953-158">Na przykład jeśli *Form1. resx* znajduje się w tym samym folderze co *Form1.cs*i `EmbeddedResourceUseDependentUponConvention` jest ustawiona na `true` , wygenerowany plik *resources* przyjmuje swoją nazwę z pierwszego typu zdefiniowanego w *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="da953-158">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="da953-159">Na przykład, jeśli `MyNamespace.Form1` jest pierwszym typem zdefiniowanym w *Form1.cs*, wygenerowana nazwa pliku ma *nazwę. Form1. resources*.</span><span class="sxs-lookup"><span data-stu-id="da953-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="da953-160">Jeśli `LogicalName` `ManifestResourceName` `DependentUpon` dla elementu określono wartość, lub lub metadanych `EmbeddedResource` , wygenerowana nazwa pliku manifestu dla tego pliku zasobów jest oparta na tym metadanych.</span><span class="sxs-lookup"><span data-stu-id="da953-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="da953-161">Domyślnie w nowym projekcie .NET Core Właściwość ta ma ustawioną wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="da953-161">By default, in a new .NET Core project, this property is set to `true`.</span></span> <span data-ttu-id="da953-162">Jeśli `false` `LogicalName` `ManifestResourceName` dla elementu w pliku projektu zostanie ustawiona wartość, i nie, lub `DependentUpon` dla tego parametru, `EmbeddedResource` Nazwa pliku manifestu zasobu jest oparta na głównej przestrzeni nazw projektu i względnej ścieżce pliku do pliku *resx* .</span><span class="sxs-lookup"><span data-stu-id="da953-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="da953-163">Aby uzyskać więcej informacji, zobacz [jak nazywa się plik manifestu zasobu](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="da953-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="da953-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="da953-164">LangVersion</span></span>

<span data-ttu-id="da953-165">`LangVersion`Właściwość umożliwia określenie konkretnej wersji języka programowania.</span><span class="sxs-lookup"><span data-stu-id="da953-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="da953-166">Na przykład jeśli chcesz uzyskać dostęp do funkcji wersji zapoznawczej języka C#, ustaw wartość `LangVersion` `preview` .</span><span class="sxs-lookup"><span data-stu-id="da953-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="da953-167">Aby uzyskać więcej informacji, zobacz [wersja języka C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="da953-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="code-analysis-properties"></a><span data-ttu-id="da953-168">Właściwości analizy kodu</span><span class="sxs-lookup"><span data-stu-id="da953-168">Code analysis properties</span></span>

### <a name="analysislevel"></a><span data-ttu-id="da953-169">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="da953-169">AnalysisLevel</span></span>

<span data-ttu-id="da953-170">`AnalysisLevel`Właściwość pozwala określić poziom analizy kodu.</span><span class="sxs-lookup"><span data-stu-id="da953-170">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="da953-171">Jeśli na przykład chcesz uzyskać dostęp do analizatorów kodu w wersji zapoznawczej, ustaw wartość `AnalysisLevel` `preview` .</span><span class="sxs-lookup"><span data-stu-id="da953-171">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="da953-172">Wartość domyślna to `latest`.</span><span class="sxs-lookup"><span data-stu-id="da953-172">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="da953-173">W poniższej tabeli przedstawiono dostępne opcje.</span><span class="sxs-lookup"><span data-stu-id="da953-173">The following table shows the available options.</span></span>

| <span data-ttu-id="da953-174">Wartość</span><span class="sxs-lookup"><span data-stu-id="da953-174">Value</span></span> | <span data-ttu-id="da953-175">Znaczenie</span><span class="sxs-lookup"><span data-stu-id="da953-175">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="da953-176">Używane są najnowsze analizatory kodu, które zostały wydane.</span><span class="sxs-lookup"><span data-stu-id="da953-176">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="da953-177">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="da953-177">This is the default.</span></span> |
| `preview` | <span data-ttu-id="da953-178">Są używane najnowsze analizatory kodu, nawet jeśli są one w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="da953-178">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="da953-179">Używany jest zestaw reguł, które zostały włączone dla wydania .NET 5,0, nawet jeśli są dostępne nowsze reguły.</span><span class="sxs-lookup"><span data-stu-id="da953-179">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="da953-180">Używany jest zestaw reguł, które zostały włączone dla wydania .NET 5,0, nawet jeśli są dostępne nowsze reguły.</span><span class="sxs-lookup"><span data-stu-id="da953-180">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="da953-181">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="da953-181">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="da953-182">`CodeAnalysisTreatWarningsAsErrors`Właściwość pozwala określić, czy ostrzeżenia analizy kodu powinny być traktowane jako ostrzeżenia i przerwać kompilację.</span><span class="sxs-lookup"><span data-stu-id="da953-182">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code analysis warnings should be treated as warnings and break the build.</span></span> <span data-ttu-id="da953-183">Jeśli używasz `-warnaserror` flagi podczas kompilowania projektów, ostrzeżenia [analizy kodu platformy .NET](../../fundamentals/productivity/code-analysis.md) również są traktowane jako błędy.</span><span class="sxs-lookup"><span data-stu-id="da953-183">If you use the `-warnaserror` flag when you build your projects, [.NET code analysis](../../fundamentals/productivity/code-analysis.md) warnings are also treated as errors.</span></span> <span data-ttu-id="da953-184">Jeśli chcesz, aby ostrzeżenia kompilatora były traktowane jako błędy, możesz ustawić `CodeAnalysisTreatWarningsAsErrors` Właściwość programu MSBuild na `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="da953-184">If you only want compiler warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="da953-185">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="da953-185">EnableNETAnalyzers</span></span>

<span data-ttu-id="da953-186">[Analiza kodu platformy .NET](../../fundamentals/productivity/code-analysis.md) jest domyślnie włączona dla projektów przeznaczonych dla platformy .NET 5,0 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="da953-186">[.NET Code analysis](../../fundamentals/productivity/code-analysis.md) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="da953-187">Możesz włączyć analizę kodu platformy .NET dla projektów przeznaczonych dla wcześniejszych wersji platformy .NET, ustawiając `EnableNETAnalyzers` Właściwość na true.</span><span class="sxs-lookup"><span data-stu-id="da953-187">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to true.</span></span> <span data-ttu-id="da953-188">Aby wyłączyć analizę kodu w dowolnym projekcie, należy ustawić tę właściwość na `false` .</span><span class="sxs-lookup"><span data-stu-id="da953-188">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="da953-189">Innym sposobem na włączenie analizy kodu .NET dla projektów przeznaczonych dla wersji .NET wcześniejszych niż .NET 5,0 jest ustawienie właściwości [AnalysisLevel](#analysislevel) na `latest` .</span><span class="sxs-lookup"><span data-stu-id="da953-189">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="da953-190">Właściwości konfiguracji czasu wykonywania</span><span class="sxs-lookup"><span data-stu-id="da953-190">Run-time configuration properties</span></span>

<span data-ttu-id="da953-191">Niektóre zachowania w czasie wykonywania można skonfigurować, określając właściwości programu MSBuild w pliku projektu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="da953-191">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="da953-192">Aby uzyskać informacje na temat innych sposobów konfigurowania zachowania w czasie wykonywania, zobacz [Ustawienia konfiguracji środowiska uruchomieniowego .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="da953-192">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="da953-193">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="da953-193">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="da953-194">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="da953-194">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="da953-195">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="da953-195">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="da953-196">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="da953-196">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="da953-197">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="da953-197">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="da953-198">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="da953-198">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="da953-199">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="da953-199">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="da953-200">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="da953-200">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="da953-201">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="da953-201">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="da953-202">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="da953-202">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="da953-203">`ConcurrentGarbageCollection`Właściwość określa, czy jest włączone [wyrzucanie elementów bezużytecznych w tle](../../standard/garbage-collection/background-gc.md) .</span><span class="sxs-lookup"><span data-stu-id="da953-203">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="da953-204">Ustaw wartość na `false` , aby wyłączyć wyrzucanie elementów bezużytecznych w tle.</span><span class="sxs-lookup"><span data-stu-id="da953-204">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="da953-205">Aby uzyskać więcej informacji, zobacz w [tle GC](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="da953-205">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="da953-206">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="da953-206">InvariantGlobalization</span></span>

<span data-ttu-id="da953-207">`InvariantGlobalization`Właściwość określa, czy aplikacja jest uruchamiana w trybie *globalizacji-niezmiennym* , co oznacza, że nie ma dostępu do danych specyficznych dla kultury.</span><span class="sxs-lookup"><span data-stu-id="da953-207">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="da953-208">Ustaw wartość tak, aby była `true` uruchamiana w trybie niezmiennym globalizacji.</span><span class="sxs-lookup"><span data-stu-id="da953-208">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="da953-209">Aby uzyskać więcej informacji, zobacz [tryb niezmienny](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="da953-209">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="da953-210">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="da953-210">RetainVMGarbageCollection</span></span>

<span data-ttu-id="da953-211">`RetainVMGarbageCollection`Właściwość konfiguruje moduł wyrzucania elementów bezużytecznych w celu umieszczenia usuniętych segmentów pamięci na liście gotowości do użycia w przyszłości lub zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="da953-211">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="da953-212">Ustawienie wartości `true` informującej Moduł wyrzucania elementów bezużytecznych w celu umieszczenia segmentów na liście gotowości.</span><span class="sxs-lookup"><span data-stu-id="da953-212">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="da953-213">Aby uzyskać więcej informacji, zobacz temat [zachowywanie maszyny wirtualnej](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="da953-213">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="da953-214">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="da953-214">ServerGarbageCollection</span></span>

<span data-ttu-id="da953-215">`ServerGarbageCollection`Właściwość określa, czy aplikacja używa [wyrzucania elementów bezużytecznych stacji roboczej lub odzyskiwania pamięci serwera](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="da953-215">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="da953-216">Ustaw wartość na, aby `true` użyć wyrzucania elementów bezużytecznych serwera.</span><span class="sxs-lookup"><span data-stu-id="da953-216">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="da953-217">Aby uzyskać więcej informacji, zobacz [stacja robocza a serwer](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="da953-217">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="da953-218">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="da953-218">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="da953-219">`ThreadPoolMaxThreads`Właściwość określa maksymalną liczbę wątków dla puli wątków roboczych.</span><span class="sxs-lookup"><span data-stu-id="da953-219">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="da953-220">Aby uzyskać więcej informacji, zobacz [maksymalne wątki](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="da953-220">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="da953-221">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="da953-221">ThreadPoolMinThreads</span></span>

<span data-ttu-id="da953-222">`ThreadPoolMinThreads`Właściwość konfiguruje minimalną liczbę wątków dla puli wątków roboczych.</span><span class="sxs-lookup"><span data-stu-id="da953-222">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="da953-223">Aby uzyskać więcej informacji, zobacz [minimalna liczba wątków](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="da953-223">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="da953-224">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="da953-224">TieredCompilation</span></span>

<span data-ttu-id="da953-225">`TieredCompilation`Właściwość określa, czy kompilator just in Time (JIT) używa [kompilacji warstwowej](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="da953-225">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="da953-226">Ustaw wartość na, aby `false` wyłączyć kompilację warstwową.</span><span class="sxs-lookup"><span data-stu-id="da953-226">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="da953-227">Aby uzyskać więcej informacji, zobacz temat [kompilacja warstwowa](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="da953-227">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="da953-228">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="da953-228">TieredCompilationQuickJit</span></span>

<span data-ttu-id="da953-229">`TieredCompilationQuickJit`Właściwość określa, czy KOMPILATOR JIT używa szybkiej JIT.</span><span class="sxs-lookup"><span data-stu-id="da953-229">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="da953-230">Ustaw wartość na `false` , aby wyłączyć szybkie JIT.</span><span class="sxs-lookup"><span data-stu-id="da953-230">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="da953-231">Aby uzyskać więcej informacji, zobacz [szybkie JIT](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="da953-231">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="da953-232">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="da953-232">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="da953-233">`TieredCompilationQuickJitForLoops`Właściwość określa, czy KOMPILATOR JIT używa szybkiej JIT metod, które zawierają pętle.</span><span class="sxs-lookup"><span data-stu-id="da953-233">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="da953-234">Ustaw wartość na, aby `true` włączyć funkcję szybkiego JIT dla metod, które zawierają pętle.</span><span class="sxs-lookup"><span data-stu-id="da953-234">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="da953-235">Aby uzyskać więcej informacji, zobacz [szybkie JIT dla pętli](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="da953-235">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="da953-236">Właściwości odwołania i elementy</span><span class="sxs-lookup"><span data-stu-id="da953-236">Reference properties and items</span></span>

- [<span data-ttu-id="da953-237">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="da953-237">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="da953-238">PackageReference</span><span class="sxs-lookup"><span data-stu-id="da953-238">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="da953-239">Elementu ProjectReference</span><span class="sxs-lookup"><span data-stu-id="da953-239">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="da953-240">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="da953-240">Reference</span></span>](#reference)
- [<span data-ttu-id="da953-241">Właściwości przywracania</span><span class="sxs-lookup"><span data-stu-id="da953-241">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="da953-242">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="da953-242">AssetTargetFallback</span></span>

<span data-ttu-id="da953-243">`AssetTargetFallback`Właściwość pozwala określić dodatkowe zgodne wersje architektury dla odwołań do projektu i pakietów NuGet.</span><span class="sxs-lookup"><span data-stu-id="da953-243">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="da953-244">Na przykład, jeśli określisz zależność pakietu przy użyciu programu `PackageReference` , ale ten pakiet nie zawiera zasobów, które są zgodne z projektem `TargetFramework` , `AssetTargetFallback` Właściwość jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="da953-244">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="da953-245">Zgodność przywoływanego pakietu jest ponownie sprawdzana przy użyciu każdej platformy docelowej określonej w `AssetTargetFallback` .</span><span class="sxs-lookup"><span data-stu-id="da953-245">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="da953-246">Można ustawić `AssetTargetFallback` Właściwość na co najmniej jedną [docelową wersję platformy](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="da953-246">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="da953-247">PackageReference</span><span class="sxs-lookup"><span data-stu-id="da953-247">PackageReference</span></span>

<span data-ttu-id="da953-248">`PackageReference`Element definiuje odwołanie do pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="da953-248">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="da953-249">Ten `Include` atrybut określa identyfikator pakietu.</span><span class="sxs-lookup"><span data-stu-id="da953-249">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="da953-250">Ten `Version` atrybut określa wersję lub zakres wersji.</span><span class="sxs-lookup"><span data-stu-id="da953-250">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="da953-251">Aby uzyskać informacje na temat określania minimalnej wersji, maksymalnej wersji, zakresu lub dokładnego dopasowania, zobacz [zakres wersji](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="da953-251">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="da953-252">Można również dodać następujące metadane do odwołania do projektu: `IncludeAssets` , `ExcludeAssets` , i `PrivateAssets` .</span><span class="sxs-lookup"><span data-stu-id="da953-252">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="da953-253">Fragment pliku projektu w poniższym przykładzie odwołuje się do pakietu [System. Runtime](https://www.nuget.org/packages/System.Runtime/) .</span><span class="sxs-lookup"><span data-stu-id="da953-253">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="da953-254">Aby uzyskać więcej informacji, zobacz [odwołania do pakietów w plikach projektu](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="da953-254">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="da953-255">Elementu ProjectReference</span><span class="sxs-lookup"><span data-stu-id="da953-255">ProjectReference</span></span>

<span data-ttu-id="da953-256">`ProjectReference`Element definiuje odwołanie do innego projektu.</span><span class="sxs-lookup"><span data-stu-id="da953-256">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="da953-257">Przywoływany projekt jest dodawany jako zależność pakietu NuGet, czyli jest traktowany tak samo jak `PackageReference` .</span><span class="sxs-lookup"><span data-stu-id="da953-257">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="da953-258">Ten `Include` atrybut określa ścieżkę do projektu.</span><span class="sxs-lookup"><span data-stu-id="da953-258">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="da953-259">Można również dodać następujące metadane do odwołania do projektu: `IncludeAssets` , `ExcludeAssets` , i `PrivateAssets` .</span><span class="sxs-lookup"><span data-stu-id="da953-259">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="da953-260">Fragment pliku projektu w poniższym przykładzie odwołuje się do projektu o nazwie `Project2` .</span><span class="sxs-lookup"><span data-stu-id="da953-260">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="da953-261">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="da953-261">Reference</span></span>

<span data-ttu-id="da953-262">`Reference`Element definiuje odwołanie do pliku zestawu.</span><span class="sxs-lookup"><span data-stu-id="da953-262">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="da953-263">`Include`Atrybut określa nazwę pliku, a `HintPath` metadane określa ścieżkę do zestawu.</span><span class="sxs-lookup"><span data-stu-id="da953-263">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="da953-264">Właściwości przywracania</span><span class="sxs-lookup"><span data-stu-id="da953-264">Restore properties</span></span>

<span data-ttu-id="da953-265">Przywracanie przywoływanego pakietu instaluje wszystkie jego bezpośrednie zależności i wszystkie zależności tych zależności.</span><span class="sxs-lookup"><span data-stu-id="da953-265">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="da953-266">Przywracanie pakietu można dostosować, określając właściwości, takie jak `RestorePackagesPath` i `RestoreIgnoreFailedSources` .</span><span class="sxs-lookup"><span data-stu-id="da953-266">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="da953-267">Aby uzyskać więcej informacji na temat tych i innych właściwości, zobacz [Restore Target](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="da953-267">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="da953-268">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="da953-268">See also</span></span>

- [<span data-ttu-id="da953-269">Odwołanie do schematu programu MSBuild</span><span class="sxs-lookup"><span data-stu-id="da953-269">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="da953-270">Typowe właściwości programu MSBuild</span><span class="sxs-lookup"><span data-stu-id="da953-270">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="da953-271">Właściwości programu MSBuild dla pakietu NuGet</span><span class="sxs-lookup"><span data-stu-id="da953-271">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="da953-272">Właściwości programu MSBuild do przywracania NuGet</span><span class="sxs-lookup"><span data-stu-id="da953-272">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="da953-273">Dostosuj kompilację</span><span class="sxs-lookup"><span data-stu-id="da953-273">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
