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
# <a name="service-oriented-applications"></a><span data-ttu-id="c34d7-103">Aplikacje zorientowane na usługę</span><span class="sxs-lookup"><span data-stu-id="c34d7-103">Service-oriented applications</span></span>

<span data-ttu-id="c34d7-104">Architektura zorientowana na usługi (SOA) była nieużywanym terminem, który ma wiele różnych rzeczy.</span><span class="sxs-lookup"><span data-stu-id="c34d7-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="c34d7-105">Jednak jako typowy mianownik, Metoda SOA oznacza strukturę architektury aplikacji, przez złożenie jej w kilku usługach (najczęściej jako usługi HTTP), które mogą być klasyfikowane w różnych typach, takich jak podsystemy lub, w innych przypadkach, jako warstwy.</span><span class="sxs-lookup"><span data-stu-id="c34d7-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="c34d7-106">Obecnie te usługi można wdrożyć jako kontenery platformy Docker, co rozwiązuje problemy związane z wdrażaniem, ponieważ wszystkie zależności są zawarte w obrazie kontenera.</span><span class="sxs-lookup"><span data-stu-id="c34d7-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="c34d7-107">Jeśli jednak chcesz skalować w poziomie SOAs, mogą wystąpić problemy, Jeśli wdrażasz je na podstawie pojedynczych wystąpień.</span><span class="sxs-lookup"><span data-stu-id="c34d7-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="c34d7-108">To wyzwanie można obsłużyć przy użyciu oprogramowania Docker clusterer lub programu Orchestrator.</span><span class="sxs-lookup"><span data-stu-id="c34d7-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="c34d7-109">Aby poznać podejścia mikrousług, Zobacz więcej szczegółów w kolejnych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="c34d7-109">You'll get to look at orchestrators in greater detail in the next section, when you explore microservices approaches.</span></span>

<span data-ttu-id="c34d7-110">Kontenery platformy Docker są przydatne (ale nie są wymagane) dla tradycyjnych architektur zorientowanych na usługę i bardziej zaawansowanych architektur mikrousług.</span><span class="sxs-lookup"><span data-stu-id="c34d7-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="c34d7-111">Na koniec dnia rozwiązania klastrowania kontenerów są przydatne dla tradycyjnej architektury SOA i bardziej zaawansowanej architektury mikrousług, w której każda mikrousługa jest właścicielem modelu danych.</span><span class="sxs-lookup"><span data-stu-id="c34d7-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="c34d7-112">Dzięki wielu baz danych można także skalować warstwę danych zamiast pracować z monolitycznymi bazami danych udostępnionymi przez usługi SOA.</span><span class="sxs-lookup"><span data-stu-id="c34d7-112">And thanks to multiple databases, you can also scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="c34d7-113">Jednak dyskusja dotycząca podziału danych ma wyłącznie na celu architekturę i projektowanie.</span><span class="sxs-lookup"><span data-stu-id="c34d7-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c34d7-114">[Poprzedni](state-and-data-in-docker-applications.md) 
> [Dalej](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="c34d7-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
