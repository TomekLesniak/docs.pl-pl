---
title: polecenie Narzędzia dotnet
description: Polecenie Narzędzia dotnet jest instalowane na komputerze jako lokalne narzędzia .NET, które znajdują się w zakresie dla bieżącego katalogu.
ms.date: 02/14/2020
ms.openlocfilehash: 3425bc6b78fd53f578c209013f83b006305dbb81
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242932"
---
# <a name="dotnet-tool-restore"></a>dotnet tool restore

**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,0 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet tool restore` -Instaluje lokalne narzędzia .NET, które znajdują się w zakresie dla bieżącego katalogu.

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

- [Narzędzia .NET](global-tools.md)
- [Samouczek: Instalowanie i używanie lokalnego narzędzia .NET przy użyciu interfejsu wiersza polecenia platformy .NET](local-tools-how-to-use.md)
