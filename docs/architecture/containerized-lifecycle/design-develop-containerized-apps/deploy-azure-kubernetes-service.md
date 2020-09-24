---
title: Organizowanie aplikacji mikrousług i aplikacji z wieloma kontenerami w celu zapewnienia wysokiej skalowalności i dostępności
description: Dowiedz się, jak wdrożyć aplikację przy użyciu usługi Azure Kubernetes Service.
ms.date: 08/06/2020
ms.openlocfilehash: ba9887c0a4837c16a60ebeb006416c0fa8c105e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163599"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="06d0f-103">Wdrażanie w usłudze Azure Kubernetes Service (AKS)</span><span class="sxs-lookup"><span data-stu-id="06d0f-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="06d0f-104">Można korzystać z AKS przy użyciu preferowanego systemu operacyjnego klienta (Windows, macOS lub Linux) z zainstalowanym interfejsem wiersza polecenia platformy Azure (Azure CLI).</span><span class="sxs-lookup"><span data-stu-id="06d0f-104">You can interact with AKS using your preferred client operating system (Windows, macOS, or Linux) with Azure command-line interface(Azure CLI) installed.</span></span> <span data-ttu-id="06d0f-105">Aby uzyskać więcej informacji, zapoznaj się z [dokumentacją interfejsu wiersza polecenia platformy Azure](/cli/azure/?view=azure-cli-latest) i [Podręcznikiem instalacji](/cli/azure/install-azure-cli?view=azure-cli-latest) dla dostępnych środowisk.</span><span class="sxs-lookup"><span data-stu-id="06d0f-105">For more details, refer [Azure CLI documentation](/cli/azure/?view=azure-cli-latest) and [Installation guide](/cli/azure/install-azure-cli?view=azure-cli-latest) for the available environments.</span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="06d0f-106">Tworzenie środowiska AKS na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="06d0f-106">Create the AKS environment in Azure</span></span>

<span data-ttu-id="06d0f-107">Istnieje kilka sposobów tworzenia środowiska AKS.</span><span class="sxs-lookup"><span data-stu-id="06d0f-107">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="06d0f-108">Można to zrobić za pomocą poleceń interfejsu wiersza polecenia platformy Azure lub przy użyciu Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="06d0f-108">It can be done by using Azure CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="06d0f-109">W tym miejscu możesz zapoznać się z przykładami za pomocą interfejsu wiersza polecenia platformy Azure, aby utworzyć klaster i Azure Portal, aby przejrzeć wyniki.</span><span class="sxs-lookup"><span data-stu-id="06d0f-109">Here you can explore some examples using the Azure CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="06d0f-110">Musisz również mieć polecenia kubectl i Docker na komputerze deweloperskim.</span><span class="sxs-lookup"><span data-stu-id="06d0f-110">You also need to have Kubectl and Docker in your development machine.</span></span>

## <a name="create-the-aks-cluster"></a><span data-ttu-id="06d0f-111">Tworzenie klastra AKS</span><span class="sxs-lookup"><span data-stu-id="06d0f-111">Create the AKS cluster</span></span>

<span data-ttu-id="06d0f-112">Utwórz klaster AKS przy użyciu tego polecenia (Grupa zasobów musi istnieć):</span><span class="sxs-lookup"><span data-stu-id="06d0f-112">Create the AKS cluster using this command (the resource group must exist):</span></span>

```console
az aks create --resource-group explore-docker-aks-rg --name explore-docker-aks --node-vm-size Standard_B2s --node-count 1 --generate-ssh-keys --location westeurope
```

> [!NOTE]
> <span data-ttu-id="06d0f-113">`--node-vm-size` `--node-count` Wartości parametrów i są wystarczające dla aplikacji przykładowej/deweloperskiej.</span><span class="sxs-lookup"><span data-stu-id="06d0f-113">The `--node-vm-size` and `--node-count` parameter values are good enough for a sample/dev application.</span></span>

<span data-ttu-id="06d0f-114">Po zakończeniu zadania tworzenia można zobaczyć:</span><span class="sxs-lookup"><span data-stu-id="06d0f-114">After the creation job finishes, you can see:</span></span>

