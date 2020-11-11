---
title: Instalowanie platformy .NET w systemie RHEL — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie RHEL.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: a742497bba3459a4d8772f5c9e3d915b5b18e62e
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506930"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="c5ca3-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie RHEL</span><span class="sxs-lookup"><span data-stu-id="c5ca3-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="c5ca3-104">Platforma .NET jest obsługiwana w systemie RHEL.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="c5ca3-105">W tym artykule opisano sposób instalowania programu .NET w systemie RHEL.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="c5ca3-106">Zarejestruj swoją subskrypcję Red Hat</span><span class="sxs-lookup"><span data-stu-id="c5ca3-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="c5ca3-107">Aby zainstalować platformę .NET z systemu Red Hat na RHEL, musisz najpierw zarejestrować się przy użyciu Menedżera subskrypcji Red Hat.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="c5ca3-108">Jeśli nie zostało to zrobione w systemie lub nie masz pewności, zobacz [dokumentację produktu Red Hat dla platformy .NET](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="c5ca3-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="c5ca3-109">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="c5ca3-109">Supported distributions</span></span>

<span data-ttu-id="c5ca3-110">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET w systemach RHEL 7 i RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="c5ca3-111">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja RHEL nie jest już obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="c5ca3-112">✔️ wskazuje, że wersja programu RHEL lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="c5ca3-113">❌Wskazuje, że wersja programu RHEL lub .NET nie jest obsługiwana w tej wersji RHEL.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="c5ca3-114">Gdy wersja programu RHEL i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="c5ca3-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="c5ca3-115">RHEL</span></span>                   | <span data-ttu-id="c5ca3-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c5ca3-116">.NET Core 2.1</span></span> | <span data-ttu-id="c5ca3-117">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="c5ca3-117">.NET Core 3.1</span></span> | <span data-ttu-id="c5ca3-118">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="c5ca3-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="c5ca3-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="c5ca3-119">✔️ [8](#rhel-8-)</span></span> | <span data-ttu-id="c5ca3-120">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="c5ca3-120">✔️ 2.1</span></span>        | <span data-ttu-id="c5ca3-121">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="c5ca3-121">✔️ 3.1</span></span>        | <span data-ttu-id="c5ca3-122">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="c5ca3-122">✔️ 5.0</span></span> |
| <span data-ttu-id="c5ca3-123">✔️ [7](#rhel-7-)</span><span class="sxs-lookup"><span data-stu-id="c5ca3-123">✔️ [7](#rhel-7-)</span></span> | <span data-ttu-id="c5ca3-124">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="c5ca3-124">✔️ 2.1</span></span>        | <span data-ttu-id="c5ca3-125">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="c5ca3-125">✔️ 3.1</span></span>        | <span data-ttu-id="c5ca3-126">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="c5ca3-126">✔️ 5.0</span></span> |

<span data-ttu-id="c5ca3-127">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="c5ca3-128">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="c5ca3-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="c5ca3-129">3.0</span><span class="sxs-lookup"><span data-stu-id="c5ca3-129">3.0</span></span>
- <span data-ttu-id="c5ca3-130">2.2</span><span class="sxs-lookup"><span data-stu-id="c5ca3-130">2.2</span></span>
- <span data-ttu-id="c5ca3-131">2,0</span><span class="sxs-lookup"><span data-stu-id="c5ca3-131">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="c5ca3-132">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="c5ca3-132">How to install other versions</span></span>

<span data-ttu-id="c5ca3-133">Zapoznaj się z [dokumentacją firmy Red Hat dla platformy .NET](https://access.redhat.com/documentation/net/5.0/) , wykonując kroki wymagane do zainstalowania innych wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-133">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="c5ca3-134">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="c5ca3-134">RHEL 8 ✔️</span></span>

<span data-ttu-id="c5ca3-135">Platforma .NET jest uwzględniona w repozytoriach AppStream dla RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-135">.NET is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7-"></a><span data-ttu-id="c5ca3-136">RHEL ✔️ 7</span><span class="sxs-lookup"><span data-stu-id="c5ca3-136">RHEL 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="c5ca3-137">Następujące polecenie instaluje `scl-utils` pakiet:</span><span class="sxs-lookup"><span data-stu-id="c5ca3-137">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="c5ca3-138">Instalacja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="c5ca3-138">Install the SDK</span></span>

<span data-ttu-id="c5ca3-139">Zestaw SDK platformy .NET umożliwia tworzenie aplikacji przy użyciu platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-139">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="c5ca3-140">W przypadku instalowania zestawu .NET SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-140">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="c5ca3-141">Aby zainstalować zestaw SDK dla platformy .NET, uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="c5ca3-141">To install the .NET SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="c5ca3-142">Red Hat nie zaleca trwałego włączania `rh-dotnet50` , ponieważ może to mieć wpływ na inne programy.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-142">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="c5ca3-143">Program zawiera na przykład `rh-dotnet50` wersję `libcurl` , która różni się od bazowej wersji RHEL.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-143">For example, `rh-dotnet50` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="c5ca3-144">Może to prowadzić do problemów z programami, które nie oczekują innej wersji programu `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="c5ca3-144">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="c5ca3-145">Jeśli chcesz `rh-dotnet` trwale włączyć, Dodaj następujący wiersz do pliku _~/.bashrc._ .</span><span class="sxs-lookup"><span data-stu-id="c5ca3-145">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a><span data-ttu-id="c5ca3-146">Instalowanie środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="c5ca3-146">Install the runtime</span></span>

<span data-ttu-id="c5ca3-147">Środowisko uruchomieniowe ASP.NET Core pozwala uruchamiać aplikacje wykonane przy użyciu platformy .NET, które nie zapewniały środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-147">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="c5ca3-148">Następujące polecenia instalują środowisko uruchomieniowe ASP.NET Core, które jest najbardziej zgodnym środowiskiem uruchomieniowym dla platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-148">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="c5ca3-149">W terminalu uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="c5ca3-149">In your terminal, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50-aspnetcore-runtime-5.0 bash
```

<span data-ttu-id="c5ca3-150">Red Hat nie zaleca trwałego włączania `rh-dotnet50-aspnetcore-runtime-5.0` , ponieważ może to mieć wpływ na inne programy.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-150">Red Hat doesn't recommend permanently enabling `rh-dotnet50-aspnetcore-runtime-5.0` because it may affect other programs.</span></span> <span data-ttu-id="c5ca3-151">Program zawiera na przykład `rh-dotnet50-aspnetcore-runtime-5.0` wersję `libcurl` , która różni się od bazowej wersji RHEL.</span><span class="sxs-lookup"><span data-stu-id="c5ca3-151">For example, `rh-dotnet50-aspnetcore-runtime-5.0` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="c5ca3-152">Może to prowadzić do problemów z programami, które nie oczekują innej wersji programu `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="c5ca3-152">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="c5ca3-153">Jeśli chcesz `rh-dotnet50-aspnetcore-runtime-5.0` trwale włączyć, Dodaj następujący wiersz do pliku _~/.bashrc._ .</span><span class="sxs-lookup"><span data-stu-id="c5ca3-153">If you want to enable `rh-dotnet50-aspnetcore-runtime-5.0` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50-aspnetcore-runtime-5.0
```

<span data-ttu-id="c5ca3-154">Jako alternatywę dla środowiska uruchomieniowego ASP.NET Core można zainstalować środowisko uruchomieniowe platformy .NET, które nie obejmuje ASP.NET Core obsługi: Zastąp `rh-dotnet50-aspnetcore-runtime-5.0` w poprzednich poleceniach poleceniem `rh-dotnet50-dotnet-runtime-5.0` .</span><span class="sxs-lookup"><span data-stu-id="c5ca3-154">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `rh-dotnet50-aspnetcore-runtime-5.0` in the previous commands with `rh-dotnet50-dotnet-runtime-5.0`.</span></span>

## <a name="snap"></a><span data-ttu-id="c5ca3-155">Przystawki</span><span class="sxs-lookup"><span data-stu-id="c5ca3-155">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="c5ca3-156">Zależności</span><span class="sxs-lookup"><span data-stu-id="c5ca3-156">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="c5ca3-157">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="c5ca3-157">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="c5ca3-158">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="c5ca3-158">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="c5ca3-159">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="c5ca3-159">Next steps</span></span>

- [<span data-ttu-id="c5ca3-160">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c5ca3-160">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
