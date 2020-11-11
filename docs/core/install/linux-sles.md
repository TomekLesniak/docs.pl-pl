---
title: Instalowanie platformy .NET w systemie SLES — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie SLES.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 558574116aac2a3c755481069641e81a435a2a43
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506888"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-sles"></a><span data-ttu-id="d5e0d-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie SLES</span><span class="sxs-lookup"><span data-stu-id="d5e0d-103">Install the .NET SDK or the .NET Runtime on SLES</span></span>

<span data-ttu-id="d5e0d-104">Platforma .NET jest obsługiwana w systemie SLES.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-104">.NET is supported on SLES.</span></span> <span data-ttu-id="d5e0d-105">W tym artykule opisano sposób instalowania programu .NET w systemie SLES.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-105">This article describes how to install .NET on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="d5e0d-106">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="d5e0d-106">Supported distributions</span></span>

<span data-ttu-id="d5e0d-107">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET na platformie SLES 12 z dodatkiem SP2 i SLES 15.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-107">The following table is a list of currently supported .NET releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="d5e0d-108">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja SLES nie jest już obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="d5e0d-109">✔️ wskazuje, że wersja programu SLES lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-109">A ✔️ indicates that the version of SLES or .NET is still supported.</span></span>
- <span data-ttu-id="d5e0d-110">❌Wskazuje, że wersja programu SLES lub .NET nie jest obsługiwana w tej wersji SLES.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-110">A ❌ indicates that the version of SLES or .NET isn't supported on that SLES release.</span></span>
- <span data-ttu-id="d5e0d-111">Gdy wersja programu SLES i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-111">When both a version of SLES and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="d5e0d-112">SLES</span><span class="sxs-lookup"><span data-stu-id="d5e0d-112">SLES</span></span>                   | <span data-ttu-id="d5e0d-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d5e0d-113">.NET Core 2.1</span></span> | <span data-ttu-id="d5e0d-114">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="d5e0d-114">.NET Core 3.1</span></span> | <span data-ttu-id="d5e0d-115">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="d5e0d-115">.NET 5.0</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="d5e0d-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="d5e0d-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="d5e0d-117">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="d5e0d-117">✔️ 2.1</span></span>        | <span data-ttu-id="d5e0d-118">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="d5e0d-118">✔️ 3.1</span></span>        | <span data-ttu-id="d5e0d-119">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="d5e0d-119">✔️ 5.0</span></span> |
| <span data-ttu-id="d5e0d-120">✔️ [12 z dodatkiem SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="d5e0d-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="d5e0d-121">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="d5e0d-121">✔️ 2.1</span></span>        | <span data-ttu-id="d5e0d-122">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="d5e0d-122">✔️ 3.1</span></span>        | <span data-ttu-id="d5e0d-123">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="d5e0d-123">✔️ 5.0</span></span> |

<span data-ttu-id="d5e0d-124">Następujące wersje programu .NET Core nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="d5e0d-125">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="d5e0d-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="d5e0d-126">3.0</span><span class="sxs-lookup"><span data-stu-id="d5e0d-126">3.0</span></span>
- <span data-ttu-id="d5e0d-127">2.2</span><span class="sxs-lookup"><span data-stu-id="d5e0d-127">2.2</span></span>
- <span data-ttu-id="d5e0d-128">2,0</span><span class="sxs-lookup"><span data-stu-id="d5e0d-128">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="d5e0d-129">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="d5e0d-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a><span data-ttu-id="d5e0d-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="d5e0d-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="d5e0d-131">Obecnie pakiet instalacyjny usługi Microsoft Repository SLES 15 instaluje plik *Microsoft-prod.* Repository w niewłaściwym katalogu, uniemożliwiając użyciu narzędzia zypper wyszukiwanie pakietów .NET.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET packages.</span></span> <span data-ttu-id="d5e0d-132">Aby rozwiązać ten problem, Utwórz link symboliczny w poprawnym katalogu.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="d5e0d-133">SLES 12 ✔️</span><span class="sxs-lookup"><span data-stu-id="d5e0d-133">SLES 12 ✔️</span></span>

<span data-ttu-id="d5e0d-134">Platforma .NET wymaga programu SP2 jako minimum dla rodziny SLES 12.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-134">.NET requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="d5e0d-135">Rozwiązywanie problemów z menedżerem pakietów</span><span class="sxs-lookup"><span data-stu-id="d5e0d-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="d5e0d-136">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas instalowania programu .NET przy użyciu Menedżera pakietów.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-136">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="d5e0d-137">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="d5e0d-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="d5e0d-138">Zależności</span><span class="sxs-lookup"><span data-stu-id="d5e0d-138">Dependencies</span></span>

<span data-ttu-id="d5e0d-139">Po zainstalowaniu programu przy użyciu Menedżera pakietów te biblioteki są instalowane dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-139">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="d5e0d-140">Jeśli jednak ręcznie zainstalujesz program .NET lub opublikujesz aplikację, należy upewnić się, że te biblioteki są zainstalowane:</span><span class="sxs-lookup"><span data-stu-id="d5e0d-140">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="d5e0d-141">krb5</span><span class="sxs-lookup"><span data-stu-id="d5e0d-141">krb5</span></span>
- <span data-ttu-id="d5e0d-142">libicu</span><span class="sxs-lookup"><span data-stu-id="d5e0d-142">libicu</span></span>
- <span data-ttu-id="d5e0d-143">libopenssl1_1</span><span class="sxs-lookup"><span data-stu-id="d5e0d-143">libopenssl1_1</span></span>

<span data-ttu-id="d5e0d-144">Jeśli docelowa wersja OpenSSL środowiska uruchomieniowego to 1,1 lub nowsza, należy zainstalować polecenie **COMPAT-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-144">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="d5e0d-145">Aby uzyskać więcej informacji o zależnościach, zobacz [samodzielne aplikacje systemu Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="d5e0d-145">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="d5e0d-146">W przypadku aplikacji .NET, które używają zestawu *System. Drawing. Common* , wymagana jest również następująca zależność:</span><span class="sxs-lookup"><span data-stu-id="d5e0d-146">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="d5e0d-147">libgdiplus (wersja 6.0.1 lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="d5e0d-147">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="d5e0d-148">Aby zainstalować najnowszą wersję programu *libgdiplus* , można dodać do systemu repozytorium mono.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-148">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="d5e0d-149">Aby uzyskać więcej informacji, zobacz <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="d5e0d-149">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="d5e0d-150">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="d5e0d-150">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="d5e0d-151">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="d5e0d-151">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="d5e0d-152">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="d5e0d-152">Next steps</span></span>

- [<span data-ttu-id="d5e0d-153">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d5e0d-153">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
