---
title: Wzorce komunikacji rozwiązań natywnych dla chmury
description: Informacje o problemach z łącznością usług w aplikacjach natywnych w chmurze
author: robvet
ms.date: 08/31/2019
ms.openlocfilehash: 3bda9baa516b7bd8f893e0f58bbe5e2bfde2b61d
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214018"
---
# <a name="cloud-native-communication-patterns"></a><span data-ttu-id="a009b-103">Wzorce komunikacji rozwiązań natywnych dla chmury</span><span class="sxs-lookup"><span data-stu-id="a009b-103">Cloud-native communication patterns</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="a009b-104">Podczas konstruowania systemu natywnego w chmurze komunikacja jest istotną decyzją projektową.</span><span class="sxs-lookup"><span data-stu-id="a009b-104">When constructing a cloud-native system, communication becomes a significant design decision.</span></span> <span data-ttu-id="a009b-105">Jak aplikacja klienta frontonu komunikuje się z mikrousługą zaplecza?</span><span class="sxs-lookup"><span data-stu-id="a009b-105">How does a front-end client application communicate with a back-end microservice?</span></span> <span data-ttu-id="a009b-106">Jak usługa back-end komunikuje się ze sobą?</span><span class="sxs-lookup"><span data-stu-id="a009b-106">How do back-end microservices communicate with each other?</span></span> <span data-ttu-id="a009b-107">Jakie są zasady, wzorce i najlepsze rozwiązania, które należy wziąć pod uwagę podczas implementowania komunikacji w aplikacjach natywnych w chmurze?</span><span class="sxs-lookup"><span data-stu-id="a009b-107">What are the principles, patterns, and best practices to consider when implementing communication in cloud-native applications?</span></span>

## <a name="communication-considerations"></a><span data-ttu-id="a009b-108">Zagadnienia dotyczące komunikacji</span><span class="sxs-lookup"><span data-stu-id="a009b-108">Communication considerations</span></span>

<span data-ttu-id="a009b-109">W aplikacji monolitycznej komunikacja jest prosta.</span><span class="sxs-lookup"><span data-stu-id="a009b-109">In a monolithic application, communication is straightforward.</span></span> <span data-ttu-id="a009b-110">Moduły kodu są wykonywane razem w tym samym obszarze plików wykonywalnych (proces) na serwerze.</span><span class="sxs-lookup"><span data-stu-id="a009b-110">The code modules execute together in the same executable space (process) on a server.</span></span> <span data-ttu-id="a009b-111">Takie podejście może mieć zalety wydajności, ponieważ wszystkie elementy działają razem w pamięci współdzielonej, ale w przypadku ściśle sprzężonego kodu trudno zachować, rozwijać i skalować.</span><span class="sxs-lookup"><span data-stu-id="a009b-111">This approach can have performance advantages as everything runs together in shared memory, but results in tightly coupled code that becomes difficult to maintain, evolve, and scale.</span></span>

<span data-ttu-id="a009b-112">Systemy natywne w chmurze implementują architekturę opartą na mikrousługach z wieloma małymi, niezależnymi mikrousługami.</span><span class="sxs-lookup"><span data-stu-id="a009b-112">Cloud-native systems implement a microservice-based architecture with many small, independent microservices.</span></span> <span data-ttu-id="a009b-113">Każda mikrousługa jest wykonywana w osobnym procesie i zazwyczaj jest uruchamiana wewnątrz kontenera wdrożonego w *klastrze*.</span><span class="sxs-lookup"><span data-stu-id="a009b-113">Each microservice executes in a separate process and typically runs inside a container that is deployed to a *cluster*.</span></span>

<span data-ttu-id="a009b-114">Klaster grupuje pulę maszyn wirtualnych w celu tworzenia środowiska o wysokiej dostępności.</span><span class="sxs-lookup"><span data-stu-id="a009b-114">A cluster groups a pool of virtual machines together to form a highly available environment.</span></span> <span data-ttu-id="a009b-115">Są one zarządzane za pomocą narzędzia Orchestration, które jest odpowiedzialne za wdrażanie mikrousług kontenerów i zarządzanie nimi.</span><span class="sxs-lookup"><span data-stu-id="a009b-115">They're managed with an orchestration tool, which is responsible for deploying and managing the containerized microservices.</span></span> <span data-ttu-id="a009b-116">Rysunek 4-1 przedstawia klaster [Kubernetes](https://kubernetes.io) wdrożony w chmurze platformy Azure z w pełni zarządzanymi [usługami Kubernetes platformy Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes).</span><span class="sxs-lookup"><span data-stu-id="a009b-116">Figure 4-1 shows a [Kubernetes](https://kubernetes.io) cluster deployed into the Azure cloud with the fully managed [Azure Kubernetes Services](https://docs.microsoft.com/azure/aks/intro-kubernetes).</span></span>

![Klaster Kubernetes na platformie Azure](./media/kubernetes-cluster-in-azure.png)

<span data-ttu-id="a009b-118">**Rysunek 4-1**.</span><span class="sxs-lookup"><span data-stu-id="a009b-118">**Figure 4-1**.</span></span> <span data-ttu-id="a009b-119">Klaster Kubernetes na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="a009b-119">A Kubernetes cluster in Azure</span></span>

