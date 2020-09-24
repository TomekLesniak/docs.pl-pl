---
title: Monitorowanie w usługach Azure Kubernetes Services
description: Monitorowanie w usługach Azure Kubernetes Services
ms.date: 05/13/2020
ms.openlocfilehash: 3900f169b9be4f807e72392da38a1224d6ce28e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163703"
---
# <a name="monitoring-in-azure-kubernetes-services"></a>Monitorowanie w usługach Azure Kubernetes Services

Wbudowane rejestrowanie w Kubernetes jest pierwotne. Dostępne są jednak pewne doskonałe opcje pobierania dzienników z usługi Kubernetes oraz do miejsca, w którym można je prawidłowo analizować. Jeśli musisz monitorować klastry AKS, skonfigurowanie elastycznego stosu dla Kubernetes jest doskonałym rozwiązaniem.

## <a name="azure-monitor-for-containers"></a>Usługa Azure Monitor dla kontenerów

[Azure monitor kontenerów](/azure/azure-monitor/insights/container-insights-overview) obsługuje używanie dzienników nie tylko Kubernetes, ale również z innych aparatów aranżacji, takich jak DC/OS, Docker Swarm i Red Hat OpenShift.

![Wykorzystywanie dzienników z różnych kontenerów ](./media/containers-diagram.png)
 **rysunek 7-10**. Zużywanie dzienników z różnych kontenerów

[Prometheus](https://prometheus.io/) to popularne rozwiązanie do monitorowania metryk typu open source. Jest to część natywnej platformy obliczeniowej w chmurze. Zazwyczaj użycie Prometheus wymaga zarządzania serwerem Prometheus z własnym magazynem. Jednak [Azure monitor dla kontenerów zapewnia bezpośrednią integrację z punktami końcowymi metryk Prometheus](/azure/azure-monitor/insights/container-insights-prometheus-integration), więc nie jest wymagany oddzielny serwer.

Informacje o dziennikach i metrykach są zbierane nie tylko z kontenerów uruchomionych w klastrze, ale również z hostów klastra. Umożliwia on skorelowanie informacji dzienników z dwóch, ułatwiając śledzenie błędów.

Instalowanie modułów zbierających dzienniki różni się w zależności od klastrów [systemów Windows](/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) i [Linux](/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) . Jednak w obu przypadkach kolekcja dzienników jest zaimplementowana jako Kubernetes [elementu daemonset](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), co oznacza, że moduł zbierający dzienniki jest uruchamiany jako kontener na każdym z węzłów.

Niezależnie od tego, który koordynator lub system operacyjny działa demon Azure Monitor, informacje dziennika są przekazywane do tych samych Azure Monitor narzędzi, z którymi użytkownicy znają. Zapewnia to równoległe środowisko w środowiskach, które mieszają różne źródła dzienników, takie jak hybrydowe środowisko Kubernetes/Azure Functions.

![Przykładowy pulpit nawigacyjny przedstawiający rejestrowanie i informacje o metrykach z wielu uruchomionych kontenerów. ](./media/containers-dashboard.png)
 **Rysunek 7-11**. Przykładowy pulpit nawigacyjny przedstawiający rejestrowanie i informacje o metrykach z wielu uruchomionych kontenerów.

## <a name="logfinalize"></a>Log. Finalize ()

Rejestrowanie jest jednym z najbardziej zagłębień, a nie najważniejszych części wdrażania dowolnej aplikacji na dużą skalę. W miarę zwiększania rozmiaru i złożoności aplikacji jest to trudne do debugowania. Posiadanie dostępnych dzienników najwyższej jakości ułatwia debugowanie i przenosi je z obszaru "niemal niemożliwe" do "przyjemnego środowiska".

>[!div class="step-by-step"]
>[Poprzedni](logging-with-elastic-stack.md) 
> [Dalej](azure-monitor.md)
