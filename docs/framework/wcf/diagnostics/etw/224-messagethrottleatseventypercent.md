---
title: 224 — MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 26b860b88313a971960a65b599562ef1ccb4e7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243524"
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="a1f03-102">224 — MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="a1f03-102">224 - MessageThrottleAtSeventyPercent</span></span>

## <a name="properties"></a><span data-ttu-id="a1f03-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="a1f03-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a1f03-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="a1f03-104">ID</span></span>|<span data-ttu-id="a1f03-105">224</span><span class="sxs-lookup"><span data-stu-id="a1f03-105">224</span></span>|  
|<span data-ttu-id="a1f03-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="a1f03-106">Keywords</span></span>|<span data-ttu-id="a1f03-107">EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a1f03-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a1f03-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="a1f03-108">Level</span></span>|<span data-ttu-id="a1f03-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="a1f03-109">Warning</span></span>|  
|<span data-ttu-id="a1f03-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="a1f03-110">Channel</span></span>|<span data-ttu-id="a1f03-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="a1f03-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a1f03-112">Opis</span><span class="sxs-lookup"><span data-stu-id="a1f03-112">Description</span></span>  

 <span data-ttu-id="a1f03-113">Po przekroczeniu jednego z głównych przepustnic usługi `MessageThrottleExceeded` zdarzenie jest emitowane.</span><span class="sxs-lookup"><span data-stu-id="a1f03-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="a1f03-114">Gdy wzrost liczby działań jest wolny i bieżąca wartość ograniczenia wynosi 70% bieżącego limitu, to zdarzenie jest emitowane.</span><span class="sxs-lookup"><span data-stu-id="a1f03-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="a1f03-115">Należy zauważyć, że to zdarzenie jest emitowane tylko raz, gdy działanie działa powoli.</span><span class="sxs-lookup"><span data-stu-id="a1f03-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="a1f03-116">Jeśli bieżąca wartość zostanie aktywowana z oznaczeniem 70 procent, (na przykład 70, 69, 70, 71, 70, 69), tylko pierwsze wystąpienie 70 procent powoduje wystąpienie zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="a1f03-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="a1f03-117">Po wydaniu tego zdarzenia przyszłe wystąpienia przekraczające limit ograniczenia ograniczają `MessageThrottleExceeded` zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="a1f03-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a1f03-118">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="a1f03-118">Message</span></span>  

 <span data-ttu-id="a1f03-119">Limit przepustnicy "%1" wynoszący "%2" wynosi od 70%%.</span><span class="sxs-lookup"><span data-stu-id="a1f03-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a1f03-120">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="a1f03-120">Details</span></span>  
  
|<span data-ttu-id="a1f03-121">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="a1f03-121">Data Item Name</span></span>|<span data-ttu-id="a1f03-122">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="a1f03-122">Data Item Type</span></span>|<span data-ttu-id="a1f03-123">Opis</span><span class="sxs-lookup"><span data-stu-id="a1f03-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a1f03-124">Nazwa ograniczenia</span><span class="sxs-lookup"><span data-stu-id="a1f03-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="a1f03-125">Nazwa ograniczenia, które zostało przekroczone.</span><span class="sxs-lookup"><span data-stu-id="a1f03-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="a1f03-126">`MaxConcurrentCalls`, `MaxConcurrentInstances` , Lub `MaxConcurrentSessions` ,</span><span class="sxs-lookup"><span data-stu-id="a1f03-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="a1f03-127">Limit</span><span class="sxs-lookup"><span data-stu-id="a1f03-127">Limit</span></span>|`xs:long`|<span data-ttu-id="a1f03-128">Aktualnie skonfigurowany limit ograniczania przepustowości.</span><span class="sxs-lookup"><span data-stu-id="a1f03-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="a1f03-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="a1f03-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="a1f03-130">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="a1f03-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a1f03-131">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="a1f03-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a1f03-132">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="a1f03-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a1f03-133">Wywołując</span><span class="sxs-lookup"><span data-stu-id="a1f03-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a1f03-134">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a1f03-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
