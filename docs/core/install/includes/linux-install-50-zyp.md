---
ms.openlocfilehash: ed269683f5c4569c21ae53e9a3c1ec65eb5ebd43
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506871"
---

### <a name="install-the-sdk"></a><span data-ttu-id="c9dd4-101">Instalacja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="c9dd4-101">Install the SDK</span></span>

<span data-ttu-id="c9dd4-102">Zestaw SDK platformy .NET umożliwia tworzenie aplikacji przy użyciu platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="c9dd4-103">W przypadku instalowania zestawu .NET SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="c9dd4-104">Aby zainstalować zestaw SDK dla platformy .NET, uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="c9dd4-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo zypper install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="c9dd4-105">Instalowanie środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="c9dd4-105">Install the runtime</span></span>

<span data-ttu-id="c9dd4-106">Środowisko uruchomieniowe ASP.NET Core pozwala uruchamiać aplikacje wykonane przy użyciu platformy .NET, które nie zapewniały środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-106">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="c9dd4-107">Następujące polecenia instalują środowisko uruchomieniowe ASP.NET Core, które jest najbardziej zgodnym środowiskiem uruchomieniowym dla platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="c9dd4-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="c9dd4-108">W terminalu uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="c9dd4-108">In your terminal, run the following commands:</span></span>

```bash
sudo zypper install aspnetcore-runtime-5.0
```

<span data-ttu-id="c9dd4-109">Jako alternatywę dla środowiska uruchomieniowego ASP.NET Core można zainstalować środowisko uruchomieniowe platformy .NET, które nie obejmuje ASP.NET Core obsługi: Zastąp `aspnetcore-runtime-5.0` w poprzednim poleceniu `dotnet-runtime-5.0` :</span><span class="sxs-lookup"><span data-stu-id="c9dd4-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo zypper install dotnet-runtime-5.0
```
