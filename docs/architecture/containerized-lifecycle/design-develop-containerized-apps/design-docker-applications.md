---
title: Projektowanie aplikacji platformy Docker
description: Zapoznaj się z tym artykułem, aby uzyskać szczegółowy przewodnik dotyczący architektury mikrousług, ponieważ jest to temat, którego nie opisano w tym przewodniku.
ms.date: 08/06/2020
ms.openlocfilehash: b63d4344abb358a393587bdacf91f6091b531af0
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915980"
---
# <a name="design-docker-applications"></a><span data-ttu-id="f3122-103">Projektowanie aplikacji platformy Docker</span><span class="sxs-lookup"><span data-stu-id="f3122-103">Design Docker applications</span></span>

<span data-ttu-id="f3122-104">Rozdział 1 wprowadził podstawowe koncepcje dotyczące kontenerów i platformy Docker.</span><span class="sxs-lookup"><span data-stu-id="f3122-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="f3122-105">Te informacje to podstawowy poziom informacji, które należy wykonać, aby rozpocząć pracę.</span><span class="sxs-lookup"><span data-stu-id="f3122-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="f3122-106">Jednak aplikacje dla przedsiębiorstw mogą być złożone i składać się z wielu usług zamiast jednej usługi lub kontenera.</span><span class="sxs-lookup"><span data-stu-id="f3122-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="f3122-107">W przypadku tych opcjonalnych przypadków użycia należy poznać dodatkowe podejścia do projektowania, takie jak architektura zorientowana na usługę (SOA) i bardziej zaawansowane koncepcje mikrousług i koncepcje aranżacji kontenerów.</span><span class="sxs-lookup"><span data-stu-id="f3122-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="f3122-108">Zakres tego dokumentu nie jest ograniczony do mikrousług, ale do dowolnego cyklu życia aplikacji platformy Docker, dlatego nie sprawdza architektury mikrousług, ponieważ można również używać kontenerów i platformy Docker z regularnymi zadaniami typu SOA, w tle lub zadaniami, a nawet z wbudowaną podejściem do wdrażania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f3122-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you can also use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="f3122-109">**Więcej informacji** Aby dowiedzieć się więcej na temat architektury aplikacji i mikrousług dla przedsiębiorstw, zapoznaj się z przewodnikiem [: Architektura sieci platformy .NET](../../microservices/index.md) , z której można pobrać aplikacje <https://aka.ms/MicroservicesEbook> .</span><span class="sxs-lookup"><span data-stu-id="f3122-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](../../microservices/index.md) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="f3122-110">Jednak zanim zaczniesz korzystać z cyklu życia aplikacji i DevOps, ważne jest, aby wiedzieć, jak planujesz projektowanie i konstruowanie aplikacji oraz jakie są opcje projektowania.</span><span class="sxs-lookup"><span data-stu-id="f3122-110">However, before you get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f3122-111">[Poprzedni](index.md) 
> [Dalej](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="f3122-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
