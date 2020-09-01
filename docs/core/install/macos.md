---
title: Zainstaluj platformę .NET Core w systemie macOS
description: Dowiedz się więcej na temat wersji programu macOS, na których można zainstalować program .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: 19d5ca77b0308533c8f228be70c61daf1b7f82d9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132758"
---
# <a name="install-net-core-on-macos"></a><span data-ttu-id="660df-103">Zainstaluj platformę .NET Core w systemie macOS</span><span class="sxs-lookup"><span data-stu-id="660df-103">Install .NET Core on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Instalowanie w systemie Windows](windows.md)
> - [Instalowanie w systemie macOS](macos.md)
> - [Instalowanie w systemie Linux](linux.md)

<span data-ttu-id="660df-107">W tym artykule dowiesz się, jak zainstalować platformę .NET Core w systemie macOS.</span><span class="sxs-lookup"><span data-stu-id="660df-107">In this article, you'll learn how to install .NET Core on macOS.</span></span> <span data-ttu-id="660df-108">Program .NET Core składa się z środowiska uruchomieniowego i zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="660df-108">.NET Core is made up of the runtime and the SDK.</span></span> <span data-ttu-id="660df-109">Środowisko uruchomieniowe służy do uruchamiania aplikacji platformy .NET Core i może być dołączane do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="660df-109">The runtime is used to run a .NET Core app and may or may not be included with the app.</span></span> <span data-ttu-id="660df-110">Zestaw SDK służy do tworzenia aplikacji i bibliotek platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="660df-110">The SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="660df-111">Środowisko uruchomieniowe platformy .NET Core jest zawsze instalowane z zestawem SDK.</span><span class="sxs-lookup"><span data-stu-id="660df-111">The .NET Core runtime is always installed with the SDK.</span></span>

<span data-ttu-id="660df-112">Najnowsza wersja platformy .NET Core to 3,1.</span><span class="sxs-lookup"><span data-stu-id="660df-112">The latest version of .NET Core is 3.1.</span></span>

