---
title: dotnet-sos-.NET Core
description: Instalowanie i używanie narzędzia wiersza polecenia dotnet-sos.
ms.date: 08/26/2020
ms.openlocfilehash: 3ce7ca79bbc2c72958d395e9d312e3001ec9fbf8
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598352"
---
# <a name="sos-installer-dotnet-sos"></a>Instalator SOS (dotnet-sos)

**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach

## <a name="install-dotnet-sos"></a>Zainstaluj dotnet-sos

Aby zainstalować najnowszą wersję `dotnet-sos` [pakietu NuGet](https://www.nuget.org/packages/dotnet-sos), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :

```dotnetcli
dotnet tool install -g dotnet-sos
```

## <a name="synopsis"></a>Streszczenie

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a>Opis

`dotnet-sos`Narzędzie globalne instaluje [rozszerzenie debugera sos](https://docs.microsoft.com/dotnet/framework/tools/sos-dll-sos-debugging-extension) umożliwiające [inspekcję stanu zarządzanego programu .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) z natywnych debugerów, takich jak WinDbg/CDB w systemach Windows i LLDB w systemach Linux i MacOS. Należy zauważyć, że najnowsze wersje debugera systemu Windows (>= Version 10.0.18317.1001 of WinDbg lub CDB) będą automatycznie ładować SOS z galerii rozszerzeń firmy Microsoft, więc zainstalowanie SOS za pomocą `dotnet-sos` narzędzia jest konieczna tylko w systemach Linux i MacOS lub w systemie Windows, jeśli są używane starsze narzędzia debugowania.

## <a name="options"></a>Opcje

- **`--version`**

  Wyświetla informacje o wersji.

- **`-h|--help`**

  Wyświetla pomoc w wierszu polecenia.

## <a name="dotnet-sos-install"></a>Instalacja dotnet-sos

Instaluje [rozszerzenie sos lokalnie](https://docs.microsoft.com/dotnet/framework/tools/sos-dll-sos-debugging-extension) na potrzeby debugowania procesów .NET Core. W systemach MacOS i Linux plik. lldbinit zostanie zaktualizowany, dzięki czemu rozszerzenie zostanie automatycznie załadowane przy uruchomieniu LLDB. Jeśli instalujesz SOS w systemie Windows przy użyciu starszych narzędzi debugowania (< wersja 10.0.18317.1001), musisz ręcznie załadować rozszerzenie w programie WinDbg lub CDB, uruchamiając `.load %USERPROFILE%\.dotnet\sos\sos.dll` je w debugerze.

### <a name="synopsis"></a>Streszczenie

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a>sos — Dezinstalacja

Odinstalowuje [rozszerzenie sos](https://docs.microsoft.com/dotnet/framework/tools/sos-dll-sos-debugging-extension) i, jeśli w systemie Linux lub MacOS, usunie je z konfiguracji LLDB.

### <a name="synopsis"></a>Streszczenie

```console
dotnet-sos uninstall
```
