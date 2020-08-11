---
title: Tworzenie pakietów dystrybucji platformy .NET Core
description: Dowiedz się, jak spakować, nazwać i wersja .NET Core do dystrybucji.
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: 3324a6a151fc6dc46a8f13ea17c89da99d108d82
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062889"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="0b707-103">Tworzenie pakietów dystrybucji platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="0b707-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="0b707-104">Ponieważ platforma .NET Core jest dostępna na więcej i większej liczbie platform, warto dowiedzieć się, jak spakować, nazwać i wersja.</span><span class="sxs-lookup"><span data-stu-id="0b707-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="0b707-105">W ten sposób programy obsługi pakietów mogą pomóc w zapewnieniu spójnego środowiska bez względu na to, gdzie użytkownicy zdecydują się na uruchomienie platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="0b707-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="0b707-106">Ten artykuł jest przydatny dla użytkowników, którzy są:</span><span class="sxs-lookup"><span data-stu-id="0b707-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="0b707-107">Podjęto próbę skompilowania platformy .NET Core ze źródła.</span><span class="sxs-lookup"><span data-stu-id="0b707-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="0b707-108">Chce wprowadzić zmiany w interfejs wiersza polecenia platformy .NET Core, które mogą mieć wpływ na wynikowy układ lub pakiety.</span><span class="sxs-lookup"><span data-stu-id="0b707-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="0b707-109">Układ dysku</span><span class="sxs-lookup"><span data-stu-id="0b707-109">Disk layout</span></span>

