---
title: 'Nieprzerwana zmiana: Wbudowana obsługa środowiska WinRT jest usuwana z platformy .NET'
description: Dowiedz się więcej o zmianie nieprzerwaności międzyoperacyjnego w programie .NET 5,0, gdzie Wbudowana obsługa środowiska WinRT została usunięta z platformy .NET.
ms.date: 10/13/2020
ms.openlocfilehash: 61d8e26d06c232a7bfa1891a2159f5232f747b8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761552"
---
# <a name="built-in-support-for-winrt-is-removed-from-net"></a><span data-ttu-id="1dae4-103">Wbudowana obsługa środowiska WinRT jest usuwana z platformy .NET</span><span class="sxs-lookup"><span data-stu-id="1dae4-103">Built-in support for WinRT is removed from .NET</span></span>

<span data-ttu-id="1dae4-104">Wbudowana obsługa użycia interfejsów API [środowiska wykonawczego systemu Windows](/uwp/winrt-cref/winrt-type-system) w programie .NET jest usuwana.</span><span class="sxs-lookup"><span data-stu-id="1dae4-104">Built-in support for consumption of [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) APIs in .NET is removed.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="1dae4-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="1dae4-105">Version introduced</span></span>

<span data-ttu-id="1dae4-106">5,0</span><span class="sxs-lookup"><span data-stu-id="1dae4-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="1dae4-107">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="1dae4-107">Change description</span></span>

<span data-ttu-id="1dae4-108">Wcześniej CoreCLR może zużywać [pliki metadanych systemu Windows (WinMD)](/uwp/winrt-cref/winmd-files) do aktywnych i korzystać z typów WinRT.</span><span class="sxs-lookup"><span data-stu-id="1dae4-108">Previously, CoreCLR could consume [Windows metadata (WinMD) files](/uwp/winrt-cref/winmd-files) to active and consume WinRT types.</span></span> <span data-ttu-id="1dae4-109">Począwszy od platformy .NET 5,0, CoreCLR nie może już bezpośrednio korzystać z plików WinMD.</span><span class="sxs-lookup"><span data-stu-id="1dae4-109">Starting in .NET 5.0, CoreCLR can no longer consume WinMD files directly.</span></span>

<span data-ttu-id="1dae4-110">Jeśli próbujesz odwołać się do nieobsługiwanego zestawu, uzyskasz <xref:System.IO.FileNotFoundException> .</span><span class="sxs-lookup"><span data-stu-id="1dae4-110">If you attempt to reference an unsupported assembly, you'll get a <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="1dae4-111">W przypadku aktywowania klasy WinRT uzyskasz <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="1dae4-111">If you activate a WinRT class, you'll get a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="1dae4-112">Ta nieprzerwana zmiana została wprowadzona z następujących powodów:</span><span class="sxs-lookup"><span data-stu-id="1dae4-112">This breaking change was made for the following reasons:</span></span>

- <span data-ttu-id="1dae4-113">Dlatego WinRT można opracowywać i ulepszyć niezależnie od środowiska uruchomieniowego .NET.</span><span class="sxs-lookup"><span data-stu-id="1dae4-113">So WinRT can be developed and improved separately from the .NET runtime.</span></span>
- <span data-ttu-id="1dae4-114">Dla symetrii z systemami międzyoperacyjnymi udostępnianymi dla innych systemów operacyjnych, takich jak iOS i Android.</span><span class="sxs-lookup"><span data-stu-id="1dae4-114">For symmetry with interop systems provided for other operating systems, such as iOS and Android.</span></span>
- <span data-ttu-id="1dae4-115">W celu skorzystania z innych funkcji platformy .NET, takich jak funkcje języka C#, konsolidacja w języku pośrednim (IL) i kompilacja przed czasem (AOT).</span><span class="sxs-lookup"><span data-stu-id="1dae4-115">To take advantage of other .NET features, such as C# features, intermediate language (IL) linking, and ahead-of-time (AOT) compilation.</span></span>
- <span data-ttu-id="1dae4-116">Aby uprościć bazę kodu środowiska uruchomieniowego platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="1dae4-116">To simplify the .NET runtime codebase.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="1dae4-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="1dae4-117">Recommended action</span></span>

- <span data-ttu-id="1dae4-118">Usuń odwołania do [pakietu Microsoft. Windows. Sdk. kontrakts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span><span class="sxs-lookup"><span data-stu-id="1dae4-118">Remove references to the [Microsoft.Windows.SDK.Contracts package](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span></span>  <span data-ttu-id="1dae4-119">Zamiast tego należy określić wersję interfejsów API systemu Windows, do których chcesz uzyskać dostęp za pośrednictwem `TargetFramework` właściwości projektu.</span><span class="sxs-lookup"><span data-stu-id="1dae4-119">Instead, specify the version of the Windows APIs that you want to access via the `TargetFramework` property of the project.</span></span>  <span data-ttu-id="1dae4-120">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="1dae4-120">For example:</span></span>

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- <span data-ttu-id="1dae4-121">Za pomocą łańcucha narzędzi [/WinRT języka C#](/windows/uwp/csharp-winrt/) można generować lub dostosowywać interfejsy API i typy środowiska WinRT dla programu .NET 5,0 i nowszych wersji.</span><span class="sxs-lookup"><span data-stu-id="1dae4-121">Use the [C#/WinRT](/windows/uwp/csharp-winrt/) tool chain to generate or customize WinRT APIs and types for .NET 5.0 and later versions.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="1dae4-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="1dae4-122">Affected APIs</span></span>

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

### Category

Interop

-->
