---
title: Instalowanie platformy .NET w systemie Fedora — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie Fedora.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: d5b5886f8b29e0f8e935850686cc84f78c55be02
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507083"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a><span data-ttu-id="99f7e-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie Fedora</span><span class="sxs-lookup"><span data-stu-id="99f7e-103">Install the .NET SDK or the .NET Runtime on Fedora</span></span>

<span data-ttu-id="99f7e-104">Platforma .NET jest obsługiwana w systemie Fedora.</span><span class="sxs-lookup"><span data-stu-id="99f7e-104">.NET is supported on Fedora.</span></span> <span data-ttu-id="99f7e-105">W tym artykule opisano sposób instalowania programu .NET w systemie Fedora.</span><span class="sxs-lookup"><span data-stu-id="99f7e-105">This article describes how to install .NET on Fedora.</span></span> <span data-ttu-id="99f7e-106">Gdy wersja Fedora nie jest obsługiwana, program .NET nie jest już obsługiwany w tej wersji.</span><span class="sxs-lookup"><span data-stu-id="99f7e-106">When a Fedora version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="99f7e-107">Jednak te instrukcje mogą pomóc w uzyskaniu środowiska .NET działającego w tych wersjach, nawet jeśli nie jest to obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="99f7e-107">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="99f7e-108">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="99f7e-108">Supported distributions</span></span>

