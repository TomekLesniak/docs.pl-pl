---
title: Wykaz identyfikatorów środowiska uruchomieniowego platformy .NET Core (RID)
description: Dowiedz się więcej o identyfikatorze środowiska uruchomieniowego (RID) i sposobie używania identyfikatorów RID w programie .NET Core.
ms.date: 02/22/2019
ms.openlocfilehash: 096ce8e33a82df3b9de682ed16e10fbe9f07fd03
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "90538227"
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="c225f-103">Katalog programu .NET Core RID</span><span class="sxs-lookup"><span data-stu-id="c225f-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="c225f-104">Identyfikator RID jest krótki dla *identyfikatora środowiska uruchomieniowego*.</span><span class="sxs-lookup"><span data-stu-id="c225f-104">RID is short for *Runtime Identifier*.</span></span> <span data-ttu-id="c225f-105">Wartości identyfikatorów RID służą do identyfikowania platform docelowych, w których jest uruchamiana aplikacja.</span><span class="sxs-lookup"><span data-stu-id="c225f-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="c225f-106">Są one używane przez pakiety .NET do reprezentowania zasobów specyficznych dla platformy w pakietach NuGet.</span><span class="sxs-lookup"><span data-stu-id="c225f-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="c225f-107">Poniżej przedstawiono przykłady identyfikatorów RID: `linux-x64` , `ubuntu.14.04-x64` , `win7-x64` lub `osx.10.12-x64` .</span><span class="sxs-lookup"><span data-stu-id="c225f-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="c225f-108">W przypadku pakietów z natywnymi zależnościami identyfikator RID określa platformy, na których można przywrócić pakiet.</span><span class="sxs-lookup"><span data-stu-id="c225f-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="c225f-109">Pojedynczy identyfikator RID można ustawić w `<RuntimeIdentifier>` elemencie pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="c225f-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="c225f-110">Wiele identyfikatorów RID można zdefiniować jako listę rozdzielaną średnikami w elemencie pliku projektu `<RuntimeIdentifiers>` .</span><span class="sxs-lookup"><span data-stu-id="c225f-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="c225f-111">Są one również używane przez `--runtime` opcję z następującymi [interfejs wiersza polecenia platformy .NET Core poleceniami](./tools/index.md):</span><span class="sxs-lookup"><span data-stu-id="c225f-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="c225f-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c225f-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="c225f-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c225f-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="c225f-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c225f-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="c225f-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c225f-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="c225f-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c225f-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="c225f-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c225f-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="c225f-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c225f-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="c225f-119">Identyfikatory RID reprezentujące konkretne systemy operacyjne zwykle są zgodne z tym wzorcem: `[os].[version]-[architecture]-[additional qualifiers]` gdzie:</span><span class="sxs-lookup"><span data-stu-id="c225f-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="c225f-120">`[os]` jest monikerem systemu operacyjnego/platformy.</span><span class="sxs-lookup"><span data-stu-id="c225f-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="c225f-121">Na przykład `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="c225f-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="c225f-122">`[version]` jest wersją systemu operacyjnego w postaci numeru wersji oddzielonej kropką ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="c225f-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="c225f-123">Na przykład `15.10`.</span><span class="sxs-lookup"><span data-stu-id="c225f-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="c225f-124">Wersja nie **powinna** być wersją marketingową, ponieważ często reprezentuje wiele dyskretnych wersji systemu operacyjnego z różnymi obszarami powierzchni interfejsu API platformy.</span><span class="sxs-lookup"><span data-stu-id="c225f-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="c225f-125">`[architecture]` jest architekturą procesora.</span><span class="sxs-lookup"><span data-stu-id="c225f-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="c225f-126">Na przykład: `x86` , `x64` , `arm` lub `arm64` .</span><span class="sxs-lookup"><span data-stu-id="c225f-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="c225f-127">`[additional qualifiers]` dalsze odróżnienie różnych platform.</span><span class="sxs-lookup"><span data-stu-id="c225f-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="c225f-128">Przykład: `aot`.</span><span class="sxs-lookup"><span data-stu-id="c225f-128">For example: `aot`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="c225f-129">Wykres RID</span><span class="sxs-lookup"><span data-stu-id="c225f-129">RID graph</span></span>

