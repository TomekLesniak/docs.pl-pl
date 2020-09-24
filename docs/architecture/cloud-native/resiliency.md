---
title: Odporność rozwiązań natywnych dla chmury
description: Tworzenie architektury natywnych aplikacji .NET w chmurze dla platformy Azure | Natywna odporność w chmurze
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 5c4fb261515c151fd666cc33cbb020447716c814
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163560"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="2c500-103">Odporność rozwiązań natywnych dla chmury</span><span class="sxs-lookup"><span data-stu-id="2c500-103">Cloud-native resiliency</span></span>

<span data-ttu-id="2c500-104">Odporność to zdolność systemu do reagowania na awarie i nadal pozostaje funkcjonalna.</span><span class="sxs-lookup"><span data-stu-id="2c500-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="2c500-105">Nie dotyczy to unikania awarii, ale akceptowania błędów i konstruowania usług natywnych w chmurze w celu reagowania na nie.</span><span class="sxs-lookup"><span data-stu-id="2c500-105">It's not about avoiding failure, but accepting failure and constructing your cloud-native services to respond to it.</span></span> <span data-ttu-id="2c500-106">Chcesz szybko przywrócić stan w pełni funkcjonalny.</span><span class="sxs-lookup"><span data-stu-id="2c500-106">You want to return to a fully functioning state quickly as possible.</span></span>

<span data-ttu-id="2c500-107">W przeciwieństwie do tradycyjnych aplikacji monolitycznych, gdzie wszystko działa razem w pojedynczym procesie, systemy natywne w chmurze stosują architekturę rozproszoną, jak pokazano na rysunku 6-1:</span><span class="sxs-lookup"><span data-stu-id="2c500-107">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace a distributed architecture as shown in Figure 6-1:</span></span>

![Rozproszone środowisko natywne w chmurze](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="2c500-109">**Rysunek 6-1.**</span><span class="sxs-lookup"><span data-stu-id="2c500-109">**Figure 6-1.**</span></span> <span data-ttu-id="2c500-110">Rozproszone środowisko natywne w chmurze</span><span class="sxs-lookup"><span data-stu-id="2c500-110">Distributed cloud-native environment</span></span>

<span data-ttu-id="2c500-111">Na powyższej ilustracji każda mikrousługa i oparta na chmurze [Usługa do tworzenia kopii zapasowych](https://12factor.net/backing-services) jest wykonywana w osobnym procesie, między infrastrukturą serwera, komunikujących się za pośrednictwem wywołań sieciowych.</span><span class="sxs-lookup"><span data-stu-id="2c500-111">In the previous figure, each microservice and cloud-based [backing service](https://12factor.net/backing-services) execute in a separate process, across server infrastructure, communicating via network-based calls.</span></span>

<span data-ttu-id="2c500-112">W tym środowisku usługa musi być wrażliwa na wiele różnych wyzwań:</span><span class="sxs-lookup"><span data-stu-id="2c500-112">Operating in this environment, a service must be sensitive to many different challenges:</span></span>

- <span data-ttu-id="2c500-113">Nieoczekiwane opóźnienie sieci — czas przesyłania żądania usługi do odbiornika i z powrotem.</span><span class="sxs-lookup"><span data-stu-id="2c500-113">Unexpected network latency - the time for a service request to travel to the receiver and back.</span></span>

- <span data-ttu-id="2c500-114">[Awarie przejściowe](/azure/architecture/best-practices/transient-faults) — krótkie Błędy łączności sieciowej.</span><span class="sxs-lookup"><span data-stu-id="2c500-114">[Transient faults](/azure/architecture/best-practices/transient-faults) - short-lived network connectivity errors.</span></span>

- <span data-ttu-id="2c500-115">Zatorem przez długotrwałą operację synchroniczną.</span><span class="sxs-lookup"><span data-stu-id="2c500-115">Blockage by a long-running synchronous operation.</span></span>

- <span data-ttu-id="2c500-116">Proces hosta, który uległ awarii i jest ponownie uruchamiany lub przenoszony.</span><span class="sxs-lookup"><span data-stu-id="2c500-116">A host process that has crashed and is being restarted or moved.</span></span>

- <span data-ttu-id="2c500-117">Przeciążona mikrousługa, która nie może odpowiadać przez krótki czas.</span><span class="sxs-lookup"><span data-stu-id="2c500-117">An overloaded microservice that can't respond for a short time.</span></span>

- <span data-ttu-id="2c500-118">Operacja programu Orchestrator w locie, taka jak uaktualnienie stopniowe lub przeniesienie usługi z jednego węzła do drugiego.</span><span class="sxs-lookup"><span data-stu-id="2c500-118">An in-flight orchestrator operation such as a rolling upgrade or moving a service from one node to another.</span></span>

- <span data-ttu-id="2c500-119">Awarie sprzętu.</span><span class="sxs-lookup"><span data-stu-id="2c500-119">Hardware failures.</span></span>

<span data-ttu-id="2c500-120">Platformy chmury mogą wykrywać i ograniczać wiele problemów z infrastrukturą.</span><span class="sxs-lookup"><span data-stu-id="2c500-120">Cloud platforms can detect and mitigate many of these infrastructure issues.</span></span> <span data-ttu-id="2c500-121">Może on zostać ponownie uruchomiony, przeskalowany w poziomie i nawet rozdystrybuowany do innego węzła.</span><span class="sxs-lookup"><span data-stu-id="2c500-121">It may restart, scale out, and even redistribute your service to a different node.</span></span>  <span data-ttu-id="2c500-122">Aby jednak w pełni korzystać z tej wbudowanej ochrony, należy zaprojektować usługi w celu reagowania na nie i rozwoju w tym środowisku dynamicznym.</span><span class="sxs-lookup"><span data-stu-id="2c500-122">However, to take full advantage of this built-in protection, you must design your services to react to it and thrive in this dynamic environment.</span></span>

<span data-ttu-id="2c500-123">W poniższych sekcjach opisano techniki obronne, które mogą wykorzystać usługa i zarządzane zasoby w chmurze w celu zminimalizowania przestojów i przerw w działaniu.</span><span class="sxs-lookup"><span data-stu-id="2c500-123">In the following sections, we'll explore defensive techniques that your service and managed cloud resources can leverage to minimize downtime and disruption.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2c500-124">[Poprzedni](elastic-search-in-azure.md) 
> [Dalej](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="2c500-124">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>
