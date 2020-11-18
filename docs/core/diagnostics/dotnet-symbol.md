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
# <a name="symbol-downloader-dotnet-symbol"></a><span data-ttu-id="12fa1-103">Narzędzie pobierania symboli (dotnet-symbol)</span><span class="sxs-lookup"><span data-stu-id="12fa1-103">Symbol downloader (dotnet-symbol)</span></span>

<span data-ttu-id="12fa1-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="12fa1-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="12fa1-105">Instalowanie</span><span class="sxs-lookup"><span data-stu-id="12fa1-105">Install</span></span>

<span data-ttu-id="12fa1-106">Aby zainstalować najnowszą wersję `dotnet-trace` [pakietu NuGet](https://www.nuget.org/packages/dotnet-trace), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="12fa1-106">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-symbol
```

## <a name="synopsis"></a><span data-ttu-id="12fa1-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="12fa1-107">Synopsis</span></span>

```console
dotnet-symbol [-h|--help] [options] <FILES>
```

## <a name="description"></a><span data-ttu-id="12fa1-108">Opis</span><span class="sxs-lookup"><span data-stu-id="12fa1-108">Description</span></span>

<span data-ttu-id="12fa1-109">`dotnet-symbol`Narzędzie globalne pobiera pliki (symbole, DAC, moduły itp.), które są niezbędne do debugowania podstawowych zrzutów i minizrzutów.</span><span class="sxs-lookup"><span data-stu-id="12fa1-109">The `dotnet-symbol` global tool downloads files (symbols, DAC, modules, etc.) needed for debugging core dumps and minidumps.</span></span> <span data-ttu-id="12fa1-110">Może to być przydatne podczas debugowania zrzutów na innym komputerze.</span><span class="sxs-lookup"><span data-stu-id="12fa1-110">This can be useful when debugging dumps captured on another machine.</span></span> <span data-ttu-id="12fa1-111">`dotnet-symbol` umożliwia pobranie modułów i symboli wymaganych do przeanalizowania zrzutu.</span><span class="sxs-lookup"><span data-stu-id="12fa1-111">`dotnet-symbol` can download modules and symbols needed to analyze the dump.</span></span>

## <a name="options"></a><span data-ttu-id="12fa1-112">Opcje</span><span class="sxs-lookup"><span data-stu-id="12fa1-112">Options</span></span>

- **`--microsoft-symbol-server`**

  <span data-ttu-id="12fa1-113">Dodaj http://msdl.microsoft.com/download/symbols ścieżkę serwera symboli "" (domyślnie).</span><span class="sxs-lookup"><span data-stu-id="12fa1-113">Add 'http://msdl.microsoft.com/download/symbols' symbol server path (default).</span></span>

- **`--server-path <symbol server path>`**

  <span data-ttu-id="12fa1-114">Dodaj serwer symboli do ścieżki serwera.</span><span class="sxs-lookup"><span data-stu-id="12fa1-114">Add a symbol server to the server path.</span></span>

- **`authenticated-server-path <pat> <server path>`**

  <span data-ttu-id="12fa1-115">Dodaj uwierzytelniony serwer symboli do ścieżki serwerowej przy użyciu osobistego tokenu dostępu.</span><span class="sxs-lookup"><span data-stu-id="12fa1-115">Add an authenticated symbol server to the server path using a personal access token (PAT).</span></span>

- **`--cache-directory <file cache directory>`**

  <span data-ttu-id="12fa1-116">Dodaje Katalog pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="12fa1-116">Adds a cache directory.</span></span>

- **`--recurse-subdirectories`**

  <span data-ttu-id="12fa1-117">Przetwarzaj pliki wejściowe we wszystkich podkatalogach.</span><span class="sxs-lookup"><span data-stu-id="12fa1-117">Process input files in all subdirectories.</span></span>

- **`--host-only`**

  <span data-ttu-id="12fa1-118">Pobierz tylko program hosta (tj. dotnet), który LLDB potrzebuje do ładowania zrzutów podstawowych.</span><span class="sxs-lookup"><span data-stu-id="12fa1-118">Download only the host program (i.e. dotnet) that lldb needs for loading core dumps.</span></span>

- **`--symbols`**

  <span data-ttu-id="12fa1-119">Pobierz pliki symboli (. pdb,. dbg,. Dwarf).</span><span class="sxs-lookup"><span data-stu-id="12fa1-119">Download symbol files (.pdb, .dbg, .dwarf).</span></span>

- **`--modules`**

  <span data-ttu-id="12fa1-120">Pobierz pliki modułów (. dll,. so,. DYLIB).</span><span class="sxs-lookup"><span data-stu-id="12fa1-120">Download the module files (.dll, .so, .dylib).</span></span>

- **`--debugging`**

  <span data-ttu-id="12fa1-121">Pobierz specjalne moduły debugowania (DAC, DBI, SOS).</span><span class="sxs-lookup"><span data-stu-id="12fa1-121">Download the special debugging modules (DAC, DBI, SOS).</span></span>

- **`--windows-pdbs`**

  <span data-ttu-id="12fa1-122">Wymuś pobieranie plików PDB systemu Windows w przypadku, gdy przenośne plików PDB są również dostępne.</span><span class="sxs-lookup"><span data-stu-id="12fa1-122">Force the downloading of the Windows PDBs when Portable PDBs are also available.</span></span>

- **`-o, --output <output directory>`**

  <span data-ttu-id="12fa1-123">Ustaw katalog wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="12fa1-123">Set the output directory.</span></span> <span data-ttu-id="12fa1-124">W przeciwnym razie Napisz obok pliku wejściowego (domyślnie).</span><span class="sxs-lookup"><span data-stu-id="12fa1-124">Otherwise, write next to the input file (default).</span></span>

- **`-d, --diagnostics`**

  <span data-ttu-id="12fa1-125">Włącz diagnostykę danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="12fa1-125">Enable diagnostic output.</span></span>

- **`-h|--help`**

  <span data-ttu-id="12fa1-126">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="12fa1-126">Shows command-line help.</span></span>

## <a name="download-symbols"></a><span data-ttu-id="12fa1-127">Pobierz symbole</span><span class="sxs-lookup"><span data-stu-id="12fa1-127">Download symbols</span></span>

<span data-ttu-id="12fa1-128">Uruchamianie w `dotnet-symbol` oparciu o plik zrzutu domyślnie pobiera wszystkie moduły, symbole i pliki DAC/DBI, które są konieczne do debugowania zrzutu, w tym zestawów zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="12fa1-128">Running `dotnet-symbol` against a dump file will, by default, download all the modules, symbols, and DAC/DBI files needed to debug the dump including the managed assemblies.</span></span> <span data-ttu-id="12fa1-129">Ponieważ SOS mogą teraz pobierać symbole, większość zrzutów rdzeni systemu Linux można analizować za pomocą LLDB tylko z modułami hosta (dotnet) i debugowania.</span><span class="sxs-lookup"><span data-stu-id="12fa1-129">Because SOS can now download symbols when needed, most Linux core dumps can be analyzed using lldb with only the host (dotnet) and debugging modules.</span></span> <span data-ttu-id="12fa1-130">Aby pobrać te pliki niezbędne do zdiagnozowania podstawowego zrzutu z uruchomieniem usługi LLDB:</span><span class="sxs-lookup"><span data-stu-id="12fa1-130">To get these files necessary for diagnosing a core dump with lldb run:</span></span>

```console
dotnet-symbol --host-only --debugging <dump file path>
```

## <a name="troubleshoot"></a><span data-ttu-id="12fa1-131">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="12fa1-131">Troubleshoot</span></span>

- <span data-ttu-id="12fa1-132">nie znaleziono 404 podczas pobierania symboli.</span><span class="sxs-lookup"><span data-stu-id="12fa1-132">404 Not Found while downloading symbols.</span></span>

   <span data-ttu-id="12fa1-133">Pobieranie symboli jest obsługiwane tylko dla oficjalnych wersji środowiska uruchomieniowego .NET Core uzyskanych za pomocą oficjalnych kanałów, takich jak [Oficjalna witryna sieci Web](https://dotnet.microsoft.com/download/dotnet-core) i [Domyślne źródła w skryptach instalacyjnych dotnet](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="12fa1-133">Symbol download is only supported for official .NET Core runtime versions acquired through official channels such as [the official web site](https://dotnet.microsoft.com/download/dotnet-core) and the [default sources in the dotnet installation scripts](../tools/dotnet-install-script.md).</span></span> <span data-ttu-id="12fa1-134">Błąd 404 podczas pobierania plików debugowania może wskazywać, że zrzut został utworzony przy użyciu środowiska uruchomieniowego platformy .NET Core z innego źródła, takiego jak jeden skompilowany ze źródła lokalnie lub dla konkretnej dystrybucji systemu Linux lub z witryn społeczności, takich jak ArchLinux.</span><span class="sxs-lookup"><span data-stu-id="12fa1-134">A 404 error while downloading debugging files may indicate that the dump was created with a .NET Core runtime from another source, such as one built from source locally or for a particular Linux distro, or from community sites like archlinux.</span></span> <span data-ttu-id="12fa1-135">W takich przypadkach plik niezbędny do debugowania (dotnet, libcoreclr.so i libmscordaccore.so) powinien być kopiowany z tych źródeł lub ze środowiska, w którym został utworzony plik zrzutu.</span><span class="sxs-lookup"><span data-stu-id="12fa1-135">In such cases, file necessary for debugging (dotnet, libcoreclr.so, and libmscordaccore.so) should be copied from those sources or from the environment the dump file was created in.</span></span>
