---
title: Obsługa wersji języka c# — Przewodnik C#
description: Dowiedz się, w jaki sposób wersja języka C# jest określana na podstawie projektu i przyczyn związanych z tym wyborem. Dowiedz się, jak ręcznie przesłonić wartość domyślną.
ms.custom: updateeachrelease
ms.date: 08/11/2020
ms.openlocfilehash: a06aa8812dad6f4b9a9254eef9f7c678c22af860
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634512"
---
# <a name="c-language-versioning"></a><span data-ttu-id="c1161-104">Przechowywanie wersji języka C#</span><span class="sxs-lookup"><span data-stu-id="c1161-104">C# language versioning</span></span>

<span data-ttu-id="c1161-105">Najnowsza kompilator języka C# określa domyślną wersję językową opartą na docelowej platformie lub strukturach projektu.</span><span class="sxs-lookup"><span data-stu-id="c1161-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="c1161-106">Program Visual Studio nie udostępnia interfejsu użytkownika do zmiany wartości, ale można go zmienić, edytując plik *csproj* .</span><span class="sxs-lookup"><span data-stu-id="c1161-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="c1161-107">Wybór domyślny zapewnia, że jest używana najnowsza wersja językowa zgodna z platformą docelową.</span><span class="sxs-lookup"><span data-stu-id="c1161-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="c1161-108">Korzystasz z dostępu do najnowszych funkcji języka zgodnych z celem projektu.</span><span class="sxs-lookup"><span data-stu-id="c1161-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="c1161-109">To ustawienie domyślne gwarantuje również, że nie używasz języka wymagającego typów lub zachowania środowiska uruchomieniowego, które nie jest dostępne w platformie docelowej.</span><span class="sxs-lookup"><span data-stu-id="c1161-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="c1161-110">Wybranie wersji językowej nowszej niż domyślna może spowodować trudne zdiagnozowanie błędów kompilacji i czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="c1161-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="c1161-111">Reguły w tym artykule mają zastosowanie do kompilatora dostarczonego z programem Visual Studio 2019 lub zestawem SDK platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="c1161-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET SDK.</span></span> <span data-ttu-id="c1161-112">Kompilatory języka C#, które są częścią instalacji programu Visual Studio 2017 lub starsze wersje zestaw .NET Core SDK wersji docelowej C# 7,0.</span><span class="sxs-lookup"><span data-stu-id="c1161-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="c1161-113">Język C# 8,0 jest obsługiwany tylko w programie .NET Core 3. x i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="c1161-113">C# 8.0 is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="c1161-114">Wiele najnowszych funkcji wymaga funkcji biblioteki i środowiska uruchomieniowego wprowadzonych w programie .NET Core 3. x:</span><span class="sxs-lookup"><span data-stu-id="c1161-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="c1161-115">[Domyślna implementacja interfejsu](../whats-new/csharp-8.md#default-interface-methods) wymaga nowych funkcji w środowisku CLR programu .net Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1161-115">[Default interface implementation](../whats-new/csharp-8.md#default-interface-methods) requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="c1161-116">[Strumienie asynchroniczne](../whats-new/csharp-8.md#asynchronous-streams) wymagają nowych typów <xref:System.IAsyncDisposable?displayProperty=nameWithType> , <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> i <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c1161-116">[Async streams](../whats-new/csharp-8.md#asynchronous-streams) require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="c1161-117">[Indeksy i zakresy](../whats-new/csharp-8.md#indices-and-ranges) wymagają nowych typów <xref:System.Index?displayProperty=nameWithType> i <xref:System.Range?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c1161-117">[Indices and ranges](../whats-new/csharp-8.md#indices-and-ranges) require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="c1161-118">[Typy odwołań dopuszczających wartości null](../whats-new/csharp-8.md#nullable-reference-types) wykorzystują kilka [atrybutów](attributes/nullable-analysis.md) w celu zapewnienia lepszych ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="c1161-118">[Nullable reference types](../whats-new/csharp-8.md#nullable-reference-types) make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="c1161-119">Te atrybuty zostały dodane w programie .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1161-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="c1161-120">Inne platformy docelowe nie zostały opatrzone adnotacją z żadnym z tych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="c1161-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="c1161-121">Oznacza to, że ostrzeżenia dopuszczające wartość null mogą nie odzwierciedlać dokładnie potencjalnych problemów.</span><span class="sxs-lookup"><span data-stu-id="c1161-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

<span data-ttu-id="c1161-122">Język C# 9,0 jest obsługiwany tylko w programie .NET 5 i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="c1161-122">C# 9.0 is supported only on .NET 5 and newer versions.</span></span>

