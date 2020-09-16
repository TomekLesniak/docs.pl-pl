---
title: polecenie włączenia źródła NuGet dotnet
description: Polecenie Enable Source NuGet narzędzia dotnet umożliwia istniejące źródło w plikach konfiguracji programu NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: b727844dd7d7cc82476e94a3f0ec4ecc6559d5ed
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537937"
---
# <a name="dotnet-nuget-enable-source"></a>dotnet nuget enable source

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet nuget enable source` -Włącz źródło narzędzia NuGet.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet nuget enable source <NAME> [--configfile <FILE>]

dotnet nuget enable source -h|--help
```

## <a name="description"></a>Opis

`dotnet nuget enable source`Polecenie włącza istniejące źródło w plikach konfiguracji programu NuGet.

## <a name="arguments"></a>Argumenty

- **`NAME`**

  Nazwa źródła.

## <a name="options"></a>Opcje

- **`--configfile <FILE>`**

  Plik konfiguracji programu NuGet. Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku. Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu. Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Przykłady

- Włącz źródło o nazwie `mySource` :

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a>Zobacz także

- [Sekcje źródłowe pakietu w plikach NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [sources — polecenie (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