- <span data-ttu-id="06d0f-115">Klaster AKS utworzony w początkowej grupie zasobów</span><span class="sxs-lookup"><span data-stu-id="06d0f-115">The AKS cluster created in the initial resource group</span></span>
- <span data-ttu-id="06d0f-116">Nowa, powiązana Grupa zasobów zawierająca zasoby związane z klastrem AKS, jak pokazano na poniższych ilustracjach.</span><span class="sxs-lookup"><span data-stu-id="06d0f-116">A new, related resource group, containing the resources related to the AKS cluster, as show in the following images.</span></span>

<span data-ttu-id="06d0f-117">Początkowa Grupa zasobów z klastrem AKS:</span><span class="sxs-lookup"><span data-stu-id="06d0f-117">The initial resource group, with the AKS cluster:</span></span>

![Widok przeglądarki grupy zasobów AKS.](media/deploy-azure-kubernetes-service/aks-cluster-view.png)

<span data-ttu-id="06d0f-119">**Rysunek 4-17**.</span><span class="sxs-lookup"><span data-stu-id="06d0f-119">**Figure 4-17**.</span></span> <span data-ttu-id="06d0f-120">AKS widok grupy zasobów na platformie Azure.</span><span class="sxs-lookup"><span data-stu-id="06d0f-120">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="06d0f-121">Grupa zasobów klastra AKS:</span><span class="sxs-lookup"><span data-stu-id="06d0f-121">The AKS cluster resource group:</span></span>

![Widok przeglądarki grupy zasobów usługi Azure AKS.](media/deploy-azure-kubernetes-service/aks-resource-group-view.png)

<span data-ttu-id="06d0f-123">**Rysunek 4-18**.</span><span class="sxs-lookup"><span data-stu-id="06d0f-123">**Figure 4-18**.</span></span> <span data-ttu-id="06d0f-124">Widok AKS na platformie Azure.</span><span class="sxs-lookup"><span data-stu-id="06d0f-124">AKS view from Azure.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06d0f-125">Ogólnie rzecz biorąc nie trzeba modyfikować zasobów w grupie zasobów klastra AKS.</span><span class="sxs-lookup"><span data-stu-id="06d0f-125">In general, you shouldn't need to modify the resources in the AKS cluster resource group.</span></span> <span data-ttu-id="06d0f-126">Na przykład grupa zasobów jest usuwana po usunięciu klastra AKS.</span><span class="sxs-lookup"><span data-stu-id="06d0f-126">For example, the resource group is deleted when you delete the AKS cluster.</span></span>

<span data-ttu-id="06d0f-127">Można również wyświetlić węzeł utworzony przy użyciu `Azure CLI` i `Kubectl` .</span><span class="sxs-lookup"><span data-stu-id="06d0f-127">You can also view the node created using `Azure CLI` and `Kubectl`.</span></span>

<span data-ttu-id="06d0f-128">Po pierwsze, pobieranie poświadczeń:</span><span class="sxs-lookup"><span data-stu-id="06d0f-128">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Dane wyjściowe konsoli z powyższego polecenia: scalono "Eksploruj-Docker-AKS" jako bieżący kontekst w/Home/Miguel/.Kube/config.](media/deploy-azure-kubernetes-service/get-credentials-command-result.png)

<span data-ttu-id="06d0f-130">**Rysunek 4-19**.</span><span class="sxs-lookup"><span data-stu-id="06d0f-130">**Figure 4-19**.</span></span> <span data-ttu-id="06d0f-131">`aks get-credentials` wynik polecenia.</span><span class="sxs-lookup"><span data-stu-id="06d0f-131">`aks get-credentials` command result.</span></span>

<span data-ttu-id="06d0f-132">A następnie pobieranie węzłów z polecenia kubectl:</span><span class="sxs-lookup"><span data-stu-id="06d0f-132">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![Dane wyjściowe konsoli z powyższego polecenia: lista węzłów ze stanem, wiek (czas działania) i wersja](media/deploy-azure-kubernetes-service/kubectl-get-nodes-command-result.png)

<span data-ttu-id="06d0f-134">**Rysunek 4-20**.</span><span class="sxs-lookup"><span data-stu-id="06d0f-134">**Figure 4-20**.</span></span> <span data-ttu-id="06d0f-135">`kubectl get nodes` wynik polecenia.</span><span class="sxs-lookup"><span data-stu-id="06d0f-135">`kubectl get nodes` command result.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="06d0f-136">[Poprzedni](orchestrate-high-scalability-availability.md) 
>  [Dalej](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="06d0f-136">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
