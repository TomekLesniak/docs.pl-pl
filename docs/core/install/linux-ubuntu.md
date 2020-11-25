---
title: Instalowanie platformy .NET w systemie Ubuntu — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 22ce3379e028f065528e1f507a2d8c1ae598f0e8
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031852"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-ubuntu"></a><span data-ttu-id="5b7d1-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5b7d1-103">Install the .NET SDK or the .NET Runtime on Ubuntu</span></span>

<span data-ttu-id="5b7d1-104">Platforma .NET jest obsługiwana w systemie Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-104">.NET is supported on Ubuntu.</span></span> <span data-ttu-id="5b7d1-105">W tym artykule opisano sposób instalowania programu .NET w systemie Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-105">This article describes how to install .NET on Ubuntu.</span></span> <span data-ttu-id="5b7d1-106">Gdy wersja Ubuntu nie jest objęta wsparciem, platforma .NET nie jest już obsługiwana w tej wersji.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-106">When an Ubuntu version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="5b7d1-107">Jednak te instrukcje mogą pomóc w uzyskaniu środowiska .NET działającego w tych wersjach, nawet jeśli nie jest to obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-107">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="5b7d1-108">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="5b7d1-108">Supported distributions</span></span>

<span data-ttu-id="5b7d1-109">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Ubuntu, w których są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-109">The following table is a list of currently supported .NET releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="5b7d1-110">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca wsparcia](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Ubuntu osiągnie koniec cyklu życia](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="5b7d1-110">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="5b7d1-111">✔️ wskazuje, że wersja programu Ubuntu lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-111">A ✔️ indicates that the version of Ubuntu or .NET is still supported.</span></span>
- <span data-ttu-id="5b7d1-112">❌Wskazuje, że wersja programu Ubuntu lub .NET nie jest obsługiwana w tej wersji Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-112">A ❌ indicates that the version of Ubuntu or .NET isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="5b7d1-113">Gdy wersja programu Ubuntu i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-113">When both a version of Ubuntu and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="5b7d1-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5b7d1-114">Ubuntu</span></span>                   | <span data-ttu-id="5b7d1-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-115">.NET Core 2.1</span></span> | <span data-ttu-id="5b7d1-116">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-116">.NET Core 3.1</span></span> | <span data-ttu-id="5b7d1-117">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-117">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="5b7d1-118">✔️ [20,10](#2010-)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-118">✔️ [20.10](#2010-)</span></span>       | <span data-ttu-id="5b7d1-119">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-119">✔️ 2.1</span></span>        | <span data-ttu-id="5b7d1-120">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-120">✔️ 3.1</span></span>        | <span data-ttu-id="5b7d1-121">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-121">✔️ 5.0</span></span> |
| <span data-ttu-id="5b7d1-122">✔️ [20,04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-122">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="5b7d1-123">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-123">✔️ 2.1</span></span>        | <span data-ttu-id="5b7d1-124">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-124">✔️ 3.1</span></span>        | <span data-ttu-id="5b7d1-125">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-125">✔️ 5.0</span></span> |
| <span data-ttu-id="5b7d1-126">❌[19,10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-126">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="5b7d1-127">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-127">✔️ 2.1</span></span>        | <span data-ttu-id="5b7d1-128">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-128">✔️ 3.1</span></span>        | <span data-ttu-id="5b7d1-129">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-129">✔️ 5.0</span></span> |
| <span data-ttu-id="5b7d1-130">❌[19,04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-130">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="5b7d1-131">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-131">✔️ 2.1</span></span>        | <span data-ttu-id="5b7d1-132">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-132">✔️ 3.1</span></span>        | <span data-ttu-id="5b7d1-133">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-133">❌ 5.0</span></span> |
| <span data-ttu-id="5b7d1-134">❌[18,10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-134">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="5b7d1-135">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-135">✔️ 2.1</span></span>        | <span data-ttu-id="5b7d1-136">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-136">❌ 3.1</span></span>        | <span data-ttu-id="5b7d1-137">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-137">❌ 5.0</span></span> |
| <span data-ttu-id="5b7d1-138">✔️ [18,04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-138">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="5b7d1-139">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-139">✔️ 2.1</span></span>        | <span data-ttu-id="5b7d1-140">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-140">✔️ 3.1</span></span>        | <span data-ttu-id="5b7d1-141">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-141">✔️ 5.0</span></span> |
| <span data-ttu-id="5b7d1-142">❌[17,10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-142">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="5b7d1-143">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-143">✔️ 2.1</span></span>        | <span data-ttu-id="5b7d1-144">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-144">❌ 3.1</span></span>        | <span data-ttu-id="5b7d1-145">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-145">❌ 5.0</span></span> |
| <span data-ttu-id="5b7d1-146">❌[17,04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-146">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="5b7d1-147">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-147">✔️ 2.1</span></span>        | <span data-ttu-id="5b7d1-148">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-148">❌ 3.1</span></span>        | <span data-ttu-id="5b7d1-149">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-149">❌ 5.0</span></span> |
| <span data-ttu-id="5b7d1-150">❌[16,10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-150">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="5b7d1-151">❌ 2,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-151">❌ 2.1</span></span>        | <span data-ttu-id="5b7d1-152">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-152">❌ 3.1</span></span>        | <span data-ttu-id="5b7d1-153">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-153">❌ 5.0</span></span> |
| <span data-ttu-id="5b7d1-154">✔️ [16,04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-154">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="5b7d1-155">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-155">✔️ 2.1</span></span>        | <span data-ttu-id="5b7d1-156">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-156">✔️ 3.1</span></span>        | <span data-ttu-id="5b7d1-157">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-157">✔️ 5.0</span></span> |

<span data-ttu-id="5b7d1-158">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-158">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="5b7d1-159">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="5b7d1-159">The downloads for these still remain published:</span></span>

- <span data-ttu-id="5b7d1-160">3.0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-160">3.0</span></span>
- <span data-ttu-id="5b7d1-161">2.2</span><span class="sxs-lookup"><span data-stu-id="5b7d1-161">2.2</span></span>
- <span data-ttu-id="5b7d1-162">2,0</span><span class="sxs-lookup"><span data-stu-id="5b7d1-162">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="5b7d1-163">Usuń wersje w wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="5b7d1-163">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5b7d1-164">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="5b7d1-164">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2010-"></a><span data-ttu-id="5b7d1-165">20,10 ✔️</span><span class="sxs-lookup"><span data-stu-id="5b7d1-165">20.10 ✔️</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b7d1-166">Program .NET Core 2,1 nie jest jeszcze dostępny w kanale informacyjnym pakietu.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-166">.NET Core 2.1 isn't yet available in the package feed.</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="2004-"></a><span data-ttu-id="5b7d1-167">20,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5b7d1-167">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1910-"></a><span data-ttu-id="5b7d1-168">19,10 ❌</span><span class="sxs-lookup"><span data-stu-id="5b7d1-168">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="5b7d1-169">19,04 ❌</span><span class="sxs-lookup"><span data-stu-id="5b7d1-169">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="5b7d1-170">18,10 ❌</span><span class="sxs-lookup"><span data-stu-id="5b7d1-170">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="5b7d1-171">18,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5b7d1-171">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1710-"></a><span data-ttu-id="5b7d1-172">17,10 ❌</span><span class="sxs-lookup"><span data-stu-id="5b7d1-172">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="5b7d1-173">17,04 ❌</span><span class="sxs-lookup"><span data-stu-id="5b7d1-173">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="5b7d1-174">16,10 ❌</span><span class="sxs-lookup"><span data-stu-id="5b7d1-174">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="5b7d1-175">16,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5b7d1-175">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="5b7d1-176">APT Update — zestaw SDK lub środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="5b7d1-176">APT update SDK or runtime</span></span>

<span data-ttu-id="5b7d1-177">Gdy jest dostępna nowa wersja poprawek dla programu .NET, można po prostu uaktualnić ją za pomocą APT przy użyciu następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="5b7d1-177">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="5b7d1-178">Rozwiązywanie problemów z APT</span><span class="sxs-lookup"><span data-stu-id="5b7d1-178">APT troubleshooting</span></span>

<span data-ttu-id="5b7d1-179">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas korzystania z programu APT w celu zainstalowania platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-179">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="5b7d1-180">Nie można znaleźć pakietu</span><span class="sxs-lookup"><span data-stu-id="5b7d1-180">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="5b7d1-181">Nie można zlokalizować niektórych pakietów, których nie można \\ zainstalować</span><span class="sxs-lookup"><span data-stu-id="5b7d1-181">Unable to locate \\ Some packages could not be installed</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="5b7d1-182">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="5b7d1-182">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="5b7d1-183">Przystawki</span><span class="sxs-lookup"><span data-stu-id="5b7d1-183">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="5b7d1-184">Zależności</span><span class="sxs-lookup"><span data-stu-id="5b7d1-184">Dependencies</span></span>

<span data-ttu-id="5b7d1-185">Po zainstalowaniu programu przy użyciu Menedżera pakietów te biblioteki są instalowane dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-185">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="5b7d1-186">Jeśli jednak ręcznie zainstalujesz program .NET lub opublikujesz aplikację, należy upewnić się, że te biblioteki są zainstalowane:</span><span class="sxs-lookup"><span data-stu-id="5b7d1-186">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="5b7d1-187">libc6</span><span class="sxs-lookup"><span data-stu-id="5b7d1-187">libc6</span></span>
- <span data-ttu-id="5b7d1-188">libgcc1</span><span class="sxs-lookup"><span data-stu-id="5b7d1-188">libgcc1</span></span>
- <span data-ttu-id="5b7d1-189">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="5b7d1-189">libgssapi-krb5-2</span></span>
- <span data-ttu-id="5b7d1-190">libicu52 (dla 14. x)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-190">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="5b7d1-191">libicu55 (dla 16. x)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-191">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="5b7d1-192">libicu60 (dla 18. x)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-192">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="5b7d1-193">libicu66 (dla 20. x)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-193">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="5b7d1-194">libssl 1.0.0 (dla 14. x, 16. x)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-194">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="5b7d1-195">libssl 1.1 (dla 18. x, 20. x)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-195">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="5b7d1-196">libstdc + + 6</span><span class="sxs-lookup"><span data-stu-id="5b7d1-196">libstdc++6</span></span>
- <span data-ttu-id="5b7d1-197">zlib1g</span><span class="sxs-lookup"><span data-stu-id="5b7d1-197">zlib1g</span></span>

<span data-ttu-id="5b7d1-198">W przypadku aplikacji .NET, które używają zestawu *System. Drawing. Common* , wymagana jest również następująca zależność:</span><span class="sxs-lookup"><span data-stu-id="5b7d1-198">For .NET apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="5b7d1-199">libgdiplus (wersja 6.0.1 lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="5b7d1-199">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="5b7d1-200">Aby zainstalować najnowszą wersję programu *libgdiplus* , można dodać do systemu repozytorium mono.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-200">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="5b7d1-201">Aby uzyskać więcej informacji, zobacz <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="5b7d1-201">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="5b7d1-202">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="5b7d1-202">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="5b7d1-203">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="5b7d1-203">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="5b7d1-204">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="5b7d1-204">Next steps</span></span>

- [<span data-ttu-id="5b7d1-205">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5b7d1-205">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
