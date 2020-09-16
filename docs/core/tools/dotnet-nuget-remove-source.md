---
title: polecenie Remove Source NuGet narzędzia dotnet
description: Polecenie Remove Source NuGet programu dotnet spowoduje usunięcie istniejącego źródła z plików konfiguracji programu NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: b5575c31c0008d6e3e5a2e52906a076614217dd0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537896"
---
# <a name="dotnet-nuget-remove-source"></a>dotnet nuget remove source

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet nuget remove source` -Usuń źródło NuGet.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a>Opis

`dotnet nuget remove source`Polecenie usuwa istniejące źródło z plików konfiguracji programu NuGet.

## <a name="arguments"></a>Argumenty

- **`NAME`**

  Nazwa źródła.

## <a name="options"></a>Opcje

- **`--configfile`**

  Plik konfiguracji programu NuGet. Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku. Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu. Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Przykłady

- Usuń źródło o nazwie `mySource` :

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a>Zobacz także

- [Sekcje źródłowe pakietu w plikach NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [sources — polecenie (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
