---
ms.openlocfilehash: 47c676122df4f0990949a7bfbcd7af8c6144d870
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160550"
---
### <a name="built-in-support-for-winrt-is-removed-from-net"></a><span data-ttu-id="ff73b-101">Wbudowana obsługa środowiska WinRT jest usuwana z platformy .NET</span><span class="sxs-lookup"><span data-stu-id="ff73b-101">Built-in support for WinRT is removed from .NET</span></span>

<span data-ttu-id="ff73b-102">Wbudowana obsługa użycia interfejsów API [środowiska wykonawczego systemu Windows](/uwp/winrt-cref/winrt-type-system) w programie .NET jest usuwana.</span><span class="sxs-lookup"><span data-stu-id="ff73b-102">Built-in support for consumption of [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) APIs in .NET is removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ff73b-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="ff73b-103">Version introduced</span></span>

<span data-ttu-id="ff73b-104">5,0 wersja zapoznawcza 6</span><span class="sxs-lookup"><span data-stu-id="ff73b-104">5.0 Preview 6</span></span>

#### <a name="change-description"></a><span data-ttu-id="ff73b-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="ff73b-105">Change description</span></span>

<span data-ttu-id="ff73b-106">Wcześniej CoreCLR może zużywać [pliki metadanych systemu Windows (WinMD)](/uwp/winrt-cref/winmd-files) do aktywnych i korzystać z typów WinRT.</span><span class="sxs-lookup"><span data-stu-id="ff73b-106">Previously, CoreCLR could consume [Windows metadata (WinMD) files](/uwp/winrt-cref/winmd-files) to active and consume WinRT types.</span></span> <span data-ttu-id="ff73b-107">Począwszy od platformy .NET 5,0, CoreCLR nie może już bezpośrednio korzystać z plików WinMD.</span><span class="sxs-lookup"><span data-stu-id="ff73b-107">Starting in .NET 5.0, CoreCLR can no longer consume WinMD files directly.</span></span>

<span data-ttu-id="ff73b-108">Jeśli próbujesz odwołać się do nieobsługiwanego zestawu, uzyskasz <xref:System.IO.FileNotFoundException> .</span><span class="sxs-lookup"><span data-stu-id="ff73b-108">If you attempt to reference an unsupported assembly, you'll get a <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="ff73b-109">W przypadku aktywowania klasy WinRT uzyskasz <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="ff73b-109">If you activate a WinRT class, you'll get a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="ff73b-110">Ta nieprzerwana zmiana została wprowadzona z następujących powodów:</span><span class="sxs-lookup"><span data-stu-id="ff73b-110">This breaking change was made for the following reasons:</span></span>

- <span data-ttu-id="ff73b-111">Dlatego WinRT można opracowywać i ulepszyć niezależnie od środowiska uruchomieniowego .NET.</span><span class="sxs-lookup"><span data-stu-id="ff73b-111">So WinRT can be developed and improved separately from the .NET runtime.</span></span>
- <span data-ttu-id="ff73b-112">Dla symetrii z systemami międzyoperacyjnymi udostępnianymi dla innych systemów operacyjnych, takich jak iOS i Android.</span><span class="sxs-lookup"><span data-stu-id="ff73b-112">For symmetry with interop systems provided for other operating systems, such as iOS and Android.</span></span>
- <span data-ttu-id="ff73b-113">W celu skorzystania z innych funkcji platformy .NET, takich jak funkcje języka C#, konsolidacja w języku pośrednim (IL) i kompilacja przed czasem (AOT).</span><span class="sxs-lookup"><span data-stu-id="ff73b-113">To take advantage of other .NET features, such as C# features, intermediate language (IL) linking, and ahead-of-time (AOT) compilation.</span></span>
- <span data-ttu-id="ff73b-114">Aby uprościć bazę kodu środowiska uruchomieniowego platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="ff73b-114">To simplify the .NET runtime codebase.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ff73b-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="ff73b-115">Recommended action</span></span>

- <span data-ttu-id="ff73b-116">Usuń odwołania do [pakietu Microsoft. Windows. Sdk. kontrakts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span><span class="sxs-lookup"><span data-stu-id="ff73b-116">Remove references to the [Microsoft.Windows.SDK.Contracts package](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span></span>  <span data-ttu-id="ff73b-117">Zamiast tego należy określić wersję interfejsów API systemu Windows, do których chcesz uzyskać dostęp za pośrednictwem `TargetFramework` właściwości projektu.</span><span class="sxs-lookup"><span data-stu-id="ff73b-117">Instead, specify the version of the Windows APIs that you want to access via the `TargetFramework` property of the project.</span></span>  <span data-ttu-id="ff73b-118">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="ff73b-118">For example:</span></span>

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- <span data-ttu-id="ff73b-119">Za pomocą łańcucha narzędzi [/WinRT języka C#](/windows/uwp/csharp-winrt/) można generować lub dostosowywać interfejsy API i typy środowiska WinRT dla programu .NET 5,0 i nowszych wersji.</span><span class="sxs-lookup"><span data-stu-id="ff73b-119">Use the [C#/WinRT](/windows/uwp/csharp-winrt/) tool chain to generate or customize WinRT APIs and types for .NET 5.0 and later versions.</span></span>

#### <a name="category"></a><span data-ttu-id="ff73b-120">Kategoria</span><span class="sxs-lookup"><span data-stu-id="ff73b-120">Category</span></span>

<span data-ttu-id="ff73b-121">Interop</span><span class="sxs-lookup"><span data-stu-id="ff73b-121">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ff73b-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ff73b-122">Affected APIs</span></span>

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

-->
