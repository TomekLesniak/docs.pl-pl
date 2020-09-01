---
description: -langversion (opcje kompilatora C#)
title: -langversion (opcje kompilatora C#)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: b0e966bcc87303c0a7c2199fbfac743b22481424
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125478"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="fd67d-103">-langversion (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="fd67d-103">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="fd67d-104">Powoduje, że kompilator akceptuje tylko składnię, która jest zawarta w wybranej specyfikacji języka C#.</span><span class="sxs-lookup"><span data-stu-id="fd67d-104">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd67d-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="fd67d-105">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="fd67d-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="fd67d-106">Arguments</span></span>

`option`

<span data-ttu-id="fd67d-107">Następujące wartości są prawidłowe:</span><span class="sxs-lookup"><span data-stu-id="fd67d-107">The following values are valid:</span></span>

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

<span data-ttu-id="fd67d-108">Domyślna wersja języka zależy od platformy docelowej dla aplikacji oraz zainstalowanej wersji zestawu SDK lub programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd67d-108">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="fd67d-109">Te reguły są zdefiniowane w artykule [Konfigurowanie wersji językowej](../configure-language-version.md#defaults) .</span><span class="sxs-lookup"><span data-stu-id="fd67d-109">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd67d-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fd67d-110">Remarks</span></span>

<span data-ttu-id="fd67d-111">Metadane przywoływane przez aplikację w języku C# nie podlegają opcji kompilatora **langversion** .</span><span class="sxs-lookup"><span data-stu-id="fd67d-111">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="fd67d-112">Ponieważ każda wersja kompilatora C# zawiera rozszerzenia specyfikacji języka, **— langversion** nie zapewnia równoważnej funkcjonalności starszej wersji kompilatora.</span><span class="sxs-lookup"><span data-stu-id="fd67d-112">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="fd67d-113">Ponadto, chociaż aktualizacje wersji języka C# zwykle pokrywają się z najważniejszymi wersjami .NET Framework, Nowa składnia i funkcje nie muszą być powiązane z tą określoną wersją platformy.</span><span class="sxs-lookup"><span data-stu-id="fd67d-113">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="fd67d-114">Nowe funkcje w nieskończoność wymagają nowej aktualizacji kompilatora, która jest również wydawana wraz z poprawką w języku C#, każda konkretna funkcja ma własne wymagania dotyczące minimalnych interfejsów API platformy .NET lub środowiska uruchomieniowego języka wspólnego, które mogą zezwalać na uruchamianie jej w ramach struktur niskiego poziomu przez uwzględnienie pakietów NuGet lub innych bibliotek.</span><span class="sxs-lookup"><span data-stu-id="fd67d-114">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="fd67d-115">Niezależnie od tego, **które ustawienie** jest używane, Użyj bieżącej wersji środowiska uruchomieniowego języka wspólnego, aby utworzyć plik. exe lub. dll.</span><span class="sxs-lookup"><span data-stu-id="fd67d-115">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="fd67d-116">Jedynym wyjątkiem są zestawy zaprzyjaźnione i [-moduleassemblyname — (opcja kompilatora C#)](./moduleassemblyname-compiler-option.md), które działają w obszarze **-langversion: ISO-1**.</span><span class="sxs-lookup"><span data-stu-id="fd67d-116">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="fd67d-117">Aby poznać inne sposoby określania wersji języka C#, zobacz artykuł [Wybieranie języka c# w wersji](../configure-language-version.md) .</span><span class="sxs-lookup"><span data-stu-id="fd67d-117">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="fd67d-118">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A> .</span><span class="sxs-lookup"><span data-stu-id="fd67d-118">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fd67d-119">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="fd67d-119">C# language specification</span></span>

| <span data-ttu-id="fd67d-120">Wersja</span><span class="sxs-lookup"><span data-stu-id="fd67d-120">Version</span></span>          | <span data-ttu-id="fd67d-121">Link</span><span class="sxs-lookup"><span data-stu-id="fd67d-121">Link</span></span>                       | <span data-ttu-id="fd67d-122">Opis</span><span class="sxs-lookup"><span data-stu-id="fd67d-122">Description</span></span>                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="fd67d-123">C# 7,0 i nowsze</span><span class="sxs-lookup"><span data-stu-id="fd67d-123">C# 7.0 and later</span></span> |                            | <span data-ttu-id="fd67d-124">Obecnie niedostępne</span><span class="sxs-lookup"><span data-stu-id="fd67d-124">Not currently available</span></span>                                                 |
| <span data-ttu-id="fd67d-125">C# 6,0</span><span class="sxs-lookup"><span data-stu-id="fd67d-125">C# 6.0</span></span>           | <span data-ttu-id="fd67d-126">[Łącze][csharp-6]</span><span class="sxs-lookup"><span data-stu-id="fd67d-126">[Link][csharp-6]</span></span>           | <span data-ttu-id="fd67d-127">Specyfikacja języka C# w wersji 6 — nieoficjalne wersje robocze: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="fd67d-127">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span> |
| <span data-ttu-id="fd67d-128">C# 5,0</span><span class="sxs-lookup"><span data-stu-id="fd67d-128">C# 5.0</span></span>           | <span data-ttu-id="fd67d-129">[Pobierz plik PDF][csharp-5]</span><span class="sxs-lookup"><span data-stu-id="fd67d-129">[Download PDF][csharp-5]</span></span>   | <span data-ttu-id="fd67d-130">Standardowa ECMA-334, wersja 5</span><span class="sxs-lookup"><span data-stu-id="fd67d-130">Standard ECMA-334 5th Edition</span></span>                                           |
| <span data-ttu-id="fd67d-131">C# 3,0</span><span class="sxs-lookup"><span data-stu-id="fd67d-131">C# 3.0</span></span>           | <span data-ttu-id="fd67d-132">[Pobierz dokument][csharp-3]</span><span class="sxs-lookup"><span data-stu-id="fd67d-132">[Download DOC][csharp-3]</span></span>   | <span data-ttu-id="fd67d-133">Specyfikacja języka C# wersja 3,0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="fd67d-133">C# Language Specification Version 3.0: Microsoft Corporation</span></span>            |
| <span data-ttu-id="fd67d-134">C# 2,0</span><span class="sxs-lookup"><span data-stu-id="fd67d-134">C# 2.0</span></span>           | <span data-ttu-id="fd67d-135">[Pobierz plik PDF][csharp-2]</span><span class="sxs-lookup"><span data-stu-id="fd67d-135">[Download PDF][csharp-2]</span></span>   | <span data-ttu-id="fd67d-136">Standard ECMA-334 czwarta</span><span class="sxs-lookup"><span data-stu-id="fd67d-136">Standard ECMA-334 4th Edition</span></span>                                           |
| <span data-ttu-id="fd67d-137">C# 1,2</span><span class="sxs-lookup"><span data-stu-id="fd67d-137">C# 1.2</span></span>           | <span data-ttu-id="fd67d-138">[Pobierz dokument][csharp-1.2]</span><span class="sxs-lookup"><span data-stu-id="fd67d-138">[Download DOC][csharp-1.2]</span></span> | <span data-ttu-id="fd67d-139">Specyfikacja języka C# wersja 1,2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="fd67d-139">C# Language Specification Version 1.2: Microsoft Corporation</span></span>            |
| <span data-ttu-id="fd67d-140">C# 1,0</span><span class="sxs-lookup"><span data-stu-id="fd67d-140">C# 1.0</span></span>           | <span data-ttu-id="fd67d-141">[Pobierz dokument][csharp-1]</span><span class="sxs-lookup"><span data-stu-id="fd67d-141">[Download DOC][csharp-1]</span></span>   | <span data-ttu-id="fd67d-142">Specyfikacja języka C# wersja 1,0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="fd67d-142">C# Language Specification Version 1.0: Microsoft Corporation</span></span>            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="fd67d-143">Minimalna wersja zestawu SDK wymagana do obsługi wszystkich funkcji języka</span><span class="sxs-lookup"><span data-stu-id="fd67d-143">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="fd67d-144">W poniższej tabeli wymieniono minimalne wersje zestawu SDK z kompilatorem C#, który obsługuje odpowiednią wersję językową:</span><span class="sxs-lookup"><span data-stu-id="fd67d-144">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

| <span data-ttu-id="fd67d-145">Wersja języka C#</span><span class="sxs-lookup"><span data-stu-id="fd67d-145">C# version</span></span> | <span data-ttu-id="fd67d-146">Minimalna wersja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="fd67d-146">Minimum SDK version</span></span>                                                                  |
|------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="fd67d-147">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="fd67d-147">C# 8.0</span></span>     | <span data-ttu-id="fd67d-148">Microsoft Visual Studio/Build Tools 2019, wersja 16,3 lub .NET Core 3,0 SDK</span><span class="sxs-lookup"><span data-stu-id="fd67d-148">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span>         |
| <span data-ttu-id="fd67d-149">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="fd67d-149">C# 7.3</span></span>     | <span data-ttu-id="fd67d-150">Microsoft Visual Studio/Build Tools 2017, wersja 15,7</span><span class="sxs-lookup"><span data-stu-id="fd67d-150">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>                               |
| <span data-ttu-id="fd67d-151">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="fd67d-151">C# 7.2</span></span>     | <span data-ttu-id="fd67d-152">Microsoft Visual Studio/Build Tools 2017, wersja 15,5</span><span class="sxs-lookup"><span data-stu-id="fd67d-152">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>                               |
| <span data-ttu-id="fd67d-153">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="fd67d-153">C# 7.1</span></span>     | <span data-ttu-id="fd67d-154">Microsoft Visual Studio/Build Tools 2017, wersja 15,3</span><span class="sxs-lookup"><span data-stu-id="fd67d-154">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>                               |
| <span data-ttu-id="fd67d-155">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="fd67d-155">C# 7.0</span></span>     | <span data-ttu-id="fd67d-156">Narzędzia Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="fd67d-156">Microsoft Visual Studio/Build Tools 2017</span></span>                                             |
| <span data-ttu-id="fd67d-157">C# 6</span><span class="sxs-lookup"><span data-stu-id="fd67d-157">C# 6</span></span>       | <span data-ttu-id="fd67d-158">Narzędzia Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="fd67d-158">Microsoft Visual Studio/Build Tools 2015</span></span>                                             |
| <span data-ttu-id="fd67d-159">C# 5</span><span class="sxs-lookup"><span data-stu-id="fd67d-159">C# 5</span></span>       | <span data-ttu-id="fd67d-160">Microsoft Visual Studio/Build Tools 2012 lub z pakietem .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="fd67d-160">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>      |
| <span data-ttu-id="fd67d-161">C# 4</span><span class="sxs-lookup"><span data-stu-id="fd67d-161">C# 4</span></span>       | <span data-ttu-id="fd67d-162">Microsoft Visual Studio/Build Tools 2010 lub z pakietem .NET Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="fd67d-162">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>      |
| <span data-ttu-id="fd67d-163">C# 3</span><span class="sxs-lookup"><span data-stu-id="fd67d-163">C# 3</span></span>       | <span data-ttu-id="fd67d-164">Microsoft Visual Studio/Build Tools 2008 lub z pakietem .NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="fd67d-164">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>      |
| <span data-ttu-id="fd67d-165">C# 2</span><span class="sxs-lookup"><span data-stu-id="fd67d-165">C# 2</span></span>       | <span data-ttu-id="fd67d-166">Microsoft Visual Studio/Build Tools 2005 lub z pakietem .NET Framework 2,0</span><span class="sxs-lookup"><span data-stu-id="fd67d-166">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>      |
| <span data-ttu-id="fd67d-167">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="fd67d-167">C# 1.0/1.2</span></span> | <span data-ttu-id="fd67d-168">Narzędzia Microsoft Visual Studio/Build Tools .NET 2002 lub w pakiecie .NET Framework 1,0</span><span class="sxs-lookup"><span data-stu-id="fd67d-168">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="fd67d-169">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fd67d-169">See also</span></span>

- [<span data-ttu-id="fd67d-170">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="fd67d-170">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="fd67d-171">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="fd67d-171">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
