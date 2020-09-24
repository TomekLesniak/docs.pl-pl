---
title: Zarządzanie środowiskami produkcyjnymi platformy Docker
description: Poznaj najważniejsze kwestie związane z zarządzaniem środowiskiem produkcyjnym opartym na kontenerach.
ms.date: 08/06/2020
ms.openlocfilehash: dbc5f541478410060420f95f32e4ff5291354075
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160648"
---
# <a name="manage-production-docker-environments"></a>Zarządzanie środowiskami produkcyjnymi platformy Docker

Zarządzanie klastrem i aranżacja to proces sterowania grupą hostów. Może to dotyczyć dodawania i usuwania hostów z klastra, uzyskiwania informacji o bieżącym stanie hostów i kontenerów oraz uruchamiania i zatrzymywania procesów. Zarządzanie klastrem i aranżacja są ściśle powiązane z planowaniem, ponieważ harmonogram musi mieć dostęp do każdego hosta w klastrze w celu zaplanowania usług. Z tego powodu to samo narzędzie jest często używane w obu celach.

## <a name="container-service-and-management-tools"></a>Usługa kontenerów i narzędzia do zarządzania

Usługa Container Service umożliwia szybkie wdrażanie popularnych rozwiązań typu "klaster" typu "open source" i "aranżacja". Używa obrazów platformy Docker, aby upewnić się, że kontenery aplikacji są w pełni przenośne. Za pomocą usługi Container Service można wdrożyć systemy DC/OS (obsługiwane przez mesosphere i Apache Mesos) oraz klastry Docker Swarm z szablonami Azure Resource Manager lub Azure Portal, aby mieć pewność, że można skalować te aplikacje do tysięcy — nawet dziesiątki tysięcy — kontenerów.

Te klastry są wdrażane za pomocą zestawów skali maszyny wirtualnej Azure, a podczas pracy korzystają z ofert magazynu i pracy w sieci na platformie Azure. Aby uzyskać dostęp do usługi Container Service, musisz mieć subskrypcję platformy Azure. Usługa Container Service umożliwia korzystanie z funkcji klasy korporacyjnej platformy Azure z zachowaniem możliwości przenoszenia aplikacji, w tym w warstwach aranżacji.

W tabeli 6-1 przedstawiono typowe narzędzia do zarządzania związane z koordynatorami, harmonogramami i platformą klastrowania.

**Tabela 6-1**. Narzędzia do zarządzania platformy Docker

| Narzędzia do zarządzania | Opis | Powiązane usługi Orchestrator |
|------------------|-------------|-----------------------|
| [Azure Monitor kontenerów](/azure/monitoring/monitoring-container-insights-overview) | Dedykowane narzędzie do zarządzania Kubernetes platformy Azure | Usługi Azure Kubernetes Service (AKS) |
| [Interfejs użytkownika sieci Web Kubernetes (pulpit nawigacyjny)](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) | Narzędzie do zarządzania Kubernetes, które umożliwia monitorowanie lokalnego klastra Kubernetes i zarządzanie nim | Azure Kubernetes Service (AKS)<br/>Kubernetes lokalny |
| [Azure Portal Service Fabric](/azure/service-fabric/service-fabric-cluster-creation-via-portal)<br/>[Service Fabric Explorer platformy Azure](/azure/service-fabric/service-fabric-visualizing-your-cluster) | Wersja online i klasyczna do zarządzania klastrami Service Fabric, na platformie Azure, lokalnie i w innych chmurach | Azure Service Fabric |
| [Monitorowanie kontenerów (Azure Monitor)](/azure/azure-monitor/insights/containers) | Ogólne rozwiązanie do monitorowania zarządzania kontenerami. Może zarządzać klastrami Kubernetes za [Azure monitor kontenerów](/azure/monitoring/monitoring-container-insights-overview). | Azure Service Fabric<br/>Azure Kubernetes Service (AKS)<br/>Mesosphere DC/OS i innych. |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Kolejną opcją dla wdrożenia klastra i zarządzania jest usługa Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) to platforma mikrousług firmy Microsoft, która obejmuje aranżację kontenera, a także modele programowania dla deweloperów, które umożliwiają tworzenie wysoce skalowalnych aplikacji mikrousług. Service Fabric obsługuje platformę Docker w kontenerach systemu Linux i Windows oraz mogą działać na serwerach z systemami Windows i Linux.

Poniżej przedstawiono Service Fabric narzędzia do zarządzania:

- [Azure Portal dla Service Fabric](/azure/service-fabric/service-fabric-cluster-creation-via-portal) operacji związanych z klastrem (Tworzenie/aktualizowanie/usuwanie) klastra lub Konfigurowanie jego infrastruktury (maszyn wirtualnych, modułu równoważenia obciążenia, sieci itp.)

- [Azure Service Fabric Explorer](/azure/service-fabric/service-fabric-visualizing-your-cluster) to WYSPECJALIZOWANY interfejs użytkownika sieci Web i narzędzie do obsługi wielu platform, które zapewnia wgląd w dane i pewne operacje w klastrze Service Fabric, z punktu widzenia węzłów/maszyn wirtualnych oraz z punktu widzenia aplikacji i usług.

>[!div class="step-by-step"]
>[Poprzedni](run-microservices-based-applications-in-production.md) 
> [Dalej](monitor-containerized-application-services.md)