<span data-ttu-id="c225f-130">Wykres RID lub wykres rezerwowy środowiska uruchomieniowego to lista identyfikatorów RID, które są zgodne ze sobą.</span><span class="sxs-lookup"><span data-stu-id="c225f-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="c225f-131">Identyfikatory RID są zdefiniowane w pakiecie [Microsoft. servicecore. platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) .</span><span class="sxs-lookup"><span data-stu-id="c225f-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="c225f-132">Listę obsługiwanych identyfikatorów RID i Graf RID można zobaczyć w [*runtime.js*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) pliku, który znajduje się w `dotnet/runtime` repozytorium.</span><span class="sxs-lookup"><span data-stu-id="c225f-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the `dotnet/runtime` repository.</span></span> <span data-ttu-id="c225f-133">W tym pliku można zobaczyć, że wszystkie identyfikatory RID, z wyjątkiem podstawowego, zawierają `"#import"` instrukcję.</span><span class="sxs-lookup"><span data-stu-id="c225f-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="c225f-134">Te instrukcje wskazują zgodne identyfikatory RID.</span><span class="sxs-lookup"><span data-stu-id="c225f-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="c225f-135">Gdy pakiet NuGet przywraca pakiety, próbuje znaleźć dokładne dopasowanie dla określonego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="c225f-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="c225f-136">Jeśli dokładne dopasowanie nie zostanie znalezione, pakiet NuGet przeprowadzi ponownie wykres do momentu znalezienia najbliższego zgodnego systemu zgodnie z wykresem RID.</span><span class="sxs-lookup"><span data-stu-id="c225f-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="c225f-137">Poniższy przykład jest rzeczywistym wpisem `osx.10.12-x64` identyfikatora RID:</span><span class="sxs-lookup"><span data-stu-id="c225f-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="c225f-138">Powyższy identyfikator RID określa, że `osx.10.12-x64` Importy `osx.10.11-x64` .</span><span class="sxs-lookup"><span data-stu-id="c225f-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="c225f-139">W związku z tym, gdy pakiet NuGet przywraca pakiety, próbuje znaleźć dokładne dopasowanie dla  `osx.10.12-x64` pakietu.</span><span class="sxs-lookup"><span data-stu-id="c225f-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="c225f-140">Jeśli NuGet nie może znaleźć określonego środowiska uruchomieniowego, można przywrócić pakiety, które określają `osx.10.11-x64` środowisko uruchomieniowe, na przykład.</span><span class="sxs-lookup"><span data-stu-id="c225f-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="c225f-141">Poniższy przykład pokazuje nieco większego wykresu RID, zdefiniowany w *runtime.jsw*  pliku:</span><span class="sxs-lookup"><span data-stu-id="c225f-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="c225f-142">Wszystkie identyfikatory RID ostatecznie zamapują się z powrotem do głównego `any` identyfikatora RID.</span><span class="sxs-lookup"><span data-stu-id="c225f-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="c225f-143">Istnieją pewne kwestie dotyczące identyfikatorów RID, które należy wziąć pod uwagę podczas pracy z nimi:</span><span class="sxs-lookup"><span data-stu-id="c225f-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="c225f-144">Nie próbuj analizować identyfikatorów RID, aby pobrać części składnika.</span><span class="sxs-lookup"><span data-stu-id="c225f-144">Don't try to parse RIDs to retrieve component parts.</span></span>
- <span data-ttu-id="c225f-145">Nie Kompiluj identyfikatorów RID programowo.</span><span class="sxs-lookup"><span data-stu-id="c225f-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="c225f-146">Użyj identyfikatorów RID, które są już zdefiniowane dla platformy.</span><span class="sxs-lookup"><span data-stu-id="c225f-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="c225f-147">Identyfikatory RID muszą być specyficzne, więc nie założono niczego z rzeczywistej wartości RID.</span><span class="sxs-lookup"><span data-stu-id="c225f-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="c225f-148">Korzystanie z identyfikatorów RID</span><span class="sxs-lookup"><span data-stu-id="c225f-148">Using RIDs</span></span>

<span data-ttu-id="c225f-149">Aby móc korzystać z identyfikatorów RID, musisz wiedzieć, które istniejące identyfikatory RID istnieją.</span><span class="sxs-lookup"><span data-stu-id="c225f-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="c225f-150">Nowe wartości są regularnie dodawane do platformy.</span><span class="sxs-lookup"><span data-stu-id="c225f-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="c225f-151">Aby uzyskać najnowszą i pełną wersję, zobacz [runtime.jsw](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) pliku w `dotnet/runtime` repozytorium.</span><span class="sxs-lookup"><span data-stu-id="c225f-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span>

<span data-ttu-id="c225f-152">Zestaw SDK platformy .NET Core 2,0 wprowadza koncepcję przenośnych identyfikatorów RID.</span><span class="sxs-lookup"><span data-stu-id="c225f-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="c225f-153">Są to nowe wartości dodawane do grafu identyfikatorów RID, które nie są powiązane z określoną wersją lub dystrybucją systemu operacyjnego i są preferowanym wyborem w przypadku korzystania z platformy .NET Core 2,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="c225f-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution and are the preferred choice when using .NET Core 2.0 and higher.</span></span> <span data-ttu-id="c225f-154">Są one szczególnie przydatne w przypadku korzystania z wielu dystrybucje systemu Linux, ponieważ większość identyfikatorów RID dystrybucji jest mapowanych na przenośne identyfikatory RID.</span><span class="sxs-lookup"><span data-stu-id="c225f-154">They're particularly useful when dealing with multiple Linux distros since most distribution RIDs are mapped to the portable RIDs.</span></span>