## <a name="defaults"></a><span data-ttu-id="c1161-123">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="c1161-123">Defaults</span></span>

<span data-ttu-id="c1161-124">Kompilator określa wartość domyślną na podstawie następujących reguł:</span><span class="sxs-lookup"><span data-stu-id="c1161-124">The compiler determines a default based on these rules:</span></span>

| <span data-ttu-id="c1161-125">Platforma docelowa</span><span class="sxs-lookup"><span data-stu-id="c1161-125">Target framework</span></span> | <span data-ttu-id="c1161-126">Wersja</span><span class="sxs-lookup"><span data-stu-id="c1161-126">version</span></span> | <span data-ttu-id="c1161-127">Domyślna wersja języka C#</span><span class="sxs-lookup"><span data-stu-id="c1161-127">C# language version default</span></span> |
|------------------|---------|-----------------------------|
| <span data-ttu-id="c1161-128">.NET</span><span class="sxs-lookup"><span data-stu-id="c1161-128">.NET</span></span>             | <span data-ttu-id="c1161-129">eksportowa</span><span class="sxs-lookup"><span data-stu-id="c1161-129">5.x</span></span>     | <span data-ttu-id="c1161-130">C# 9.0</span><span class="sxs-lookup"><span data-stu-id="c1161-130">C# 9.0</span></span>                      |
| <span data-ttu-id="c1161-131">.NET Core</span><span class="sxs-lookup"><span data-stu-id="c1161-131">.NET Core</span></span>        | <span data-ttu-id="c1161-132">wersji</span><span class="sxs-lookup"><span data-stu-id="c1161-132">3.x</span></span>     | <span data-ttu-id="c1161-133">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="c1161-133">C# 8.0</span></span>                      |
| <span data-ttu-id="c1161-134">.NET Core</span><span class="sxs-lookup"><span data-stu-id="c1161-134">.NET Core</span></span>        | <span data-ttu-id="c1161-135">2.x</span><span class="sxs-lookup"><span data-stu-id="c1161-135">2.x</span></span>     | <span data-ttu-id="c1161-136">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="c1161-136">C# 7.3</span></span>                      |
| <span data-ttu-id="c1161-137">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="c1161-137">.NET Standard</span></span>    | <span data-ttu-id="c1161-138">2.1</span><span class="sxs-lookup"><span data-stu-id="c1161-138">2.1</span></span>     | <span data-ttu-id="c1161-139">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="c1161-139">C# 8.0</span></span>                      |
| <span data-ttu-id="c1161-140">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="c1161-140">.NET Standard</span></span>    | <span data-ttu-id="c1161-141">2,0</span><span class="sxs-lookup"><span data-stu-id="c1161-141">2.0</span></span>     | <span data-ttu-id="c1161-142">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="c1161-142">C# 7.3</span></span>                      |
| <span data-ttu-id="c1161-143">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="c1161-143">.NET Standard</span></span>    | <span data-ttu-id="c1161-144">1.x</span><span class="sxs-lookup"><span data-stu-id="c1161-144">1.x</span></span>     | <span data-ttu-id="c1161-145">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="c1161-145">C# 7.3</span></span>                      |
| <span data-ttu-id="c1161-146">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="c1161-146">.NET Framework</span></span>   | <span data-ttu-id="c1161-147">all</span><span class="sxs-lookup"><span data-stu-id="c1161-147">all</span></span>     | <span data-ttu-id="c1161-148">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="c1161-148">C# 7.3</span></span>                      |

<span data-ttu-id="c1161-149">Jeśli projekt jest przeznaczony dla platformy wersji zapoznawczej, która ma odpowiednią wersję języka wersji zapoznawczej, używana jest wersja języka w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="c1161-149">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="c1161-150">Należy używać najnowszych funkcji w wersji zapoznawczej w dowolnym środowisku, bez wywierania wpływu na projekty przeznaczone do wydania .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c1161-150">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

> [!TIP]
> <span data-ttu-id="c1161-151">Aby dowiedzieć się, jaka wersja językowa jest obecnie używana, umieść `#error version` (z uwzględnieniem wielkości liter) w kodzie.</span><span class="sxs-lookup"><span data-stu-id="c1161-151">To know what language version you're currently using, put `#error version` (case sensitive) in your code.</span></span> <span data-ttu-id="c1161-152">Dzięki temu kompilator tworzy diagnostykę, CS8304 z komunikatem zawierającym używaną wersję kompilatora i bieżącą wybraną wersję językową.</span><span class="sxs-lookup"><span data-stu-id="c1161-152">This makes the compiler produce a diagnostic, CS8304, with a message containing the compiler version being used and the current selected language version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="c1161-153">Zastąp wartość domyślną</span><span class="sxs-lookup"><span data-stu-id="c1161-153">Override a default</span></span>

