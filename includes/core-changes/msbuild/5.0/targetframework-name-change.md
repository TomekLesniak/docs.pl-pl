---
ms.openlocfilehash: 1ddc2cea19872b44ff9659bcebd76117587ea89a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159495"
---
### <a name="targetframework-change-from-netcoreapp-to-net"></a>TargetFramework Zmień z netcoreapp na net

Wartość `TargetFramework` właściwości MSBuild została zmieniona z `netcoreapp3.1` na `net5.0` . Może to spowodować przerwanie kodu, który opiera się na analizie wartości `TargetFramework` .

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="change-description"></a>Zmień opis

W przypadku platformy .NET Core 1,0-3,1 wartość `TargetFramework` właściwości MSBuild zaczyna się od `netcoreapp` , na przykład `netcoreapp3.1` w przypadku aplikacji przeznaczonych dla platformy .NET Core 3,1. Począwszy od platformy .NET 5,0, ta wartość jest uproszczona, aby po prostu zacząć od `net` , na przykład `net5.0` dla programu .NET 5,0.

Aby uzyskać więcej informacji, zobacz [przyszłość nazw .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) i [docelowej platformy w programie .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).

#### <a name="reason-for-change"></a>Przyczyna zmiany

- Upraszcza `TargetFramework` wartość.
- Włącza projekty w celu uwzględnienia `TargetPlatform` `TargetFramework` właściwości.

#### <a name="recommended-action"></a>Zalecana akcja

Jeśli masz logikę, która analizuje wartość, musisz `TargetFramework` ją zaktualizować. Na przykład poniższy warunek MSBuild opiera się na wartości `TargetFramework` .

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

W przypadku tego wymagania można zaktualizować kod w celu porównania w zamian identyfikatora platformy docelowej.

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

#### <a name="category"></a>Kategoria

MSBuild

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie dotyczy

<!--

#### Affected APIs

Not detectable via API analysis.

-->
