---
title: Wprowadzenie do platformy i narzędzi firmy Microsoft dla aplikacji konteneryzowanych
description: Uzyskaj informacje o ofertach firmy Microsoft w celu obsługi cyklu życia aplikacji platformy Docker.
ms.date: 08/06/2020
ms.openlocfilehash: 72b98f945494936b7775a525297a17c5ce72c69a
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916061"
---
# <a name="introduction-to-the-microsoft-platform-andtools-for-containerized-apps"></a>Wprowadzenie do platformy i narzędzi firmy Microsoft dla aplikacji konteneryzowanych

*Wizja: Utwórz dostosowywalny cykl życia aplikacji klasy korporacyjnej, który obejmuje rozwój, operacje IT i zarządzanie produkcyjne.*

Rysunek 3-1 przedstawia główne filary w cyklu życia aplikacji platformy Docker sklasyfikowane według typu pracy dostarczonej przez wiele zespołów (Programowanie aplikacji, procesy infrastruktury DevOps oraz zarządzanie i operacje IT). Zwykle w przedsiębiorstwie profile "osoba" odpowiadające za poszczególne obszary są różne. Są to ich umiejętności.

![Dodaj nowe okno projektu w programie Visual Studio, wybierając ASP.NET Core aplikacji sieci Web.](media/index/microsoft-tools-contanerized-docker-app.png)

**Rysunek 3-1.** Główne filary w cyklu życia dla kontenerów platformy Docker z platformą i narzędziami firmy Microsoft

Przepływ pracy platformy Docker w ramach cyklu życia może być wstępnie zadawany w oparciu o "według domyślnych produktów", co ułatwia deweloperom szybkie rozpoczynanie pracy, ale jest to istotne w przypadku, gdy jest to konieczne, aby można było korzystać z różnych kontekstów z każdej organizacji lub przedsiębiorstwa. Infrastruktura przepływu pracy (składniki i produkty) musi być elastyczna, aby pokryć środowisko, w którym każda firma będzie w przyszłości, nawet z możliwością zamiany produktów programistycznych lub DevOps na inne. Ta elastyczność, otwartość i szeroki wybór technologii na platformie i infrastrukturze to dokładne priorytety firmy Microsoft dla kontenerów aplikacji platformy Docker, jak wyjaśniono w kolejnych działach.

Tabela 3-1 pokazuje, że zamiarem usługi Azure DevOps dla kontenerów aplikacji platformy Docker jest zapewnienie otwartego przepływu pracy DevOps, dzięki czemu można wybrać produkty, które mają być używane dla każdej fazy (firmy Microsoft lub innych firm), a jednocześnie zapewnić uproszczony przepływ pracy, który zapewnia już połączone produkty "według domyślnych"; Dzięki temu możesz szybko rozpocząć pracę z przepływem pracy DevOps na poziomie przedsiębiorstwa dla aplikacji platformy Docker.

**Tabela 3-1.** Przepływy pracy usługi Azure DevOps, otwarte dla dowolnej technologii

| Host | Technologie firmy Microsoft | Inna firma (podłączana do platformy Azure) |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Platforma dla aplikacji platformy Docker   | • Microsoft Visual Studio i Visual Studio Code<br /> • .NET<br /> • Microsoft Azure Kubernetes Service (AKS)<br /> • Azure Container Registry<br /> | • Dowolny edytor kodu (na przykład subwapno)<br /> • Dowolny język (Node.js, Java, go itp.)<br /> • Wszystkie usługi Orchestrator i Scheduler<br />  • Dowolny rejestr platformy Docker<br /> |
| DevOps dla aplikacji platformy Docker     | • Azure DevOps Services<br /> • Microsoft Team Foundation Server<br /> • Usługa Azure Kubernetes Service (AKS)<br /> | • GitHub, Git, Subversion itp.<br /> • Jenkins, Chef, Puppet, prędkość, CircleCI, TravisCI itd.<br /> • Lokalne centrum danych platformy Docker, Kubernetes, Mesos DC/OS itp.<br /> |
| Zarządzanie i monitorowanie  | • Azure Monitor | • Marathon, Chronos itp.<br />|

Platforma i narzędzia firmy Microsoft dla kontenerów platformy Docker, zgodnie z definicją w tabeli 3-1, składają się z następujących składników:

