---
ms.openlocfilehash: 188fef66444cd60f59a3cb9619c0d86efd155f99
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93136233"
---

### <a name="install-the-sdk"></a><span data-ttu-id="37748-101">Instalacja zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="37748-101">Install the SDK</span></span>

<span data-ttu-id="37748-102">Zestaw .NET Core SDK umożliwia tworzenie aplikacji przy użyciu platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="37748-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="37748-103">W przypadku zainstalowania zestaw .NET Core SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="37748-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="37748-104">Aby zainstalować zestaw .NET Core SDK, uruchom następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="37748-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="37748-105">Jeśli zostanie wyświetlony komunikat o błędzie podobny do sytuacji, w której **nie można znaleźć pakietu dotnet-SDK-2,1** , zobacz sekcję [Rozwiązywanie problemów z apt](#apt-troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="37748-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-2.1** , see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="37748-106">Instalowanie środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="37748-106">Install the runtime</span></span>

<span data-ttu-id="37748-107">Środowisko uruchomieniowe programu .NET Core umożliwia uruchamianie aplikacji, które zostały wykonane przy użyciu platformy .NET Core, które nie zawierały środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="37748-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="37748-108">Następujące polecenia instalują środowisko uruchomieniowe ASP.NET Core, które jest najbardziej zgodnym środowiskiem uruchomieniowym dla platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="37748-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="37748-109">W terminalu uruchom następujące polecenia.</span><span class="sxs-lookup"><span data-stu-id="37748-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="37748-110">Jeśli zostanie wyświetlony komunikat o błędzie podobny do sytuacji, w której **nie można znaleźć pakietu aspnetcore-Runtime-2,1** , zobacz sekcję [Rozwiązywanie problemów z apt](#apt-troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="37748-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-2.1** , see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="37748-111">Jako alternatywę dla środowiska uruchomieniowego ASP.NET Core można zainstalować środowisko uruchomieniowe programu .NET Core, które nie obejmuje ASP.NET Core Support: Zastąp `aspnetcore-runtime-2.1` w poprzednim poleceniu poleceniem `dotnet-runtime-2.1` .</span><span class="sxs-lookup"><span data-stu-id="37748-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the previous command with `dotnet-runtime-2.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-2.1
```
