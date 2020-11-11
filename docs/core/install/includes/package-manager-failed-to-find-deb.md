---
ms.openlocfilehash: aba7b473af7685aa45f7e093a2f75311687593df
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506984"
---

<span data-ttu-id="b6ad9-101">Jeśli zostanie wyświetlony komunikat o błędzie podobny do następującego: **nie można znaleźć pakietu {dotnet-Package}** lub nie można **zainstalować niektórych pakietów** , uruchom następujące polecenia.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-101">If you receive an error message similar to **Unable to locate package {dotnet-package}** or **Some packages could not be installed** , run the following commands.</span></span>

<span data-ttu-id="b6ad9-102">W poniższym zestawie poleceń znajdują się dwa symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="b6ad9-103">Reprezentuje pakiet .NET, który instalujesz, na przykład `aspnetcore-runtime-3.1` .</span><span class="sxs-lookup"><span data-stu-id="b6ad9-103">This represents the .NET package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="b6ad9-104">Ta wartość jest używana w poniższym `sudo apt-get install` poleceniu.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-104">This is used in the following `sudo apt-get install` command.</span></span>

- `{os-version}`\
<span data-ttu-id="b6ad9-105">Oznacza to, że wersja systemu Linux jest włączona.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="b6ad9-106">Ta wartość jest używana w `wget` poniższym poleceniu.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="b6ad9-107">Najpierw spróbuj wyczyszczenie listy pakietów:</span><span class="sxs-lookup"><span data-stu-id="b6ad9-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="b6ad9-108">Następnie spróbuj ponownie zainstalować platformę .NET.</span><span class="sxs-lookup"><span data-stu-id="b6ad9-108">Then, try to install .NET again.</span></span> <span data-ttu-id="b6ad9-109">Jeśli to nie zadziała, można uruchomić instalację ręczną przy użyciu następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="b6ad9-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
