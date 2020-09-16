---
title: polecenie źródła listy NuGet dotnet
description: Polecenie Source list NuGet programu dotnet zawiera listę wszystkich istniejących źródeł z plików konfiguracji programu NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 071061e32aa1bf888e197ec6bf97f4e4f6859f0b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537900"
---
# <a name="dotnet-nuget-list-source"></a>dotnet nuget list source

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet nuget list source` -Wyświetla wszystkie skonfigurowane źródła NuGet.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet nuget list source [--format [Detailed|Short]] [--configfile <FILE>]

dotnet nuget list source -h|--help
```

## <a name="description"></a>Opis

`dotnet nuget list source`Polecenie wyświetla listę wszystkich istniejących źródeł z plików konfiguracji programu NuGet.

## <a name="options"></a>Opcje

- **`--configfile <FILE>`**

  Plik konfiguracji programu NuGet. Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku. Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu. Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).

- **`--format [Detailed|Short]`**

  Format danych wyjściowych polecenia list: `Detailed` (wartość domyślna) i `Short` .

## <a name="examples"></a>Przykłady

- Wyświetl listę skonfigurowanych źródeł z bieżącego katalogu:

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a>Zobacz także

- [Sekcje źródłowe pakietu w plikach NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [sources — polecenie (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
