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
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Wdrażanie w usłudze Azure Kubernetes Service (AKS)

Można korzystać z AKS przy użyciu preferowanego systemu operacyjnego klienta (Windows, macOS lub Linux) z zainstalowanym interfejsem wiersza polecenia platformy Azure (Azure CLI). Aby uzyskać więcej informacji, zapoznaj się z [dokumentacją interfejsu wiersza polecenia platformy Azure](/cli/azure/?view=azure-cli-latest) i [Podręcznikiem instalacji](/cli/azure/install-azure-cli?view=azure-cli-latest) dla dostępnych środowisk.

## <a name="create-the-aks-environment-in-azure"></a>Tworzenie środowiska AKS na platformie Azure

Istnieje kilka sposobów tworzenia środowiska AKS. Można to zrobić za pomocą poleceń interfejsu wiersza polecenia platformy Azure lub przy użyciu Azure Portal.

W tym miejscu możesz zapoznać się z przykładami za pomocą interfejsu wiersza polecenia platformy Azure, aby utworzyć klaster i Azure Portal, aby przejrzeć wyniki. Musisz również mieć polecenia kubectl i Docker na komputerze deweloperskim.

## <a name="create-the-aks-cluster"></a>Tworzenie klastra AKS

Utwórz klaster AKS przy użyciu tego polecenia (Grupa zasobów musi istnieć):

```console
az aks create --resource-group explore-docker-aks-rg --name explore-docker-aks --node-vm-size Standard_B2s --node-count 1 --generate-ssh-keys --location westeurope
```

> [!NOTE]
> `--node-vm-size` `--node-count` Wartości parametrów i są wystarczające dla aplikacji przykładowej/deweloperskiej.

Po zakończeniu zadania tworzenia można zobaczyć:

- Klaster AKS utworzony w początkowej grupie zasobów
- Nowa, powiązana Grupa zasobów zawierająca zasoby związane z klastrem AKS, jak pokazano na poniższych ilustracjach.

Początkowa Grupa zasobów z klastrem AKS:

![Widok przeglądarki grupy zasobów AKS.](media/deploy-azure-kubernetes-service/aks-cluster-view.png)

**Rysunek 4-17**. AKS widok grupy zasobów na platformie Azure.

Grupa zasobów klastra AKS:

![Widok przeglądarki grupy zasobów usługi Azure AKS.](media/deploy-azure-kubernetes-service/aks-resource-group-view.png)

**Rysunek 4-18**. Widok AKS na platformie Azure.

> [!IMPORTANT]
> Ogólnie rzecz biorąc nie trzeba modyfikować zasobów w grupie zasobów klastra AKS. Na przykład grupa zasobów jest usuwana po usunięciu klastra AKS.

Można również wyświetlić węzeł utworzony przy użyciu `Azure CLI` i `Kubectl` .

Po pierwsze, pobieranie poświadczeń:

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Dane wyjściowe konsoli z powyższego polecenia: scalono "Eksploruj-Docker-AKS" jako bieżący kontekst w/Home/Miguel/.Kube/config.](media/deploy-azure-kubernetes-service/get-credentials-command-result.png)

**Rysunek 4-19**. `aks get-credentials` wynik polecenia.

A następnie pobieranie węzłów z polecenia kubectl:

```console
kubectl get nodes
```

![Dane wyjściowe konsoli z powyższego polecenia: lista węzłów ze stanem, wiek (czas działania) i wersja](media/deploy-azure-kubernetes-service/kubectl-get-nodes-command-result.png)

**Rysunek 4-20**. `kubectl get nodes` wynik polecenia.

> [!div class="step-by-step"]
> [Poprzedni](orchestrate-high-scalability-availability.md) 
>  [Dalej](docker-apps-development-environment.md)
