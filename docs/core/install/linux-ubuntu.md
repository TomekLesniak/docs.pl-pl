---
title: Instalowanie programu .NET Core w systemie Ubuntu — .NET Core
description: Ilustruje różne sposoby instalowania zestaw .NET Core SDK i środowiska uruchomieniowego .NET Core w systemie Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 5c07de20110a1aecf2ec5cb9de88f204625e548d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538462"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-ubuntu"></a><span data-ttu-id="5e867-103">Zainstaluj zestaw .NET Core SDK lub środowisko uruchomieniowe platformy .NET Core w systemie Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5e867-103">Install .NET Core SDK or .NET Core Runtime on Ubuntu</span></span>

<span data-ttu-id="5e867-104">Platforma .NET Core jest obsługiwana w systemie Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5e867-104">.NET Core is supported on Ubuntu.</span></span> <span data-ttu-id="5e867-105">W tym artykule opisano sposób instalowania programu .NET Core w systemie Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5e867-105">This article describes how to install .NET Core on Ubuntu.</span></span> <span data-ttu-id="5e867-106">Gdy wersja Ubuntu nie jest objęta wsparciem, platforma .NET Core nie jest już obsługiwana w tej wersji.</span><span class="sxs-lookup"><span data-stu-id="5e867-106">When an Ubuntu version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="5e867-107">Te instrukcje mogą jednak ułatwić uzyskanie programu .NET Core działającego w tych wersjach, chociaż nie jest to obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="5e867-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="5e867-108">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="5e867-108">Supported distributions</span></span>

