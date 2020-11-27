---
title: 222 — OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: 64b41ee78e943ca16eaa791133454ec62ccf6ed8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263090"
---
# <a name="222---operationfailed"></a><span data-ttu-id="2089b-102">222 — OperationFailed</span><span class="sxs-lookup"><span data-stu-id="2089b-102">222 - OperationFailed</span></span>

## <a name="properties"></a><span data-ttu-id="2089b-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="2089b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2089b-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="2089b-104">ID</span></span>|<span data-ttu-id="2089b-105">222</span><span class="sxs-lookup"><span data-stu-id="2089b-105">222</span></span>|  
|<span data-ttu-id="2089b-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="2089b-106">Keywords</span></span>|<span data-ttu-id="2089b-107">EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2089b-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2089b-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="2089b-108">Level</span></span>|<span data-ttu-id="2089b-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="2089b-109">Warning</span></span>|  
|<span data-ttu-id="2089b-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="2089b-110">Channel</span></span>|<span data-ttu-id="2089b-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="2089b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2089b-112">Opis</span><span class="sxs-lookup"><span data-stu-id="2089b-112">Description</span></span>  

 <span data-ttu-id="2089b-113">To zdarzenie jest emitowane, gdy domyślny model usługi `OperationInvoker` napotkał wyjątek podczas wywoływania jego metody.</span><span class="sxs-lookup"><span data-stu-id="2089b-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="2089b-114">Należy zauważyć, że wyjątki, które wynikają z `FaultException` spowodowania tego zdarzenia, nie są emitowane.</span><span class="sxs-lookup"><span data-stu-id="2089b-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2089b-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="2089b-115">Message</span></span>  

 <span data-ttu-id="2089b-116">Metoda "%1" zgłosiła nieobsługiwany wyjątek podczas wywoływania przez OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="2089b-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="2089b-117">Czas trwania wywołania metody to "%2" MS.</span><span class="sxs-lookup"><span data-stu-id="2089b-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2089b-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="2089b-118">Details</span></span>  
  
|<span data-ttu-id="2089b-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="2089b-119">Data Item Name</span></span>|<span data-ttu-id="2089b-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="2089b-120">Data Item Type</span></span>|<span data-ttu-id="2089b-121">Opis</span><span class="sxs-lookup"><span data-stu-id="2089b-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2089b-122">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="2089b-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="2089b-123">Nazwa środowiska CLR metody, która została wywołana przez `OperationInvoker` .</span><span class="sxs-lookup"><span data-stu-id="2089b-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="2089b-124">Czas trwania</span><span class="sxs-lookup"><span data-stu-id="2089b-124">Duration</span></span>|`xs:long`|<span data-ttu-id="2089b-125">Czas (w milisekundach), przez który miało `OperationInvoker` wywołać metodę.</span><span class="sxs-lookup"><span data-stu-id="2089b-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="2089b-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="2089b-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="2089b-127">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="2089b-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2089b-128">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="2089b-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2089b-129">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="2089b-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2089b-130">Wywołując</span><span class="sxs-lookup"><span data-stu-id="2089b-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2089b-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2089b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
