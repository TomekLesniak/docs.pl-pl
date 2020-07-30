---
title: polecenie Narzędzia dotnet
description: Polecenie programu dotnet narzędzie do przywracania instaluje na komputerze środowisko .NET Core Local Tools znajdujące się w zakresie dla bieżącego katalogu.
ms.date: 02/14/2020
ms.openlocfilehash: ceef3274ec9d337f8c51009d5a8c27e808b14035
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302675"
---
# <a name="dotnet-tool-restore"></a>dotnet tool restore

**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,0 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet tool restore`-Instaluje na komputerze lokalne narzędzia platformy .NET Core, które znajdują się w zakresie dla bieżącego katalogu.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet tool restore
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a>Opis

`dotnet tool restore`Polecenie znajduje plik manifestu narzędzia, który znajduje się w zakresie dla bieżącego katalogu i instaluje narzędzia, które są w nim wymienione. Aby uzyskać informacje na temat plików manifestu, zobacz [Instalowanie narzędzia lokalnego](global-tools.md#install-a-local-tool) i [wywoływanie narzędzia lokalnego](global-tools.md#invoke-a-local-tool).

## <a name="options"></a>Opcje

- **`--configfile <FILE>`**

  Plik konfiguracji NuGet (*nuget.config*) do użycia.

- **`--add-source <SOURCE>`**

  Dodaje dodatkowe źródło pakietów NuGet do użycia podczas instalacji.

- **`--tool-manifest <PATH>`**

  Ścieżka do pliku manifestu.

- **`--disable-parallel`**

  Zapobiegaj równoległemu przywracaniu wielu projektów.

- **`--ignore-failed-sources`**

  Traktuj błędy źródłowe pakietu jako ostrzeżenia.

- **`--no-cache`**

  Nie Buforuj pakietów i żądań HTTP.

- **`--interactive`**

  Umożliwia zatrzymanie polecenia i oczekiwanie na dane wejściowe użytkownika lub akcję (na przykład zakończenie uwierzytelniania).

- **`-h|--help`**

  Drukuje krótką pomoc dla polecenia.

- **`-v|--verbosity <LEVEL>`**

  Ustawia poziom szczegółowości polecenia. Dozwolone wartości to `q[uiet]` , `m[inimal]` , `n[ormal]` , `d[etailed]` i `diag[nostic]` .

## <a name="example"></a>Przykład

- **`dotnet tool restore`**

  Przywraca lokalne narzędzia dla bieżącego katalogu.

## <a name="see-also"></a>Zobacz też

- [Narzędzia .NET Core](global-tools.md)
- [Samouczek: Instalowanie lokalnego narzędzia .NET Core i używanie go przy użyciu interfejs wiersza polecenia platformy .NET Core](local-tools-how-to-use.md)
