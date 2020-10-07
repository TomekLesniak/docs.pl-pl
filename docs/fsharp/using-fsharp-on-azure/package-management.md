---
title: 'Używanie Zarządzanie pakietami z językiem F # dla platformy Azure'
description: 'Korzystanie z usługi Paket lub NuGet do zarządzania zależnościami w języku F #'
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 7816c82e87db113a35fef967886c8c3e27959332
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756237"
---
# <a name="package-management-for-f-azure-dependencies"></a>Zarządzanie pakietami dla zależności platformy Azure w języku F#

Uzyskiwanie pakietów do programowania na platformie Azure jest proste w przypadku korzystania z Menedżera pakietów. Te dwie opcje to [Paket](https://fsprojects.github.io/Paket/) i [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Korzystanie z Paket

Jeśli używasz [Paket](https://fsprojects.github.io/Paket/) jako Menedżera zależności, możesz użyć `paket.exe` Narzędzia, aby dodać zależności platformy Azure. Przykład:

```console
> paket add nuget WindowsAzure.Storage
```

Lub, jeśli używasz narzędzia [mono](https://www.mono-project.com/) do tworzenia aplikacji dla wielu platform .NET:

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

Spowoduje to dodanie `WindowsAzure.Storage` do zestawu zależności pakietu dla projektu w bieżącym katalogu, zmodyfikowanie `paket.dependencies` pliku i pobranie pakietu. Jeśli wcześniej skonfigurowano zależności lub pracujesz z projektem, w którym zależności zostały skonfigurowane przez innego dewelopera, możesz rozwiązać i zainstalować zależności lokalnie w następujący sposób:

```console
> paket install
```

Lub, w przypadku programowania mono:

```console
> mono paket.exe install
```

Wszystkie zależności pakietu można zaktualizować do najnowszej wersji, np.:

```console
> paket update
```

Lub, w przypadku programowania mono:

```console
> mono paket.exe update
```

## <a name="using-nuget"></a>Korzystanie z NuGet

Jeśli używasz programu [NuGet](https://www.nuget.org/) jako Menedżera zależności, możesz użyć `nuget.exe` Narzędzia, aby dodać zależności platformy Azure. Przykład:

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

Lub, w przypadku programowania mono:

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

Spowoduje to dodanie `WindowsAzure.Storage` do zestawu zależności pakietu dla projektu w bieżącym katalogu i pobranie pakietu. Jeśli wcześniej skonfigurowano zależności lub pracujesz z projektem, w którym zależności zostały skonfigurowane przez innego dewelopera, możesz rozwiązać i zainstalować zależności lokalnie w następujący sposób:

```console
> nuget restore
```

Lub, w przypadku programowania mono:

```console
> mono nuget.exe restore
```

Wszystkie zależności pakietu można zaktualizować do najnowszej wersji, np.:

```console
> nuget update
```

Lub, w przypadku programowania mono:

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a>Odwoływanie się do zestawów

Aby można było używać pakietów w skrypcie języka F #, należy odwołać się do zestawów zawartych w pakietach przy użyciu `#r` dyrektywy. Przykład:

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

Jak widać, należy określić ścieżkę względną do biblioteki DLL i pełną nazwę biblioteki DLL, która może nie być dokładnie taka sama jak nazwa pakietu. Ścieżka będzie zawierać wersję platformy i prawdopodobnie numer wersji pakietu. Aby znaleźć wszystkie zainstalowane zestawy, możesz użyć podobnej do tego w wierszu polecenia systemu Windows:

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

Lub w powłoce systemu UNIX:

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

Spowoduje to udostępnienie ścieżek do zainstalowanych zestawów. W tym miejscu możesz wybrać poprawną ścieżkę do wersji platformy.
