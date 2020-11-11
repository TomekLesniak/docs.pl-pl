---
ms.openlocfilehash: 87c7abf6a20dd8e9769f3b3b3cbe271d32fd62c3
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507002"
---

### <a name="install-the-sdk"></a><span data-ttu-id="40070-101">Instalacja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="40070-101">Install the SDK</span></span>

<span data-ttu-id="40070-102">Zestaw SDK platformy .NET umożliwia tworzenie aplikacji przy użyciu platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="40070-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="40070-103">W przypadku instalowania zestawu .NET SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="40070-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="40070-104">Aby zainstalować zestaw SDK dla platformy .NET, uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="40070-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-5.0
```

> [!IMPORTANT]
> <span data-ttu-id="40070-105">Jeśli zostanie wyświetlony komunikat o błędzie podobny do sytuacji, w której **nie można znaleźć pakietu dotnet-SDK-5,0** , zobacz sekcję [Rozwiązywanie problemów z apt](#apt-troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="40070-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-5.0** , see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="40070-106">Instalowanie środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="40070-106">Install the runtime</span></span>

<span data-ttu-id="40070-107">Środowisko uruchomieniowe ASP.NET Core pozwala uruchamiać aplikacje wykonane przy użyciu platformy .NET, które nie zapewniały środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="40070-107">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="40070-108">Następujące polecenia instalują środowisko uruchomieniowe ASP.NET Core, które jest najbardziej zgodnym środowiskiem uruchomieniowym dla platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="40070-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="40070-109">W terminalu uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="40070-109">In your terminal, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-5.0
```

> [!IMPORTANT]
> <span data-ttu-id="40070-110">Jeśli zostanie wyświetlony komunikat o błędzie podobny do sytuacji, w której **nie można znaleźć pakietu aspnetcore-Runtime-5,0** , zobacz sekcję [Rozwiązywanie problemów z apt](#apt-troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="40070-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-5.0** , see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="40070-111">Jako alternatywę dla środowiska uruchomieniowego ASP.NET Core można zainstalować środowisko uruchomieniowe platformy .NET, które nie obejmuje ASP.NET Core obsługi: Zastąp `aspnetcore-runtime-5.0` w poprzednim poleceniu `dotnet-runtime-5.0` :</span><span class="sxs-lookup"><span data-stu-id="40070-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo apt-get install -y dotnet-runtime-5.0
```
