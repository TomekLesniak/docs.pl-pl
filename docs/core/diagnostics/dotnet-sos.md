---
title: Narzędzie diagnostyczne dotnet-sos — interfejs wiersza polecenia platformy .NET
description: Dowiedz się, jak zainstalować i użyć narzędzia interfejsu wiersza polecenia dotnet-sos do zarządzania rozszerzeniem debugera SOS, które jest używane z natywnymi debugerami w systemach Windows i Linux.
ms.date: 11/17/2020
ms.openlocfilehash: 59512c42a778f68bb3cd092dc854dcc727fd2881
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825445"
---
# <a name="sos-installer-dotnet-sos"></a>Instalator SOS (dotnet-sos)

**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach

## <a name="install"></a>Instalowanie

Istnieją dwa sposoby na pobranie i zainstalowanie `dotnet-sos` :

- **Narzędzie globalne dotnet:**

  Aby zainstalować najnowszą wersję `dotnet-sos` [pakietu NuGet](https://www.nuget.org/packages/dotnet-sos), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- **Pobieranie bezpośrednie:**

  Pobierz plik wykonywalny narzędzia, który jest zgodny z platformą:

  | System operacyjny  | Platforma |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [ARM](https://aka.ms/dotnet-sos/win-arm) \| [ARM — x64](https://aka.ms/dotnet-sos/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-sos/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-sos/linux-x64) \| [ARM](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [MUSL — x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [MUSL — arm64](https://aka.ms/dotnet-sos/linux-musl-arm64) |

## <a name="synopsis"></a>Streszczenie

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a>Opis

`dotnet-sos`Narzędzie globalne instaluje [rozszerzenie debugera sos](../../framework/tools/sos-dll-sos-debugging-extension.md) umożliwiające [inspekcję stanu zarządzanego programu .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) z natywnych debugerów, takich jak WinDbg/CDB w systemach Windows i LLDB w systemach Linux i macOS. Najnowsze wersje debugera systemu Windows (>= Version 10.0.18317.1001 of WinDbg lub CDB) będą automatycznie ładować SOS z galerii rozszerzeń firmy Microsoft, więc zainstalowanie SOS za pomocą `dotnet-sos` narzędzia jest konieczna tylko w systemach Linux i macOS lub w systemie Windows, jeśli są używane starsze narzędzia debugowania.

## <a name="options"></a>Opcje

- **`--version`**

  Wyświetla informacje o wersji.

- **`-h|--help`**

  Wyświetla pomoc w wierszu polecenia.

## <a name="dotnet-sos-install"></a>Instalacja dotnet-sos

Instaluje [rozszerzenie sos](../../framework/tools/sos-dll-sos-debugging-extension.md) lokalnie na potrzeby debugowania procesów .NET Core. W systemach macOS i Linux plik. lldbinit zostanie zaktualizowany, dzięki czemu rozszerzenie zostanie automatycznie załadowane przy uruchomieniu LLDB. Jeśli instalujesz SOS w systemie Windows przy użyciu starszych narzędzi debugowania (< wersja 10.0.18317.1001), musisz ręcznie załadować rozszerzenie w programie WinDbg lub CDB, uruchamiając `.load %USERPROFILE%\.dotnet\sos\sos.dll` je w debugerze.

### <a name="synopsis"></a>Streszczenie

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a>sos — Dezinstalacja

Odinstalowuje [rozszerzenie sos](../../framework/tools/sos-dll-sos-debugging-extension.md) i, jeśli w systemie Linux lub macOS, usunie je z konfiguracji LLDB.

### <a name="synopsis"></a>Streszczenie

```console
dotnet-sos uninstall
```
