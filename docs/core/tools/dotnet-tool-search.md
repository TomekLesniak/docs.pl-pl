---
title: polecenie wyszukiwania narzędzia dotnet
description: Polecenie wyszukiwania narzędzia dotnet przeszukuje narzędzia .NET, które są publikowane w NuGet.org.
ms.date: 11/11/2020
ms.openlocfilehash: e0289e651ec4a439c791c8c948bef2d85d9c3794
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634145"
---
# <a name="dotnet-tool-search"></a>Wyszukiwanie narzędzia dotnet

**Ten artykuł dotyczy:** ✔️ .NET 5,0 SDK i nowszych wersji

## <a name="name"></a>Nazwa

`dotnet tool search` — Przeszukuje wszystkie [Narzędzia .NET](global-tools.md) , które są publikowane w programie NuGet.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a>Opis

`dotnet tool search`Polecenie umożliwia przeszukiwanie narzędzia NuGet dla narzędzi, które mogą być używane jako globalne, narzędzie-ścieżka i narzędzia platformy .NET. Polecenie przeszukuje nazwy i metadane narzędzi, takie jak tytuły, opisy i Tagi.

Polecenie używa [interfejsu API wyszukiwania NuGet](/nuget/api/search-query-service-resource#search-for-packages). Filtruje on `packageType=dotnettool` , aby wybrać tylko pakiety narzędzi .NET.

## <a name="options"></a>Opcje

- **`--detail`**

  Pokazuje szczegółowe wyniki zapytania.

- **`--prerelease`**

  Obejmuje pakiety wersji wstępnej.

- **`--skip <NUMBER>`**

  Określa liczbę wyników zapytania do pominięcia. Używany do dzielenia na strony.

- **`--take <NUMBER>`**

  Określa liczbę wyników zapytania do wyświetlenia. Używany do dzielenia na strony.

- **`-h|--help`**

  Wyświetla pomoc w wierszu polecenia.

## <a name="examples"></a>Przykłady

- Wyszukaj NuGet.org dla narzędzi .NET, które mają "format" w nazwie lub opisie pakietu:

  ```dotnetcli
  dotnet tool search format
  ```

  Dane wyjściowe wyglądają podobnie do poniższego przykładu:

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- Wyszukiwanie w programie NuGet.org dla narzędzi .NET, które mają "format" w nazwie lub metadanych pakietu, pokazują tylko pierwszy wynik i pokazują widok szczegółowy.

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  Dane wyjściowe wyglądają podobnie do poniższego przykładu:

  ```output
  ----------------
  dotnet-format
  Latest Version: 4.1.131201
  Authors: Microsoft
  Tags:
  Downloads: 496746
  Verified: False
  Description: Command line tool for formatting C# and Visual Basic code files based on .editorconfig settings.
  Versions:
          3.0.2 Downloads: 1973
          3.0.4 Downloads: 9064
          3.1.37601 Downloads: 114730
          3.2.107702 Downloads: 13423
          3.3.111304 Downloads: 131195
          4.0.130203 Downloads: 78610
          4.1.131201 Downloads: 145927
  ```

## <a name="see-also"></a>Zobacz też

- [Narzędzia .NET](global-tools.md)
- [Samouczek: Instalowanie i używanie narzędzia globalnego platformy .NET przy użyciu interfejsu wiersza polecenia platformy .NET](global-tools-how-to-use.md)
- [Samouczek: Instalowanie i używanie lokalnego narzędzia .NET przy użyciu interfejsu wiersza polecenia platformy .NET](local-tools-how-to-use.md)
