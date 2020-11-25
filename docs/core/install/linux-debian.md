---
title: Instalowanie platformy .NET w systemie Debian — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie Debian.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 683d0a9c47edf3cf9c47426d659e778eeb6f84df
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031894"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-debian"></a><span data-ttu-id="fa41b-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie Debian</span><span class="sxs-lookup"><span data-stu-id="fa41b-103">Install the .NET SDK or the .NET Runtime on Debian</span></span>

<span data-ttu-id="fa41b-104">W tym artykule opisano sposób instalowania programu .NET w systemie Debian.</span><span class="sxs-lookup"><span data-stu-id="fa41b-104">This article describes how to install .NET on Debian.</span></span> <span data-ttu-id="fa41b-105">Gdy wersja Debian nie jest obsługiwana, program .NET nie jest już obsługiwany w tej wersji.</span><span class="sxs-lookup"><span data-stu-id="fa41b-105">When a Debian version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="fa41b-106">Jednak te instrukcje mogą pomóc w uzyskaniu środowiska .NET działającego w tych wersjach, nawet jeśli nie jest to obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="fa41b-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="fa41b-107">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="fa41b-107">Supported distributions</span></span>

<span data-ttu-id="fa41b-108">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Debian, w których są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="fa41b-108">The following table is a list of currently supported .NET releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="fa41b-109">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca wsparcia](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Debian osiągnie koniec cyklu życia](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="fa41b-109">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="fa41b-110">✔️ wskazuje, że wersja programu debian lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="fa41b-110">A ✔️ indicates that the version of Debian or .NET is still supported.</span></span>
- <span data-ttu-id="fa41b-111">❌Wskazuje, że wersja programu debian lub .NET nie jest obsługiwana w tej wersji Debian.</span><span class="sxs-lookup"><span data-stu-id="fa41b-111">A ❌ indicates that the version of Debian or .NET isn't supported on that Debian release.</span></span>
- <span data-ttu-id="fa41b-112">Gdy wersja programu Debian i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="fa41b-112">When both a version of Debian and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="fa41b-113">Debian</span><span class="sxs-lookup"><span data-stu-id="fa41b-113">Debian</span></span>                   | <span data-ttu-id="fa41b-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fa41b-114">.NET Core 2.1</span></span> | <span data-ttu-id="fa41b-115">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="fa41b-115">.NET Core 3.1</span></span> | <span data-ttu-id="fa41b-116">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="fa41b-116">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="fa41b-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="fa41b-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="fa41b-118">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="fa41b-118">✔️ 2.1</span></span>        | <span data-ttu-id="fa41b-119">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="fa41b-119">✔️ 3.1</span></span>        | <span data-ttu-id="fa41b-120">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="fa41b-120">✔️ 5.0</span></span> |
| <span data-ttu-id="fa41b-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="fa41b-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="fa41b-122">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="fa41b-122">✔️ 2.1</span></span>        | <span data-ttu-id="fa41b-123">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="fa41b-123">✔️ 3.1</span></span>        | <span data-ttu-id="fa41b-124">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="fa41b-124">✔️ 5.0</span></span> |
| <span data-ttu-id="fa41b-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="fa41b-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="fa41b-126">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="fa41b-126">✔️ 2.1</span></span>        | <span data-ttu-id="fa41b-127">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="fa41b-127">❌ 3.1</span></span>        | <span data-ttu-id="fa41b-128">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="fa41b-128">❌ 5.0</span></span> |

<span data-ttu-id="fa41b-129">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="fa41b-129">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="fa41b-130">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="fa41b-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="fa41b-131">3.0</span><span class="sxs-lookup"><span data-stu-id="fa41b-131">3.0</span></span>
- <span data-ttu-id="fa41b-132">2.2</span><span class="sxs-lookup"><span data-stu-id="fa41b-132">2.2</span></span>
- <span data-ttu-id="fa41b-133">2,0</span><span class="sxs-lookup"><span data-stu-id="fa41b-133">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="fa41b-134">Usuń wersje w wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="fa41b-134">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="fa41b-135">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="fa41b-135">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="fa41b-136">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="fa41b-136">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="fa41b-137">Debian ✔️ 9</span><span class="sxs-lookup"><span data-stu-id="fa41b-137">Debian 9 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-8-"></a><span data-ttu-id="fa41b-138">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="fa41b-138">Debian 8 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="fa41b-139">APT Update — zestaw SDK lub środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="fa41b-139">APT update SDK or runtime</span></span>

<span data-ttu-id="fa41b-140">Gdy jest dostępna nowa wersja poprawek dla programu .NET, można po prostu uaktualnić ją za pomocą APT przy użyciu następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="fa41b-140">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="fa41b-141">Rozwiązywanie problemów z APT</span><span class="sxs-lookup"><span data-stu-id="fa41b-141">APT troubleshooting</span></span>

<span data-ttu-id="fa41b-142">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas korzystania z programu APT w celu zainstalowania platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="fa41b-142">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="fa41b-143">Nie można znaleźć pakietu</span><span class="sxs-lookup"><span data-stu-id="fa41b-143">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="fa41b-144">Nie można zlokalizować niektórych pakietów, których nie można \\ zainstalować</span><span class="sxs-lookup"><span data-stu-id="fa41b-144">Unable to locate \\ Some packages could not be installed</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="fa41b-145">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="fa41b-145">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="fa41b-146">Przystawki</span><span class="sxs-lookup"><span data-stu-id="fa41b-146">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="fa41b-147">Zależności</span><span class="sxs-lookup"><span data-stu-id="fa41b-147">Dependencies</span></span>

<span data-ttu-id="fa41b-148">Po zainstalowaniu programu przy użyciu Menedżera pakietów te biblioteki są instalowane dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="fa41b-148">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="fa41b-149">Jeśli jednak ręcznie zainstalujesz platformę .NET Core lub opublikujesz aplikację, musisz upewnić się, że te biblioteki są zainstalowane:</span><span class="sxs-lookup"><span data-stu-id="fa41b-149">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="fa41b-150">libc6</span><span class="sxs-lookup"><span data-stu-id="fa41b-150">libc6</span></span>
- <span data-ttu-id="fa41b-151">libgcc1</span><span class="sxs-lookup"><span data-stu-id="fa41b-151">libgcc1</span></span>
- <span data-ttu-id="fa41b-152">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="fa41b-152">libgssapi-krb5-2</span></span>
- <span data-ttu-id="fa41b-153">libicu52 (dla 8. x)</span><span class="sxs-lookup"><span data-stu-id="fa41b-153">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="fa41b-154">libicu57 (dla 9. x)</span><span class="sxs-lookup"><span data-stu-id="fa41b-154">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="fa41b-155">libicu63 (dla 10. x)</span><span class="sxs-lookup"><span data-stu-id="fa41b-155">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="fa41b-156">libicu67 (dla 11. x)</span><span class="sxs-lookup"><span data-stu-id="fa41b-156">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="fa41b-157">libssl 1.0.0 (dla 8. x)</span><span class="sxs-lookup"><span data-stu-id="fa41b-157">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="fa41b-158">libssl 1.1 (dla 9. x-11. x)</span><span class="sxs-lookup"><span data-stu-id="fa41b-158">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="fa41b-159">libstdc + + 6</span><span class="sxs-lookup"><span data-stu-id="fa41b-159">libstdc++6</span></span>
- <span data-ttu-id="fa41b-160">zlib1g</span><span class="sxs-lookup"><span data-stu-id="fa41b-160">zlib1g</span></span>

<span data-ttu-id="fa41b-161">W przypadku aplikacji .NET Core, które używają zestawu *System. Drawing. Common* , wymagana jest również następująca zależność:</span><span class="sxs-lookup"><span data-stu-id="fa41b-161">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="fa41b-162">libgdiplus (wersja 6.0.1 lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="fa41b-162">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="fa41b-163">Aby zainstalować najnowszą wersję programu *libgdiplus* , można dodać do systemu repozytorium mono.</span><span class="sxs-lookup"><span data-stu-id="fa41b-163">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="fa41b-164">Aby uzyskać więcej informacji, zobacz <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="fa41b-164">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="fa41b-165">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="fa41b-165">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="fa41b-166">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="fa41b-166">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="fa41b-167">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="fa41b-167">Next steps</span></span>

- [<span data-ttu-id="fa41b-168">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fa41b-168">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
