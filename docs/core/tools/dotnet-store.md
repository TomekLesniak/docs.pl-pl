---
title: polecenie magazynu dotnet
description: Polecenie "Sklep dotnet" przechowuje określone zestawy w magazynie pakietów środowiska uruchomieniowego.
ms.date: 02/14/2020
ms.openlocfilehash: 8efb11c6bf648bc7787d5627e02b180abb8a0afd
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634340"
---
# <a name="dotnet-store"></a>dotnet store

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 2. x SDK i nowszych wersji

## <a name="name"></a>Nazwa

`dotnet store` -Przechowuje określone zestawy w [magazynie pakietów środowiska uruchomieniowego](../deploying/runtime-store.md).

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet store -m|--manifest <PATH_TO_MANIFEST_FILE>
    -f|--framework <FRAMEWORK_VERSION> -r|--runtime <RUNTIME_IDENTIFIER>
    [--framework-version <FRAMEWORK_VERSION>] [--output <OUTPUT_DIRECTORY>]
    [--skip-optimization] [--skip-symbols] [-v|--verbosity <LEVEL>]
    [--working-dir <WORKING_DIRECTORY>]

dotnet store -h|--help
```

## <a name="description"></a>Opis

`dotnet store` przechowuje określone zestawy w [magazynie pakietów środowiska uruchomieniowego](../deploying/runtime-store.md). Domyślnie zestawy są zoptymalizowane pod kątem docelowego środowiska uruchomieniowego i struktury. Aby uzyskać więcej informacji, zobacz temat [Magazyn pakietów środowiska uruchomieniowego](../deploying/runtime-store.md) .

## <a name="required-options"></a>Wymagane opcje

- **`-f|--framework <FRAMEWORK>`**

  Określa [platformę docelową](../../standard/frameworks.md). W pliku projektu należy określić platformę docelową.

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  *Plik manifestu magazynu pakietów* to plik XML zawierający listę pakietów do przechowywania. Format pliku manifestu jest zgodny z formatem projektu w stylu zestawu SDK. W związku z tym plik projektu, który odwołuje się do żądanych pakietów, może być używany z `-m|--manifest` opcją przechowywania zestawów w magazynie pakietów środowiska uruchomieniowego. Aby określić wiele plików manifestu, powtórz opcję i ścieżkę dla każdego pliku. Na przykład: `--manifest packages1.csproj --manifest packages2.csproj`.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  [Identyfikator środowiska uruchomieniowego](../rid-catalog.md) dla elementu docelowego.

## <a name="optional-options"></a>Opcje opcjonalne

- **`--framework-version <FRAMEWORK_VERSION>`**

  Określa wersję zestawu SDK platformy .NET. Ta opcja umożliwia wybranie określonej wersji struktury poza strukturą określoną przez `-f|--framework` opcję.

- **`-h|--help`**

  Wyświetla informacje pomocy.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Określa ścieżkę do magazynu pakietów środowiska uruchomieniowego. Jeśli nie zostanie określony, domyślnie jest to podkatalog *sklepu* katalogu instalacji .NET profilu użytkownika.

- **`--skip-optimization`**

  Pomija fazę optymalizacji.

- **`--skip-symbols`**

  Pomija generowanie symboli. Obecnie można generować tylko symbole w systemach Windows i Linux.

- **`-v|--verbosity <LEVEL>`**

  Ustawia poziom szczegółowości polecenia. Dozwolone wartości to `q[uiet]` , `m[inimal]` , `n[ormal]` , `d[etailed]` i `diag[nostic]` .

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  Katalog roboczy używany przez polecenie. Jeśli nie zostanie określony, używa podkatalogu *obj* w bieżącym katalogu.

## <a name="examples"></a>Przykłady

- Przechowuj pakiety określone w pliku projektu *Packages. csproj* dla programu .NET Core 2.0.0:

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- Przechowuj pakiety określone w *Packages. csproj* bez optymalizacji:

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a>Zobacz też

- [Magazyn pakietu środowiska uruchomieniowego](../deploying/runtime-store.md)
