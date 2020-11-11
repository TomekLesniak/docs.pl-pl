---
ms.openlocfilehash: 2cd5459ab7f2c8c96638bf27dd30980282036925
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506938"
---

### <a name="install-the-sdk"></a><span data-ttu-id="9c390-101">Instalacja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="9c390-101">Install the SDK</span></span>

<span data-ttu-id="9c390-102">Zestaw SDK platformy .NET umożliwia tworzenie aplikacji przy użyciu platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="9c390-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="9c390-103">W przypadku instalowania zestawu .NET SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="9c390-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="9c390-104">Aby zainstalować zestaw SDK dla platformy .NET, uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="9c390-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo dnf install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="9c390-105">Instalowanie środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="9c390-105">Install the runtime</span></span>

<span data-ttu-id="9c390-106">Środowisko uruchomieniowe ASP.NET Core pozwala uruchamiać aplikacje wykonane przy użyciu platformy .NET, które nie zapewniały środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="9c390-106">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="9c390-107">Następujące polecenia instalują środowisko uruchomieniowe ASP.NET Core, które jest najbardziej zgodnym środowiskiem uruchomieniowym dla platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="9c390-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="9c390-108">W terminalu uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="9c390-108">In your terminal, run the following commands:</span></span>

```bash
sudo dnf install aspnetcore-runtime-5.0
```

<span data-ttu-id="9c390-109">Jako alternatywę dla środowiska uruchomieniowego ASP.NET Core można zainstalować środowisko uruchomieniowe platformy .NET, które nie obejmuje ASP.NET Core obsługi: Zastąp `aspnetcore-runtime-5.0` w poprzednim poleceniu `dotnet-runtime-5.0` :</span><span class="sxs-lookup"><span data-stu-id="9c390-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo dnf install dotnet-runtime-5.0
```