<span data-ttu-id="99f7e-109">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Fedora, w których są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="99f7e-109">The following table is a list of currently supported .NET releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="99f7e-110">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca wsparcia](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Fedora osiągnie koniec cyklu życia](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="99f7e-110">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="99f7e-111">✔️ wskazuje, że wersja programu Fedora lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="99f7e-111">A ✔️ indicates that the version of Fedora or .NET is still supported.</span></span>
- <span data-ttu-id="99f7e-112">❌Wskazuje, że wersja programu Fedora lub .NET nie jest obsługiwana w tej wersji Fedora.</span><span class="sxs-lookup"><span data-stu-id="99f7e-112">A ❌ indicates that the version of Fedora or .NET isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="99f7e-113">Gdy wersja programu Fedora i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="99f7e-113">When both a version of Fedora and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="99f7e-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="99f7e-114">Fedora</span></span>               | <span data-ttu-id="99f7e-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="99f7e-115">.NET Core 2.1</span></span> | <span data-ttu-id="99f7e-116">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-116">.NET Core 3.1</span></span> | <span data-ttu-id="99f7e-117">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="99f7e-117">.NET 5.0</span></span> |
|----------------------|---------------|---------------|----------|
| <span data-ttu-id="99f7e-118">✔️ [33](#fedora-33-)</span><span class="sxs-lookup"><span data-stu-id="99f7e-118">✔️ [33](#fedora-33-)</span></span> | <span data-ttu-id="99f7e-119">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-119">✔️ 2.1</span></span>        | <span data-ttu-id="99f7e-120">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-120">✔️ 3.1</span></span>        | <span data-ttu-id="99f7e-121">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="99f7e-121">✔️ 5.0</span></span> |
| <span data-ttu-id="99f7e-122">✔️ [32](#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="99f7e-122">✔️ [32](#fedora-32-)</span></span> | <span data-ttu-id="99f7e-123">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-123">✔️ 2.1</span></span>        | <span data-ttu-id="99f7e-124">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-124">✔️ 3.1</span></span>        | <span data-ttu-id="99f7e-125">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="99f7e-125">✔️ 5.0</span></span> |
| <span data-ttu-id="99f7e-126">❌[31](#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="99f7e-126">❌ [31](#fedora-31-)</span></span> | <span data-ttu-id="99f7e-127">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-127">✔️ 2.1</span></span>        | <span data-ttu-id="99f7e-128">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-128">✔️ 3.1</span></span>        | <span data-ttu-id="99f7e-129">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="99f7e-129">❌ 5.0</span></span> |
| <span data-ttu-id="99f7e-130">❌ [30](#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="99f7e-130">❌ [30](#fedora-30-)</span></span> | <span data-ttu-id="99f7e-131">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-131">✔️ 2.1</span></span>        | <span data-ttu-id="99f7e-132">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-132">✔️ 3.1</span></span>        | <span data-ttu-id="99f7e-133">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="99f7e-133">❌ 5.0</span></span> |
| <span data-ttu-id="99f7e-134">❌[29](#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="99f7e-134">❌ [29](#fedora-29-)</span></span> | <span data-ttu-id="99f7e-135">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-135">✔️ 2.1</span></span>        | <span data-ttu-id="99f7e-136">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-136">✔️ 3.1</span></span>        | <span data-ttu-id="99f7e-137">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="99f7e-137">❌ 5.0</span></span> |
| <span data-ttu-id="99f7e-138">❌[28](#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="99f7e-138">❌ [28](#fedora-28-)</span></span> | <span data-ttu-id="99f7e-139">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-139">✔️ 2.1</span></span>        | <span data-ttu-id="99f7e-140">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-140">❌ 3.1</span></span>        | <span data-ttu-id="99f7e-141">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="99f7e-141">❌ 5.0</span></span> |
| <span data-ttu-id="99f7e-142">❌[27](#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="99f7e-142">❌ [27](#fedora-27-)</span></span> | <span data-ttu-id="99f7e-143">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-143">✔️ 2.1</span></span>        | <span data-ttu-id="99f7e-144">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="99f7e-144">❌ 3.1</span></span>        | <span data-ttu-id="99f7e-145">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="99f7e-145">❌ 5.0</span></span> |

<span data-ttu-id="99f7e-146">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="99f7e-146">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="99f7e-147">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="99f7e-147">The downloads for these still remain published:</span></span>

- <span data-ttu-id="99f7e-148">3.0</span><span class="sxs-lookup"><span data-stu-id="99f7e-148">3.0</span></span>
- <span data-ttu-id="99f7e-149">2.2</span><span class="sxs-lookup"><span data-stu-id="99f7e-149">2.2</span></span>
- <span data-ttu-id="99f7e-150">2,0</span><span class="sxs-lookup"><span data-stu-id="99f7e-150">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="99f7e-151">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="99f7e-151">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-33-"></a><span data-ttu-id="99f7e-152">Fedora 33 ✔️</span><span class="sxs-lookup"><span data-stu-id="99f7e-152">Fedora 33 ✔️</span></span>

<span data-ttu-id="99f7e-153">.NET 5 i .NET Core 3,1 są dostępne w domyślnych repozytoriach pakietów dla Fedora 33.</span><span class="sxs-lookup"><span data-stu-id="99f7e-153">.NET 5 and .NET Core 3.1 are available in the default package repositories for Fedora 33.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-50-dnf.md)]

## <a name="fedora-32-"></a><span data-ttu-id="99f7e-154">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="99f7e-154">Fedora 32 ✔️</span></span>

<span data-ttu-id="99f7e-155">Program .NET Core 3,1 jest dostępny w repozytoriach pakietów domyślnych dla Fedora 32.</span><span class="sxs-lookup"><span data-stu-id="99f7e-155">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="99f7e-156">Fedora 31 ❌</span><span class="sxs-lookup"><span data-stu-id="99f7e-156">Fedora 31 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="99f7e-157">Fedora 30 ❌</span><span class="sxs-lookup"><span data-stu-id="99f7e-157">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="99f7e-158">Fedora 29 ❌</span><span class="sxs-lookup"><span data-stu-id="99f7e-158">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="99f7e-159">Fedora 28 ❌</span><span class="sxs-lookup"><span data-stu-id="99f7e-159">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="99f7e-160">Fedora 27 ❌</span><span class="sxs-lookup"><span data-stu-id="99f7e-160">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="99f7e-161">Rozwiązywanie problemów z menedżerem pakietów</span><span class="sxs-lookup"><span data-stu-id="99f7e-161">Troubleshoot the package manager</span></span>

<span data-ttu-id="99f7e-162">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas korzystania z Menedżera pakietów w celu zainstalowania platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="99f7e-162">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="99f7e-163">Nie można znaleźć pakietu</span><span class="sxs-lookup"><span data-stu-id="99f7e-163">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="99f7e-164">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="99f7e-164">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="99f7e-165">Przystawki</span><span class="sxs-lookup"><span data-stu-id="99f7e-165">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="99f7e-166">Zależności</span><span class="sxs-lookup"><span data-stu-id="99f7e-166">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="99f7e-167">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="99f7e-167">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="99f7e-168">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="99f7e-168">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="99f7e-169">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="99f7e-169">Next steps</span></span>

- [<span data-ttu-id="99f7e-170">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="99f7e-170">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
