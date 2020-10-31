---
ms.openlocfilehash: 787b0a04c5bf312ad3f3e7834664e70dae9678e0
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93136115"
---

### <a name="install-the-sdk"></a><span data-ttu-id="90794-101">Instalacja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="90794-101">Install the SDK</span></span>

<span data-ttu-id="90794-102">Zestaw .NET Core SDK umożliwia tworzenie aplikacji przy użyciu platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="90794-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="90794-103">W przypadku zainstalowania zestaw .NET Core SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="90794-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="90794-104">Aby zainstalować zestaw .NET Core SDK, uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="90794-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo dnf install dotnet-sdk-2.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="90794-105">Instalowanie środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="90794-105">Install the runtime</span></span>

<span data-ttu-id="90794-106">Środowisko uruchomieniowe programu .NET Core umożliwia uruchamianie aplikacji, które zostały wykonane przy użyciu platformy .NET Core, które nie zawierały środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="90794-106">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="90794-107">Następujące polecenia instalują środowisko uruchomieniowe ASP.NET Core, które jest najbardziej zgodnym środowiskiem uruchomieniowym dla platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="90794-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="90794-108">W terminalu uruchom następujące polecenia.</span><span class="sxs-lookup"><span data-stu-id="90794-108">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install aspnetcore-runtime-2.0
```

<span data-ttu-id="90794-109">Jako alternatywę dla środowiska uruchomieniowego ASP.NET Core można zainstalować środowisko uruchomieniowe programu .NET Core, które nie obejmuje ASP.NET Core Support: Zastąp `aspnetcore-runtime-2.0` w poprzednim poleceniu poleceniem `dotnet-runtime-2.0` .</span><span class="sxs-lookup"><span data-stu-id="90794-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.0` in the previous command with `dotnet-runtime-2.0`.</span></span>

```bash
sudo dnf install dotnet-runtime-2.0
```
