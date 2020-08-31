---
title: Instalowanie programu .NET Core w systemie Debian — .NET Core
description: Ilustruje różne sposoby instalowania zestaw .NET Core SDK i środowiska uruchomieniowego .NET Core w systemie Debian.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: a9ccc461362b1be3e5bc2ee7d13d5d7d383192e4
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053160"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a><span data-ttu-id="bed8f-103">Zainstaluj zestaw .NET Core SDK lub środowisko uruchomieniowe platformy .NET Core w systemie Debian</span><span class="sxs-lookup"><span data-stu-id="bed8f-103">Install .NET Core SDK or .NET Core Runtime on Debian</span></span>

<span data-ttu-id="bed8f-104">W tym artykule opisano sposób instalowania programu .NET Core w systemie Debian.</span><span class="sxs-lookup"><span data-stu-id="bed8f-104">This article describes how to install .NET Core on Debian.</span></span> <span data-ttu-id="bed8f-105">Gdy wersja Debian nie jest objęta wsparciem, platforma .NET Core nie jest już obsługiwana w tej wersji.</span><span class="sxs-lookup"><span data-stu-id="bed8f-105">When a Debian version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="bed8f-106">Te instrukcje mogą jednak ułatwić uzyskanie programu .NET Core działającego w tych wersjach, chociaż nie jest to obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="bed8f-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="bed8f-107">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="bed8f-107">Supported distributions</span></span>

