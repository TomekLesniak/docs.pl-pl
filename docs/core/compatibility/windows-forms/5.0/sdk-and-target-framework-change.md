---
title: 'Nieprzerwana zmiana: aplikacje WinForms i WPF korzystają z Microsoft. NET. Sdk'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której aplikacje Windows Forms i Windows Presentation Framework używają teraz zestawu .NET SDK zamiast narzędzi .NET Core WinForms i WPF SDK.
ms.date: 09/18/2020
ms.openlocfilehash: 5f25be44c390abc173f155351d8cb007a6b370b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761584"
---
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>WinForms i aplikacje WPF używają Microsoft. NET. Sdk

Aplikacje Windows Forms i Windows Presentation Framework (WPF) używają teraz zestawu .NET SDK ( `Microsoft.NET.Sdk` ) zamiast programu .NET Core WinForms i zestawu WPF SDK ( `Microsoft.NET.Sdk.WindowsDesktop` ).

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET Core, WinForms i aplikacje WPF używały oddzielnego [zestawu SDK projektu](../../../project-sdk/overview.md) ( `Microsoft.NET.Sdk.WindowsDesktop` ). Począwszy od platformy .NET 5,0, kontrolki WinForm i zestaw WPF SDK zostały ujednolicone z zestawem SDK platformy .NET ( `Microsoft.NET.Sdk` ). Ponadto nowe [monikery platformy docelowej (TFM)](../../../../standard/frameworks.md) zastępują `netcoreapp` i `netstandard` w programie .NET 5. Poniższy przykład pokazuje zmiany, które należy wprowadzić dla pliku projektu WPF podczas przekierowywania do programu .NET 5,0 lub nowszego.

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

## <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0

## <a name="recommended-action"></a>Zalecana akcja

W pliku projektu WPF lub Windows Forms:

- Zaktualizuj `Sdk` atrybut do `Microsoft.NET.Sdk` .
- Zaktualizuj `TargetFramework` Właściwość do `net5.0-windows` .

## <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
