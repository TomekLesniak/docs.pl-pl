---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656349"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>WinForms i aplikacje WPF używają Microsoft. NET. Sdk

Aplikacje Windows Forms i Windows Presentation Framework (WPF) używają teraz zestawu .NET SDK ( `Microsoft.NET.Sdk` ) zamiast programu .NET Core WinForms i zestawu WPF SDK ( `Microsoft.NET.Sdk.WindowsDesktop` ).

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET Core, WinForms i aplikacje WPF używały oddzielnego [zestawu SDK projektu](../../../../docs/core/project-sdk/overview.md) ( `Microsoft.NET.Sdk.WindowsDesktop` ). Począwszy od platformy .NET 5,0, kontrolki WinForm i zestaw WPF SDK zostały ujednolicone z zestawem SDK platformy .NET ( `Microsoft.NET.Sdk` ). Ponadto nowe [monikery platformy docelowej (TFM)](../../../../docs/standard/frameworks.md) zastępują `netcoreapp` i `netstandard` w programie .NET 5. Poniższy przykład pokazuje zmiany, które należy wprowadzić dla pliku projektu WPF podczas przekierowywania do programu .NET 5,0 lub nowszego.

W poprzednich wersjach programu .NET Core:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

W programie .NET 5,0 i jego nowszych wersjach:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

#### <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0 — wersja zapoznawcza 8

#### <a name="recommended-action"></a>Zalecana akcja

W pliku projektu WPF lub Windows Forms:

- Zaktualizuj `Sdk` atrybut do `Microsoft.NET.Sdk` .
- Zaktualizuj `TargetFramework` Właściwość do `net5.0-windows` .

#### <a name="category"></a>Kategoria

- Windows Forms
- Struktura prezentacji systemu Windows (WPF)

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