<span data-ttu-id="c225f-155">Na poniższej liście przedstawiono mały podzestaw najbardziej typowych identyfikatorów RID użytych dla każdego systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="c225f-155">The following list shows a small subset of the most common RIDs used for each OS.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="c225f-156">Identyfikatory RID systemu Windows</span><span class="sxs-lookup"><span data-stu-id="c225f-156">Windows RIDs</span></span>

<span data-ttu-id="c225f-157">Wyświetlane są tylko typowe wartości.</span><span class="sxs-lookup"><span data-stu-id="c225f-157">Only common values are listed.</span></span> <span data-ttu-id="c225f-158">Aby uzyskać najnowszą i pełną wersję, zapoznaj się z tematem [runtime.jsw](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) pliku w `dotnet/runtime` repozytorium.</span><span class="sxs-lookup"><span data-stu-id="c225f-158">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on `dotnet/runtime` repository.</span></span>

- <span data-ttu-id="c225f-159">Przenośne (.NET Core 2,0 lub nowsze wersje)</span><span class="sxs-lookup"><span data-stu-id="c225f-159">Portable (.NET Core 2.0 or later versions)</span></span>
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- <span data-ttu-id="c225f-160">Windows 7/Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c225f-160">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="c225f-161">Windows 8.1/Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c225f-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="c225f-162">Windows 10/Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c225f-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="c225f-163">Aby uzyskać więcej informacji, zobacz [zależności i wymagania dotyczące platformy .NET Core](./install/windows.md#dependencies).</span><span class="sxs-lookup"><span data-stu-id="c225f-163">For more information, see [.NET Core dependencies and requirements](./install/windows.md#dependencies).</span></span>

## <a name="linux-rids"></a><span data-ttu-id="c225f-164">Identyfikatory RID systemu Linux</span><span class="sxs-lookup"><span data-stu-id="c225f-164">Linux RIDs</span></span>

<span data-ttu-id="c225f-165">Wyświetlane są tylko typowe wartości.</span><span class="sxs-lookup"><span data-stu-id="c225f-165">Only common values are listed.</span></span> <span data-ttu-id="c225f-166">Aby uzyskać najnowszą i pełną wersję, zobacz [runtime.jsw](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) pliku w `dotnet/runtime` repozytorium.</span><span class="sxs-lookup"><span data-stu-id="c225f-166">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span> <span data-ttu-id="c225f-167">Urządzenia korzystające z dystrybucji niewymienionej poniżej mogą działać z jednym z przenośnych identyfikatorów RID.</span><span class="sxs-lookup"><span data-stu-id="c225f-167">Devices running a distribution not listed below may work with one of the Portable RIDs.</span></span> <span data-ttu-id="c225f-168">Na przykład urządzenia Raspberry Pi z dystrybucją systemu Linux, których nie ma na liście, mogą być wskazywane przez `linux-arm` .</span><span class="sxs-lookup"><span data-stu-id="c225f-168">For example, Raspberry Pi devices running a Linux distribution not listed can be targeted with `linux-arm`.</span></span>

