---
title: polecenie Wyłącz źródło NuGet dotnet
description: Polecenie Wyłącz źródło NuGet programu dotnet wyłącza istniejące źródło w plikach konfiguracji programu NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: af37a6589cebaf0501ee5647ebadb83125d0f56e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537954"
---
# <a name="dotnet-nuget-disable-source"></a>dotnet nuget disable source

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet nuget disable source` -Wyłącz źródło NuGet.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet nuget disable source <NAME> [--configfile <FILE>]

dotnet nuget disable source -h|--help
```

## <a name="description"></a>Opis

`dotnet nuget disable source`Polecenie wyłącza istniejące źródło w plikach konfiguracji NuGet.

## <a name="arguments"></a>Argumenty

- **`NAME`**

  Nazwa źródła.

## <a name="options"></a>Opcje

- **`--configfile <FILE>`**

  Plik konfiguracji programu NuGet. Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku. Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu. Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Przykłady

- Wyłącz źródło o nazwie `mySource` :

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a>Zobacz także

- [Sekcje źródłowe pakietu w plikach NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [sources — polecenie (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
