---
title: Instalowanie platformy .NET w systemie Fedora — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie Fedora.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 9e96773e30fb8ee395e37dca7a4794cd42359bb2
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594622"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a><span data-ttu-id="a9017-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie Fedora</span><span class="sxs-lookup"><span data-stu-id="a9017-103">Install the .NET SDK or the .NET Runtime on Fedora</span></span>

<span data-ttu-id="a9017-104">Platforma .NET jest obsługiwana w systemie Fedora.</span><span class="sxs-lookup"><span data-stu-id="a9017-104">.NET is supported on Fedora.</span></span> <span data-ttu-id="a9017-105">W tym artykule opisano sposób instalowania programu .NET w systemie Fedora.</span><span class="sxs-lookup"><span data-stu-id="a9017-105">This article describes how to install .NET on Fedora.</span></span> <span data-ttu-id="a9017-106">Gdy wersja Fedora nie jest obsługiwana, program .NET nie jest już obsługiwany w tej wersji.</span><span class="sxs-lookup"><span data-stu-id="a9017-106">When a Fedora version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="a9017-107">Jednak te instrukcje mogą pomóc w uzyskaniu środowiska .NET działającego w tych wersjach, nawet jeśli nie jest to obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="a9017-107">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="a9017-108">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="a9017-108">Supported distributions</span></span>

