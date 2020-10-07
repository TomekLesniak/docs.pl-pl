---
title: 'NETSDK1145: brak elementu docelowego lub pakietu AppHost'
description: Jak rozwiązać problem z brakującym pakietem docelowym, gdy przywracanie pakietu NuGet nie jest obsługiwane
author: wli3
ms.topic: error-reference
ms.date: 09/14/2020
f1_keywords:
- NETSDK1145
ms.openlocfilehash: c343952582cafb63eae388fd216769e6c67d4741
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805325"
---
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a><span data-ttu-id="b0ecc-103">NETSDK1145: brak elementu docelowego lub pakietu AppHost</span><span class="sxs-lookup"><span data-stu-id="b0ecc-103">NETSDK1145: Targeting or apphost pack missing</span></span>

<span data-ttu-id="b0ecc-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET 5.0.100 SDK i nowszych wersji</span><span class="sxs-lookup"><span data-stu-id="b0ecc-104">**This article applies to:** ✔️ .NET 5.0.100 SDK and later versions</span></span>

<span data-ttu-id="b0ecc-105">W przypadku wystąpienia błędu NETSDK1145 zestawu .NET SDK nie jest zainstalowany pakiet docelowy lub AppHost, a przywracanie pakietu NuGet nie jest obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="b0ecc-105">When the .NET SDK issues error NETSDK1145, the targeting or apphost pack is not installed and NuGet package restore is not supported.</span></span> <span data-ttu-id="b0ecc-106">Jest to zazwyczaj spowodowane przez posiadanie nowszego zestawu SDK niż ten, który jest dołączony do projektów Visual Studio for C++/CLI.</span><span class="sxs-lookup"><span data-stu-id="b0ecc-106">This is typically caused by having a newer SDK than the one included in Visual Studio for C++/CLI projects.</span></span> <span data-ttu-id="b0ecc-107">Uaktualnij program Visual Studio, Usuń _global.jsw_ przypadku wybrania określonej wersji zestawu SDK i odinstalowania nowszego zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="b0ecc-107">Upgrade Visual Studio, remove _global.json_ if it specifies a certain SDK version, and uninstall the newer SDK.</span></span> <span data-ttu-id="b0ecc-108">Alternatywnie można przesłonić wersję docelową lub AppHost.</span><span class="sxs-lookup"><span data-stu-id="b0ecc-108">Alternatively, you could override the targeting or apphost version.</span></span> <span data-ttu-id="b0ecc-109">Znajdź wersję, która istnieje w katalogu pakietu z komunikatu o błędzie i jest zgodna z platformą docelową projektu.</span><span class="sxs-lookup"><span data-stu-id="b0ecc-109">Find the version that exists under the pack directory from the error message and matches the target framework of the project.</span></span> <span data-ttu-id="b0ecc-110">Dodaj następujący projekt do projektu:</span><span class="sxs-lookup"><span data-stu-id="b0ecc-110">Add the following to the project:</span></span>

<span data-ttu-id="b0ecc-111">Pakiet AppHost</span><span class="sxs-lookup"><span data-stu-id="b0ecc-111">For apphost pack</span></span>

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

<span data-ttu-id="b0ecc-112">Dla pakietu docelowego</span><span class="sxs-lookup"><span data-stu-id="b0ecc-112">For targeting pack</span></span>

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
