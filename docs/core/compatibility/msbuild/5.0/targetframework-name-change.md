---
title: 'Zmiana podziału: TargetFramework zmiana z netcoreapp na net'
description: Zapoznaj się z istotną zmianą w programie .NET 5,0, w której wartość właściwości MSBuild TargetFramework zmieniła się z netcoreapp 3.1 na NET 5.0.
ms.date: 10/17/2020
ms.openlocfilehash: c3b39a36548d58d6ed75fd8b1c84b0cccfc738f0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761451"
---
# <a name="targetframework-change-from-netcoreapp-to-net"></a><span data-ttu-id="a986f-103">TargetFramework Zmień z netcoreapp na net</span><span class="sxs-lookup"><span data-stu-id="a986f-103">TargetFramework change from netcoreapp to net</span></span>

<span data-ttu-id="a986f-104">Wartość `TargetFramework` właściwości MSBuild została zmieniona z `netcoreapp3.1` na `net5.0` .</span><span class="sxs-lookup"><span data-stu-id="a986f-104">The value for the MSBuild `TargetFramework` property changed from `netcoreapp3.1` to `net5.0`.</span></span> <span data-ttu-id="a986f-105">Może to spowodować przerwanie kodu, który opiera się na analizie wartości `TargetFramework` .</span><span class="sxs-lookup"><span data-stu-id="a986f-105">This can break code that relies on parsing the value of `TargetFramework`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a986f-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a986f-106">Version introduced</span></span>

<span data-ttu-id="a986f-107">5,0</span><span class="sxs-lookup"><span data-stu-id="a986f-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="a986f-108">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="a986f-108">Change description</span></span>

<span data-ttu-id="a986f-109">W przypadku platformy .NET Core 1,0-3,1 wartość `TargetFramework` właściwości MSBuild zaczyna się od `netcoreapp` , na przykład `netcoreapp3.1` w przypadku aplikacji przeznaczonych dla platformy .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="a986f-109">In .NET Core 1.0 - 3.1, the value for the MSBuild `TargetFramework` property starts with `netcoreapp`, for example, `netcoreapp3.1` for apps that target .NET Core 3.1.</span></span> <span data-ttu-id="a986f-110">Począwszy od platformy .NET 5,0, ta wartość jest uproszczona, aby po prostu zacząć od `net` , na przykład `net5.0` dla programu .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="a986f-110">Starting in .NET 5.0, this value is simplified to just start with `net`, for example, `net5.0` for .NET 5.0.</span></span>

<span data-ttu-id="a986f-111">Aby uzyskać więcej informacji, zobacz [przyszłość nazw .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) i [docelowej platformy w programie .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span><span class="sxs-lookup"><span data-stu-id="a986f-111">For more information, see [The future of .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) and [Target framework names in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a986f-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="a986f-112">Reason for change</span></span>

- <span data-ttu-id="a986f-113">Upraszcza `TargetFramework` wartość.</span><span class="sxs-lookup"><span data-stu-id="a986f-113">Simplifies the `TargetFramework` value.</span></span>
- <span data-ttu-id="a986f-114">Włącza projekty w celu uwzględnienia `TargetPlatform` `TargetFramework` właściwości.</span><span class="sxs-lookup"><span data-stu-id="a986f-114">Enables projects to include a `TargetPlatform` in the `TargetFramework` property.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a986f-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a986f-115">Recommended action</span></span>

<span data-ttu-id="a986f-116">Jeśli masz logikę, która analizuje wartość, musisz `TargetFramework` ją zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="a986f-116">If you have logic that parses the value of `TargetFramework`, you'll need to update it.</span></span> <span data-ttu-id="a986f-117">Na przykład poniższy warunek MSBuild opiera się na wartości `TargetFramework` .</span><span class="sxs-lookup"><span data-stu-id="a986f-117">For example, the following MSBuild condition relies on the value of `TargetFramework`.</span></span>

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

<span data-ttu-id="a986f-118">W przypadku tego wymagania można zaktualizować kod w celu porównania w zamian identyfikatora platformy docelowej.</span><span class="sxs-lookup"><span data-stu-id="a986f-118">For this requirement, you can update the code to compare the target framework identifier instead.</span></span>

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

## <a name="affected-apis"></a><span data-ttu-id="a986f-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a986f-119">Affected APIs</span></span>

<span data-ttu-id="a986f-120">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="a986f-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
