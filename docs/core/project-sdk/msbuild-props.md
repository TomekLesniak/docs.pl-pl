---
title: Właściwości programu MSBuild dla Microsoft. NET. Sdk
description: Odwołanie do właściwości i elementów programu MSBuild, które są zrozumiałe dla zestawu .NET SDK.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: faa0dc0e94800a49b56af8810562ee0540f118d2
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247578"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a><span data-ttu-id="58a5c-103">Dokumentacja programu MSBuild dla projektów zestawu .NET SDK</span><span class="sxs-lookup"><span data-stu-id="58a5c-103">MSBuild reference for .NET SDK projects</span></span>

<span data-ttu-id="58a5c-104">Ta strona jest odwołaniem do właściwości i elementów programu MSBuild, których można użyć do konfigurowania projektów platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="58a5c-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET projects.</span></span>

> [!NOTE]
> <span data-ttu-id="58a5c-105">Ta strona jest w toku i nie zawiera wszystkich przydatnych właściwości programu MSBuild dla zestawu .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="58a5c-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET SDK.</span></span> <span data-ttu-id="58a5c-106">Aby zapoznać się z listą typowych właściwości programu MSBuild, zobacz [typowe właściwości programu MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="58a5c-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="58a5c-107">Właściwości struktury</span><span class="sxs-lookup"><span data-stu-id="58a5c-107">Framework properties</span></span>