- **Platforma do tworzenia aplikacji platformy Docker** Tworzenie usługi lub zbieranie usług, które tworzą "aplikację". Platforma programistyczna zapewnia wszystkim deweloperom pracującym przed wypchnięciem ich kodu do udostępnionego repozytorium kodu. Opracowywanie usług, wdrożonych jako kontenery, są podobne do rozwoju tych samych aplikacji lub usług, które nie są zadokowane. Będziesz nadal korzystać z preferowanego języka (.NET, Node.js, go itp.) i preferowanego edytora lub środowiska IDE, takiego jak Visual Studio lub Visual Studio Code. Jednak zamiast rozważać rozwiązanie Docker jako miejsce docelowe wdrożenia, można opracowywać usługi w środowisku Docker. Kompiluj, uruchamiaj, Testuj i Debuguj swój kod w kontenerach lokalnie, dostarczając środowisko docelowe w czasie projektowania. Dostarczając środowisko docelowe lokalnie, kontenery platformy Docker skonfigurują co radykalnie pomożesz ulepszyć cykl życia DevOps. Program Visual Studio i Visual Studio Code mają rozszerzenia umożliwiające integrację kontenerów platformy Docker w ramach procesu tworzenia oprogramowania.

- **DevOps dla aplikacji platformy Docker** Deweloperzy tworzący aplikacje platformy Docker mogą korzystać z [usługi Azure DevOps](https://azure.microsoft.com/services/devops/) lub innych produktów innych firm, takich jak Jenkins, w celu utworzenia kompleksowego zautomatyzowanego zarządzania cyklem życia aplikacji (ALM).

  Dzięki usłudze Azure DevOps deweloperzy mogą tworzyć DevOps skoncentrowane na kontenerach dla szybkiego, iteracyjnego procesu, który obejmuje kontrolę kodu źródłowego z dowolnego miejsca (Azure DevOps-git, GitHub, dowolne zdalne repozytorium Git lub Subversion), ciągłą integrację (CI), wewnętrzne testy jednostkowe, testy integracji między kontenerami/usługami, ciągłe dostarczanie (CD) i Zarządzanie wersjami (RM). Deweloperzy mogą również zautomatyzować swoje wersje aplikacji platformy Docker w usłudze Azure Kubernetes Service (AKS), od projektowania do środowiska przejściowego i produkcyjnego.

- **Zarządzanie i monitorowanie** Umożliwia ona zarządzanie i monitorowanie aplikacji i usług produkcyjnych na kilka sposobów, co umożliwia integrację obu perspektyw w skonsolidowanym środowisku.

  - **Azure Portal**   Usługa Azure Kubernetes Service (AKS) ułatwia Konfigurowanie środowisk platformy Docker i zarządzanie nimi. Do wizualizacji i konfigurowania klastra można również użyć innych koordynatorów.

  - Narzędzia platformy Docker **Docker tools**   Możesz zarządzać aplikacjami kontenera za pomocą znanych narzędzi. Nie trzeba zmieniać istniejących praktyk zarządzania platformy Docker, aby przenosić obciążenia kontenerów do chmury. Skorzystaj z narzędzi do zarządzania aplikacjami, które są już znane, i Połącz się za pośrednictwem standardowych punktów końcowych interfejsu API dla wybranego koordynatora. Możesz również użyć innych narzędzi innych firm do zarządzania aplikacjami platformy Docker, a nawet narzędziami Docker interfejsu wiersza polecenia.

    Nawet jeśli znasz polecenia systemu Linux, możesz zarządzać aplikacjami kontenera przy użyciu systemu Microsoft Windows i programu PowerShell z systemem operacyjnym z systemem Linux oraz z systemami (Docker, Kubernetes...) uruchomionymi w tej funkcji podsystemu Linux. Dowiesz się więcej na temat używania tych narzędzi w podsystemie Linux przy użyciu ulubionego systemu operacyjnego Microsoft Windows w dalszej części tego podręcznika.

  - **Narzędzia**   Open Source Ponieważ AKS uwidacznia standardowe punkty końcowe interfejsu API dla aparatu aranżacji, najpopularniejsze narzędzia są zgodne z AKS i w większości przypadków będą wyłączane z tego pola — w tym Wizualizatory, monitorowanie, narzędzia wiersza polecenia, a nawet przyszłe narzędzia, gdy staną się dostępne.

  - **Azure monitor** To rozwiązanie platformy Azure do monitorowania każdego kąta w środowisku produkcyjnym. Aby monitorować produkcyjne aplikacje platformy Docker, wystarczy skonfigurować swój zestaw SDK w swoich usługach, aby można było uzyskać dane dziennika generowane przez system z aplikacji.

W związku z tym firma Microsoft oferuje kompletną podstawę do kompleksowego cyklu życia aplikacji platformy Docker. Jest to jednak *zbiór produktów i technologii, które umożliwiają opcjonalne Wybieranie i integrację z istniejącymi narzędziami i procesami*. Elastyczność w szerokim podejściu wraz z siłą na głębokości funkcji umieszczaj firmę Microsoft w silnym położeniu dla tworzenia kontenerów aplikacji platformy Docker.

>[!div class="step-by-step"]
>[Poprzedni](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md) 
> [Dalej](../design-develop-containerized-apps/index.md)
