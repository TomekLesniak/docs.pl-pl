---
title: Instalowanie platformy .NET na platformie Alpine-.NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET na platformie Alpine.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 29901cc24ddd4bbe8200a36765ddd29f501394c0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506836"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a><span data-ttu-id="aba23-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET na platformie Alpine</span><span class="sxs-lookup"><span data-stu-id="aba23-103">Install the .NET SDK or the .NET Runtime on Alpine</span></span>

<span data-ttu-id="aba23-104">W tym artykule opisano sposób instalowania programu .NET w ramach platformy Alpine.</span><span class="sxs-lookup"><span data-stu-id="aba23-104">This article describes how to install .NET on Alpine.</span></span> <span data-ttu-id="aba23-105">Gdy wersja Alpine nie jest objęta wsparciem, platforma .NET nie jest już obsługiwana w tej wersji.</span><span class="sxs-lookup"><span data-stu-id="aba23-105">When an Alpine version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="aba23-106">Jednak te instrukcje mogą pomóc w uzyskaniu środowiska .NET działającego w tych wersjach, nawet jeśli nie jest to obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="aba23-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="aba23-107">Brak instalatorów dla Alpine.</span><span class="sxs-lookup"><span data-stu-id="aba23-107">There are no installers for Alpine.</span></span> <span data-ttu-id="aba23-108">Musisz użyć [skryptu instalacji](#scripted-install) lub instrukcji [instalacji ręcznej](#manual-install) .</span><span class="sxs-lookup"><span data-stu-id="aba23-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="aba23-109">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="aba23-109">Supported distributions</span></span>

<span data-ttu-id="aba23-110">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Alpine, w których są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="aba23-110">The following table is a list of currently supported .NET releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="aba23-111">Te wersje pozostają obsługiwane do momentu, aż wersja [platformy .NET osiągnie koniec okresu obsłudze](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Alp osiągnie koniec cyklu życia](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span><span class="sxs-lookup"><span data-stu-id="aba23-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="aba23-112">✔️ wskazuje, że wersja Alpine lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="aba23-112">A ✔️ indicates that the version of Alpine or .NET is still supported.</span></span>
- <span data-ttu-id="aba23-113">❌Wskazuje, że wersja Alpine lub .NET nie jest obsługiwana w tej wersji Alpine.</span><span class="sxs-lookup"><span data-stu-id="aba23-113">A ❌ indicates that the version of Alpine or .NET isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="aba23-114">Gdy zarówno wersja Alpine, jak i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="aba23-114">When both a version of Alpine and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="aba23-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="aba23-115">Alpine</span></span>  | <span data-ttu-id="aba23-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="aba23-116">.NET Core 2.1</span></span> | <span data-ttu-id="aba23-117">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="aba23-117">.NET Core 3.1</span></span> | <span data-ttu-id="aba23-118">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="aba23-118">.NET 5.0</span></span> |
|-------- |---------------|---------------|----------------|
| <span data-ttu-id="aba23-119">✔️ 3,12</span><span class="sxs-lookup"><span data-stu-id="aba23-119">✔️ 3.12</span></span> | <span data-ttu-id="aba23-120">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="aba23-120">✔️ 2.1</span></span>        | <span data-ttu-id="aba23-121">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="aba23-121">✔️ 3.1</span></span>        | <span data-ttu-id="aba23-122">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="aba23-122">✔️ 5.0</span></span> |
| <span data-ttu-id="aba23-123">✔️ 3,11</span><span class="sxs-lookup"><span data-stu-id="aba23-123">✔️ 3.11</span></span> | <span data-ttu-id="aba23-124">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="aba23-124">✔️ 2.1</span></span>        | <span data-ttu-id="aba23-125">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="aba23-125">✔️ 3.1</span></span>        | <span data-ttu-id="aba23-126">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="aba23-126">✔️ 5.0</span></span> |
| <span data-ttu-id="aba23-127">✔️ 3,10</span><span class="sxs-lookup"><span data-stu-id="aba23-127">✔️ 3.10</span></span> | <span data-ttu-id="aba23-128">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="aba23-128">✔️ 2.1</span></span>        | <span data-ttu-id="aba23-129">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="aba23-129">✔️ 3.1</span></span>        | <span data-ttu-id="aba23-130">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="aba23-130">❌ 5.0</span></span> |
| <span data-ttu-id="aba23-131">❌ 3,9</span><span class="sxs-lookup"><span data-stu-id="aba23-131">❌ 3.9</span></span>  | <span data-ttu-id="aba23-132">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="aba23-132">✔️ 2.1</span></span>        | <span data-ttu-id="aba23-133">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="aba23-133">✔️ 3.1</span></span>        | <span data-ttu-id="aba23-134">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="aba23-134">❌ 5.0</span></span> |
| <span data-ttu-id="aba23-135">❌ 3,8</span><span class="sxs-lookup"><span data-stu-id="aba23-135">❌ 3.8</span></span>  | <span data-ttu-id="aba23-136">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="aba23-136">✔️ 2.1</span></span>        | <span data-ttu-id="aba23-137">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="aba23-137">✔️ 3.1</span></span>        | <span data-ttu-id="aba23-138">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="aba23-138">❌ 5.0</span></span> |

<span data-ttu-id="aba23-139">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="aba23-139">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="aba23-140">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="aba23-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="aba23-141">3.0</span><span class="sxs-lookup"><span data-stu-id="aba23-141">3.0</span></span>
- <span data-ttu-id="aba23-142">2.2</span><span class="sxs-lookup"><span data-stu-id="aba23-142">2.2</span></span>
- <span data-ttu-id="aba23-143">2,0</span><span class="sxs-lookup"><span data-stu-id="aba23-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="aba23-144">Zależności</span><span class="sxs-lookup"><span data-stu-id="aba23-144">Dependencies</span></span>

<span data-ttu-id="aba23-145">Platforma .NET w systemie Alpine Linux wymaga zainstalowanych następujących zależności:</span><span class="sxs-lookup"><span data-stu-id="aba23-145">.NET on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="aba23-146">ICU — libs</span><span class="sxs-lookup"><span data-stu-id="aba23-146">icu-libs</span></span>
- <span data-ttu-id="aba23-147">krb5 — libs</span><span class="sxs-lookup"><span data-stu-id="aba23-147">krb5-libs</span></span>
- <span data-ttu-id="aba23-148">libgcc</span><span class="sxs-lookup"><span data-stu-id="aba23-148">libgcc</span></span>
- <span data-ttu-id="aba23-149">libintl</span><span class="sxs-lookup"><span data-stu-id="aba23-149">libintl</span></span>
- <span data-ttu-id="aba23-150">libssl 1.1 (Alpine v lub nowszy)</span><span class="sxs-lookup"><span data-stu-id="aba23-150">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="aba23-151">libssl 1.0 (Alpine v 3.8 lub Lower)</span><span class="sxs-lookup"><span data-stu-id="aba23-151">libssl1.0 (Alpine v3.8 or lower)</span></span>
- <span data-ttu-id="aba23-152">libstdc + +</span><span class="sxs-lookup"><span data-stu-id="aba23-152">libstdc++</span></span>
- <span data-ttu-id="aba23-153">zlib</span><span class="sxs-lookup"><span data-stu-id="aba23-153">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="aba23-154">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="aba23-154">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="aba23-155">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="aba23-155">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="aba23-156">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="aba23-156">Next steps</span></span>

- [<span data-ttu-id="aba23-157">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="aba23-157">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
