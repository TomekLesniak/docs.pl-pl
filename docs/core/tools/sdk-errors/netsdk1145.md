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
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a>NETSDK1145: brak elementu docelowego lub pakietu AppHost

**Ten artykuł ma zastosowanie do:** ✔️ .NET 5.0.100 SDK i nowszych wersji

W przypadku wystąpienia błędu NETSDK1145 zestawu .NET SDK nie jest zainstalowany pakiet docelowy lub AppHost, a przywracanie pakietu NuGet nie jest obsługiwane. Jest to zazwyczaj spowodowane przez posiadanie nowszego zestawu SDK niż ten, który jest dołączony do projektów Visual Studio for C++/CLI. Uaktualnij program Visual Studio, Usuń _global.jsw_ przypadku wybrania określonej wersji zestawu SDK i odinstalowania nowszego zestawu SDK. Alternatywnie można przesłonić wersję docelową lub AppHost. Znajdź wersję, która istnieje w katalogu pakietu z komunikatu o błędzie i jest zgodna z platformą docelową projektu. Dodaj następujący projekt do projektu:

Pakiet AppHost

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

Dla pakietu docelowego

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
