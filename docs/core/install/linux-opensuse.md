---
title: Instalowanie platformy .NET w systemie openSUSE — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie openSUSE.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: eb31e3109ccd40999c22a27607d48544bf117dc2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031868"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-opensuse"></a><span data-ttu-id="b85e1-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie openSUSE</span><span class="sxs-lookup"><span data-stu-id="b85e1-103">Install the .NET SDK or the .NET Runtime on openSUSE</span></span>

<span data-ttu-id="b85e1-104">Platforma .NET jest obsługiwana w systemie openSUSE.</span><span class="sxs-lookup"><span data-stu-id="b85e1-104">.NET is supported on openSUSE.</span></span> <span data-ttu-id="b85e1-105">W tym artykule opisano sposób instalowania programu .NET w systemie openSUSE.</span><span class="sxs-lookup"><span data-stu-id="b85e1-105">This article describes how to install .NET on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="b85e1-106">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="b85e1-106">Supported distributions</span></span>

<span data-ttu-id="b85e1-107">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET w systemie openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="b85e1-107">The following table is a list of currently supported .NET releases on openSUSE 15.</span></span> <span data-ttu-id="b85e1-108">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja openSUSE nie jest już obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="b85e1-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="b85e1-109">✔️ wskazuje, że wersja programu openSUSE lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="b85e1-109">A ✔️ indicates that the version of openSUSE or .NET is still supported.</span></span>
- <span data-ttu-id="b85e1-110">❌Wskazuje, że wersja programu openSUSE lub .NET nie jest obsługiwana w tej wersji openSUSE.</span><span class="sxs-lookup"><span data-stu-id="b85e1-110">A ❌ indicates that the version of openSUSE or .NET isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="b85e1-111">Gdy wersja programu openSUSE i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="b85e1-111">When both a version of openSUSE and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="b85e1-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="b85e1-112">openSUSE</span></span>                   | <span data-ttu-id="b85e1-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b85e1-113">.NET Core 2.1</span></span> | <span data-ttu-id="b85e1-114">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="b85e1-114">.NET Core 3.1</span></span> | <span data-ttu-id="b85e1-115">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="b85e1-115">.NET 5.0</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="b85e1-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="b85e1-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="b85e1-117">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="b85e1-117">✔️ 2.1</span></span>        | <span data-ttu-id="b85e1-118">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="b85e1-118">✔️ 3.1</span></span>        | <span data-ttu-id="b85e1-119">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="b85e1-119">✔️ 5.0</span></span> |

<span data-ttu-id="b85e1-120">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="b85e1-120">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="b85e1-121">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="b85e1-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="b85e1-122">3.0</span><span class="sxs-lookup"><span data-stu-id="b85e1-122">3.0</span></span>
- <span data-ttu-id="b85e1-123">2.2</span><span class="sxs-lookup"><span data-stu-id="b85e1-123">2.2</span></span>
- <span data-ttu-id="b85e1-124">2,0</span><span class="sxs-lookup"><span data-stu-id="b85e1-124">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="b85e1-125">Usuń wersje w wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="b85e1-125">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b85e1-126">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="b85e1-126">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="b85e1-127">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="b85e1-127">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="b85e1-128">Rozwiązywanie problemów z menedżerem pakietów</span><span class="sxs-lookup"><span data-stu-id="b85e1-128">Troubleshoot the package manager</span></span>

<span data-ttu-id="b85e1-129">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas instalowania programu .NET przy użyciu Menedżera pakietów.</span><span class="sxs-lookup"><span data-stu-id="b85e1-129">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="b85e1-130">Nie można znaleźć pakietu</span><span class="sxs-lookup"><span data-stu-id="b85e1-130">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="b85e1-131">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="b85e1-131">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="b85e1-132">Przystawki</span><span class="sxs-lookup"><span data-stu-id="b85e1-132">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="b85e1-133">Zależności</span><span class="sxs-lookup"><span data-stu-id="b85e1-133">Dependencies</span></span>

<span data-ttu-id="b85e1-134">Po zainstalowaniu programu przy użyciu Menedżera pakietów te biblioteki są instalowane dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="b85e1-134">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="b85e1-135">Jeśli jednak ręcznie zainstalujesz program .NET lub opublikujesz aplikację, należy upewnić się, że te biblioteki są zainstalowane:</span><span class="sxs-lookup"><span data-stu-id="b85e1-135">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="b85e1-136">krb5</span><span class="sxs-lookup"><span data-stu-id="b85e1-136">krb5</span></span>
- <span data-ttu-id="b85e1-137">libicu</span><span class="sxs-lookup"><span data-stu-id="b85e1-137">libicu</span></span>
- <span data-ttu-id="b85e1-138">libopenssl1_0_0</span><span class="sxs-lookup"><span data-stu-id="b85e1-138">libopenssl1_0_0</span></span>

<span data-ttu-id="b85e1-139">Jeśli docelowa wersja OpenSSL środowiska uruchomieniowego to 1,1 lub nowsza, należy zainstalować polecenie **COMPAT-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="b85e1-139">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="b85e1-140">Aby uzyskać więcej informacji o zależnościach, zobacz [samodzielne aplikacje systemu Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="b85e1-140">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="b85e1-141">W przypadku aplikacji .NET, które używają zestawu *System. Drawing. Common* , wymagana jest również następująca zależność:</span><span class="sxs-lookup"><span data-stu-id="b85e1-141">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="b85e1-142">libgdiplus (wersja 6.0.1 lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="b85e1-142">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="b85e1-143">Aby zainstalować najnowszą wersję programu *libgdiplus* , można dodać do systemu repozytorium mono.</span><span class="sxs-lookup"><span data-stu-id="b85e1-143">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="b85e1-144">Aby uzyskać więcej informacji, zobacz <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="b85e1-144">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="b85e1-145">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="b85e1-145">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="b85e1-146">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="b85e1-146">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="b85e1-147">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="b85e1-147">Next steps</span></span>

- [<span data-ttu-id="b85e1-148">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b85e1-148">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
