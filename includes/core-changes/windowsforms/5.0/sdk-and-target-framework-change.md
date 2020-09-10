---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656349"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="bef2e-101">WinForms i aplikacje WPF używają Microsoft. NET. Sdk</span><span class="sxs-lookup"><span data-stu-id="bef2e-101">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="bef2e-102">Aplikacje Windows Forms i Windows Presentation Framework (WPF) używają teraz zestawu .NET SDK ( `Microsoft.NET.Sdk` ) zamiast programu .NET Core WinForms i zestawu WPF SDK ( `Microsoft.NET.Sdk.WindowsDesktop` ).</span><span class="sxs-lookup"><span data-stu-id="bef2e-102">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

#### <a name="change-description"></a><span data-ttu-id="bef2e-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="bef2e-103">Change description</span></span>

<span data-ttu-id="bef2e-104">W poprzednich wersjach programu .NET Core, WinForms i aplikacje WPF używały oddzielnego [zestawu SDK projektu](../../../../docs/core/project-sdk/overview.md) ( `Microsoft.NET.Sdk.WindowsDesktop` ).</span><span class="sxs-lookup"><span data-stu-id="bef2e-104">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="bef2e-105">Począwszy od platformy .NET 5,0, kontrolki WinForm i zestaw WPF SDK zostały ujednolicone z zestawem SDK platformy .NET ( `Microsoft.NET.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="bef2e-105">Starting in .NET 5.0, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="bef2e-106">Ponadto nowe [monikery platformy docelowej (TFM)](../../../../docs/standard/frameworks.md) zastępują `netcoreapp` i `netstandard` w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="bef2e-106">In addition, new [target framework monikers (TFM)](../../../../docs/standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="bef2e-107">Poniższy przykład pokazuje zmiany, które należy wprowadzić dla pliku projektu WPF podczas przekierowywania do programu .NET 5,0 lub nowszego.</span><span class="sxs-lookup"><span data-stu-id="bef2e-107">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5.0 or later.</span></span>

<span data-ttu-id="bef2e-108">W poprzednich wersjach programu .NET Core:</span><span class="sxs-lookup"><span data-stu-id="bef2e-108">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="bef2e-109">W programie .NET 5,0 i jego nowszych wersjach:</span><span class="sxs-lookup"><span data-stu-id="bef2e-109">In .NET 5.0 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

#### <a name="version-introduced"></a><span data-ttu-id="bef2e-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="bef2e-110">Version introduced</span></span>

<span data-ttu-id="bef2e-111">.NET 5,0 — wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="bef2e-111">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bef2e-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="bef2e-112">Recommended action</span></span>

<span data-ttu-id="bef2e-113">W pliku projektu WPF lub Windows Forms:</span><span class="sxs-lookup"><span data-stu-id="bef2e-113">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="bef2e-114">Zaktualizuj `Sdk` atrybut do `Microsoft.NET.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="bef2e-114">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="bef2e-115">Zaktualizuj `TargetFramework` Właściwość do `net5.0-windows` .</span><span class="sxs-lookup"><span data-stu-id="bef2e-115">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

#### <a name="category"></a><span data-ttu-id="bef2e-116">Kategoria</span><span class="sxs-lookup"><span data-stu-id="bef2e-116">Category</span></span>

- <span data-ttu-id="bef2e-117">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bef2e-117">Windows Forms</span></span>
- <span data-ttu-id="bef2e-118">Struktura prezentacji systemu Windows (WPF)</span><span class="sxs-lookup"><span data-stu-id="bef2e-118">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bef2e-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="bef2e-119">Affected APIs</span></span>

<span data-ttu-id="bef2e-120">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="bef2e-120">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
