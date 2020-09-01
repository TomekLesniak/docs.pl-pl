---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132950"
---

<span data-ttu-id="2f502-101">Jeśli zostanie wyświetlony komunikat o błędzie podobny do następującego: **nie można znaleźć pakietu {servicecore-Package}** lub nie można **zainstalować niektórych pakietów**, uruchom następujące polecenia.</span><span class="sxs-lookup"><span data-stu-id="2f502-101">If you receive an error message similar to **Unable to locate package {netcore-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="2f502-102">W poniższym zestawie poleceń znajdują się dwa symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="2f502-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="2f502-103">Reprezentuje pakiet .NET Core, który instalujesz, na przykład `aspnetcore-runtime-3.1` .</span><span class="sxs-lookup"><span data-stu-id="2f502-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="2f502-104">Ta wartość jest używana w `sudo apt-get install` poniższym poleceniu.</span><span class="sxs-lookup"><span data-stu-id="2f502-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="2f502-105">Oznacza to, że wersja systemu Linux jest włączona.</span><span class="sxs-lookup"><span data-stu-id="2f502-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="2f502-106">Ta wartość jest używana w `wget` poniższym poleceniu.</span><span class="sxs-lookup"><span data-stu-id="2f502-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="2f502-107">Najpierw spróbuj wyczyszczenie listy pakietów:</span><span class="sxs-lookup"><span data-stu-id="2f502-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="2f502-108">Następnie spróbuj ponownie zainstalować platformę .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2f502-108">Then, try to install .NET Core again.</span></span> <span data-ttu-id="2f502-109">Jeśli to nie zadziała, można uruchomić instalację ręczną przy użyciu następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="2f502-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
