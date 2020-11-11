---
title: Instalowanie platformy .NET w systemie Debian — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie Debian.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 6dad4e1779600b22b8301e03ffb8fb2c16786ead
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506997"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-debian"></a><span data-ttu-id="cb004-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie Debian</span><span class="sxs-lookup"><span data-stu-id="cb004-103">Install the .NET SDK or the .NET Runtime on Debian</span></span>

<span data-ttu-id="cb004-104">W tym artykule opisano sposób instalowania programu .NET w systemie Debian.</span><span class="sxs-lookup"><span data-stu-id="cb004-104">This article describes how to install .NET on Debian.</span></span> <span data-ttu-id="cb004-105">Gdy wersja Debian nie jest obsługiwana, program .NET nie jest już obsługiwany w tej wersji.</span><span class="sxs-lookup"><span data-stu-id="cb004-105">When a Debian version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="cb004-106">Jednak te instrukcje mogą pomóc w uzyskaniu środowiska .NET działającego w tych wersjach, nawet jeśli nie jest to obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="cb004-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="cb004-107">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="cb004-107">Supported distributions</span></span>

<span data-ttu-id="cb004-108">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Debian, w których są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="cb004-108">The following table is a list of currently supported .NET releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="cb004-109">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca wsparcia](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Debian osiągnie koniec cyklu życia](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="cb004-109">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="cb004-110">✔️ wskazuje, że wersja programu debian lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="cb004-110">A ✔️ indicates that the version of Debian or .NET is still supported.</span></span>
- <span data-ttu-id="cb004-111">❌Wskazuje, że wersja programu debian lub .NET nie jest obsługiwana w tej wersji Debian.</span><span class="sxs-lookup"><span data-stu-id="cb004-111">A ❌ indicates that the version of Debian or .NET isn't supported on that Debian release.</span></span>
- <span data-ttu-id="cb004-112">Gdy wersja programu Debian i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="cb004-112">When both a version of Debian and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="cb004-113">Debian</span><span class="sxs-lookup"><span data-stu-id="cb004-113">Debian</span></span>                   | <span data-ttu-id="cb004-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cb004-114">.NET Core 2.1</span></span> | <span data-ttu-id="cb004-115">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="cb004-115">.NET Core 3.1</span></span> | <span data-ttu-id="cb004-116">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="cb004-116">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="cb004-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="cb004-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="cb004-118">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="cb004-118">✔️ 2.1</span></span>        | <span data-ttu-id="cb004-119">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="cb004-119">✔️ 3.1</span></span>        | <span data-ttu-id="cb004-120">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="cb004-120">✔️ 5.0</span></span> |
| <span data-ttu-id="cb004-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="cb004-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="cb004-122">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="cb004-122">✔️ 2.1</span></span>        | <span data-ttu-id="cb004-123">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="cb004-123">✔️ 3.1</span></span>        | <span data-ttu-id="cb004-124">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="cb004-124">✔️ 5.0</span></span> |
| <span data-ttu-id="cb004-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="cb004-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="cb004-126">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="cb004-126">✔️ 2.1</span></span>        | <span data-ttu-id="cb004-127">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="cb004-127">❌ 3.1</span></span>        | <span data-ttu-id="cb004-128">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="cb004-128">❌ 5.0</span></span> |

<span data-ttu-id="cb004-129">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="cb004-129">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="cb004-130">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="cb004-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="cb004-131">3.0</span><span class="sxs-lookup"><span data-stu-id="cb004-131">3.0</span></span>
- <span data-ttu-id="cb004-132">2.2</span><span class="sxs-lookup"><span data-stu-id="cb004-132">2.2</span></span>
- <span data-ttu-id="cb004-133">2,0</span><span class="sxs-lookup"><span data-stu-id="cb004-133">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="cb004-134">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="cb004-134">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="cb004-135">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="cb004-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="cb004-136">Debian ✔️ 9</span><span class="sxs-lookup"><span data-stu-id="cb004-136">Debian 9 ✔️</span></span>

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

## <a name="debian-8-"></a><span data-ttu-id="cb004-137">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="cb004-137">Debian 8 ❌</span></span>

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

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="cb004-138">APT Update — zestaw SDK lub środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="cb004-138">APT update SDK or runtime</span></span>

<span data-ttu-id="cb004-139">Gdy jest dostępna nowa wersja poprawek dla programu .NET, można po prostu uaktualnić ją za pomocą APT przy użyciu następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="cb004-139">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="cb004-140">Rozwiązywanie problemów z APT</span><span class="sxs-lookup"><span data-stu-id="cb004-140">APT troubleshooting</span></span>

<span data-ttu-id="cb004-141">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas korzystania z programu APT w celu zainstalowania platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="cb004-141">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="cb004-142">Nie można znaleźć pakietu</span><span class="sxs-lookup"><span data-stu-id="cb004-142">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="cb004-143">Nie można zlokalizować niektórych pakietów, których nie można \\ zainstalować</span><span class="sxs-lookup"><span data-stu-id="cb004-143">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="cb004-144">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="cb004-144">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="cb004-145">Przystawki</span><span class="sxs-lookup"><span data-stu-id="cb004-145">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="cb004-146">Zależności</span><span class="sxs-lookup"><span data-stu-id="cb004-146">Dependencies</span></span>

<span data-ttu-id="cb004-147">Po zainstalowaniu programu przy użyciu Menedżera pakietów te biblioteki są instalowane dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="cb004-147">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="cb004-148">Jeśli jednak ręcznie zainstalujesz platformę .NET Core lub opublikujesz aplikację, musisz upewnić się, że te biblioteki są zainstalowane:</span><span class="sxs-lookup"><span data-stu-id="cb004-148">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="cb004-149">libc6</span><span class="sxs-lookup"><span data-stu-id="cb004-149">libc6</span></span>
- <span data-ttu-id="cb004-150">libgcc1</span><span class="sxs-lookup"><span data-stu-id="cb004-150">libgcc1</span></span>
- <span data-ttu-id="cb004-151">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="cb004-151">libgssapi-krb5-2</span></span>
- <span data-ttu-id="cb004-152">libicu52 (dla 8. x)</span><span class="sxs-lookup"><span data-stu-id="cb004-152">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="cb004-153">libicu57 (dla 9. x)</span><span class="sxs-lookup"><span data-stu-id="cb004-153">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="cb004-154">libicu63 (dla 10. x)</span><span class="sxs-lookup"><span data-stu-id="cb004-154">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="cb004-155">libicu67 (dla 11. x)</span><span class="sxs-lookup"><span data-stu-id="cb004-155">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="cb004-156">libssl 1.0.0 (dla 8. x)</span><span class="sxs-lookup"><span data-stu-id="cb004-156">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="cb004-157">libssl 1.1 (dla 9. x-11. x)</span><span class="sxs-lookup"><span data-stu-id="cb004-157">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="cb004-158">libstdc + + 6</span><span class="sxs-lookup"><span data-stu-id="cb004-158">libstdc++6</span></span>
- <span data-ttu-id="cb004-159">zlib1g</span><span class="sxs-lookup"><span data-stu-id="cb004-159">zlib1g</span></span>

<span data-ttu-id="cb004-160">W przypadku aplikacji .NET Core, które używają zestawu *System. Drawing. Common* , wymagana jest również następująca zależność:</span><span class="sxs-lookup"><span data-stu-id="cb004-160">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="cb004-161">libgdiplus (wersja 6.0.1 lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="cb004-161">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="cb004-162">Aby zainstalować najnowszą wersję programu *libgdiplus* , można dodać do systemu repozytorium mono.</span><span class="sxs-lookup"><span data-stu-id="cb004-162">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="cb004-163">Aby uzyskać więcej informacji, zobacz <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="cb004-163">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="cb004-164">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="cb004-164">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="cb004-165">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="cb004-165">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="cb004-166">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="cb004-166">Next steps</span></span>

- [<span data-ttu-id="cb004-167">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cb004-167">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
