---
title: polecenie Narzędzia dotnet narzędzie do odinstalowywania
description: Polecenie Narzędzia dotnet narzędzie do odinstalowywania Odinstalowuje określone narzędzie .NET z komputera.
ms.date: 02/14/2020
ms.openlocfilehash: 34dffde8f9c930327c6b42d1d89bb4f511959fb2
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634093"
---
# <a name="dotnet-tool-uninstall"></a>dotnet tool uninstall

**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet tool uninstall` -Odinstalowuje określone [Narzędzie .NET](global-tools.md) z komputera.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> -g|--global

dotnet tool uninstall <PACKAGE_NAME> --tool-path <PATH>

dotnet tool uninstall <PACKAGE_NAME>

dotnet tool uninstall -h|--help
```

## <a name="description"></a>Opis

`dotnet tool uninstall`Polecenie umożliwia odinstalowanie narzędzi .NET z komputera. Aby użyć polecenia, należy określić jedną z następujących opcji:

* Aby odinstalować narzędzie globalne, które zostało zainstalowane w lokalizacji domyślnej, użyj `--global` opcji.
* Aby odinstalować narzędzie globalne, które zostało zainstalowane w niestandardowej lokalizacji, użyj `--tool-path` opcji.
* Aby odinstalować narzędzie lokalne, należy pominąć `--global` Opcje i `--tool-path` .

**Narzędzia lokalne są dostępne począwszy od zestaw .NET Core SDK 3,0.**

## <a name="arguments"></a>Argumenty

- **`PACKAGE_NAME`**

  Nazwa/identyfikator pakietu NuGet zawierającego narzędzie .NET do odinstalowania. Nazwę pakietu można znaleźć przy użyciu polecenia [listy narzędzi dotnet](dotnet-tool-list.md) .

## <a name="options"></a>Opcje

- **`-g|--global`**

  Określa, że narzędzie ma zostać usunięte z instalacji na poziomie użytkownika. Nie można łączyć z `--tool-path` opcją. Pominięcie obu tych elementów `--global` i `--tool-path` oznacza, że narzędzie, które ma zostać usunięte, jest narzędziem lokalnym.

- **`-h|--help`**

  Drukuje krótką pomoc dla polecenia.

- **`--tool-path <PATH>`**

  Określa lokalizację, w której ma zostać odinstalowane narzędzie. ŚCIEŻKA może być bezwzględna lub względna. Nie można łączyć z `--global` opcją. Pominięcie obu tych elementów `--global` i `--tool-path` oznacza, że narzędzie, które ma zostać usunięte, jest narzędziem lokalnym.

## <a name="examples"></a>Przykłady

- **`dotnet tool uninstall -g dotnetsay`**

  Odinstalowuje narzędzie globalne [dotnetsay](https://www.nuget.org/packages/dotnetsay/) .

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  Odinstalowuje narzędzie globalne [dotnetsay](https://www.nuget.org/packages/dotnetsay/) z określonego katalogu systemu Windows.

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  Odinstalowuje narzędzie globalne [dotnetsay](https://www.nuget.org/packages/dotnetsay/) z określonego katalogu systemu Linux/macOS.

- **`dotnet tool uninstall dotnetsay`**

  Odinstalowuje narzędzie lokalne [dotnetsay](https://www.nuget.org/packages/dotnetsay/) z bieżącego katalogu.

## <a name="see-also"></a>Zobacz też

- [Narzędzia .NET](global-tools.md)
- [Samouczek: Instalowanie i używanie narzędzia globalnego platformy .NET przy użyciu interfejsu wiersza polecenia platformy .NET](global-tools-how-to-use.md)
- [Samouczek: Instalowanie i używanie lokalnego narzędzia .NET przy użyciu interfejsu wiersza polecenia platformy .NET](local-tools-how-to-use.md)
