---
ms.openlocfilehash: 4ab2fc0645f76870dead99b5f45eef763643fb27
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506904"
---

[<span data-ttu-id="ccd87-101">Program .NET Core jest dostępny w magazynie Snap.</span><span class="sxs-lookup"><span data-stu-id="ccd87-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="ccd87-102">Przyciąganie to pakiet aplikacji i jej zależności, które działają bez modyfikacji dla wielu różnych dystrybucji systemu Linux.</span><span class="sxs-lookup"><span data-stu-id="ccd87-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="ccd87-103">Przyciąganie jest wykrywalne i instalowane z magazynu Snap.</span><span class="sxs-lookup"><span data-stu-id="ccd87-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="ccd87-104">Aby uzyskać więcej informacji na temat przyciągania, zobacz [wprowadzenie do przyciągania](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="ccd87-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="ccd87-105">Tylko obsługiwane wersje programu .NET Core są dostępne za poorednictwem przyciągania.</span><span class="sxs-lookup"><span data-stu-id="ccd87-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="ccd87-106">Instalacja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="ccd87-106">Install the SDK</span></span>

<span data-ttu-id="ccd87-107">Pakiety przyciągania dla zestawu .NET SDK są publikowane w ramach tego samego identyfikatora: `dotnet-sdk` .</span><span class="sxs-lookup"><span data-stu-id="ccd87-107">Snap packages for .NET SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="ccd87-108">Określoną wersję zestawu SDK można zainstalować, określając kanał.</span><span class="sxs-lookup"><span data-stu-id="ccd87-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="ccd87-109">Zestaw SDK obejmuje środowisko uruchomieniowe współreagujące.</span><span class="sxs-lookup"><span data-stu-id="ccd87-109">The SDK includes the coresponding runtime.</span></span> <span data-ttu-id="ccd87-110">W poniższej tabeli wymieniono kanały:</span><span class="sxs-lookup"><span data-stu-id="ccd87-110">The following table list the channels:</span></span>

| <span data-ttu-id="ccd87-111">Wersja platformy .NET</span><span class="sxs-lookup"><span data-stu-id="ccd87-111">.NET version</span></span> | <span data-ttu-id="ccd87-112">Pakiet przyciągania</span><span class="sxs-lookup"><span data-stu-id="ccd87-112">Snap package</span></span>             |
|--------------|--------------------------|
| <span data-ttu-id="ccd87-113">5,0</span><span class="sxs-lookup"><span data-stu-id="ccd87-113">5.0</span></span>          | <span data-ttu-id="ccd87-114">`5.0` lub `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="ccd87-114">`5.0` or `latest/stable`</span></span> |
| <span data-ttu-id="ccd87-115">3,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ccd87-115">3.1 (LTS)</span></span>    | <span data-ttu-id="ccd87-116">`3.1` lub `lts/stable`</span><span class="sxs-lookup"><span data-stu-id="ccd87-116">`3.1` or `lts/stable`</span></span>    |
| <span data-ttu-id="ccd87-117">2,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ccd87-117">2.1 (LTS)</span></span>    | `2.1`                    |

<span data-ttu-id="ccd87-118">Użyj `snap install` polecenia, aby zainstalować pakiet przyciągania zestawu .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="ccd87-118">Use the `snap install` command to install a .NET SDK snap package.</span></span> <span data-ttu-id="ccd87-119">Użyj `--channel` parametru, aby wskazać wersję do zainstalowania.</span><span class="sxs-lookup"><span data-stu-id="ccd87-119">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="ccd87-120">Jeśli ten parametr zostanie pominięty, `latest/stable` jest używany.</span><span class="sxs-lookup"><span data-stu-id="ccd87-120">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="ccd87-121">W tym przykładzie `5.0` określono:</span><span class="sxs-lookup"><span data-stu-id="ccd87-121">In this example, `5.0` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

<span data-ttu-id="ccd87-122">Następnie zarejestruj `dotnet` polecenie dla systemu przy użyciu `snap alias` polecenia:</span><span class="sxs-lookup"><span data-stu-id="ccd87-122">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="ccd87-123">To polecenie jest sformatowane jako: `sudo snap alias {package}.{command} {alias}` .</span><span class="sxs-lookup"><span data-stu-id="ccd87-123">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="ccd87-124">Możesz wybrać dowolną `{alias}` nazwę.</span><span class="sxs-lookup"><span data-stu-id="ccd87-124">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="ccd87-125">Można na przykład nazwać polecenie po zainstalowaniu określonej wersji przez przyciąganie: `sudo snap alias dotnet-sdk.dotnet dotnet50` .</span><span class="sxs-lookup"><span data-stu-id="ccd87-125">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span></span> <span data-ttu-id="ccd87-126">Korzystając z polecenia `dotnet50` , należy wywołać tę konkretną wersję platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="ccd87-126">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="ccd87-127">Ale jest to niezgodne z większością samouczków i przykładów, ponieważ oczekuje, że `dotnet` polecenie jest dostępne.</span><span class="sxs-lookup"><span data-stu-id="ccd87-127">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="ccd87-128">Instalowanie środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="ccd87-128">Install the runtime</span></span>

<span data-ttu-id="ccd87-129">Pakiety przyciągania dla środowiska uruchomieniowego .NET Core są publikowane w ramach własnego identyfikatora pakietu.</span><span class="sxs-lookup"><span data-stu-id="ccd87-129">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="ccd87-130">W poniższej tabeli wymieniono identyfikatory pakietów:</span><span class="sxs-lookup"><span data-stu-id="ccd87-130">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="ccd87-131">Wersja platformy .NET</span><span class="sxs-lookup"><span data-stu-id="ccd87-131">.NET version</span></span>      | <span data-ttu-id="ccd87-132">Pakiet przyciągania</span><span class="sxs-lookup"><span data-stu-id="ccd87-132">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="ccd87-133">5,0</span><span class="sxs-lookup"><span data-stu-id="ccd87-133">5.0</span></span>               | `dotnet-runtime-50` |
| <span data-ttu-id="ccd87-134">3,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ccd87-134">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="ccd87-135">3.0</span><span class="sxs-lookup"><span data-stu-id="ccd87-135">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="ccd87-136">2.2</span><span class="sxs-lookup"><span data-stu-id="ccd87-136">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="ccd87-137">2,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ccd87-137">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="ccd87-138">Użyj `snap install` polecenia, aby zainstalować pakiet przyciągania środowiska uruchomieniowego platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="ccd87-138">Use the `snap install` command to install a .NET Runtime snap package.</span></span> <span data-ttu-id="ccd87-139">W tym przykładzie jest zainstalowany program .NET 5,0:</span><span class="sxs-lookup"><span data-stu-id="ccd87-139">In this example, .NET 5.0 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-50 --classic
```

<span data-ttu-id="ccd87-140">Następnie zarejestruj `dotnet` polecenie dla systemu przy użyciu `snap alias` polecenia:</span><span class="sxs-lookup"><span data-stu-id="ccd87-140">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

<span data-ttu-id="ccd87-141">To polecenie jest sformatowane jako: `sudo snap alias {package}.{command} {alias}` .</span><span class="sxs-lookup"><span data-stu-id="ccd87-141">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="ccd87-142">Możesz wybrać dowolną `{alias}` nazwę.</span><span class="sxs-lookup"><span data-stu-id="ccd87-142">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="ccd87-143">Można na przykład nazwać polecenie po zainstalowaniu określonej wersji przez przyciąganie: `sudo snap alias dotnet-runtime-50.dotnet dotnet50` .</span><span class="sxs-lookup"><span data-stu-id="ccd87-143">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span></span> <span data-ttu-id="ccd87-144">Korzystając z polecenia `dotnet50` , należy wywołać tę konkretną wersję platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="ccd87-144">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="ccd87-145">Ale jest to niezgodne z większością samouczków i przykładów, ponieważ oczekuje, że `dotnet` polecenie jest dostępne.</span><span class="sxs-lookup"><span data-stu-id="ccd87-145">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="ccd87-146">Błędy certyfikatów SSL</span><span class="sxs-lookup"><span data-stu-id="ccd87-146">SSL Certificate errors</span></span>

<span data-ttu-id="ccd87-147">Po zainstalowaniu programu .NET za pośrednictwem przyciągania możliwe jest, że na niektórych dystrybucje nie można odnaleźć certyfikatów protokołu SSL platformy .NET i może zostać wyświetlony błąd podobny do poniższego `restore` :</span><span class="sxs-lookup"><span data-stu-id="ccd87-147">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="ccd87-148">Aby rozwiązać ten problem, ustaw kilka zmiennych środowisko:</span><span class="sxs-lookup"><span data-stu-id="ccd87-148">To resolve this issue, set a few enviornment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="ccd87-149">Lokalizacja certyfikatu zależy od dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="ccd87-149">The certificate location will vary by distro.</span></span> <span data-ttu-id="ccd87-150">Poniżej znajdują się lokalizacje dystrybucje, w których wystąpił problem.</span><span class="sxs-lookup"><span data-stu-id="ccd87-150">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="ccd87-151">Fedora `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="ccd87-151">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="ccd87-152">OpenSUSE `/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="ccd87-152">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="ccd87-153">Solus - `/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="ccd87-153">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>