<span data-ttu-id="5e867-109">Poniższa tabela zawiera listę obecnie obsługiwanych wersji programu .NET Core oraz wersji Ubuntu, na których są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="5e867-109">The following table is a list of currently supported .NET Core releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="5e867-110">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET Core osiągnie koniec okresu obsłudze](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Ubuntu osiągnie koniec cyklu życia](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="5e867-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="5e867-111">✔️ wskazuje, że wersja programu Ubuntu lub .NET Core jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="5e867-111">A ✔️ indicates that the version of Ubuntu or .NET Core is still supported.</span></span>
- <span data-ttu-id="5e867-112">❌Wskazuje, że wersja Ubuntu lub .NET Core nie jest obsługiwana w tej wersji Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5e867-112">A ❌ indicates that the version of Ubuntu or .NET Core isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="5e867-113">Gdy wersja Ubuntu i wersja platformy .NET Core mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="5e867-113">When both a version of Ubuntu and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="5e867-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5e867-114">Ubuntu</span></span>                   | <span data-ttu-id="5e867-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5e867-115">.NET Core 2.1</span></span> | <span data-ttu-id="5e867-116">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="5e867-116">.NET Core 3.1</span></span> | <span data-ttu-id="5e867-117">.NET 5 (wersja zapoznawcza) (tylko instalacja ręczna)</span><span class="sxs-lookup"><span data-stu-id="5e867-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="5e867-118">✔️ [20,04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="5e867-118">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="5e867-119">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5e867-119">✔️ 2.1</span></span>        | <span data-ttu-id="5e867-120">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5e867-120">✔️ 3.1</span></span>        | <span data-ttu-id="5e867-121">✔️ 5,0 — wersja zapoznawcza</span><span class="sxs-lookup"><span data-stu-id="5e867-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="5e867-122">❌[19,10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="5e867-122">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="5e867-123">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5e867-123">✔️ 2.1</span></span>        | <span data-ttu-id="5e867-124">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5e867-124">✔️ 3.1</span></span>        | <span data-ttu-id="5e867-125">✔️ 5,0 — wersja zapoznawcza</span><span class="sxs-lookup"><span data-stu-id="5e867-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="5e867-126">❌[19,04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="5e867-126">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="5e867-127">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5e867-127">✔️ 2.1</span></span>        | <span data-ttu-id="5e867-128">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5e867-128">✔️ 3.1</span></span>        | <span data-ttu-id="5e867-129">❌ wersja zapoznawcza 5,0</span><span class="sxs-lookup"><span data-stu-id="5e867-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5e867-130">❌[18,10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="5e867-130">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="5e867-131">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5e867-131">✔️ 2.1</span></span>        | <span data-ttu-id="5e867-132">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="5e867-132">❌ 3.1</span></span>        | <span data-ttu-id="5e867-133">❌ wersja zapoznawcza 5,0</span><span class="sxs-lookup"><span data-stu-id="5e867-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5e867-134">✔️ [18,04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="5e867-134">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="5e867-135">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5e867-135">✔️ 2.1</span></span>        | <span data-ttu-id="5e867-136">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5e867-136">✔️ 3.1</span></span>        | <span data-ttu-id="5e867-137">✔️ 5,0 — wersja zapoznawcza</span><span class="sxs-lookup"><span data-stu-id="5e867-137">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="5e867-138">❌[17,10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="5e867-138">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="5e867-139">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5e867-139">✔️ 2.1</span></span>        | <span data-ttu-id="5e867-140">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="5e867-140">❌ 3.1</span></span>        | <span data-ttu-id="5e867-141">❌ wersja zapoznawcza 5,0</span><span class="sxs-lookup"><span data-stu-id="5e867-141">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5e867-142">❌[17,04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="5e867-142">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="5e867-143">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5e867-143">✔️ 2.1</span></span>        | <span data-ttu-id="5e867-144">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="5e867-144">❌ 3.1</span></span>        | <span data-ttu-id="5e867-145">❌ wersja zapoznawcza 5,0</span><span class="sxs-lookup"><span data-stu-id="5e867-145">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5e867-146">❌[16,10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="5e867-146">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="5e867-147">❌ 2,1</span><span class="sxs-lookup"><span data-stu-id="5e867-147">❌ 2.1</span></span>        | <span data-ttu-id="5e867-148">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="5e867-148">❌ 3.1</span></span>        | <span data-ttu-id="5e867-149">❌ wersja zapoznawcza 5,0</span><span class="sxs-lookup"><span data-stu-id="5e867-149">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5e867-150">✔️ [16,04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="5e867-150">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="5e867-151">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="5e867-151">✔️ 2.1</span></span>        | <span data-ttu-id="5e867-152">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="5e867-152">✔️ 3.1</span></span>        | <span data-ttu-id="5e867-153">✔️ 5,0 — wersja zapoznawcza</span><span class="sxs-lookup"><span data-stu-id="5e867-153">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="5e867-154">Następujące wersje programu .NET Core nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="5e867-154">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="5e867-155">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="5e867-155">The downloads for these still remain published:</span></span>

- <span data-ttu-id="5e867-156">3,0</span><span class="sxs-lookup"><span data-stu-id="5e867-156">3.0</span></span>
- <span data-ttu-id="5e867-157">2.2</span><span class="sxs-lookup"><span data-stu-id="5e867-157">2.2</span></span>
- <span data-ttu-id="5e867-158">2,0</span><span class="sxs-lookup"><span data-stu-id="5e867-158">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5e867-159">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="5e867-159">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2004-"></a><span data-ttu-id="5e867-160">20,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5e867-160">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1910-"></a><span data-ttu-id="5e867-161">19,10 ❌</span><span class="sxs-lookup"><span data-stu-id="5e867-161">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="5e867-162">19,04 ❌</span><span class="sxs-lookup"><span data-stu-id="5e867-162">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="5e867-163">18,10 ❌</span><span class="sxs-lookup"><span data-stu-id="5e867-163">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="5e867-164">18,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5e867-164">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1710-"></a><span data-ttu-id="5e867-165">17,10 ❌</span><span class="sxs-lookup"><span data-stu-id="5e867-165">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="5e867-166">17,04 ❌</span><span class="sxs-lookup"><span data-stu-id="5e867-166">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="5e867-167">16,10 ❌</span><span class="sxs-lookup"><span data-stu-id="5e867-167">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="5e867-168">16,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5e867-168">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="5e867-169">APT Update — zestaw SDK lub środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="5e867-169">APT update SDK or runtime</span></span>

<span data-ttu-id="5e867-170">Gdy dostępna jest nowa wersja poprawek dla programu .NET Core, można po prostu uaktualnić ją za pomocą APT za pomocą następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="5e867-170">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="5e867-171">Rozwiązywanie problemów z APT</span><span class="sxs-lookup"><span data-stu-id="5e867-171">APT troubleshooting</span></span>

<span data-ttu-id="5e867-172">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas instalowania programu .NET Core przy użyciu programu APT.</span><span class="sxs-lookup"><span data-stu-id="5e867-172">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="5e867-173">Nie można znaleźć pakietu</span><span class="sxs-lookup"><span data-stu-id="5e867-173">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="5e867-174">Nie można zlokalizować niektórych pakietów, których nie można \\ zainstalować</span><span class="sxs-lookup"><span data-stu-id="5e867-174">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="5e867-175">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="5e867-175">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="5e867-176">Przystawki</span><span class="sxs-lookup"><span data-stu-id="5e867-176">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="5e867-177">Zależności</span><span class="sxs-lookup"><span data-stu-id="5e867-177">Dependencies</span></span>

<span data-ttu-id="5e867-178">Po zainstalowaniu programu przy użyciu Menedżera pakietów te biblioteki są instalowane dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="5e867-178">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="5e867-179">Jeśli jednak ręcznie zainstalujesz platformę .NET Core lub opublikujesz aplikację, musisz upewnić się, że te biblioteki są zainstalowane:</span><span class="sxs-lookup"><span data-stu-id="5e867-179">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="5e867-180">libc6</span><span class="sxs-lookup"><span data-stu-id="5e867-180">libc6</span></span>
- <span data-ttu-id="5e867-181">libgcc1</span><span class="sxs-lookup"><span data-stu-id="5e867-181">libgcc1</span></span>
- <span data-ttu-id="5e867-182">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="5e867-182">libgssapi-krb5-2</span></span>
- <span data-ttu-id="5e867-183">libicu52 (dla 14. x)</span><span class="sxs-lookup"><span data-stu-id="5e867-183">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="5e867-184">libicu55 (dla 16. x)</span><span class="sxs-lookup"><span data-stu-id="5e867-184">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="5e867-185">libicu60 (dla 18. x)</span><span class="sxs-lookup"><span data-stu-id="5e867-185">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="5e867-186">libicu66 (dla 20. x)</span><span class="sxs-lookup"><span data-stu-id="5e867-186">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="5e867-187">libssl 1.0.0 (dla 14. x, 16. x)</span><span class="sxs-lookup"><span data-stu-id="5e867-187">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="5e867-188">libssl 1.1 (dla 18. x, 20. x)</span><span class="sxs-lookup"><span data-stu-id="5e867-188">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="5e867-189">libstdc + + 6</span><span class="sxs-lookup"><span data-stu-id="5e867-189">libstdc++6</span></span>
- <span data-ttu-id="5e867-190">zlib1g</span><span class="sxs-lookup"><span data-stu-id="5e867-190">zlib1g</span></span>

<span data-ttu-id="5e867-191">W przypadku aplikacji .NET Core, które używają zestawu *System. Drawing. Common* , wymagana jest również następująca zależność:</span><span class="sxs-lookup"><span data-stu-id="5e867-191">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="5e867-192">libgdiplus (wersja 6.0.1 lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="5e867-192">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="5e867-193">Aby zainstalować najnowszą wersję programu *libgdiplus* , można dodać do systemu repozytorium mono.</span><span class="sxs-lookup"><span data-stu-id="5e867-193">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="5e867-194">Aby uzyskać więcej informacji, zobacz <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="5e867-194">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="5e867-195">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="5e867-195">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="5e867-196">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="5e867-196">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="5e867-197">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="5e867-197">Next steps</span></span>

- [<span data-ttu-id="5e867-198">Samouczek: Tworzenie aplikacji konsolowej z zestaw .NET Core SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5e867-198">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