- [<span data-ttu-id="58a5c-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="58a5c-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="58a5c-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="58a5c-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="58a5c-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="58a5c-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="58a5c-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="58a5c-111">TargetFramework</span></span>

<span data-ttu-id="58a5c-112">`TargetFramework`Właściwość określa wersję platformy docelowej dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="58a5c-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="58a5c-113">Aby zapoznać się z listą prawidłowych monikerów platformy docelowej, zobacz [platformę docelową w projektach w stylu zestawu SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="58a5c-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="58a5c-114">Aby uzyskać więcej informacji, zobacz [Platformy docelowe w projektach w stylu zestawu SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="58a5c-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="58a5c-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="58a5c-115">TargetFrameworks</span></span>

<span data-ttu-id="58a5c-116">Użyj `TargetFrameworks` właściwości, jeśli chcesz, aby aplikacja była przeznaczona dla wielu platform.</span><span class="sxs-lookup"><span data-stu-id="58a5c-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="58a5c-117">Aby zapoznać się z listą prawidłowych monikerów platformy docelowej, zobacz [platformę docelową w projektach w stylu zestawu SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="58a5c-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="58a5c-118">Ta właściwość jest ignorowana, jeśli `TargetFramework` określono (pojedynczo).</span><span class="sxs-lookup"><span data-stu-id="58a5c-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="58a5c-119">Aby uzyskać więcej informacji, zobacz [Platformy docelowe w projektach w stylu zestawu SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="58a5c-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="58a5c-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="58a5c-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="58a5c-121">Ta właściwość ma zastosowanie tylko do projektów korzystających z programu `netstandard1.x` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="58a5c-122">Nie dotyczy to projektów, które używają `netstandard2.x` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="58a5c-123">Użyj `NetStandardImplicitPackageVersion` właściwości, aby określić wersję platformy, która jest starsza niż wersja pakietu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="58a5c-124">Plik projektu w poniższym przykładzie docelowym `netstandard1.3` , ale używa wersji 1.6.0 `NETStandard.Library` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="58a5c-125">Właściwości pakietu</span><span class="sxs-lookup"><span data-stu-id="58a5c-125">Package properties</span></span>

<span data-ttu-id="58a5c-126">Można określić właściwości, takie jak `PackageId` ,,, `PackageVersion` `PackageIcon` `Title` i, `Description` aby opisać pakiet, który zostanie utworzony na podstawie projektu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="58a5c-127">Aby uzyskać informacje o tych i innych właściwościach, zobacz [pakiet Target](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="58a5c-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="58a5c-128">Publikowanie właściwości i elementów</span><span class="sxs-lookup"><span data-stu-id="58a5c-128">Publish properties and items</span></span>

- [<span data-ttu-id="58a5c-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="58a5c-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="58a5c-130">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="58a5c-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="58a5c-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="58a5c-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="58a5c-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="58a5c-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="58a5c-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="58a5c-133">RuntimeIdentifier</span></span>

<span data-ttu-id="58a5c-134">`RuntimeIdentifier`Właściwość umożliwia określenie pojedynczego [identyfikatora środowiska uruchomieniowego (RID)](../rid-catalog.md) dla projektu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="58a5c-135">Identyfikator RID umożliwia publikowanie samodzielnego wdrożenia.</span><span class="sxs-lookup"><span data-stu-id="58a5c-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="58a5c-136">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="58a5c-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="58a5c-137">`RuntimeIdentifiers`Właściwość pozwala określić rozdzielaną średnikami listę [identyfikatorów środowiska uruchomieniowego (RID)](../rid-catalog.md) dla projektu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="58a5c-138">Użyj tej właściwości, jeśli chcesz opublikować dla wielu środowisk uruchomieniowych.</span><span class="sxs-lookup"><span data-stu-id="58a5c-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="58a5c-139">`RuntimeIdentifiers` jest używany podczas przywracania, aby upewnić się, że odpowiednie zasoby znajdują się na wykresie.</span><span class="sxs-lookup"><span data-stu-id="58a5c-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="58a5c-140">`RuntimeIdentifier` (pojedyncze) może zapewnić szybsze kompilacje, gdy wymagane jest tylko jedno środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="58a5c-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="58a5c-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="58a5c-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="58a5c-142">`TrimmerRootAssembly`Element umożliwia wykluczenie zestawu z [*przycinania*](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="58a5c-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="58a5c-143">Przycinanie jest procesem usuwania nieużywanych części środowiska uruchomieniowego z spakowanej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="58a5c-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="58a5c-144">W niektórych przypadkach przycinanie może niepoprawnie usunąć wymagane odwołania.</span><span class="sxs-lookup"><span data-stu-id="58a5c-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="58a5c-145">Poniższy kod XML wyklucza `System.Security` zestaw z przycinania.</span><span class="sxs-lookup"><span data-stu-id="58a5c-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="58a5c-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="58a5c-146">UseAppHost</span></span>

<span data-ttu-id="58a5c-147">`UseAppHost`Właściwość została wprowadzona w wersji 2.1.400 zestawu .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="58a5c-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET SDK.</span></span> <span data-ttu-id="58a5c-148">Określa, czy dla wdrożenia jest tworzony natywny plik wykonywalny.</span><span class="sxs-lookup"><span data-stu-id="58a5c-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="58a5c-149">Natywny plik wykonywalny jest wymagany w przypadku wdrożeń samodzielnych.</span><span class="sxs-lookup"><span data-stu-id="58a5c-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="58a5c-150">W programie .NET Core 3,0 i jego nowszych wersjach domyślnie tworzony jest plik wykonywalny zależny od platformy.</span><span class="sxs-lookup"><span data-stu-id="58a5c-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="58a5c-151">Ustaw `UseAppHost` Właściwość na `false` , aby wyłączyć generowanie pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="58a5c-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="58a5c-152">Aby uzyskać więcej informacji o wdrażaniu, zobacz [wdrażanie aplikacji .NET](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="58a5c-152">For more information about deployment, see [.NET application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="58a5c-153">Kompiluj właściwości</span><span class="sxs-lookup"><span data-stu-id="58a5c-153">Compile properties</span></span>

- [<span data-ttu-id="58a5c-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="58a5c-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="58a5c-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="58a5c-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="58a5c-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="58a5c-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="58a5c-157">`EmbeddedResourceUseDependentUponConvention`Właściwość określa, czy nazwy plików manifestu zasobów są generowane na podstawie informacji o typie w plikach źródłowych, które znajdują się w plikach zasobów.</span><span class="sxs-lookup"><span data-stu-id="58a5c-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="58a5c-158">Na przykład jeśli *Form1. resx* znajduje się w tym samym folderze co *Form1.cs*i `EmbeddedResourceUseDependentUponConvention` jest ustawiona na `true` , wygenerowany plik *resources* przyjmuje swoją nazwę z pierwszego typu zdefiniowanego w *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="58a5c-158">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="58a5c-159">Na przykład, jeśli `MyNamespace.Form1` jest pierwszym typem zdefiniowanym w *Form1.cs*, wygenerowana nazwa pliku ma *nazwę. Form1. resources*.</span><span class="sxs-lookup"><span data-stu-id="58a5c-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="58a5c-160">Jeśli `LogicalName` `ManifestResourceName` `DependentUpon` dla elementu określono wartość, lub lub metadanych `EmbeddedResource` , wygenerowana nazwa pliku manifestu dla tego pliku zasobów jest oparta na tym metadanych.</span><span class="sxs-lookup"><span data-stu-id="58a5c-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="58a5c-161">Domyślnie w nowym projekcie .NET ta właściwość jest ustawiona na `true` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-161">By default, in a new .NET project, this property is set to `true`.</span></span> <span data-ttu-id="58a5c-162">Jeśli `false` `LogicalName` `ManifestResourceName` dla elementu w pliku projektu zostanie ustawiona wartość, i nie, lub `DependentUpon` dla tego parametru, `EmbeddedResource` Nazwa pliku manifestu zasobu jest oparta na głównej przestrzeni nazw projektu i względnej ścieżce pliku do pliku *resx* .</span><span class="sxs-lookup"><span data-stu-id="58a5c-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="58a5c-163">Aby uzyskać więcej informacji, zobacz [jak nazywa się plik manifestu zasobu](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="58a5c-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="58a5c-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="58a5c-164">LangVersion</span></span>

<span data-ttu-id="58a5c-165">`LangVersion`Właściwość umożliwia określenie konkretnej wersji języka programowania.</span><span class="sxs-lookup"><span data-stu-id="58a5c-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="58a5c-166">Na przykład jeśli chcesz uzyskać dostęp do funkcji wersji zapoznawczej języka C#, ustaw wartość `LangVersion` `preview` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="58a5c-167">Aby uzyskać więcej informacji, zobacz [wersja języka C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="58a5c-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="code-analysis-properties"></a><span data-ttu-id="58a5c-168">Właściwości analizy kodu</span><span class="sxs-lookup"><span data-stu-id="58a5c-168">Code analysis properties</span></span>

### <a name="analysislevel"></a><span data-ttu-id="58a5c-169">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="58a5c-169">AnalysisLevel</span></span>

<span data-ttu-id="58a5c-170">`AnalysisLevel`Właściwość pozwala określić poziom analizy kodu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-170">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="58a5c-171">Jeśli na przykład chcesz uzyskać dostęp do analizatorów kodu w wersji zapoznawczej, ustaw wartość `AnalysisLevel` `preview` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-171">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="58a5c-172">Wartość domyślna to `latest`.</span><span class="sxs-lookup"><span data-stu-id="58a5c-172">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="58a5c-173">W poniższej tabeli przedstawiono dostępne opcje.</span><span class="sxs-lookup"><span data-stu-id="58a5c-173">The following table shows the available options.</span></span>

| <span data-ttu-id="58a5c-174">Wartość</span><span class="sxs-lookup"><span data-stu-id="58a5c-174">Value</span></span> | <span data-ttu-id="58a5c-175">Znaczenie</span><span class="sxs-lookup"><span data-stu-id="58a5c-175">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="58a5c-176">Używane są najnowsze analizatory kodu, które zostały wydane.</span><span class="sxs-lookup"><span data-stu-id="58a5c-176">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="58a5c-177">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="58a5c-177">This is the default.</span></span> |
| `preview` | <span data-ttu-id="58a5c-178">Są używane najnowsze analizatory kodu, nawet jeśli są one w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="58a5c-178">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="58a5c-179">Używany jest zestaw reguł, które zostały włączone dla wydania .NET 5,0, nawet jeśli są dostępne nowsze reguły.</span><span class="sxs-lookup"><span data-stu-id="58a5c-179">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="58a5c-180">Używany jest zestaw reguł, które zostały włączone dla wydania .NET 5,0, nawet jeśli są dostępne nowsze reguły.</span><span class="sxs-lookup"><span data-stu-id="58a5c-180">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="analysismode"></a><span data-ttu-id="58a5c-181">Analizamode</span><span class="sxs-lookup"><span data-stu-id="58a5c-181">AnalysisMode</span></span>

<span data-ttu-id="58a5c-182">Począwszy od platformy .NET 5,0 RC2, zestaw .NET SDK jest dostarczany ze wszystkimi [regułami dotyczącymi jakości kodu "CA"](../../fundamentals/code-analysis/rules/quality-rules-reference.md).</span><span class="sxs-lookup"><span data-stu-id="58a5c-182">Starting with .NET 5.0 RC2, the .NET SDK ships with all of the ["CA" code quality rules](../../fundamentals/code-analysis/rules/quality-rules-reference.md).</span></span> <span data-ttu-id="58a5c-183">Domyślnie tylko [niektóre reguły są włączane](../../fundamentals/code-analysis/overview.md#enabled-rules) jako ostrzeżenia kompilacji.</span><span class="sxs-lookup"><span data-stu-id="58a5c-183">By default, only [some rules are enabled](../../fundamentals/code-analysis/overview.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="58a5c-184">`AnalysisMode`Właściwość umożliwia dostosowanie zestawu reguł, które są domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="58a5c-184">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="58a5c-185">Można przełączać się na bardziej agresywny tryb analizy lub bardziej ostrożny tryb analizy.</span><span class="sxs-lookup"><span data-stu-id="58a5c-185">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="58a5c-186">Na przykład jeśli chcesz włączyć wszystkie reguły domyślnie jako ostrzeżenia kompilacji, ustaw wartość na `AllEnabledByDefault` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-186">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="58a5c-187">W poniższej tabeli przedstawiono dostępne opcje.</span><span class="sxs-lookup"><span data-stu-id="58a5c-187">The following table shows the available options.</span></span>

| <span data-ttu-id="58a5c-188">Wartość</span><span class="sxs-lookup"><span data-stu-id="58a5c-188">Value</span></span> | <span data-ttu-id="58a5c-189">Znaczenie</span><span class="sxs-lookup"><span data-stu-id="58a5c-189">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="58a5c-190">Domyślny tryb, w którym niektóre reguły są włączone jako ostrzeżenia kompilacji, niektóre reguły są włączane jako sugestie środowiska IDE programu Visual Studio, a reszta jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="58a5c-190">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="58a5c-191">Tryb agresywny lub rezygnacji, w którym wszystkie reguły są domyślnie włączone jako ostrzeżenia kompilacji.</span><span class="sxs-lookup"><span data-stu-id="58a5c-191">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="58a5c-192">Możesz selektywnie [zrezygnować](../../fundamentals/code-analysis/configuration-options.md) z poszczególnych reguł, aby je wyłączyć.</span><span class="sxs-lookup"><span data-stu-id="58a5c-192">You can selectively [opt out](../../fundamentals/code-analysis/configuration-options.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="58a5c-193">Tryb wyłączania lub niewłączania, gdzie wszystkie reguły są domyślnie wyłączone.</span><span class="sxs-lookup"><span data-stu-id="58a5c-193">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="58a5c-194">Można [wybiórczo](../../fundamentals/code-analysis/configuration-options.md) wybierać poszczególne reguły, aby je włączyć.</span><span class="sxs-lookup"><span data-stu-id="58a5c-194">You can selectively [opt into](../../fundamentals/code-analysis/configuration-options.md) individual rules to enable them.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="58a5c-195">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="58a5c-195">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="58a5c-196">`CodeAnalysisTreatWarningsAsErrors`Właściwość umożliwia skonfigurowanie, czy ostrzeżenia analizy jakości kodu (CAxxxx) powinny być traktowane jako ostrzeżenia i przerywać kompilację.</span><span class="sxs-lookup"><span data-stu-id="58a5c-196">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="58a5c-197">Jeśli używasz `-warnaserror` flagi podczas kompilowania projektów, ostrzeżenia [analizy jakości kodu platformy .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) również są traktowane jako błędy.</span><span class="sxs-lookup"><span data-stu-id="58a5c-197">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="58a5c-198">Jeśli nie chcesz, aby ostrzeżenia analizy jakości kodu były traktowane jako błędy, możesz ustawić `CodeAnalysisTreatWarningsAsErrors` Właściwość programu MSBuild na `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-198">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="58a5c-199">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="58a5c-199">EnableNETAnalyzers</span></span>

<span data-ttu-id="58a5c-200">[Analiza jakości kodu platformy .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) jest domyślnie włączona dla projektów przeznaczonych dla platformy .NET 5,0 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="58a5c-200">[.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="58a5c-201">Można włączyć analizę kodu platformy .NET dla projektów przeznaczonych dla wcześniejszych wersji platformy .NET przez ustawienie `EnableNETAnalyzers` właściwości na `true` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-201">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="58a5c-202">Aby wyłączyć analizę kodu w dowolnym projekcie, należy ustawić tę właściwość na `false` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-202">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="58a5c-203">Innym sposobem na włączenie analizy kodu .NET dla projektów przeznaczonych dla wersji .NET wcześniejszych niż .NET 5,0 jest ustawienie właściwości [AnalysisLevel](#analysislevel) na `latest` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-203">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="58a5c-204">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="58a5c-204">EnforceCodeStyleInBuild</span></span>

<span data-ttu-id="58a5c-205">[Analiza stylu kodu platformy .NET](../../fundamentals/code-analysis/overview.md#code-style-analysis) jest domyślnie wyłączona w przypadku kompilacji dla wszystkich projektów .NET.</span><span class="sxs-lookup"><span data-stu-id="58a5c-205">[.NET code style analysis](../../fundamentals/code-analysis/overview.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="58a5c-206">Można włączyć analizę stylu kodu dla projektów .NET, ustawiając `EnforceCodeStyleInBuild` Właściwość na `true` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-206">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="58a5c-207">Wszystkie reguły stylu kodu, które są [skonfigurowane](../../fundamentals/code-analysis/overview.md#code-style-analysis) do wyświetlania ostrzeżeń lub błędów, będą wykonywane w przypadku naruszeń kompilacji i raportu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-207">All code style rules that are [configured](../../fundamentals/code-analysis/overview.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="58a5c-208">Właściwości konfiguracji czasu wykonywania</span><span class="sxs-lookup"><span data-stu-id="58a5c-208">Run-time configuration properties</span></span>

<span data-ttu-id="58a5c-209">Niektóre zachowania w czasie wykonywania można skonfigurować, określając właściwości programu MSBuild w pliku projektu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="58a5c-209">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="58a5c-210">Aby uzyskać informacje na temat innych sposobów konfigurowania zachowania w czasie wykonywania, zobacz [Ustawienia konfiguracji w czasie wykonywania](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="58a5c-210">For information about other ways of configuring run-time behavior, see [Run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="58a5c-211">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="58a5c-211">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="58a5c-212">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="58a5c-212">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="58a5c-213">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="58a5c-213">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="58a5c-214">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="58a5c-214">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="58a5c-215">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="58a5c-215">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="58a5c-216">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="58a5c-216">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="58a5c-217">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="58a5c-217">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="58a5c-218">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="58a5c-218">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="58a5c-219">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="58a5c-219">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="58a5c-220">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="58a5c-220">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="58a5c-221">`ConcurrentGarbageCollection`Właściwość określa, czy jest włączone [wyrzucanie elementów bezużytecznych w tle](../../standard/garbage-collection/background-gc.md) .</span><span class="sxs-lookup"><span data-stu-id="58a5c-221">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="58a5c-222">Ustaw wartość na `false` , aby wyłączyć wyrzucanie elementów bezużytecznych w tle.</span><span class="sxs-lookup"><span data-stu-id="58a5c-222">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="58a5c-223">Aby uzyskać więcej informacji, zobacz w [tle GC](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="58a5c-223">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="58a5c-224">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="58a5c-224">InvariantGlobalization</span></span>

<span data-ttu-id="58a5c-225">`InvariantGlobalization`Właściwość określa, czy aplikacja jest uruchamiana w trybie *globalizacji-niezmiennym* , co oznacza, że nie ma dostępu do danych specyficznych dla kultury.</span><span class="sxs-lookup"><span data-stu-id="58a5c-225">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="58a5c-226">Ustaw wartość tak, aby była `true` uruchamiana w trybie niezmiennym globalizacji.</span><span class="sxs-lookup"><span data-stu-id="58a5c-226">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="58a5c-227">Aby uzyskać więcej informacji, zobacz [tryb niezmienny](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="58a5c-227">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="58a5c-228">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="58a5c-228">RetainVMGarbageCollection</span></span>

<span data-ttu-id="58a5c-229">`RetainVMGarbageCollection`Właściwość konfiguruje moduł wyrzucania elementów bezużytecznych w celu umieszczenia usuniętych segmentów pamięci na liście gotowości do użycia w przyszłości lub zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="58a5c-229">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="58a5c-230">Ustawienie wartości `true` informującej Moduł wyrzucania elementów bezużytecznych w celu umieszczenia segmentów na liście gotowości.</span><span class="sxs-lookup"><span data-stu-id="58a5c-230">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="58a5c-231">Aby uzyskać więcej informacji, zobacz temat [zachowywanie maszyny wirtualnej](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="58a5c-231">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="58a5c-232">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="58a5c-232">ServerGarbageCollection</span></span>

<span data-ttu-id="58a5c-233">`ServerGarbageCollection`Właściwość określa, czy aplikacja używa [wyrzucania elementów bezużytecznych stacji roboczej lub odzyskiwania pamięci serwera](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="58a5c-233">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="58a5c-234">Ustaw wartość na, aby `true` użyć wyrzucania elementów bezużytecznych serwera.</span><span class="sxs-lookup"><span data-stu-id="58a5c-234">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="58a5c-235">Aby uzyskać więcej informacji, zobacz [stacja robocza a serwer](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="58a5c-235">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="58a5c-236">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="58a5c-236">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="58a5c-237">`ThreadPoolMaxThreads`Właściwość określa maksymalną liczbę wątków dla puli wątków roboczych.</span><span class="sxs-lookup"><span data-stu-id="58a5c-237">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="58a5c-238">Aby uzyskać więcej informacji, zobacz [maksymalne wątki](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="58a5c-238">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="58a5c-239">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="58a5c-239">ThreadPoolMinThreads</span></span>

<span data-ttu-id="58a5c-240">`ThreadPoolMinThreads`Właściwość konfiguruje minimalną liczbę wątków dla puli wątków roboczych.</span><span class="sxs-lookup"><span data-stu-id="58a5c-240">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="58a5c-241">Aby uzyskać więcej informacji, zobacz [minimalna liczba wątków](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="58a5c-241">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="58a5c-242">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="58a5c-242">TieredCompilation</span></span>

<span data-ttu-id="58a5c-243">`TieredCompilation`Właściwość określa, czy kompilator just in Time (JIT) używa [kompilacji warstwowej](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="58a5c-243">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="58a5c-244">Ustaw wartość na, aby `false` wyłączyć kompilację warstwową.</span><span class="sxs-lookup"><span data-stu-id="58a5c-244">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="58a5c-245">Aby uzyskać więcej informacji, zobacz temat [kompilacja warstwowa](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="58a5c-245">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="58a5c-246">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="58a5c-246">TieredCompilationQuickJit</span></span>

<span data-ttu-id="58a5c-247">`TieredCompilationQuickJit`Właściwość określa, czy KOMPILATOR JIT używa szybkiej JIT.</span><span class="sxs-lookup"><span data-stu-id="58a5c-247">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="58a5c-248">Ustaw wartość na `false` , aby wyłączyć szybkie JIT.</span><span class="sxs-lookup"><span data-stu-id="58a5c-248">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="58a5c-249">Aby uzyskać więcej informacji, zobacz [szybkie JIT](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="58a5c-249">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="58a5c-250">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="58a5c-250">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="58a5c-251">`TieredCompilationQuickJitForLoops`Właściwość określa, czy KOMPILATOR JIT używa szybkiej JIT metod, które zawierają pętle.</span><span class="sxs-lookup"><span data-stu-id="58a5c-251">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="58a5c-252">Ustaw wartość na, aby `true` włączyć funkcję szybkiego JIT dla metod, które zawierają pętle.</span><span class="sxs-lookup"><span data-stu-id="58a5c-252">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="58a5c-253">Aby uzyskać więcej informacji, zobacz [szybkie JIT dla pętli](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="58a5c-253">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="58a5c-254">Właściwości odwołania i elementy</span><span class="sxs-lookup"><span data-stu-id="58a5c-254">Reference properties and items</span></span>

- [<span data-ttu-id="58a5c-255">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="58a5c-255">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="58a5c-256">PackageReference</span><span class="sxs-lookup"><span data-stu-id="58a5c-256">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="58a5c-257">Elementu ProjectReference</span><span class="sxs-lookup"><span data-stu-id="58a5c-257">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="58a5c-258">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="58a5c-258">Reference</span></span>](#reference)
- [<span data-ttu-id="58a5c-259">Właściwości przywracania</span><span class="sxs-lookup"><span data-stu-id="58a5c-259">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="58a5c-260">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="58a5c-260">AssetTargetFallback</span></span>

<span data-ttu-id="58a5c-261">`AssetTargetFallback`Właściwość pozwala określić dodatkowe zgodne wersje architektury dla odwołań do projektu i pakietów NuGet.</span><span class="sxs-lookup"><span data-stu-id="58a5c-261">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="58a5c-262">Na przykład, jeśli określisz zależność pakietu przy użyciu programu `PackageReference` , ale ten pakiet nie zawiera zasobów, które są zgodne z projektem `TargetFramework` , `AssetTargetFallback` Właściwość jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="58a5c-262">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="58a5c-263">Zgodność przywoływanego pakietu jest ponownie sprawdzana przy użyciu każdej platformy docelowej określonej w `AssetTargetFallback` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-263">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="58a5c-264">Można ustawić `AssetTargetFallback` Właściwość na co najmniej jedną [docelową wersję platformy](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="58a5c-264">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="58a5c-265">PackageReference</span><span class="sxs-lookup"><span data-stu-id="58a5c-265">PackageReference</span></span>

<span data-ttu-id="58a5c-266">`PackageReference`Element definiuje odwołanie do pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="58a5c-266">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="58a5c-267">Ten `Include` atrybut określa identyfikator pakietu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-267">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="58a5c-268">Ten `Version` atrybut określa wersję lub zakres wersji.</span><span class="sxs-lookup"><span data-stu-id="58a5c-268">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="58a5c-269">Aby uzyskać informacje na temat określania minimalnej wersji, maksymalnej wersji, zakresu lub dokładnego dopasowania, zobacz [zakres wersji](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="58a5c-269">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="58a5c-270">Można również dodać następujące metadane do odwołania do projektu: `IncludeAssets` , `ExcludeAssets` , i `PrivateAssets` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-270">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="58a5c-271">Fragment pliku projektu w poniższym przykładzie odwołuje się do pakietu [System. Runtime](https://www.nuget.org/packages/System.Runtime/) .</span><span class="sxs-lookup"><span data-stu-id="58a5c-271">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="58a5c-272">Aby uzyskać więcej informacji, zobacz [odwołania do pakietów w plikach projektu](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="58a5c-272">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="58a5c-273">Elementu ProjectReference</span><span class="sxs-lookup"><span data-stu-id="58a5c-273">ProjectReference</span></span>

<span data-ttu-id="58a5c-274">`ProjectReference`Element definiuje odwołanie do innego projektu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-274">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="58a5c-275">Przywoływany projekt jest dodawany jako zależność pakietu NuGet, czyli jest traktowany tak samo jak `PackageReference` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-275">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="58a5c-276">Ten `Include` atrybut określa ścieżkę do projektu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-276">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="58a5c-277">Można również dodać następujące metadane do odwołania do projektu: `IncludeAssets` , `ExcludeAssets` , i `PrivateAssets` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-277">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="58a5c-278">Fragment pliku projektu w poniższym przykładzie odwołuje się do projektu o nazwie `Project2` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-278">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="58a5c-279">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="58a5c-279">Reference</span></span>

<span data-ttu-id="58a5c-280">`Reference`Element definiuje odwołanie do pliku zestawu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-280">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="58a5c-281">`Include`Atrybut określa nazwę pliku, a `HintPath` metadane określa ścieżkę do zestawu.</span><span class="sxs-lookup"><span data-stu-id="58a5c-281">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="58a5c-282">Właściwości przywracania</span><span class="sxs-lookup"><span data-stu-id="58a5c-282">Restore properties</span></span>

<span data-ttu-id="58a5c-283">Przywracanie przywoływanego pakietu instaluje wszystkie jego bezpośrednie zależności i wszystkie zależności tych zależności.</span><span class="sxs-lookup"><span data-stu-id="58a5c-283">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="58a5c-284">Przywracanie pakietu można dostosować, określając właściwości, takie jak `RestorePackagesPath` i `RestoreIgnoreFailedSources` .</span><span class="sxs-lookup"><span data-stu-id="58a5c-284">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="58a5c-285">Aby uzyskać więcej informacji na temat tych i innych właściwości, zobacz [Restore Target](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="58a5c-285">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="58a5c-286">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="58a5c-286">See also</span></span>

- [<span data-ttu-id="58a5c-287">Odwołanie do schematu programu MSBuild</span><span class="sxs-lookup"><span data-stu-id="58a5c-287">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="58a5c-288">Typowe właściwości programu MSBuild</span><span class="sxs-lookup"><span data-stu-id="58a5c-288">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="58a5c-289">Właściwości programu MSBuild dla pakietu NuGet</span><span class="sxs-lookup"><span data-stu-id="58a5c-289">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="58a5c-290">Właściwości programu MSBuild do przywracania NuGet</span><span class="sxs-lookup"><span data-stu-id="58a5c-290">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="58a5c-291">Dostosuj kompilację</span><span class="sxs-lookup"><span data-stu-id="58a5c-291">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
