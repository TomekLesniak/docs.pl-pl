---
title: Instalowanie platformy .NET w systemie Ubuntu — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 419bcf3ccd011cadba8f8c64e195d7dbdbf7e241
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507029"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-ubuntu"></a><span data-ttu-id="a7648-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a7648-103">Install the .NET SDK or the .NET Runtime on Ubuntu</span></span>

<span data-ttu-id="a7648-104">Platforma .NET jest obsługiwana w systemie Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="a7648-104">.NET is supported on Ubuntu.</span></span> <span data-ttu-id="a7648-105">W tym artykule opisano sposób instalowania programu .NET w systemie Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="a7648-105">This article describes how to install .NET on Ubuntu.</span></span> <span data-ttu-id="a7648-106">Gdy wersja Ubuntu nie jest objęta wsparciem, platforma .NET nie jest już obsługiwana w tej wersji.</span><span class="sxs-lookup"><span data-stu-id="a7648-106">When an Ubuntu version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="a7648-107">Jednak te instrukcje mogą pomóc w uzyskaniu środowiska .NET działającego w tych wersjach, nawet jeśli nie jest to obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="a7648-107">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="a7648-108">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="a7648-108">Supported distributions</span></span>

<span data-ttu-id="a7648-109">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Ubuntu, w których są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="a7648-109">The following table is a list of currently supported .NET releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="a7648-110">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca wsparcia](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Ubuntu osiągnie koniec cyklu życia](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="a7648-110">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="a7648-111">✔️ wskazuje, że wersja programu Ubuntu lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="a7648-111">A ✔️ indicates that the version of Ubuntu or .NET is still supported.</span></span>
- <span data-ttu-id="a7648-112">❌Wskazuje, że wersja programu Ubuntu lub .NET nie jest obsługiwana w tej wersji Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="a7648-112">A ❌ indicates that the version of Ubuntu or .NET isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="a7648-113">Gdy wersja programu Ubuntu i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="a7648-113">When both a version of Ubuntu and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="a7648-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a7648-114">Ubuntu</span></span>                   | <span data-ttu-id="a7648-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a7648-115">.NET Core 2.1</span></span> | <span data-ttu-id="a7648-116">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-116">.NET Core 3.1</span></span> | <span data-ttu-id="a7648-117">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-117">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="a7648-118">✔️ [20,10](#2010-)</span><span class="sxs-lookup"><span data-stu-id="a7648-118">✔️ [20.10](#2010-)</span></span>       | <span data-ttu-id="a7648-119">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a7648-119">✔️ 2.1</span></span>        | <span data-ttu-id="a7648-120">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-120">✔️ 3.1</span></span>        | <span data-ttu-id="a7648-121">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-121">✔️ 5.0</span></span> |
| <span data-ttu-id="a7648-122">✔️ [20,04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="a7648-122">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="a7648-123">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a7648-123">✔️ 2.1</span></span>        | <span data-ttu-id="a7648-124">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-124">✔️ 3.1</span></span>        | <span data-ttu-id="a7648-125">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-125">✔️ 5.0</span></span> |
| <span data-ttu-id="a7648-126">❌[19,10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="a7648-126">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="a7648-127">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a7648-127">✔️ 2.1</span></span>        | <span data-ttu-id="a7648-128">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-128">✔️ 3.1</span></span>        | <span data-ttu-id="a7648-129">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-129">✔️ 5.0</span></span> |
| <span data-ttu-id="a7648-130">❌[19,04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="a7648-130">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="a7648-131">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a7648-131">✔️ 2.1</span></span>        | <span data-ttu-id="a7648-132">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-132">✔️ 3.1</span></span>        | <span data-ttu-id="a7648-133">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-133">❌ 5.0</span></span> |
| <span data-ttu-id="a7648-134">❌[18,10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="a7648-134">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="a7648-135">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a7648-135">✔️ 2.1</span></span>        | <span data-ttu-id="a7648-136">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-136">❌ 3.1</span></span>        | <span data-ttu-id="a7648-137">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-137">❌ 5.0</span></span> |
| <span data-ttu-id="a7648-138">✔️ [18,04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="a7648-138">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="a7648-139">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a7648-139">✔️ 2.1</span></span>        | <span data-ttu-id="a7648-140">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-140">✔️ 3.1</span></span>        | <span data-ttu-id="a7648-141">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-141">✔️ 5.0</span></span> |
| <span data-ttu-id="a7648-142">❌[17,10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="a7648-142">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="a7648-143">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a7648-143">✔️ 2.1</span></span>        | <span data-ttu-id="a7648-144">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-144">❌ 3.1</span></span>        | <span data-ttu-id="a7648-145">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-145">❌ 5.0</span></span> |
| <span data-ttu-id="a7648-146">❌[17,04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="a7648-146">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="a7648-147">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a7648-147">✔️ 2.1</span></span>        | <span data-ttu-id="a7648-148">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-148">❌ 3.1</span></span>        | <span data-ttu-id="a7648-149">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-149">❌ 5.0</span></span> |
| <span data-ttu-id="a7648-150">❌[16,10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="a7648-150">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="a7648-151">❌ 2,1</span><span class="sxs-lookup"><span data-stu-id="a7648-151">❌ 2.1</span></span>        | <span data-ttu-id="a7648-152">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-152">❌ 3.1</span></span>        | <span data-ttu-id="a7648-153">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-153">❌ 5.0</span></span> |
| <span data-ttu-id="a7648-154">✔️ [16,04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="a7648-154">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="a7648-155">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a7648-155">✔️ 2.1</span></span>        | <span data-ttu-id="a7648-156">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a7648-156">✔️ 3.1</span></span>        | <span data-ttu-id="a7648-157">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="a7648-157">✔️ 5.0</span></span> |

<span data-ttu-id="a7648-158">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="a7648-158">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="a7648-159">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="a7648-159">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a7648-160">3.0</span><span class="sxs-lookup"><span data-stu-id="a7648-160">3.0</span></span>
- <span data-ttu-id="a7648-161">2.2</span><span class="sxs-lookup"><span data-stu-id="a7648-161">2.2</span></span>
- <span data-ttu-id="a7648-162">2,0</span><span class="sxs-lookup"><span data-stu-id="a7648-162">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a7648-163">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="a7648-163">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2010-"></a><span data-ttu-id="a7648-164">20,10 ✔️</span><span class="sxs-lookup"><span data-stu-id="a7648-164">20.10 ✔️</span></span>

<span data-ttu-id="a7648-165">W programie .NET 5 i źródłach danych pakietu .NET Core 3,1 dla Ubuntu 20,10 obecnie występuje problem.</span><span class="sxs-lookup"><span data-stu-id="a7648-165">.NET 5 and .NET Core 3.1 package feeds for Ubuntu 20.10 currently have an issue.</span></span> <span data-ttu-id="a7648-166">Aby uzyskać więcej informacji o tym problemie, zobacz sekcję dotyczącą usługi [GitHub wydaj/Core # 5549](https://github.com/dotnet/core/issues/5549).</span><span class="sxs-lookup"><span data-stu-id="a7648-166">For more information about the issue, see [GitHub issue dotnet/core#5549](https://github.com/dotnet/core/issues/5549).</span></span> <span data-ttu-id="a7648-167">Ten artykuł zostanie zaktualizowany po rozwiązaniu problemu.</span><span class="sxs-lookup"><span data-stu-id="a7648-167">This article will be updated when the issue is resolved.</span></span>

<span data-ttu-id="a7648-168">Aby zainstalować platformę .NET 5 lub .NET Core 3,1 w systemie Ubuntu 20,10, postępuj zgodnie z instrukcjami dotyczącymi [20,04](#2004-).</span><span class="sxs-lookup"><span data-stu-id="a7648-168">To install .NET 5 or .NET Core 3.1 on Ubuntu 20.10, follow the instructions for [20.04](#2004-).</span></span>

## <a name="2004-"></a><span data-ttu-id="a7648-169">20,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="a7648-169">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1910-"></a><span data-ttu-id="a7648-170">19,10 ❌</span><span class="sxs-lookup"><span data-stu-id="a7648-170">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="a7648-171">19,04 ❌</span><span class="sxs-lookup"><span data-stu-id="a7648-171">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="a7648-172">18,10 ❌</span><span class="sxs-lookup"><span data-stu-id="a7648-172">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="a7648-173">18,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="a7648-173">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1710-"></a><span data-ttu-id="a7648-174">17,10 ❌</span><span class="sxs-lookup"><span data-stu-id="a7648-174">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="a7648-175">17,04 ❌</span><span class="sxs-lookup"><span data-stu-id="a7648-175">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="a7648-176">16,10 ❌</span><span class="sxs-lookup"><span data-stu-id="a7648-176">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="a7648-177">16,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="a7648-177">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="a7648-178">APT Update — zestaw SDK lub środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="a7648-178">APT update SDK or runtime</span></span>

<span data-ttu-id="a7648-179">Gdy jest dostępna nowa wersja poprawek dla programu .NET, można po prostu uaktualnić ją za pomocą APT przy użyciu następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="a7648-179">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="a7648-180">Rozwiązywanie problemów z APT</span><span class="sxs-lookup"><span data-stu-id="a7648-180">APT troubleshooting</span></span>

<span data-ttu-id="a7648-181">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas korzystania z programu APT w celu zainstalowania platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="a7648-181">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="a7648-182">Nie można znaleźć pakietu</span><span class="sxs-lookup"><span data-stu-id="a7648-182">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="a7648-183">Nie można zlokalizować niektórych pakietów, których nie można \\ zainstalować</span><span class="sxs-lookup"><span data-stu-id="a7648-183">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="a7648-184">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="a7648-184">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="a7648-185">Przystawki</span><span class="sxs-lookup"><span data-stu-id="a7648-185">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="a7648-186">Zależności</span><span class="sxs-lookup"><span data-stu-id="a7648-186">Dependencies</span></span>

<span data-ttu-id="a7648-187">Po zainstalowaniu programu przy użyciu Menedżera pakietów te biblioteki są instalowane dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="a7648-187">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="a7648-188">Jeśli jednak ręcznie zainstalujesz program .NET lub opublikujesz aplikację, należy upewnić się, że te biblioteki są zainstalowane:</span><span class="sxs-lookup"><span data-stu-id="a7648-188">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="a7648-189">libc6</span><span class="sxs-lookup"><span data-stu-id="a7648-189">libc6</span></span>
- <span data-ttu-id="a7648-190">libgcc1</span><span class="sxs-lookup"><span data-stu-id="a7648-190">libgcc1</span></span>
- <span data-ttu-id="a7648-191">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="a7648-191">libgssapi-krb5-2</span></span>
- <span data-ttu-id="a7648-192">libicu52 (dla 14. x)</span><span class="sxs-lookup"><span data-stu-id="a7648-192">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="a7648-193">libicu55 (dla 16. x)</span><span class="sxs-lookup"><span data-stu-id="a7648-193">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="a7648-194">libicu60 (dla 18. x)</span><span class="sxs-lookup"><span data-stu-id="a7648-194">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="a7648-195">libicu66 (dla 20. x)</span><span class="sxs-lookup"><span data-stu-id="a7648-195">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="a7648-196">libssl 1.0.0 (dla 14. x, 16. x)</span><span class="sxs-lookup"><span data-stu-id="a7648-196">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="a7648-197">libssl 1.1 (dla 18. x, 20. x)</span><span class="sxs-lookup"><span data-stu-id="a7648-197">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="a7648-198">libstdc + + 6</span><span class="sxs-lookup"><span data-stu-id="a7648-198">libstdc++6</span></span>
- <span data-ttu-id="a7648-199">zlib1g</span><span class="sxs-lookup"><span data-stu-id="a7648-199">zlib1g</span></span>

<span data-ttu-id="a7648-200">W przypadku aplikacji .NET, które używają zestawu *System. Drawing. Common* , wymagana jest również następująca zależność:</span><span class="sxs-lookup"><span data-stu-id="a7648-200">For .NET apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="a7648-201">libgdiplus (wersja 6.0.1 lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="a7648-201">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="a7648-202">Aby zainstalować najnowszą wersję programu *libgdiplus* , można dodać do systemu repozytorium mono.</span><span class="sxs-lookup"><span data-stu-id="a7648-202">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="a7648-203">Aby uzyskać więcej informacji, zobacz <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="a7648-203">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="a7648-204">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="a7648-204">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="a7648-205">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="a7648-205">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="a7648-206">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="a7648-206">Next steps</span></span>

- [<span data-ttu-id="a7648-207">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a7648-207">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