<span data-ttu-id="c1161-154">Jeśli musisz jawnie określić wersję języka C#, możesz to zrobić na kilka sposobów:</span><span class="sxs-lookup"><span data-stu-id="c1161-154">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="c1161-155">Edytuj ręcznie [plik projektu](#edit-the-project-file).</span><span class="sxs-lookup"><span data-stu-id="c1161-155">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="c1161-156">Ustaw wersję językową [dla wielu projektów w podkatalogu](#configure-multiple-projects).</span><span class="sxs-lookup"><span data-stu-id="c1161-156">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="c1161-157">Skonfiguruj [ `-langversion` opcję kompilatora](compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c1161-157">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="c1161-158">Edytuj plik projektu</span><span class="sxs-lookup"><span data-stu-id="c1161-158">Edit the project file</span></span>

<span data-ttu-id="c1161-159">Możesz ustawić wersję językową w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="c1161-159">You can set the language version in your project file.</span></span> <span data-ttu-id="c1161-160">Jeśli na przykład jawnie chcesz uzyskać dostęp do funkcji w wersji zapoznawczej, Dodaj element podobny do tego:</span><span class="sxs-lookup"><span data-stu-id="c1161-160">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="c1161-161">Ta wartość `preview` używa najnowszej dostępnej wersji językowej C# obsługiwanej przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="c1161-161">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="c1161-162">Konfigurowanie wielu projektów</span><span class="sxs-lookup"><span data-stu-id="c1161-162">Configure multiple projects</span></span>

<span data-ttu-id="c1161-163">Aby skonfigurować wiele projektów, można utworzyć plik **Directory. Build. props** , który zawiera `<LangVersion>` element.</span><span class="sxs-lookup"><span data-stu-id="c1161-163">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="c1161-164">Zwykle jest to wykonywane w katalogu rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="c1161-164">You typically do that in your solution directory.</span></span> <span data-ttu-id="c1161-165">Dodaj następujący element do pliku **Directory. Build. props** w katalogu rozwiązania:</span><span class="sxs-lookup"><span data-stu-id="c1161-165">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="c1161-166">Kompilacje we wszystkich podkatalogach katalogu zawierającego ten plik będą korzystać z wersji zapoznawczej języka C#.</span><span class="sxs-lookup"><span data-stu-id="c1161-166">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="c1161-167">Aby uzyskać więcej informacji, zobacz artykuł na temat [dostosowywania kompilacji](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="c1161-167">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="c1161-168">Dokumentacja wersji języka C#</span><span class="sxs-lookup"><span data-stu-id="c1161-168">C# language version reference</span></span>

<span data-ttu-id="c1161-169">W poniższej tabeli przedstawiono wszystkie bieżące wersje języka C#.</span><span class="sxs-lookup"><span data-stu-id="c1161-169">The following table shows all current C# language versions.</span></span> <span data-ttu-id="c1161-170">Kompilator może niekoniecznie zrozumieć każdą wartość, jeśli jest starszy.</span><span class="sxs-lookup"><span data-stu-id="c1161-170">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="c1161-171">W przypadku zainstalowania najnowszego zestawu SDK platformy .NET masz dostęp do wszystkich elementów na liście.</span><span class="sxs-lookup"><span data-stu-id="c1161-171">If you install the latest .NET SDK, then you have access to everything listed.</span></span>

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> <span data-ttu-id="c1161-172">Otwórz [wiersz polecenia dla deweloperów dla programu Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md)i uruchom następujące polecenie, aby wyświetlić listę wersji językowych dostępnych na komputerze.</span><span class="sxs-lookup"><span data-stu-id="c1161-172">Open the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), and run the following command to see the listing of language versions available on your machine.</span></span>
>
> ```CMD
> csc -langversion:?
> ```
>
> <span data-ttu-id="c1161-173">Pytania dotyczące opcji Kompiluj [-langversion](compiler-options/langversion-compiler-option.md) w następujący sposób spowoduje wydrukowanie coś podobnego do poniższego:</span><span class="sxs-lookup"><span data-stu-id="c1161-173">Questioning the [-langversion](compiler-options/langversion-compiler-option.md) compile option like this, will print something similar to the following:</span></span>
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0
> 9.0 (default)
> latestmajor
> preview
> latest
> ```