<span data-ttu-id="a9017-109">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Fedora, w których są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="a9017-109">The following table is a list of currently supported .NET releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="a9017-110">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca wsparcia](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Fedora osiągnie koniec cyklu życia](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="a9017-110">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="a9017-111">✔️ wskazuje, że wersja programu Fedora lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="a9017-111">A ✔️ indicates that the version of Fedora or .NET is still supported.</span></span>
- <span data-ttu-id="a9017-112">❌Wskazuje, że wersja programu Fedora lub .NET nie jest obsługiwana w tej wersji Fedora.</span><span class="sxs-lookup"><span data-stu-id="a9017-112">A ❌ indicates that the version of Fedora or .NET isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="a9017-113">Gdy wersja programu Fedora i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="a9017-113">When both a version of Fedora and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="a9017-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="a9017-114">Fedora</span></span>               | <span data-ttu-id="a9017-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a9017-115">.NET Core 2.1</span></span> | <span data-ttu-id="a9017-116">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="a9017-116">.NET Core 3.1</span></span> | <span data-ttu-id="a9017-117">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="a9017-117">.NET 5.0</span></span> |
|----------------------|---------------|---------------|----------|
| <span data-ttu-id="a9017-118">✔️ [33](#fedora-33-)</span><span class="sxs-lookup"><span data-stu-id="a9017-118">✔️ [33](#fedora-33-)</span></span> | <span data-ttu-id="a9017-119">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a9017-119">✔️ 2.1</span></span>        | <span data-ttu-id="a9017-120">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a9017-120">✔️ 3.1</span></span>        | <span data-ttu-id="a9017-121">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="a9017-121">✔️ 5.0</span></span> |
| <span data-ttu-id="a9017-122">✔️ [32](#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="a9017-122">✔️ [32](#fedora-32-)</span></span> | <span data-ttu-id="a9017-123">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a9017-123">✔️ 2.1</span></span>        | <span data-ttu-id="a9017-124">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a9017-124">✔️ 3.1</span></span>        | <span data-ttu-id="a9017-125">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="a9017-125">✔️ 5.0</span></span> |
| <span data-ttu-id="a9017-126">❌[31](#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="a9017-126">❌ [31](#fedora-31-)</span></span> | <span data-ttu-id="a9017-127">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a9017-127">✔️ 2.1</span></span>        | <span data-ttu-id="a9017-128">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a9017-128">✔️ 3.1</span></span>        | <span data-ttu-id="a9017-129">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a9017-129">❌ 5.0</span></span> |
| <span data-ttu-id="a9017-130">❌ [30](#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="a9017-130">❌ [30](#fedora-30-)</span></span> | <span data-ttu-id="a9017-131">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a9017-131">✔️ 2.1</span></span>        | <span data-ttu-id="a9017-132">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a9017-132">✔️ 3.1</span></span>        | <span data-ttu-id="a9017-133">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a9017-133">❌ 5.0</span></span> |
| <span data-ttu-id="a9017-134">❌[29](#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="a9017-134">❌ [29](#fedora-29-)</span></span> | <span data-ttu-id="a9017-135">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a9017-135">✔️ 2.1</span></span>        | <span data-ttu-id="a9017-136">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a9017-136">✔️ 3.1</span></span>        | <span data-ttu-id="a9017-137">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a9017-137">❌ 5.0</span></span> |
| <span data-ttu-id="a9017-138">❌[28](#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="a9017-138">❌ [28](#fedora-28-)</span></span> | <span data-ttu-id="a9017-139">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a9017-139">✔️ 2.1</span></span>        | <span data-ttu-id="a9017-140">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="a9017-140">❌ 3.1</span></span>        | <span data-ttu-id="a9017-141">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a9017-141">❌ 5.0</span></span> |
| <span data-ttu-id="a9017-142">❌[27](#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="a9017-142">❌ [27](#fedora-27-)</span></span> | <span data-ttu-id="a9017-143">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a9017-143">✔️ 2.1</span></span>        | <span data-ttu-id="a9017-144">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="a9017-144">❌ 3.1</span></span>        | <span data-ttu-id="a9017-145">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a9017-145">❌ 5.0</span></span> |

<span data-ttu-id="a9017-146">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="a9017-146">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="a9017-147">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="a9017-147">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a9017-148">3.0</span><span class="sxs-lookup"><span data-stu-id="a9017-148">3.0</span></span>
- <span data-ttu-id="a9017-149">2.2</span><span class="sxs-lookup"><span data-stu-id="a9017-149">2.2</span></span>
- <span data-ttu-id="a9017-150">2,0</span><span class="sxs-lookup"><span data-stu-id="a9017-150">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a9017-151">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="a9017-151">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-33-"></a><span data-ttu-id="a9017-152">Fedora 33 ✔️</span><span class="sxs-lookup"><span data-stu-id="a9017-152">Fedora 33 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="a9017-153">Program .NET Core 3,1 jest dostępny w repozytoriach pakietów domyślnych dla Fedora 33.</span><span class="sxs-lookup"><span data-stu-id="a9017-153">.NET Core 3.1 is available in the default package repositories for Fedora 33.</span></span> <span data-ttu-id="a9017-154">Aby zainstalować program .NET Core 3,1, użyj `dnf install` polecenia z odpowiednim pakietem, takim jak `aspnetcore-runtime-3.1` lub `dotnet-sdk-3.1` .</span><span class="sxs-lookup"><span data-stu-id="a9017-154">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="a9017-155">Program .NET 5,0 nie jest jeszcze dostępny w repozytoriach pakietów domyślnych.</span><span class="sxs-lookup"><span data-stu-id="a9017-155">.NET 5.0 isn't yet available in the default package repositories.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/33/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="fedora-32-"></a><span data-ttu-id="a9017-156">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="a9017-156">Fedora 32 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="a9017-157">Program .NET Core 3,1 jest dostępny w repozytoriach pakietów domyślnych dla Fedora 32.</span><span class="sxs-lookup"><span data-stu-id="a9017-157">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span> <span data-ttu-id="a9017-158">Aby zainstalować program .NET Core 3,1, użyj `dnf install` polecenia z odpowiednim pakietem, takim jak `aspnetcore-runtime-3.1` lub `dotnet-sdk-3.1` .</span><span class="sxs-lookup"><span data-stu-id="a9017-158">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="a9017-159">Program .NET 5,0 nie jest jeszcze dostępny w repozytoriach pakietów domyślnych.</span><span class="sxs-lookup"><span data-stu-id="a9017-159">.NET 5.0 isn't yet available in the default package repositories.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/32/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="a9017-160">Fedora 31 ❌</span><span class="sxs-lookup"><span data-stu-id="a9017-160">Fedora 31 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="a9017-161">Fedora 30 ❌</span><span class="sxs-lookup"><span data-stu-id="a9017-161">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="a9017-162">Fedora 29 ❌</span><span class="sxs-lookup"><span data-stu-id="a9017-162">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="a9017-163">Fedora 28 ❌</span><span class="sxs-lookup"><span data-stu-id="a9017-163">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="a9017-164">Fedora 27 ❌</span><span class="sxs-lookup"><span data-stu-id="a9017-164">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="a9017-165">Rozwiązywanie problemów z menedżerem pakietów</span><span class="sxs-lookup"><span data-stu-id="a9017-165">Troubleshoot the package manager</span></span>

<span data-ttu-id="a9017-166">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas korzystania z Menedżera pakietów w celu zainstalowania platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a9017-166">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="a9017-167">Nie można znaleźć pakietu</span><span class="sxs-lookup"><span data-stu-id="a9017-167">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="a9017-168">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="a9017-168">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="a9017-169">Przystawki</span><span class="sxs-lookup"><span data-stu-id="a9017-169">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="a9017-170">Zależności</span><span class="sxs-lookup"><span data-stu-id="a9017-170">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="a9017-171">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="a9017-171">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="a9017-172">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="a9017-172">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="a9017-173">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="a9017-173">Next steps</span></span>

- [<span data-ttu-id="a9017-174">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a9017-174">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
