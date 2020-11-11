---
ms.openlocfilehash: f8bf759272ad75b6684496a913cdef7f7912286d
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506829"
---

<span data-ttu-id="f9c31-101">[Skrypty dotnet-Install](../../tools/dotnet-install-script.md) są używane na potrzeby automatyzacji i nieadministracyjnych instalacji **zestawu SDK** i **środowiska uruchomieniowego**.</span><span class="sxs-lookup"><span data-stu-id="f9c31-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="f9c31-102">Skrypt można pobrać z programu <https://dot.net/v1/dotnet-install.sh> .</span><span class="sxs-lookup"><span data-stu-id="f9c31-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="f9c31-103">Skrypt domyślnie instaluje najnowszą wersję programu [obsługi długoterminowej (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) zestawu SDK, która jest .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="f9c31-103">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET 5.0.</span></span> <span data-ttu-id="f9c31-104">Aby zainstalować bieżącą wersję, która nie może być wersją (LTS), użyj `-c Current` parametru.</span><span class="sxs-lookup"><span data-stu-id="f9c31-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="f9c31-105">Aby zainstalować środowisko uruchomieniowe platformy .NET zamiast zestawu SDK, użyj `--runtime` parametru.</span><span class="sxs-lookup"><span data-stu-id="f9c31-105">To install .NET Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="f9c31-106">Określoną wersję można zainstalować, zmieniając `-c` parametr w celu wskazania określonej wersji.</span><span class="sxs-lookup"><span data-stu-id="f9c31-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="f9c31-107">Następujące polecenie instaluje zestaw SDK programu .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="f9c31-107">The following command installs .NET SDK 5.0.</span></span>

```bash
./dotnet-install.sh -c 5.0
```

<span data-ttu-id="f9c31-108">Aby uzyskać więcej informacji, zobacz temat informacje o [skryptach dotnet-Install](../../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="f9c31-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>
