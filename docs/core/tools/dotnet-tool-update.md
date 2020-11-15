---
title: polecenie aktualizacji narzędzia dotnet
description: Polecenie aktualizacji narzędzia dotnet umożliwia zaktualizowanie określonego narzędzia platformy .NET na komputerze.
ms.date: 07/08/2020
ms.openlocfilehash: 18b153e53a6dbcb32e50ae4a7d06a1c2f53d1eb5
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634080"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="d34e8-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="d34e8-103">dotnet tool update</span></span>

<span data-ttu-id="d34e8-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="d34e8-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d34e8-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="d34e8-105">Name</span></span>

<span data-ttu-id="d34e8-106">`dotnet tool update` -Aktualizuje określone [Narzędzie .NET](global-tools.md) na komputerze.</span><span class="sxs-lookup"><span data-stu-id="d34e8-106">`dotnet tool update` - Updates the specified [.NET tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d34e8-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="d34e8-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a><span data-ttu-id="d34e8-108">Opis</span><span class="sxs-lookup"><span data-stu-id="d34e8-108">Description</span></span>

<span data-ttu-id="d34e8-109">`dotnet tool update`Polecenie umożliwia zaktualizowanie narzędzi .NET Tools na komputerze do najnowszej stabilnej wersji pakietu.</span><span class="sxs-lookup"><span data-stu-id="d34e8-109">The `dotnet tool update` command provides a way for you to update .NET tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="d34e8-110">Polecenie Odinstalowuje i ponownie instaluje narzędzie, co skutecznie aktualizuje go.</span><span class="sxs-lookup"><span data-stu-id="d34e8-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="d34e8-111">Aby użyć polecenia, należy określić jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="d34e8-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="d34e8-112">Aby zaktualizować narzędzie globalne, które zostało zainstalowane w lokalizacji domyślnej, użyj `--global` opcji</span><span class="sxs-lookup"><span data-stu-id="d34e8-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="d34e8-113">Aby zaktualizować narzędzie globalne, które zostało zainstalowane w niestandardowej lokalizacji, użyj `--tool-path` opcji.</span><span class="sxs-lookup"><span data-stu-id="d34e8-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="d34e8-114">Aby zaktualizować narzędzie lokalne, użyj `--local` opcji.</span><span class="sxs-lookup"><span data-stu-id="d34e8-114">To update a local tool, use the `--local` option.</span></span>

<span data-ttu-id="d34e8-115">**Narzędzia lokalne są dostępne począwszy od zestaw .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="d34e8-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="d34e8-116">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d34e8-116">Arguments</span></span>

- **`PACKAGE_ID`**

  <span data-ttu-id="d34e8-117">Nazwa/identyfikator pakietu NuGet zawierającego narzędzie globalne platformy .NET do zaktualizowania.</span><span class="sxs-lookup"><span data-stu-id="d34e8-117">Name/ID of the NuGet package that contains the .NET global tool to update.</span></span> <span data-ttu-id="d34e8-118">Nazwę pakietu można znaleźć przy użyciu polecenia [listy narzędzi dotnet](dotnet-tool-list.md) .</span><span class="sxs-lookup"><span data-stu-id="d34e8-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="d34e8-119">Opcje</span><span class="sxs-lookup"><span data-stu-id="d34e8-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="d34e8-120">Dodaje dodatkowe źródło pakietów NuGet do użycia podczas instalacji.</span><span class="sxs-lookup"><span data-stu-id="d34e8-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="d34e8-121">Plik konfiguracji NuGet ( *nuget.config* ) do użycia.</span><span class="sxs-lookup"><span data-stu-id="d34e8-121">The NuGet configuration ( *nuget.config* ) file to use.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="d34e8-122">Zapobiegaj równoległemu przywracaniu wielu projektów.</span><span class="sxs-lookup"><span data-stu-id="d34e8-122">Prevent restoring multiple projects in parallel.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="d34e8-123">Określa [platformę docelową](../../standard/frameworks.md) do zaktualizowania narzędzia dla programu.</span><span class="sxs-lookup"><span data-stu-id="d34e8-123">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="d34e8-124">Traktuj błędy źródłowe pakietu jako ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="d34e8-124">Treat package source failures as warnings.</span></span>

- **`--interactive`**

  <span data-ttu-id="d34e8-125">Umożliwia zatrzymanie polecenia i oczekiwanie na dane wejściowe użytkownika lub akcję (na przykład zakończenie uwierzytelniania).</span><span class="sxs-lookup"><span data-stu-id="d34e8-125">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`--local`**

  <span data-ttu-id="d34e8-126">Aktualizowanie narzędzia i manifestu narzędzia lokalnego.</span><span class="sxs-lookup"><span data-stu-id="d34e8-126">Update the tool and the local tool manifest.</span></span> <span data-ttu-id="d34e8-127">Nie można łączyć z `--global` opcją lub `--tool-path` opcją.</span><span class="sxs-lookup"><span data-stu-id="d34e8-127">Can't be combined with the `--global` option or the `--tool-path` option.</span></span>

- **`--no-cache`**

  <span data-ttu-id="d34e8-128">Nie Buforuj pakietów i żądań HTTP.</span><span class="sxs-lookup"><span data-stu-id="d34e8-128">Do not cache packages and HTTP requests.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="d34e8-129">Ścieżka do pliku manifestu.</span><span class="sxs-lookup"><span data-stu-id="d34e8-129">Path to the manifest file.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="d34e8-130">Określa lokalizację, w której zainstalowano narzędzie globalne.</span><span class="sxs-lookup"><span data-stu-id="d34e8-130">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="d34e8-131">ŚCIEŻKA może być bezwzględna lub względna.</span><span class="sxs-lookup"><span data-stu-id="d34e8-131">PATH can be absolute or relative.</span></span> <span data-ttu-id="d34e8-132">Nie można łączyć z `--global` opcją.</span><span class="sxs-lookup"><span data-stu-id="d34e8-132">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="d34e8-133">Pominięcie obu `--global` i `--tool-path` oznacza, że narzędzie, które ma zostać zaktualizowane, jest narzędziem lokalnym.</span><span class="sxs-lookup"><span data-stu-id="d34e8-133">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`--version <VERSION>`**

  <span data-ttu-id="d34e8-134">Zakres wersji pakietu Narzędzia do zaktualizowania.</span><span class="sxs-lookup"><span data-stu-id="d34e8-134">The version range of the tool package to update to.</span></span> <span data-ttu-id="d34e8-135">Nie można użyć tego do obniżenia wersji, najpierw musisz mieć `uninstall` nowsze wersje.</span><span class="sxs-lookup"><span data-stu-id="d34e8-135">This cannot be used to downgrade versions, you must `uninstall` newer versions first.</span></span>

- **`-g|--global`**

  <span data-ttu-id="d34e8-136">Określa, że aktualizacja dotyczy narzędzia dla całego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d34e8-136">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="d34e8-137">Nie można łączyć z `--tool-path` opcją.</span><span class="sxs-lookup"><span data-stu-id="d34e8-137">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="d34e8-138">Pominięcie obu `--global` i `--tool-path` oznacza, że narzędzie, które ma zostać zaktualizowane, jest narzędziem lokalnym.</span><span class="sxs-lookup"><span data-stu-id="d34e8-138">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d34e8-139">Drukuje krótką pomoc dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="d34e8-139">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="d34e8-140">Ustawia poziom szczegółowości polecenia.</span><span class="sxs-lookup"><span data-stu-id="d34e8-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d34e8-141">Dozwolone wartości to `q[uiet]` , `m[inimal]` , `n[ormal]` , `d[etailed]` i `diag[nostic]` .</span><span class="sxs-lookup"><span data-stu-id="d34e8-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="d34e8-142">Przykłady</span><span class="sxs-lookup"><span data-stu-id="d34e8-142">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="d34e8-143">Aktualizuje narzędzie globalne [dotnetsay](https://www.nuget.org/packages/dotnetsay/) .</span><span class="sxs-lookup"><span data-stu-id="d34e8-143">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="d34e8-144">Aktualizuje narzędzie globalne [dotnetsay](https://www.nuget.org/packages/dotnetsay/) znajdujące się w określonym katalogu systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="d34e8-144">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="d34e8-145">Aktualizuje narzędzie globalne [dotnetsay](https://www.nuget.org/packages/dotnetsay/) znajdujące się w określonym katalogu systemu Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="d34e8-145">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="d34e8-146">Aktualizuje narzędzie lokalne [dotnetsay](https://www.nuget.org/packages/dotnetsay/) zainstalowane dla bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="d34e8-146">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  <span data-ttu-id="d34e8-147">Aktualizuje narzędzie globalne [dotnetsay](https://www.nuget.org/packages/dotnetsay/) do najnowszej wersji poprawki, z wersją główną `2` i wersją pomocniczą programu `0` .</span><span class="sxs-lookup"><span data-stu-id="d34e8-147">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the latest patch version, with a major version of `2`, and a minor version of `0`.</span></span>

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  <span data-ttu-id="d34e8-148">Aktualizuje narzędzie globalne [dotnetsay](https://www.nuget.org/packages/dotnetsay/) do najniższej wersji w określonym zakresie `(> 2.0.0 && < 2.1.4)` , wersja zostanie `2.1.0` zainstalowana.</span><span class="sxs-lookup"><span data-stu-id="d34e8-148">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the lowest version within the specified range `(> 2.0.0 && < 2.1.4)`, version `2.1.0` would be installed.</span></span> <span data-ttu-id="d34e8-149">Aby uzyskać więcej informacji na temat zakresów wersji semantycznej, zobacz [zakres wersji pakietów NuGet](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="d34e8-149">For more information on semantic versioning ranges, see [NuGet packaging version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span>

## <a name="see-also"></a><span data-ttu-id="d34e8-150">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d34e8-150">See also</span></span>

- [<span data-ttu-id="d34e8-151">Narzędzia .NET</span><span class="sxs-lookup"><span data-stu-id="d34e8-151">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="d34e8-152">Semantyczna obsługa wersji</span><span class="sxs-lookup"><span data-stu-id="d34e8-152">Semantic versioning</span></span>](https://semver.org)
- [<span data-ttu-id="d34e8-153">Samouczek: Instalowanie i używanie narzędzia globalnego platformy .NET przy użyciu interfejsu wiersza polecenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="d34e8-153">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="d34e8-154">Samouczek: Instalowanie i używanie lokalnego narzędzia .NET przy użyciu interfejsu wiersza polecenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="d34e8-154">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