<span data-ttu-id="0b707-110">Po zainstalowaniu programu .NET Core składa się z kilku składników, które zostały wdrożone w systemie plików:</span><span class="sxs-lookup"><span data-stu-id="0b707-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
{dotnet_root}                                     (*)
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host                                          (*)
│   └── fxr                                       (*)
│       └── <fxr version>        (2)
├── sdk                                           (*)
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)              (*)
├── packs                                         (*)
│   ├── Microsoft.AspNetCore.App.Ref              (*)
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref                 (*)
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>          (*)
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref          (*)
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref                   (*)
│       └── <netstandard version>        (15)
├── shared                                        (*)
│   ├── Microsoft.NETCore.App                     (*)
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App                  (*)
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All                  (*)
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App              (*)
│       └── <desktop app version> (7)
└── templates                                     (*)
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="0b707-111">(1) **dotnet** Host (znany również jako "muxer") ma dwie odrębne role: Aktywuj środowisko uruchomieniowe, aby uruchomić aplikację, i aktywuj zestaw SDK, aby wysłać do niego polecenia.</span><span class="sxs-lookup"><span data-stu-id="0b707-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="0b707-112">Host jest natywnym plikiem wykonywalnym ( `dotnet.exe` ).</span><span class="sxs-lookup"><span data-stu-id="0b707-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="0b707-113">W przypadku jednego hosta większość innych składników znajduje się w katalogach z wersjami (2, 3, 5, 6).</span><span class="sxs-lookup"><span data-stu-id="0b707-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="0b707-114">Oznacza to, że w systemie może być dostępnych wiele wersji, ponieważ są one instalowane obok siebie.</span><span class="sxs-lookup"><span data-stu-id="0b707-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="0b707-115">(2) \*\*host/FXR/ \<fxr version> \*\* zawiera logikę rozpoznawania architektury używaną przez hosta.</span><span class="sxs-lookup"><span data-stu-id="0b707-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="0b707-116">Host używa najnowszej hostfxr, która jest zainstalowana.</span><span class="sxs-lookup"><span data-stu-id="0b707-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="0b707-117">Hostfxr jest odpowiedzialny za wybór odpowiedniego środowiska uruchomieniowego podczas wykonywania aplikacji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0b707-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="0b707-118">Na przykład aplikacja skompilowana dla programu .NET Core 2.0.0 używa środowiska uruchomieniowego 2.0.5, gdy jest ono dostępne.</span><span class="sxs-lookup"><span data-stu-id="0b707-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="0b707-119">Podobnie hostfxr wybiera odpowiedni zestaw SDK podczas opracowywania.</span><span class="sxs-lookup"><span data-stu-id="0b707-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="0b707-120">(3) **zestaw SDK \<sdk version> /** zestaw SDK (znany również jako "narzędzia") to zestaw narzędzi zarządzanych, które są używane do pisania i kompilowania bibliotek i aplikacji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0b707-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="0b707-121">Zestaw SDK zawiera interfejs wiersza polecenia platformy .NET Core, kompilatory języków zarządzanych, program MSBuild oraz skojarzone zadania kompilacji i elementy docelowe, narzędzia NuGet, nowe szablony projektów itd.</span><span class="sxs-lookup"><span data-stu-id="0b707-121">The SDK includes the .NET Core CLI, the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="0b707-122">(4) **zestaw SDK/NuGetFallbackFolder** zawiera pamięć podręczną pakietów NuGet używanych przez zestaw SDK podczas operacji przywracania, na przykład w przypadku uruchamiania systemu `dotnet restore` lub `dotnet build` .</span><span class="sxs-lookup"><span data-stu-id="0b707-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build`.</span></span> <span data-ttu-id="0b707-123">Ten folder jest używany tylko przed platformą .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="0b707-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="0b707-124">Nie można go skompilować ze źródła, ponieważ zawiera wstępnie skompilowane zasoby binarne z `nuget.org` .</span><span class="sxs-lookup"><span data-stu-id="0b707-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="0b707-125">Folder **udostępniony** zawiera struktury.</span><span class="sxs-lookup"><span data-stu-id="0b707-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="0b707-126">Struktura udostępniona udostępnia zestaw bibliotek w centralnej lokalizacji, dzięki czemu mogą one być używane przez różne aplikacje.</span><span class="sxs-lookup"><span data-stu-id="0b707-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="0b707-127">(5) \*\*Shared/Microsoft. Core. app/ \<runtime version> \*\* to Framework zawiera środowisko uruchomieniowe platformy .NET Core i obsługujące biblioteki zarządzane.</span><span class="sxs-lookup"><span data-stu-id="0b707-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="0b707-128">(6) \*\*Shared/Microsoft. AspNetCore. { Aplikacja, wszystkie}/ \<aspnetcore version> \*\* zawiera biblioteki ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0b707-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="0b707-129">Biblioteki w obszarze programu `Microsoft.AspNetCore.App` są opracowywane i obsługiwane w ramach projektu .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0b707-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="0b707-130">Biblioteki w obszarze `Microsoft.AspNetCore.All` stanowią nadzbiór, który zawiera również biblioteki innych firm.</span><span class="sxs-lookup"><span data-stu-id="0b707-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="0b707-131">(7) \*\*Shared/Microsoft. Desktop. app/ \<desktop app version> \*\* zawiera biblioteki pulpitu systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="0b707-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="0b707-132">Nie jest to uwzględnione na platformach innych niż Windows.</span><span class="sxs-lookup"><span data-stu-id="0b707-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="0b707-133">(8) **LICENSE.txt, ThirdPartyNotices.txt** to licencja .NET Core i licencje na biblioteki innych firm używane odpowiednio w programie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0b707-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="0b707-134">(9, 10) **dotnet. 1. gz, dotnet** `dotnet.1.gz` jest stroną ręczną dotnet.</span><span class="sxs-lookup"><span data-stu-id="0b707-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="0b707-135">`dotnet`jest link symboliczny hosta dotnet (1).</span><span class="sxs-lookup"><span data-stu-id="0b707-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="0b707-136">Te pliki są instalowane w dobrze znanych lokalizacjach na potrzeby integracji systemu.</span><span class="sxs-lookup"><span data-stu-id="0b707-136">These files are installed at well-known locations for system integration.</span></span>

- <span data-ttu-id="0b707-137">(11, 12) **Microsoft. servicecore. app. ref, Microsoft. AspNetCore. app. ref** opisują odpowiednio interfejs API `x.y` wersji programu .net core i ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0b707-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="0b707-138">Te pakiety są używane podczas kompilowania dla tych wersji docelowych.</span><span class="sxs-lookup"><span data-stu-id="0b707-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="0b707-139">(13) \*\*Microsoft. servicecore. app. host. \<rid> \*\*</span><span class="sxs-lookup"><span data-stu-id="0b707-139">(13) **Microsoft.NETCore.App.Host.\<rid>**</span></span> <span data-ttu-id="0b707-140">zawiera natywny plik binarny dla platformy `rid` .</span><span class="sxs-lookup"><span data-stu-id="0b707-140">contains a native binary for platform `rid`.</span></span> <span data-ttu-id="0b707-141">Ten plik binarny jest szablonem podczas kompilowania aplikacji .NET Core do natywnego pliku binarnego dla tej platformy.</span><span class="sxs-lookup"><span data-stu-id="0b707-141">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="0b707-142">(14) **Microsoft. WindowsDesktop. app. ref** — zawiera opis interfejsu API `x.y` wersji aplikacji klasycznych systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="0b707-142">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="0b707-143">Te pliki są używane podczas kompilowania dla tego obiektu docelowego.</span><span class="sxs-lookup"><span data-stu-id="0b707-143">These files are used when compiling for that target.</span></span> <span data-ttu-id="0b707-144">Nie jest to obsługiwane na platformach innych niż Windows.</span><span class="sxs-lookup"><span data-stu-id="0b707-144">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="0b707-145">(15) **Standard. Library. ref** — opisuje standardowy `x.y` interfejs API.</span><span class="sxs-lookup"><span data-stu-id="0b707-145">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="0b707-146">Te pliki są używane podczas kompilowania dla tego obiektu docelowego.</span><span class="sxs-lookup"><span data-stu-id="0b707-146">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="0b707-147">(16) **/etc/dotnet/install_location** jest plikiem, który zawiera pełną ścieżkę do `{dotnet_root}` .</span><span class="sxs-lookup"><span data-stu-id="0b707-147">(16) **/etc/dotnet/install_location** is a file that contains the full path for `{dotnet_root}`.</span></span> <span data-ttu-id="0b707-148">Ścieżka może kończyć się znakiem nowego wiersza.</span><span class="sxs-lookup"><span data-stu-id="0b707-148">The path may end with a newline.</span></span> <span data-ttu-id="0b707-149">Nie trzeba dodawać tego pliku, gdy katalog główny to `/usr/share/dotnet` .</span><span class="sxs-lookup"><span data-stu-id="0b707-149">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="0b707-150">**Szablony** (17) zawierają szablony używane przez zestaw SDK.</span><span class="sxs-lookup"><span data-stu-id="0b707-150">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="0b707-151">Na przykład w `dotnet new` tym miejscu znajduje się szablon projektu.</span><span class="sxs-lookup"><span data-stu-id="0b707-151">For example, `dotnet new` finds project templates here.</span></span>