- <span data-ttu-id="c225f-169">Przenośne (.NET Core 2,0 lub nowsze wersje)</span><span class="sxs-lookup"><span data-stu-id="c225f-169">Portable (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="c225f-170">`linux-x64` (Większość dystrybucji komputerów, takich jak CentOS, Debian, Fedora, Ubuntu i pochodne)</span><span class="sxs-lookup"><span data-stu-id="c225f-170">`linux-x64` (Most desktop distributions like CentOS, Debian, Fedora, Ubuntu, and derivatives)</span></span>
  - <span data-ttu-id="c225f-171">`linux-musl-x64` (Lekkie dystrybucje korzystające z [MUSL](https://wiki.musl-libc.org/projects-using-musl.html) , na przykład Alpine Linux)</span><span class="sxs-lookup"><span data-stu-id="c225f-171">`linux-musl-x64` (Lightweight distributions using [musl](https://wiki.musl-libc.org/projects-using-musl.html) like Alpine Linux)</span></span>
  - <span data-ttu-id="c225f-172">`linux-arm` (Dystrybucje systemu Linux działające na ARM, takie jak raspbian na Raspberry Pi Model 2 +)</span><span class="sxs-lookup"><span data-stu-id="c225f-172">`linux-arm` (Linux distributions running on ARM like Raspbian on Raspberry Pi Model 2+)</span></span>
  - <span data-ttu-id="c225f-173">`linux-arm64` (Dystrybucje systemu Linux uruchomione na 64-bitowych ARM, takich jak Ubuntu Server 64-bit in Raspberry Pi Model 3 +)</span><span class="sxs-lookup"><span data-stu-id="c225f-173">`linux-arm64` (Linux distributions running on 64-bit ARM like Ubuntu Server 64-bit on Raspberry Pi Model 3+)</span></span>
- <span data-ttu-id="c225f-174">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c225f-174">Red Hat Enterprise Linux</span></span>
  - <span data-ttu-id="c225f-175">`rhel-x64` (Zastąpione przez `linux-x64` dla RHEL powyżej wersji 6)</span><span class="sxs-lookup"><span data-stu-id="c225f-175">`rhel-x64` (Superseded by `linux-x64` for RHEL above version 6)</span></span>
  - <span data-ttu-id="c225f-176">`rhel.6-x64` (.NET Core 2,0 lub nowsze wersje)</span><span class="sxs-lookup"><span data-stu-id="c225f-176">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="c225f-177">Tizen (.NET Core 2,0 lub nowszy)</span><span class="sxs-lookup"><span data-stu-id="c225f-177">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

<span data-ttu-id="c225f-178">Aby uzyskać więcej informacji, zobacz [zależności i wymagania dotyczące platformy .NET Core](./install/linux.md).</span><span class="sxs-lookup"><span data-stu-id="c225f-178">For more information, see [.NET Core dependencies and requirements](./install/linux.md).</span></span>

## <a name="macos-rids"></a><span data-ttu-id="c225f-179">macOS RID</span><span class="sxs-lookup"><span data-stu-id="c225f-179">macOS RIDs</span></span>

<span data-ttu-id="c225f-180">macOS RID używają starszej marki "OSX".</span><span class="sxs-lookup"><span data-stu-id="c225f-180">macOS RIDs use the older "OSX" branding.</span></span> <span data-ttu-id="c225f-181">Wyświetlane są tylko typowe wartości.</span><span class="sxs-lookup"><span data-stu-id="c225f-181">Only common values are listed.</span></span> <span data-ttu-id="c225f-182">Aby uzyskać najnowszą i pełną wersję, zobacz [runtime.jsw](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) pliku w `dotnet/runtime` repozytorium.</span><span class="sxs-lookup"><span data-stu-id="c225f-182">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span>

- <span data-ttu-id="c225f-183">Przenośne (.NET Core 2,0 lub nowsze wersje)</span><span class="sxs-lookup"><span data-stu-id="c225f-183">Portable (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="c225f-184">`osx-x64` (Minimalna wersja systemu operacyjnego to macOS 10,12 Sierra)</span><span class="sxs-lookup"><span data-stu-id="c225f-184">`osx-x64` (Minimum OS version is macOS 10.12 Sierra)</span></span>
- <span data-ttu-id="c225f-185">macOS 10,10, Yosemite</span><span class="sxs-lookup"><span data-stu-id="c225f-185">macOS 10.10  Yosemite</span></span>
  - `osx.10.10-x64`
- <span data-ttu-id="c225f-186">macOS 10,11 El Capitan</span><span class="sxs-lookup"><span data-stu-id="c225f-186">macOS 10.11 El Capitan</span></span>
  - `osx.10.11-x64`
- <span data-ttu-id="c225f-187">macOS 10,12 Sierra (wersja .NET Core 1,1 lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="c225f-187">macOS 10.12 Sierra (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.12-x64`
- <span data-ttu-id="c225f-188">macOS 10,13 wysoka Sierra (.NET Core 1,1 lub nowsze wersje)</span><span class="sxs-lookup"><span data-stu-id="c225f-188">macOS 10.13 High Sierra (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.13-x64`
- <span data-ttu-id="c225f-189">macOS 10,14 Mojave (wersja .NET Core 1,1 lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="c225f-189">macOS 10.14 Mojave (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.14-x64`

<span data-ttu-id="c225f-190">Aby uzyskać więcej informacji, zobacz [zależności i wymagania dotyczące platformy .NET Core](./install/macos.md#dependencies).</span><span class="sxs-lookup"><span data-stu-id="c225f-190">For more information, see [.NET Core dependencies and requirements](./install/macos.md#dependencies).</span></span>

## <a name="see-also"></a><span data-ttu-id="c225f-191">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c225f-191">See also</span></span>

- [<span data-ttu-id="c225f-192">Identyfikatory środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="c225f-192">Runtime IDs</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/readme.md)