<span data-ttu-id="a009b-120">W całym klastrze mikrousługi komunikują się ze sobą za pośrednictwem interfejsów API i technologii obsługi komunikatów.</span><span class="sxs-lookup"><span data-stu-id="a009b-120">Across the cluster, microservices communicate with each other through APIs and messaging technologies.</span></span>

<span data-ttu-id="a009b-121">Chociaż zapewniają wiele korzyści, mikrousługi nie są bezpłatnymi obiadami.</span><span class="sxs-lookup"><span data-stu-id="a009b-121">While they provide many benefits, microservices are no free lunch.</span></span> <span data-ttu-id="a009b-122">Lokalne wywołania metod w procesie między składnikami są teraz zastępowane wywołaniami sieci.</span><span class="sxs-lookup"><span data-stu-id="a009b-122">Local in-process method calls between components are now replaced with network calls.</span></span> <span data-ttu-id="a009b-123">Każda mikrousługa musi komunikować się za pośrednictwem protokołu sieciowego, który dodaje złożoność do systemu:</span><span class="sxs-lookup"><span data-stu-id="a009b-123">Each microservice must communicate over a network protocol, which adds complexity to your system:</span></span>

- <span data-ttu-id="a009b-124">Przeciążenie sieci, opóźnienia i błędy przejściowe są stałą kwestią.</span><span class="sxs-lookup"><span data-stu-id="a009b-124">Network congestion, latency, and transient faults are a constant concern.</span></span>

- <span data-ttu-id="a009b-125">Odporność (czyli ponawianie nieudanych żądań) jest istotna.</span><span class="sxs-lookup"><span data-stu-id="a009b-125">Resiliency (that is, retrying failed requests) is essential.</span></span>

- <span data-ttu-id="a009b-126">Niektóre wywołania muszą być [idempotentne](https://www.restapitutorial.com/lessons/idempotency.html) , aby zachować spójny stan.</span><span class="sxs-lookup"><span data-stu-id="a009b-126">Some calls must be [idempotent](https://www.restapitutorial.com/lessons/idempotency.html) as to keep consistent state.</span></span>

- <span data-ttu-id="a009b-127">Każda mikrousługa musi uwierzytelniać i autoryzować wywołania.</span><span class="sxs-lookup"><span data-stu-id="a009b-127">Each microservice must authenticate and authorize calls.</span></span>

- <span data-ttu-id="a009b-128">Każdy komunikat musi być serializowany, a następnie deserializowany, co może być kosztowne.</span><span class="sxs-lookup"><span data-stu-id="a009b-128">Each message must be serialized and then deserialized - which can be expensive.</span></span>

- <span data-ttu-id="a009b-129">Szyfrowanie lub odszyfrowywanie wiadomości jest ważne.</span><span class="sxs-lookup"><span data-stu-id="a009b-129">Message encryption/decryption becomes important.</span></span>

<span data-ttu-id="a009b-130">Mikrousługi [książki .NET: Architektura kontenerów aplikacji](https://docs.microsoft.com/dotnet/standard/microservices-architecture/)platformy .NET, które są dostępne bezpłatnie od firmy Microsoft, zapewnia szczegółowe pokrycie wzorców komunikacji dla aplikacji mikrousług.</span><span class="sxs-lookup"><span data-stu-id="a009b-130">The book [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/standard/microservices-architecture/), available for free from Microsoft, provides an in-depth coverage of communication patterns for microservice applications.</span></span> <span data-ttu-id="a009b-131">W tym rozdziale udostępniamy ogólne omówienie tych wzorców wraz z opcjami implementacji dostępnymi w chmurze platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="a009b-131">In this chapter, we provide a high-level overview of these patterns along with implementation options available in the Azure cloud.</span></span>

<span data-ttu-id="a009b-132">W tym rozdziale będziemy najpierw rozwiązywać komunikaty między aplikacjami frontonu a mikrousługami zaplecza.</span><span class="sxs-lookup"><span data-stu-id="a009b-132">In this chapter, we'll first address communication between front-end applications and back-end microservices.</span></span> <span data-ttu-id="a009b-133">Następnie będziemy informować o mikrousługach zaplecza.</span><span class="sxs-lookup"><span data-stu-id="a009b-133">We'll then look at back-end microservices communicate with each other.</span></span> <span data-ttu-id="a009b-134">Będziemy poznać technologię komunikacji w górę i w gRPC.</span><span class="sxs-lookup"><span data-stu-id="a009b-134">We'll explore the up and gRPC communication technology.</span></span> <span data-ttu-id="a009b-135">Na koniec będziemy szukać nowych innowacyjnych wzorców komunikacji przy użyciu technologii siatki usług.</span><span class="sxs-lookup"><span data-stu-id="a009b-135">Finally, we'll look new innovative communication patterns using service mesh technology.</span></span> <span data-ttu-id="a009b-136">Zobaczymy również, w jaki sposób usługa Azure Cloud oferuje różne rodzaje *usług zapasowych* w celu obsługi komunikacji natywnej w chmurze.</span><span class="sxs-lookup"><span data-stu-id="a009b-136">We'll also see how the Azure cloud provides different kinds of *backing services* to support cloud-native communication.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a009b-137">[Poprzedni](other-deployment-options.md)
>[Następny](front-end-communication.md)</span><span class="sxs-lookup"><span data-stu-id="a009b-137">[Previous](other-deployment-options.md)
[Next](front-end-communication.md)</span></span>