<span data-ttu-id="0b707-152">Foldery oznaczone za pomocą `(*)` są używane przez wiele pakietów.</span><span class="sxs-lookup"><span data-stu-id="0b707-152">The folders marked with `(*)` are used by multiple packages.</span></span> <span data-ttu-id="0b707-153">Niektóre formaty pakietów (na przykład `rpm` ) wymagają specjalnej obsługi takich folderów.</span><span class="sxs-lookup"><span data-stu-id="0b707-153">Some package formats (for example, `rpm`) require special handling of such folders.</span></span> <span data-ttu-id="0b707-154">Należy zachować ostrożność nad pakietem.</span><span class="sxs-lookup"><span data-stu-id="0b707-154">The package maintainer must take care of this.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="0b707-155">Zalecane pakiety</span><span class="sxs-lookup"><span data-stu-id="0b707-155">Recommended packages</span></span>

<span data-ttu-id="0b707-156">Wersja programu .NET Core jest oparta na numerach wersji składnika środowiska uruchomieniowego `[major].[minor]` .</span><span class="sxs-lookup"><span data-stu-id="0b707-156">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="0b707-157">Wersja zestawu SDK używa tych samych `[major].[minor]` i ma niezależną `[patch]` , która łączy semantykę funkcji i poprawki dla zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="0b707-157">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="0b707-158">Na przykład: zestaw SDK w wersji 2.2.302 to druga wersja poprawki zestawu SDK, która obsługuje środowisko uruchomieniowe 2,2.</span><span class="sxs-lookup"><span data-stu-id="0b707-158">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="0b707-159">Aby uzyskać więcej informacji o działaniu wersji, zobacz [Omówienie wersji platformy .NET Core](./versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="0b707-159">For more information about how versioning works, see [.NET Core versioning overview](./versions/index.md).</span></span>

<span data-ttu-id="0b707-160">Niektóre pakiety zawierają część numeru wersji w nazwie.</span><span class="sxs-lookup"><span data-stu-id="0b707-160">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="0b707-161">Pozwala to na zainstalowanie określonej wersji.</span><span class="sxs-lookup"><span data-stu-id="0b707-161">This allows you to install a specific version.</span></span>
<span data-ttu-id="0b707-162">Reszta wersji nie jest uwzględniona w nazwie wersji.</span><span class="sxs-lookup"><span data-stu-id="0b707-162">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="0b707-163">Dzięki temu Menedżer pakietów systemu operacyjnego może aktualizować pakiety (na przykład automatycznie instalując poprawki zabezpieczeń).</span><span class="sxs-lookup"><span data-stu-id="0b707-163">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="0b707-164">Obsługiwane menedżery pakietów są specyficzne dla systemu Linux.</span><span class="sxs-lookup"><span data-stu-id="0b707-164">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="0b707-165">Poniżej przedstawiono listę zalecanych pakietów:</span><span class="sxs-lookup"><span data-stu-id="0b707-165">The following lists the recommended packages:</span></span>

- <span data-ttu-id="0b707-166">`dotnet-sdk-[major].[minor]`-Instaluje najnowszy zestaw SDK dla określonego środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="0b707-166">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="0b707-167">**Wersja:**\<sdk version></span><span class="sxs-lookup"><span data-stu-id="0b707-167">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="0b707-168">**Przykład:** dotnet-sdk-2,1</span><span class="sxs-lookup"><span data-stu-id="0b707-168">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="0b707-169">**Zawiera:** (3), (4)</span><span class="sxs-lookup"><span data-stu-id="0b707-169">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="0b707-170">**Zależności:** `dotnet-runtime-[major].[minor]` , `aspnetcore-runtime-[major].[minor]` , `dotnet-targeting-pack-[major].[minor]` , `aspnetcore-targeting-pack-[major].[minor]` , `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` , `dotnet-apphost-pack-[major].[minor]``dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="0b707-170">**Dependencies:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="0b707-171">`aspnetcore-runtime-[major].[minor]`-Instaluje określone środowisko uruchomieniowe ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0b707-171">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="0b707-172">**Wersja:**\<aspnetcore runtime version></span><span class="sxs-lookup"><span data-stu-id="0b707-172">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="0b707-173">**Przykład:** aspnetcore-runtime-2,1</span><span class="sxs-lookup"><span data-stu-id="0b707-173">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="0b707-174">**Zawiera:** (6)</span><span class="sxs-lookup"><span data-stu-id="0b707-174">**Contains:** (6)</span></span>
  - <span data-ttu-id="0b707-175">**Zależności:**`dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="0b707-175">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="0b707-176">`dotnet-runtime-deps-[major].[minor]`_(Opcjonalnie)_ — instaluje zależności do uruchamiania aplikacji samodzielnych</span><span class="sxs-lookup"><span data-stu-id="0b707-176">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="0b707-177">**Wersja:**\<runtime version></span><span class="sxs-lookup"><span data-stu-id="0b707-177">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="0b707-178">**Przykład:** dotnet-Runtime-deps-2,1</span><span class="sxs-lookup"><span data-stu-id="0b707-178">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="0b707-179">**Zależności:** _zależności dotyczące dystrybucji_</span><span class="sxs-lookup"><span data-stu-id="0b707-179">**Dependencies:** _distribution-specific dependencies_</span></span>

- <span data-ttu-id="0b707-180">`dotnet-runtime-[major].[minor]`-Instaluje określone środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="0b707-180">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="0b707-181">**Wersja:**\<runtime version></span><span class="sxs-lookup"><span data-stu-id="0b707-181">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="0b707-182">**Przykład:** dotnet-runtime-2,1</span><span class="sxs-lookup"><span data-stu-id="0b707-182">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="0b707-183">**Zawiera:** (5)</span><span class="sxs-lookup"><span data-stu-id="0b707-183">**Contains:** (5)</span></span>
  - <span data-ttu-id="0b707-184">**Zależności:** `dotnet-hostfxr-[major].[minor]` ,`dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="0b707-184">**Dependencies:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="0b707-185">`dotnet-hostfxr-[major].[minor]`-zależność</span><span class="sxs-lookup"><span data-stu-id="0b707-185">`dotnet-hostfxr-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="0b707-186">**Wersja:**\<runtime version></span><span class="sxs-lookup"><span data-stu-id="0b707-186">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="0b707-187">**Przykład:** dotnet-hostfxr-3,0</span><span class="sxs-lookup"><span data-stu-id="0b707-187">**Example:** dotnet-hostfxr-3.0</span></span>
  - <span data-ttu-id="0b707-188">**Zawiera:** (2)</span><span class="sxs-lookup"><span data-stu-id="0b707-188">**Contains:** (2)</span></span>
  - <span data-ttu-id="0b707-189">**Zależności:**`dotnet-host`</span><span class="sxs-lookup"><span data-stu-id="0b707-189">**Dependencies:** `dotnet-host`</span></span>

- <span data-ttu-id="0b707-190">`dotnet-host`-zależność</span><span class="sxs-lookup"><span data-stu-id="0b707-190">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="0b707-191">**Wersja:**\<runtime version></span><span class="sxs-lookup"><span data-stu-id="0b707-191">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="0b707-192">**Przykład:** dotnet-Host</span><span class="sxs-lookup"><span data-stu-id="0b707-192">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="0b707-193">**Zawiera:** (1), (8), (9), (10), (16)</span><span class="sxs-lookup"><span data-stu-id="0b707-193">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="0b707-194">`dotnet-apphost-pack-[major].[minor]`-zależność</span><span class="sxs-lookup"><span data-stu-id="0b707-194">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="0b707-195">**Wersja:**\<runtime version></span><span class="sxs-lookup"><span data-stu-id="0b707-195">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="0b707-196">**Zawiera:** (13)</span><span class="sxs-lookup"><span data-stu-id="0b707-196">**Contains:** (13)</span></span>

- <span data-ttu-id="0b707-197">`dotnet-targeting-pack-[major].[minor]`-Zezwala na nienajnowszy czas wykonywania</span><span class="sxs-lookup"><span data-stu-id="0b707-197">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="0b707-198">**Wersja:**\<runtime version></span><span class="sxs-lookup"><span data-stu-id="0b707-198">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="0b707-199">**Zawiera:** (12)</span><span class="sxs-lookup"><span data-stu-id="0b707-199">**Contains:** (12)</span></span>

- <span data-ttu-id="0b707-200">`aspnetcore-targeting-pack-[major].[minor]`-Zezwala na nienajnowszy czas wykonywania</span><span class="sxs-lookup"><span data-stu-id="0b707-200">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="0b707-201">**Wersja:**\<aspnetcore runtime version></span><span class="sxs-lookup"><span data-stu-id="0b707-201">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="0b707-202">**Zawiera:** (11)</span><span class="sxs-lookup"><span data-stu-id="0b707-202">**Contains:** (11)</span></span>

- <span data-ttu-id="0b707-203">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`-Umożliwia kierowanie do wersji standardowej</span><span class="sxs-lookup"><span data-stu-id="0b707-203">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="0b707-204">**Wersja:**\<sdk version></span><span class="sxs-lookup"><span data-stu-id="0b707-204">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="0b707-205">**Zawiera:** (15)</span><span class="sxs-lookup"><span data-stu-id="0b707-205">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="0b707-206">**Wersja:**\<sdk version></span><span class="sxs-lookup"><span data-stu-id="0b707-206">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="0b707-207">**Zawiera:** (15)</span><span class="sxs-lookup"><span data-stu-id="0b707-207">**Contains:** (15)</span></span>

<span data-ttu-id="0b707-208">`dotnet-runtime-deps-[major].[minor]`Wymaga zrozumienie _zależności specyficznych dla dystrybucji_.</span><span class="sxs-lookup"><span data-stu-id="0b707-208">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro-specific dependencies_.</span></span> <span data-ttu-id="0b707-209">Ponieważ system kompilacji dystrybucji może być w stanie automatycznie dziedziczyć, pakiet jest opcjonalny, w takim przypadku te zależności są dodawane bezpośrednio do `dotnet-runtime-[major].[minor]` pakietu.</span><span class="sxs-lookup"><span data-stu-id="0b707-209">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="0b707-210">Gdy zawartość pakietu znajduje się w folderze z uruchomioną wersją, nazwa pakietu jest `[major].[minor]` zgodna z nazwą folderu z wersją.</span><span class="sxs-lookup"><span data-stu-id="0b707-210">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="0b707-211">Wszystkie pakiety, z wyjątkiem programu `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` , są również zgodne z wersją .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0b707-211">For all packages, except the `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="0b707-212">Zależności między pakietami powinny mieć wartość _równą lub większą niż_ wymaganie wersji.</span><span class="sxs-lookup"><span data-stu-id="0b707-212">Dependencies between packages should use an _equal or greater than_ version requirement.</span></span> <span data-ttu-id="0b707-213">Na przykład `dotnet-sdk-2.2:2.2.401` wymaga `aspnetcore-runtime-2.2 >= 2.2.6` .</span><span class="sxs-lookup"><span data-stu-id="0b707-213">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="0b707-214">Dzięki temu użytkownik może uaktualnić instalację za pośrednictwem pakietu głównego (na przykład `dnf update dotnet-sdk-2.2` ).</span><span class="sxs-lookup"><span data-stu-id="0b707-214">This makes it possible for the user to upgrade their installation via a root package (for example, `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="0b707-215">Większość dystrybucji wymaga, aby wszystkie artefakty zostały skompilowane ze źródła.</span><span class="sxs-lookup"><span data-stu-id="0b707-215">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="0b707-216">Ma to wpływ na pakiety:</span><span class="sxs-lookup"><span data-stu-id="0b707-216">This has some impact on the packages:</span></span>

- <span data-ttu-id="0b707-217">Bibliotek innych firm w obszarze `shared/Microsoft.AspNetCore.All` nie można łatwo skompilować ze źródła.</span><span class="sxs-lookup"><span data-stu-id="0b707-217">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="0b707-218">Ten folder zostanie pominięty z `aspnetcore-runtime` pakietu.</span><span class="sxs-lookup"><span data-stu-id="0b707-218">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="0b707-219">`NuGetFallbackFolder`Jest wypełniany przy użyciu artefaktów binarnych z `nuget.org` .</span><span class="sxs-lookup"><span data-stu-id="0b707-219">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="0b707-220">Powinna pozostać pusta.</span><span class="sxs-lookup"><span data-stu-id="0b707-220">It should remain empty.</span></span>

<span data-ttu-id="0b707-221">Wiele `dotnet-sdk` pakietów może dostarczyć te same pliki dla `NuGetFallbackFolder` .</span><span class="sxs-lookup"><span data-stu-id="0b707-221">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="0b707-222">Aby uniknąć problemów z menedżerem pakietów, te pliki powinny być identyczne (suma kontrolna, Data modyfikacji itd.).</span><span class="sxs-lookup"><span data-stu-id="0b707-222">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="0b707-223">Kompilowanie pakietów</span><span class="sxs-lookup"><span data-stu-id="0b707-223">Building packages</span></span>

<span data-ttu-id="0b707-224">Repozytorium [dotnet/Source-Build](https://github.com/dotnet/source-build) zawiera instrukcje dotyczące sposobu tworzenia źródłowej plik tar zestaw .NET Core SDK i wszystkich jego składników.</span><span class="sxs-lookup"><span data-stu-id="0b707-224">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="0b707-225">Dane wyjściowe repozytorium Build source są zgodne z układem opisanym w pierwszej sekcji tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="0b707-225">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