<span data-ttu-id="bed8f-108">Poniższa tabela zawiera listę obecnie obsługiwanych wersji programu .NET Core oraz wersji Debian, na których są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="bed8f-108">The following table is a list of currently supported .NET Core releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="bed8f-109">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET Core osiągnie koniec okresu obsłudze](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Debian osiągnie koniec cyklu życia](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="bed8f-109">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="bed8f-110">✔️ wskazuje, że wersja programu debian lub .NET Core jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="bed8f-110">A ✔️ indicates that the version of Debian or .NET Core is still supported.</span></span>
- <span data-ttu-id="bed8f-111">❌Wskazuje, że wersja Debian lub .NET Core nie jest obsługiwana w tej wersji Debian.</span><span class="sxs-lookup"><span data-stu-id="bed8f-111">A ❌ indicates that the version of Debian or .NET Core isn't supported on that Debian release.</span></span>
- <span data-ttu-id="bed8f-112">Gdy wersja Debian i wersja platformy .NET Core mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="bed8f-112">When both a version of Debian and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="bed8f-113">Debian</span><span class="sxs-lookup"><span data-stu-id="bed8f-113">Debian</span></span>                   | <span data-ttu-id="bed8f-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bed8f-114">.NET Core 2.1</span></span> | <span data-ttu-id="bed8f-115">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="bed8f-115">.NET Core 3.1</span></span> | <span data-ttu-id="bed8f-116">.NET 5 (wersja zapoznawcza) (tylko instalacja ręczna)</span><span class="sxs-lookup"><span data-stu-id="bed8f-116">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="bed8f-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="bed8f-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="bed8f-118">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="bed8f-118">✔️ 2.1</span></span>        | <span data-ttu-id="bed8f-119">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="bed8f-119">✔️ 3.1</span></span>        | <span data-ttu-id="bed8f-120">✔️ 5,0 — wersja zapoznawcza</span><span class="sxs-lookup"><span data-stu-id="bed8f-120">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="bed8f-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="bed8f-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="bed8f-122">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="bed8f-122">✔️ 2.1</span></span>        | <span data-ttu-id="bed8f-123">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="bed8f-123">✔️ 3.1</span></span>        | <span data-ttu-id="bed8f-124">✔️ 5,0 — wersja zapoznawcza</span><span class="sxs-lookup"><span data-stu-id="bed8f-124">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="bed8f-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="bed8f-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="bed8f-126">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="bed8f-126">✔️ 2.1</span></span>        | <span data-ttu-id="bed8f-127">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="bed8f-127">❌ 3.1</span></span>        | <span data-ttu-id="bed8f-128">❌ wersja zapoznawcza 5,0</span><span class="sxs-lookup"><span data-stu-id="bed8f-128">❌ 5.0 Preview</span></span> |

<span data-ttu-id="bed8f-129">Następujące wersje programu .NET Core nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="bed8f-129">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="bed8f-130">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="bed8f-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="bed8f-131">3,0</span><span class="sxs-lookup"><span data-stu-id="bed8f-131">3.0</span></span>
- <span data-ttu-id="bed8f-132">2,2</span><span class="sxs-lookup"><span data-stu-id="bed8f-132">2.2</span></span>
- <span data-ttu-id="bed8f-133">2,0</span><span class="sxs-lookup"><span data-stu-id="bed8f-133">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="bed8f-134">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="bed8f-134">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="bed8f-135">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="bed8f-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="bed8f-136">Debian ✔️ 9</span><span class="sxs-lookup"><span data-stu-id="bed8f-136">Debian 9 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-8-"></a><span data-ttu-id="bed8f-137">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="bed8f-137">Debian 8 ❌</span></span>

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

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="bed8f-138">APT Update — zestaw SDK lub środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="bed8f-138">APT update SDK or runtime</span></span>

<span data-ttu-id="bed8f-139">Gdy dostępna jest nowa wersja poprawek dla programu .NET Core, można po prostu uaktualnić ją za pomocą APT za pomocą następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="bed8f-139">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="bed8f-140">Rozwiązywanie problemów z APT</span><span class="sxs-lookup"><span data-stu-id="bed8f-140">APT troubleshooting</span></span>

<span data-ttu-id="bed8f-141">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas instalowania programu .NET Core przy użyciu programu APT.</span><span class="sxs-lookup"><span data-stu-id="bed8f-141">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="bed8f-142">Nie można zlokalizować</span><span class="sxs-lookup"><span data-stu-id="bed8f-142">Unable to locate</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="bed8f-143">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="bed8f-143">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="bed8f-144">Przystawki</span><span class="sxs-lookup"><span data-stu-id="bed8f-144">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="bed8f-145">Zależności</span><span class="sxs-lookup"><span data-stu-id="bed8f-145">Dependencies</span></span>

<span data-ttu-id="bed8f-146">Po zainstalowaniu programu przy użyciu Menedżera pakietów te biblioteki są instalowane dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="bed8f-146">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="bed8f-147">Jeśli jednak ręcznie zainstalujesz platformę .NET Core lub opublikujesz aplikację, musisz upewnić się, że te biblioteki są zainstalowane:</span><span class="sxs-lookup"><span data-stu-id="bed8f-147">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="bed8f-148">libc6</span><span class="sxs-lookup"><span data-stu-id="bed8f-148">libc6</span></span>
- <span data-ttu-id="bed8f-149">libgcc1</span><span class="sxs-lookup"><span data-stu-id="bed8f-149">libgcc1</span></span>
- <span data-ttu-id="bed8f-150">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="bed8f-150">libgssapi-krb5-2</span></span>
- <span data-ttu-id="bed8f-151">libicu52 (dla 8. x)</span><span class="sxs-lookup"><span data-stu-id="bed8f-151">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="bed8f-152">libicu57 (dla 9. x)</span><span class="sxs-lookup"><span data-stu-id="bed8f-152">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="bed8f-153">libicu63 (dla 10. x)</span><span class="sxs-lookup"><span data-stu-id="bed8f-153">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="bed8f-154">libicu67 (dla 11. x)</span><span class="sxs-lookup"><span data-stu-id="bed8f-154">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="bed8f-155">libssl 1.0.0 (dla 8. x)</span><span class="sxs-lookup"><span data-stu-id="bed8f-155">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="bed8f-156">libssl 1.1 (dla 9. x-11. x)</span><span class="sxs-lookup"><span data-stu-id="bed8f-156">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="bed8f-157">libstdc + + 6</span><span class="sxs-lookup"><span data-stu-id="bed8f-157">libstdc++6</span></span>
- <span data-ttu-id="bed8f-158">zlib1g</span><span class="sxs-lookup"><span data-stu-id="bed8f-158">zlib1g</span></span>

<span data-ttu-id="bed8f-159">W przypadku aplikacji .NET Core, które używają zestawu *System. Drawing. Common* , wymagana jest również następująca zależność:</span><span class="sxs-lookup"><span data-stu-id="bed8f-159">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="bed8f-160">libgdiplus (wersja 6.0.1 lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="bed8f-160">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="bed8f-161">Aby zainstalować najnowszą wersję programu *libgdiplus* , można dodać do systemu repozytorium mono.</span><span class="sxs-lookup"><span data-stu-id="bed8f-161">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="bed8f-162">Aby uzyskać więcej informacji, zobacz <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="bed8f-162">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="bed8f-163">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="bed8f-163">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="bed8f-164">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="bed8f-164">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="bed8f-165">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="bed8f-165">Next steps</span></span>

- [<span data-ttu-id="bed8f-166">Samouczek: Tworzenie aplikacji konsolowej z zestaw .NET Core SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bed8f-166">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
