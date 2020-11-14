---
title: Instalowanie platformy .NET w systemie RHEL — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie RHEL.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: cb03f84cf84557d467f0a067b8d5629a843ec7e3
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594583"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="ebd2f-103">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie RHEL</span><span class="sxs-lookup"><span data-stu-id="ebd2f-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="ebd2f-104">Platforma .NET jest obsługiwana w systemie RHEL.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="ebd2f-105">W tym artykule opisano sposób instalowania programu .NET w systemie RHEL.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="ebd2f-106">Zarejestruj swoją subskrypcję Red Hat</span><span class="sxs-lookup"><span data-stu-id="ebd2f-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="ebd2f-107">Aby zainstalować platformę .NET z systemu Red Hat na RHEL, musisz najpierw zarejestrować się przy użyciu Menedżera subskrypcji Red Hat.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="ebd2f-108">Jeśli nie zostało to zrobione w systemie lub nie masz pewności, zobacz [dokumentację produktu Red Hat dla platformy .NET](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="ebd2f-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="ebd2f-109">Obsługiwane dystrybucje</span><span class="sxs-lookup"><span data-stu-id="ebd2f-109">Supported distributions</span></span>

<span data-ttu-id="ebd2f-110">Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET w systemach RHEL 7 i RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="ebd2f-111">Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja RHEL nie jest już obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="ebd2f-112">✔️ wskazuje, że wersja programu RHEL lub .NET jest nadal obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="ebd2f-113">❌Wskazuje, że wersja programu RHEL lub .NET nie jest obsługiwana w tej wersji RHEL.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="ebd2f-114">Gdy wersja programu RHEL i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="ebd2f-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="ebd2f-115">RHEL</span></span>                     | <span data-ttu-id="ebd2f-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ebd2f-116">.NET Core 2.1</span></span> | <span data-ttu-id="ebd2f-117">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="ebd2f-117">.NET Core 3.1</span></span> | <span data-ttu-id="ebd2f-118">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="ebd2f-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="ebd2f-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="ebd2f-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="ebd2f-120">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="ebd2f-120">✔️ 2.1</span></span>        | <span data-ttu-id="ebd2f-121">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="ebd2f-121">✔️ 3.1</span></span>        | <span data-ttu-id="ebd2f-122">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="ebd2f-122">✔️ 5.0</span></span> |
| <span data-ttu-id="ebd2f-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="ebd2f-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="ebd2f-124">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="ebd2f-124">✔️ 2.1</span></span>        | <span data-ttu-id="ebd2f-125">✔️ [3,1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="ebd2f-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="ebd2f-126">✔️ [5,0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="ebd2f-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="ebd2f-127">Następujące wersje platformy .NET nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="ebd2f-128">Pliki do pobrania dla tych nadal są publikowane:</span><span class="sxs-lookup"><span data-stu-id="ebd2f-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="ebd2f-129">3.0</span><span class="sxs-lookup"><span data-stu-id="ebd2f-129">3.0</span></span>
- <span data-ttu-id="ebd2f-130">2.2</span><span class="sxs-lookup"><span data-stu-id="ebd2f-130">2.2</span></span>
- <span data-ttu-id="ebd2f-131">2,0</span><span class="sxs-lookup"><span data-stu-id="ebd2f-131">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="ebd2f-132">Jak zainstalować inne wersje</span><span class="sxs-lookup"><span data-stu-id="ebd2f-132">How to install other versions</span></span>

<span data-ttu-id="ebd2f-133">Zapoznaj się z [dokumentacją firmy Red Hat dla platformy .NET](https://access.redhat.com/documentation/net/5.0/) , wykonując kroki wymagane do zainstalowania innych wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-133">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="ebd2f-134">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="ebd2f-134">RHEL 8 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="ebd2f-135">Program .NET 5,0 nie jest jeszcze dostępny w repozytoriach AppStream, ale .NET Core 3,1 to.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-135">.NET 5.0 isn't yet available in the AppStream repositories, but .NET Core 3.1 is.</span></span> <span data-ttu-id="ebd2f-136">Aby zainstalować program .NET Core 3,1, użyj `dnf install` polecenia z odpowiednim pakietem, takim jak `aspnetcore-runtime-3.1` lub `dotnet-sdk-3.1` .</span><span class="sxs-lookup"><span data-stu-id="ebd2f-136">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="ebd2f-137">Poniższe instrukcje dotyczą programu .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-137">The following instructions are for .NET 5.0.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/8/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="ebd2f-138">RHEL 7 ✔️ .NET 5,0</span><span class="sxs-lookup"><span data-stu-id="ebd2f-138">RHEL 7 ✔️ .NET 5.0</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/7/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-yum.md)]

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="ebd2f-139">RHEL 7 ✔️ .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="ebd2f-139">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="ebd2f-140">Następujące polecenie instaluje `scl-utils` pakiet:</span><span class="sxs-lookup"><span data-stu-id="ebd2f-140">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="ebd2f-141">Instalacja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="ebd2f-141">Install the SDK</span></span>

<span data-ttu-id="ebd2f-142">Zestaw .NET Core SDK umożliwia tworzenie aplikacji przy użyciu platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-142">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="ebd2f-143">W przypadku zainstalowania zestaw .NET Core SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-143">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="ebd2f-144">Aby zainstalować zestaw .NET Core SDK, uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="ebd2f-144">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="ebd2f-145">Red Hat nie zaleca trwałego włączania `rh-dotnet31` , ponieważ może to mieć wpływ na inne programy.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-145">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="ebd2f-146">Program zawiera na przykład `rh-dotnet31` wersję `libcurl` , która różni się od bazowej wersji RHEL.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-146">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="ebd2f-147">Może to prowadzić do problemów z programami, które nie oczekują innej wersji programu `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="ebd2f-147">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="ebd2f-148">Jeśli chcesz `rh-dotnet` trwale włączyć, Dodaj następujący wiersz do pliku _~/.bashrc._ .</span><span class="sxs-lookup"><span data-stu-id="ebd2f-148">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="ebd2f-149">Instalowanie środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="ebd2f-149">Install the runtime</span></span>

<span data-ttu-id="ebd2f-150">Środowisko uruchomieniowe programu .NET Core umożliwia uruchamianie aplikacji, które zostały wykonane przy użyciu platformy .NET Core, które nie zawierały środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-150">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="ebd2f-151">Poniższe polecenia instalują środowisko uruchomieniowe ASP.NET Core, które jest najbardziej zgodnym środowiskiem uruchomieniowym dla platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-151">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="ebd2f-152">W terminalu uruchom następujące polecenia.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-152">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="ebd2f-153">Red Hat nie zaleca trwałego włączania `rh-dotnet31-aspnetcore-runtime-3.1` , ponieważ może to mieć wpływ na inne programy.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-153">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="ebd2f-154">Program zawiera na przykład `rh-dotnet31-aspnetcore-runtime-3.1` wersję `libcurl` , która różni się od bazowej wersji RHEL.</span><span class="sxs-lookup"><span data-stu-id="ebd2f-154">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="ebd2f-155">Może to prowadzić do problemów z programami, które nie oczekują innej wersji programu `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="ebd2f-155">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="ebd2f-156">Jeśli chcesz `rh-dotnet31-aspnetcore-runtime-3.1` trwale włączyć, Dodaj następujący wiersz do pliku _~/.bashrc._ .</span><span class="sxs-lookup"><span data-stu-id="ebd2f-156">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="ebd2f-157">Jako alternatywę dla środowiska uruchomieniowego ASP.NET Core można zainstalować środowisko uruchomieniowe programu .NET Core, które nie obejmuje ASP.NET Core Support: Zastąp `rh-dotnet31-aspnetcore-runtime-3.1` w poleceniach powyżej `rh-dotnet31-dotnet-runtime-3.1` .</span><span class="sxs-lookup"><span data-stu-id="ebd2f-157">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="ebd2f-158">Przystawki</span><span class="sxs-lookup"><span data-stu-id="ebd2f-158">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="ebd2f-159">Zależności</span><span class="sxs-lookup"><span data-stu-id="ebd2f-159">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="ebd2f-160">Instalacja z skryptami</span><span class="sxs-lookup"><span data-stu-id="ebd2f-160">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="ebd2f-161">Instalacja ręczna</span><span class="sxs-lookup"><span data-stu-id="ebd2f-161">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="ebd2f-162">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="ebd2f-162">Next steps</span></span>

- [<span data-ttu-id="ebd2f-163">Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ebd2f-163">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
