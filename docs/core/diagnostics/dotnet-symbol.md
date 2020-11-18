---
title: Narzędzie diagnostyczne symbol dotnet-interfejs wiersza polecenia platformy .NET
description: Informacje na temat instalowania i używania narzędzia dotnet-symbol interfejsu wiersza polecenia do pobierania plików wymaganych do debugowania zrzutów .NET i minizrzutów.
ms.date: 11/17/2020
ms.openlocfilehash: 8ea694e5331f1e4e75b3b3ad644428568e515331
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825341"
---
# <a name="symbol-downloader-dotnet-symbol"></a>Narzędzie pobierania symboli (dotnet-symbol)

**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach

## <a name="install"></a>Instalowanie

Aby zainstalować najnowszą wersję `dotnet-trace` [pakietu NuGet](https://www.nuget.org/packages/dotnet-trace), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :

```dotnetcli
dotnet tool install --global dotnet-symbol
```

## <a name="synopsis"></a>Streszczenie

```console
dotnet-symbol [-h|--help] [options] <FILES>
```

## <a name="description"></a>Opis

`dotnet-symbol`Narzędzie globalne pobiera pliki (symbole, DAC, moduły itp.), które są niezbędne do debugowania podstawowych zrzutów i minizrzutów. Może to być przydatne podczas debugowania zrzutów na innym komputerze. `dotnet-symbol` umożliwia pobranie modułów i symboli wymaganych do przeanalizowania zrzutu.

## <a name="options"></a>Opcje

- **`--microsoft-symbol-server`**

  Dodaj http://msdl.microsoft.com/download/symbols ścieżkę serwera symboli "" (domyślnie).

- **`--server-path <symbol server path>`**

  Dodaj serwer symboli do ścieżki serwera.

- **`authenticated-server-path <pat> <server path>`**

  Dodaj uwierzytelniony serwer symboli do ścieżki serwerowej przy użyciu osobistego tokenu dostępu.

- **`--cache-directory <file cache directory>`**

  Dodaje Katalog pamięci podręcznej.

- **`--recurse-subdirectories`**

  Przetwarzaj pliki wejściowe we wszystkich podkatalogach.

- **`--host-only`**

  Pobierz tylko program hosta (tj. dotnet), który LLDB potrzebuje do ładowania zrzutów podstawowych.

- **`--symbols`**

  Pobierz pliki symboli (. pdb,. dbg,. Dwarf).

- **`--modules`**

  Pobierz pliki modułów (. dll,. so,. DYLIB).

- **`--debugging`**

  Pobierz specjalne moduły debugowania (DAC, DBI, SOS).

- **`--windows-pdbs`**

  Wymuś pobieranie plików PDB systemu Windows w przypadku, gdy przenośne plików PDB są również dostępne.

- **`-o, --output <output directory>`**

  Ustaw katalog wyjściowy. W przeciwnym razie Napisz obok pliku wejściowego (domyślnie).

- **`-d, --diagnostics`**

  Włącz diagnostykę danych wyjściowych.

- **`-h|--help`**

  Wyświetla pomoc w wierszu polecenia.

## <a name="download-symbols"></a>Pobierz symbole

Uruchamianie w `dotnet-symbol` oparciu o plik zrzutu domyślnie pobiera wszystkie moduły, symbole i pliki DAC/DBI, które są konieczne do debugowania zrzutu, w tym zestawów zarządzanych. Ponieważ SOS mogą teraz pobierać symbole, większość zrzutów rdzeni systemu Linux można analizować za pomocą LLDB tylko z modułami hosta (dotnet) i debugowania. Aby pobrać te pliki niezbędne do zdiagnozowania podstawowego zrzutu z uruchomieniem usługi LLDB:

```console
dotnet-symbol --host-only --debugging <dump file path>
```

## <a name="troubleshoot"></a>Rozwiązywanie problemów

- nie znaleziono 404 podczas pobierania symboli.

   Pobieranie symboli jest obsługiwane tylko dla oficjalnych wersji środowiska uruchomieniowego .NET Core uzyskanych za pomocą oficjalnych kanałów, takich jak [Oficjalna witryna sieci Web](https://dotnet.microsoft.com/download/dotnet-core) i [Domyślne źródła w skryptach instalacyjnych dotnet](../tools/dotnet-install-script.md). Błąd 404 podczas pobierania plików debugowania może wskazywać, że zrzut został utworzony przy użyciu środowiska uruchomieniowego platformy .NET Core z innego źródła, takiego jak jeden skompilowany ze źródła lokalnie lub dla konkretnej dystrybucji systemu Linux lub z witryn społeczności, takich jak ArchLinux. W takich przypadkach plik niezbędny do debugowania (dotnet, libcoreclr.so i libmscordaccore.so) powinien być kopiowany z tych źródeł lub ze środowiska, w którym został utworzony plik zrzutu.
