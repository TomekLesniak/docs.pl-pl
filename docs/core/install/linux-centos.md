---
title: Instalowanie platformy .NET w systemie CentOS — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie CentOS.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: b30aa206057107aa17fcd62e0f042f9fe3ad56dc
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031933"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-centos"></a><span data-ttu-id="0877d-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie CentOS</span><span class="sxs-lookup"><span data-stu-id="0877d-103">Install the .NET SDK or the .NET Runtime on CentOS</span></span>

<span data-ttu-id="0877d-104">Platforma .NET jest obsługiwana w systemie CentOS.</span><span class="sxs-lookup"><span data-stu-id="0877d-104">.NET is supported on CentOS.</span></span> <span data-ttu-id="0877d-105">W tym artykule opisano sposób instalowania programu .NET w systemie CentOS.</span><span class="sxs-lookup"><span data-stu-id="0877d-105">This article describes how to install .NET on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="0877d-106">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="0877d-106">Supported distributions</span></span>

<span data-ttu-id="0877d-107">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET w systemach CentOS 7 i CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="0877d-107">The following table is a list of currently supported .NET releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="0877d-108">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja CentOS nie jest już obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="0877d-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="0877d-109">✔️ wskazuje, że wersja programu CentOS lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="0877d-109">A ✔️ indicates that the version of CentOS or .NET is still supported.</span></span>
- <span data-ttu-id="0877d-110">❌Wskazuje, że wersja programu CentOS lub .NET nie jest obsługiwana w tej wersji CentOS.</span><span class="sxs-lookup"><span data-stu-id="0877d-110">A ❌ indicates that the version of CentOS or .NET isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="0877d-111">Gdy wersja programu CentOS i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="0877d-111">When both a version of CentOS and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="0877d-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="0877d-112">CentOS</span></span>                   | <span data-ttu-id="0877d-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0877d-113">.NET Core 2.1</span></span> | <span data-ttu-id="0877d-114">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="0877d-114">.NET Core 3.1</span></span> | <span data-ttu-id="0877d-115">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="0877d-115">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="0877d-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="0877d-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="0877d-117">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="0877d-117">✔️ 2.1</span></span>        | <span data-ttu-id="0877d-118">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="0877d-118">✔️ 3.1</span></span>        | <span data-ttu-id="0877d-119">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="0877d-119">✔️ 5.0</span></span> |
| <span data-ttu-id="0877d-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="0877d-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="0877d-121">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="0877d-121">✔️ 2.1</span></span>        | <span data-ttu-id="0877d-122">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="0877d-122">✔️ 3.1</span></span>        | <span data-ttu-id="0877d-123">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="0877d-123">✔️ 5.0</span></span> |

<span data-ttu-id="0877d-124">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="0877d-124">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="0877d-125">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="0877d-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="0877d-126">3.0</span><span class="sxs-lookup"><span data-stu-id="0877d-126">3.0</span></span>
- <span data-ttu-id="0877d-127">2.2</span><span class="sxs-lookup"><span data-stu-id="0877d-127">2.2</span></span>
- <span data-ttu-id="0877d-128">2,0</span><span class="sxs-lookup"><span data-stu-id="0877d-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="remove-preview-versions"></a><span data-ttu-id="0877d-129">Usuń wersje w wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="0877d-129">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="0877d-130">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="0877d-130">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a><span data-ttu-id="0877d-131">CentOS 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="0877d-131">CentOS 8 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="0877d-132">Program .NET 5,0 nie jest jeszcze dostępny w repozytoriach pakietów domyślnych, ale .NET Core 3,1 to.</span><span class="sxs-lookup"><span data-stu-id="0877d-132">.NET 5.0 isn't yet available in the default package repositories, but .NET Core 3.1 is.</span></span> <span data-ttu-id="0877d-133">Aby zainstalować program .NET Core 3,1, użyj `dnf install` polecenia z odpowiednim pakietem, takim jak `aspnetcore-runtime-3.1` lub `dotnet-sdk-3.1` .</span><span class="sxs-lookup"><span data-stu-id="0877d-133">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="0877d-134">Poniższe instrukcje dotyczą programu .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="0877d-134">The following instructions are for .NET 5.0.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/8/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="0877d-135">CentOS ✔️ 7</span><span class="sxs-lookup"><span data-stu-id="0877d-135">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-50](includes/linux-install-50-yum.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="0877d-136">Rozwiązywanie problemów z menedżerem pakietów</span><span class="sxs-lookup"><span data-stu-id="0877d-136">Troubleshoot the package manager</span></span>

<span data-ttu-id="0877d-137">Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas instalowania programu .NET przy użyciu Menedżera pakietów.</span><span class="sxs-lookup"><span data-stu-id="0877d-137">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="0877d-138">Nie można znaleźć pakietu</span><span class="sxs-lookup"><span data-stu-id="0877d-138">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="0877d-139">Nie można pobrać</span><span class="sxs-lookup"><span data-stu-id="0877d-139">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="0877d-140">Przystawki</span><span class="sxs-lookup"><span data-stu-id="0877d-140">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="0877d-141">Zależności</span><span class="sxs-lookup"><span data-stu-id="0877d-141">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="0877d-142">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="0877d-142">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="0877d-143">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="0877d-143">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="0877d-144">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="0877d-144">Next steps</span></span>

- [<span data-ttu-id="0877d-145">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0877d-145">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