> [!div class="button"]
> [<span data-ttu-id="660df-113">Pobierz program .NET Core</span><span class="sxs-lookup"><span data-stu-id="660df-113">Download .NET Core</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="660df-114">Obsługiwane wersje</span><span class="sxs-lookup"><span data-stu-id="660df-114">Supported releases</span></span>

<span data-ttu-id="660df-115">Poniższa tabela zawiera listę obecnie obsługiwanych wersji programu .NET Core oraz wersji macOS, na których są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="660df-115">The following table is a list of currently supported .NET Core releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="660df-116">Te wersje pozostają obsługiwane albo wersja [platformy .NET Core osiągnie koniec obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="660df-116">These versions remain supported either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="660df-117">✔️ wskazuje, że wersja platformy .NET Core jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="660df-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="660df-118">❌Wskazuje, że wersja programu .NET Core nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="660df-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="660df-119">System operacyjny</span><span class="sxs-lookup"><span data-stu-id="660df-119">Operating System</span></span>          | <span data-ttu-id="660df-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="660df-120">.NET Core 2.1</span></span> | <span data-ttu-id="660df-121">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="660df-121">.NET Core 3.1</span></span> | <span data-ttu-id="660df-122">.NET 5 (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="660df-122">.NET 5 Preview</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="660df-123">macOS 10,15 "Catalina"</span><span class="sxs-lookup"><span data-stu-id="660df-123">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="660df-124">✔️ 2,1 ([Informacje o wersji][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="660df-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="660df-125">✔️ 3,1 ([Informacje o wersji][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="660df-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="660df-126">✔️ 5,0 — wersja zapoznawcza ([Informacje o wersji][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="660df-126">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="660df-127">macOS 10,14 "Mojave"</span><span class="sxs-lookup"><span data-stu-id="660df-127">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="660df-128">✔️ 2,1 ([Informacje o wersji][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="660df-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="660df-129">✔️ 3,1 ([Informacje o wersji][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="660df-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="660df-130">✔️ 5,0 — wersja zapoznawcza ([Informacje o wersji][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="660df-130">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="660df-131">macOS 10,13 "wysoka firma Sierra"</span><span class="sxs-lookup"><span data-stu-id="660df-131">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="660df-132">✔️ 2,1 ([Informacje o wersji][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="660df-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="660df-133">✔️ 3,1 ([Informacje o wersji][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="660df-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="660df-134">✔️ 5,0 — wersja zapoznawcza ([Informacje o wersji][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="660df-134">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="660df-135">macOS 10,12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="660df-135">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="660df-136">✔️ 2,1 ([Informacje o wersji][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="660df-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="660df-137">❌ 3,1 ([Informacje o wersji][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="660df-137">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="660df-138">❌ 5,0 Preview ([Informacje o wersji][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="660df-138">❌ 5.0 Preview ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="660df-139">Nieobsługiwane wersje</span><span class="sxs-lookup"><span data-stu-id="660df-139">Unsupported releases</span></span>

<span data-ttu-id="660df-140">Następujące wersje programu .NET Core nie są ❌ już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="660df-140">The following versions of .NET Core are ❌ no longer supported.</span></span> <span data-ttu-id="660df-141">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="660df-141">The downloads for these still remain published:</span></span>

- <span data-ttu-id="660df-142">3,0 ([Informacje o wersji][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="660df-142">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="660df-143">2,2 ([Informacje o wersji][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="660df-143">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="660df-144">2,0 ([Informacje o wersji][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="660df-144">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="660df-145">Informacje o środowisku uruchomieniowym</span><span class="sxs-lookup"><span data-stu-id="660df-145">Runtime information</span></span>

<span data-ttu-id="660df-146">Środowisko uruchomieniowe służy do uruchamiania aplikacji utworzonych za pomocą platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="660df-146">The runtime is used to run apps created with .NET Core.</span></span> <span data-ttu-id="660df-147">Gdy autor aplikacji publikuje aplikację, może ona obejmować środowisko uruchomieniowe wraz z ich aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="660df-147">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="660df-148">Jeśli nie obejmują środowiska uruchomieniowego, można zainstalować środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="660df-148">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="660df-149">Istnieją trzy różne środowiska uruchomieniowe, które można zainstalować w systemie macOS:</span><span class="sxs-lookup"><span data-stu-id="660df-149">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="660df-150">*Środowisko uruchomieniowe ASP.NET Core*</span><span class="sxs-lookup"><span data-stu-id="660df-150">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="660df-151">Uruchamia ASP.NET Core aplikacje.</span><span class="sxs-lookup"><span data-stu-id="660df-151">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="660df-152">Zawiera środowisko uruchomieniowe platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="660df-152">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="660df-153">*Środowisko uruchomieniowe platformy .NET Core*</span><span class="sxs-lookup"><span data-stu-id="660df-153">*.NET Core runtime*</span></span>\
<span data-ttu-id="660df-154">To środowisko uruchomieniowe jest najprostszym środowiskiem uruchomieniowym i nie zawiera żadnego innego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="660df-154">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="660df-155">Zdecydowanie zaleca się zainstalowanie *ASP.NET Core środowiska uruchomieniowego* w celu uzyskania najlepszej zgodności z aplikacjami .NET Core.</span><span class="sxs-lookup"><span data-stu-id="660df-155">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET Core apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="660df-156">Pobierz środowisko uruchomieniowe platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="660df-156">Download .NET Core Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="660df-157">Informacje o zestawie SDK</span><span class="sxs-lookup"><span data-stu-id="660df-157">SDK information</span></span>

<span data-ttu-id="660df-158">Zestaw SDK służy do kompilowania i publikowania aplikacji i bibliotek platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="660df-158">The SDK is used to build and publish .NET Core apps and libraries.</span></span> <span data-ttu-id="660df-159">Instalowanie zestawu SDK obejmuje zarówno [środowisko uruchomieniowe](#runtime-information): ASP.NET Core, jak i .NET Core.</span><span class="sxs-lookup"><span data-stu-id="660df-159">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET Core.</span></span>

> [!div class="button"]
> [<span data-ttu-id="660df-160">Pobierz zestaw .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="660df-160">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a><span data-ttu-id="660df-161">Zależności</span><span class="sxs-lookup"><span data-stu-id="660df-161">Dependencies</span></span>

<span data-ttu-id="660df-162">Platforma .NET Core jest obsługiwana w następujących wersjach macOS:</span><span class="sxs-lookup"><span data-stu-id="660df-162">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="660df-163">`+`Symbol reprezentuje wersję minimalną.</span><span class="sxs-lookup"><span data-stu-id="660df-163">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="660df-164">Wersja platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="660df-164">.NET Core Version</span></span> | <span data-ttu-id="660df-165">macOS</span><span class="sxs-lookup"><span data-stu-id="660df-165">macOS</span></span>                 | <span data-ttu-id="660df-166">Architektury</span><span class="sxs-lookup"><span data-stu-id="660df-166">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="660df-167">3,1</span><span class="sxs-lookup"><span data-stu-id="660df-167">3.1</span></span>               | <span data-ttu-id="660df-168">Wysoka firma Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="660df-168">High Sierra (10.13+)</span></span>  | <span data-ttu-id="660df-169">x64</span><span class="sxs-lookup"><span data-stu-id="660df-169">x64</span></span> | [<span data-ttu-id="660df-170">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="660df-170">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="660df-171">3,0</span><span class="sxs-lookup"><span data-stu-id="660df-171">3.0</span></span>               | <span data-ttu-id="660df-172">Wysoka firma Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="660df-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="660df-173">x64</span><span class="sxs-lookup"><span data-stu-id="660df-173">x64</span></span> | [<span data-ttu-id="660df-174">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="660df-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="660df-175">2.2</span><span class="sxs-lookup"><span data-stu-id="660df-175">2.2</span></span>               | <span data-ttu-id="660df-176">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="660df-176">Sierra (10.12+)</span></span>       | <span data-ttu-id="660df-177">x64</span><span class="sxs-lookup"><span data-stu-id="660df-177">x64</span></span> | [<span data-ttu-id="660df-178">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="660df-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="660df-179">2.1</span><span class="sxs-lookup"><span data-stu-id="660df-179">2.1</span></span>               | <span data-ttu-id="660df-180">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="660df-180">Sierra (10.12+)</span></span>       | <span data-ttu-id="660df-181">x64</span><span class="sxs-lookup"><span data-stu-id="660df-181">x64</span></span> | [<span data-ttu-id="660df-182">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="660df-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="660df-183">Począwszy od programu macOS Catalina (wersja 10,15), całe oprogramowanie skompilowane po 1 czerwca 2019, które jest dystrybuowane z IDENTYFIKATORem dewelopera, musi być notarialne.</span><span class="sxs-lookup"><span data-stu-id="660df-183">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="660df-184">To wymaganie dotyczy środowiska uruchomieniowego .NET Core, zestaw .NET Core SDK i oprogramowania utworzonego za pomocą platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="660df-184">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="660df-185">Instalatory dla programu .NET Core (zarówno środowisko uruchomieniowe, jak i zestaw SDK) w wersji 3,1, 3,0 i 2,1 zostały zgłoszone od 18 lutego 2020.</span><span class="sxs-lookup"><span data-stu-id="660df-185">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="660df-186">Wcześniejsze wersje nie zostały ujawnione.</span><span class="sxs-lookup"><span data-stu-id="660df-186">Prior released versions aren't notarized.</span></span> <span data-ttu-id="660df-187">Jeśli uruchomisz zanotarialną aplikację, zobaczysz komunikat o błędzie podobny do następującego:</span><span class="sxs-lookup"><span data-stu-id="660df-187">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Alert notarization macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="660df-189">Aby uzyskać więcej informacji na temat sposobu, w jaki wymuszone — notarization wpływa na platformę .NET Core (i aplikacje platformy .NET Core), zobacz [Praca z MacOS Catalina notarization](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="660df-189">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="660df-190">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="660df-190">libgdiplus</span></span>

<span data-ttu-id="660df-191">Aplikacje .NET Core używające zestawu *System. Drawing. Common* wymagają zainstalowania libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="660df-191">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="660df-192">Łatwym sposobem uzyskania libgdiplus jest użycie Menedżera pakietów [oprogramowania homebrew ("rozwiązania brew")](https://brew.sh/) dla macOS.</span><span class="sxs-lookup"><span data-stu-id="660df-192">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="660df-193">Po zainstalowaniu *rozwiązania brew*Zainstaluj libgdiplus, wykonując następujące polecenia w wierszu terminalu (polecenie):</span><span class="sxs-lookup"><span data-stu-id="660df-193">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="660df-194">Instalowanie za pomocą Instalatora</span><span class="sxs-lookup"><span data-stu-id="660df-194">Install with an installer</span></span>

<span data-ttu-id="660df-195">macOS ma autonomiczne Instalatory, których można użyć do zainstalowania zestawu SDK programu .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="660df-195">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="660df-196">Procesory x64 (64-bitowe)</span><span class="sxs-lookup"><span data-stu-id="660df-196">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="660df-197">Pobierz i ręcznie zainstaluj</span><span class="sxs-lookup"><span data-stu-id="660df-197">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="660df-198">Jako alternatywę dla instalatorów macOS dla platformy .NET Core można pobrać i ręcznie zainstalować zestaw SDK i środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="660df-198">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="660df-199">Instalacja ręczna jest zwykle wykonywana w ramach testowania ciągłej integracji.</span><span class="sxs-lookup"><span data-stu-id="660df-199">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="660df-200">Dla deweloperów lub użytkowników zazwyczaj lepiej jest użyć [Instalatora](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="660df-200">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="660df-201">W przypadku zainstalowania zestaw .NET Core SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="660df-201">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="660df-202">Najpierw pobierz wydanie **binarne** dla zestawu SDK lub środowiska uruchomieniowego z jednej z następujących lokacji:</span><span class="sxs-lookup"><span data-stu-id="660df-202">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="660df-203">✔️ [pobierania wersji zapoznawczej programu .net 5,0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="660df-203">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="660df-204">[pliki do pobrania ✔️ .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="660df-204">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="660df-205">[pliki do pobrania ✔️ .NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="660df-205">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="660df-206">Wszystkie pliki do pobrania z platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="660df-206">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="660df-207">Następnie wyodrębnij pobrany plik i użyj polecenia, `export` Aby ustawić zmienne używane przez platformę .NET Core, a następnie upewnij się, że program .NET Core znajduje się w ścieżce.</span><span class="sxs-lookup"><span data-stu-id="660df-207">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="660df-208">Aby wyodrębnić środowisko uruchomieniowe i udostępnić interfejs wiersza polecenia platformy .NET Core polecenia w terminalu, należy najpierw pobrać wydanie binarne platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="660df-208">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="660df-209">Następnie otwórz Terminal i uruchom następujące polecenia z katalogu, w którym zapisano plik.</span><span class="sxs-lookup"><span data-stu-id="660df-209">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="660df-210">Nazwa pliku archiwum może się różnić w zależności od pobranych informacji.</span><span class="sxs-lookup"><span data-stu-id="660df-210">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="660df-211">**Aby wyodrębnić środowisko uruchomieniowe, użyj następującego polecenia**:</span><span class="sxs-lookup"><span data-stu-id="660df-211">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="660df-212">**Użyj następującego polecenia, aby wyodrębnić zestaw SDK**:</span><span class="sxs-lookup"><span data-stu-id="660df-212">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="660df-213">Powyższe `export` polecenia sprawiają, że polecenia interfejs wiersza polecenia platformy .NET Core są dostępne tylko dla sesji terminalu, w której została uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="660df-213">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="660df-214">Możesz edytować profil powłoki, aby trwale dodać polecenia.</span><span class="sxs-lookup"><span data-stu-id="660df-214">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="660df-215">Istnieje wiele różnych powłok dostępnych dla systemu Linux, a każdy z nich ma inny profil.</span><span class="sxs-lookup"><span data-stu-id="660df-215">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="660df-216">Przykład:</span><span class="sxs-lookup"><span data-stu-id="660df-216">For example:</span></span>
>
> - <span data-ttu-id="660df-217">**Bash Shell**: *~/. bash_profile*, *~/.bashrc.*</span><span class="sxs-lookup"><span data-stu-id="660df-217">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="660df-218">**Powłoka Korn**: *~/.KSHRC* lub *. profile*</span><span class="sxs-lookup"><span data-stu-id="660df-218">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="660df-219">**Powłoka Z**: *~/.zshrc* lub *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="660df-219">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="660df-220">Edytuj odpowiedni plik źródłowy dla powłoki i Dodaj `:$HOME/dotnet` na końcu istniejącej `PATH` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="660df-220">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="660df-221">Jeśli `PATH` instrukcja nie jest uwzględniona, Dodaj nowy wiersz za pomocą `export PATH=$PATH:$HOME/dotnet` .</span><span class="sxs-lookup"><span data-stu-id="660df-221">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="660df-222">Ponadto Dodaj `export DOTNET_ROOT=$HOME/dotnet` na końcu pliku.</span><span class="sxs-lookup"><span data-stu-id="660df-222">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="660df-223">Takie podejście umożliwia zainstalowanie różnych wersji w oddzielnych lokalizacjach i wybór jawny, który ma być używany przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="660df-223">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="660df-224">Zainstaluj przy użyciu Visual Studio dla komputerów Mac</span><span class="sxs-lookup"><span data-stu-id="660df-224">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="660df-225">Visual Studio dla komputerów Mac instaluje zestaw .NET Core SDK w przypadku wybrania obciążenia **.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="660df-225">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="660df-226">Aby rozpocząć pracę z programowaniem programu .NET Core w systemie macOS, zobacz [Instalowanie programu Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="660df-226">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="660df-227">W przypadku najnowszej wersji programu .NET Core 3,1 należy użyć Visual Studio dla komputerów Mac 8,4.</span><span class="sxs-lookup"><span data-stu-id="660df-227">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="660df-228">[![macOS Visual Studio 2019 for Mac z funkcją obciążenia .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="660df-228">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="660df-229">Zainstaluj obok Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="660df-229">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="660df-230">Visual Studio Code to zaawansowany i lekki Edytor kodu źródłowego, który jest uruchamiany na pulpicie.</span><span class="sxs-lookup"><span data-stu-id="660df-230">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="660df-231">Visual Studio Code jest dostępny dla systemów Windows, macOS i Linux.</span><span class="sxs-lookup"><span data-stu-id="660df-231">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="660df-232">Mimo że Visual Studio Code nie jest dołączony do zautomatyzowanego Instalatora .NET Core, takiego jak Visual Studio, Dodawanie obsługi .NET Core jest proste.</span><span class="sxs-lookup"><span data-stu-id="660df-232">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="660df-233">[Pobierz i zainstaluj Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="660df-233">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="660df-234">[Pobierz i zainstaluj zestaw .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="660df-234">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="660df-235">[Zainstaluj rozszerzenie C# z witryny Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="660df-235">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="660df-236">Instalowanie przy użyciu usługi Bash Automation</span><span class="sxs-lookup"><span data-stu-id="660df-236">Install with bash automation</span></span>

<span data-ttu-id="660df-237">[Skrypty programu dotnet-Install](../tools/dotnet-install-script.md) są używane na potrzeby automatyzacji i instalacji niebędących administratorami środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="660df-237">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="660df-238">Skrypt można pobrać ze [strony odniesienia do skryptu dotnet-Install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="660df-238">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="660df-239">Skrypt domyślnie instaluje najnowszą [LTS](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) wersję, która jest platformą .net Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="660df-239">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="660df-240">Możesz wybrać określoną wersję, określając `current` przełącznik.</span><span class="sxs-lookup"><span data-stu-id="660df-240">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="660df-241">Dołącz `runtime` przełącznik, aby zainstalować środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="660df-241">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="660df-242">W przeciwnym razie skrypt instaluje [zestaw SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="660df-242">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="660df-243">Powyższe polecenie instaluje środowisko uruchomieniowe ASP.NET Core, aby uzyskać maksymalną zgodność.</span><span class="sxs-lookup"><span data-stu-id="660df-243">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="660df-244">Środowisko uruchomieniowe ASP.NET Core obejmuje również standardowe środowisko uruchomieniowe programu .NET Core.</span><span class="sxs-lookup"><span data-stu-id="660df-244">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="660df-245">Docker</span><span class="sxs-lookup"><span data-stu-id="660df-245">Docker</span></span>

<span data-ttu-id="660df-246">Kontenery zapewniają lekki sposób izolowania aplikacji od pozostałej części systemu hosta.</span><span class="sxs-lookup"><span data-stu-id="660df-246">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="660df-247">Kontenery na tym samym komputerze udostępniają tylko jądro i używają zasobów przyznanych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="660df-247">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="660df-248">Środowisko .NET Core można uruchomić w kontenerze platformy Docker.</span><span class="sxs-lookup"><span data-stu-id="660df-248">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="660df-249">Oficjalne obrazy .NET Core Docker są publikowane w Container Registry firmy Microsoft (MCR) i można je odnajdywać w [repozytorium Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="660df-249">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="660df-250">Każde repozytorium zawiera obrazy różnych kombinacji platformy .NET (zestawu SDK lub środowiska uruchomieniowego) i systemu operacyjnego, których można użyć.</span><span class="sxs-lookup"><span data-stu-id="660df-250">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="660df-251">Firma Microsoft udostępnia obrazy dostosowane do konkretnych scenariuszy.</span><span class="sxs-lookup"><span data-stu-id="660df-251">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="660df-252">Na przykład [repozytorium ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) zawiera obrazy skompilowane do uruchamiania aplikacji ASP.NET Core w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="660df-252">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="660df-253">Aby uzyskać więcej informacji na temat korzystania z platformy .NET Core w kontenerze platformy Docker, zobacz [wprowadzenie do oprogramowania .NET i platformy Docker](../docker/introduction.md) i [przykładów](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="660df-253">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="660df-254">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="660df-254">Next steps</span></span>

- <span data-ttu-id="660df-255">[Jak sprawdzić, czy program .NET Core jest już zainstalowany](how-to-detect-installed-versions.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="660df-255">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="660df-256">[Praca z MacOS Catalina notarization](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="660df-256">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="660df-257">[Samouczek: Rozpoczynanie pracy w witrynie macOS](../tutorials/with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="660df-257">[Tutorial: Get started on macOS](../tutorials/with-visual-studio-mac.md).</span></span>
- <span data-ttu-id="660df-258">[Samouczek: Tworzenie nowej aplikacji przy użyciu Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="660df-258">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="660df-259">[Samouczek: konteneryzowanie aplikacji .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="660df-259">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
