---
title: Aplikacje SOA
description: Należy pamiętać, że kontenery mogą być również przydatną opcją wdrażania dla aplikacji SOA.
ms.date: 08/06/2020
ms.openlocfilehash: 5cc616eaf3be31ae704320df6ec54deed9529989
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915259"
---
# <a name="service-oriented-applications"></a>Aplikacje zorientowane na usługę

Architektura zorientowana na usługi (SOA) była nieużywanym terminem, który ma wiele różnych rzeczy. Jednak jako typowy mianownik, Metoda SOA oznacza strukturę architektury aplikacji, przez złożenie jej w kilku usługach (najczęściej jako usługi HTTP), które mogą być klasyfikowane w różnych typach, takich jak podsystemy lub, w innych przypadkach, jako warstwy.

Obecnie te usługi można wdrożyć jako kontenery platformy Docker, co rozwiązuje problemy związane z wdrażaniem, ponieważ wszystkie zależności są zawarte w obrazie kontenera. Jeśli jednak chcesz skalować w poziomie SOAs, mogą wystąpić problemy, Jeśli wdrażasz je na podstawie pojedynczych wystąpień. To wyzwanie można obsłużyć przy użyciu oprogramowania Docker clusterer lub programu Orchestrator. Aby poznać podejścia mikrousług, Zobacz więcej szczegółów w kolejnych sekcjach.

Kontenery platformy Docker są przydatne (ale nie są wymagane) dla tradycyjnych architektur zorientowanych na usługę i bardziej zaawansowanych architektur mikrousług.

Na koniec dnia rozwiązania klastrowania kontenerów są przydatne dla tradycyjnej architektury SOA i bardziej zaawansowanej architektury mikrousług, w której każda mikrousługa jest właścicielem modelu danych. Dzięki wielu baz danych można także skalować warstwę danych zamiast pracować z monolitycznymi bazami danych udostępnionymi przez usługi SOA. Jednak dyskusja dotycząca podziału danych ma wyłącznie na celu architekturę i projektowanie.

>[!div class="step-by-step"]
>[Poprzedni](state-and-data-in-docker-applications.md) 
> [Dalej](orchestrate-high-scalability-availability.md)
