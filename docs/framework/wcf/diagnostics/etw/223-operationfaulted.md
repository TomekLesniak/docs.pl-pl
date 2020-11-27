---
title: 223 — OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: 310e91320d27dd9817302fc14ef088d180152b73
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263077"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="ecf1b-102">223 — OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="ecf1b-102">223 - OperationFaulted</span></span>

## <a name="properties"></a><span data-ttu-id="ecf1b-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ecf1b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecf1b-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="ecf1b-104">ID</span></span>|<span data-ttu-id="ecf1b-105">223</span><span class="sxs-lookup"><span data-stu-id="ecf1b-105">223</span></span>|  
|<span data-ttu-id="ecf1b-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="ecf1b-106">Keywords</span></span>|<span data-ttu-id="ecf1b-107">EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ecf1b-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ecf1b-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="ecf1b-108">Level</span></span>|<span data-ttu-id="ecf1b-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="ecf1b-109">Warning</span></span>|  
|<span data-ttu-id="ecf1b-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="ecf1b-110">Channel</span></span>|<span data-ttu-id="ecf1b-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="ecf1b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ecf1b-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ecf1b-112">Description</span></span>  

 <span data-ttu-id="ecf1b-113">To zdarzenie jest emitowane, gdy domyślny model usługi `OperationInvoker` napotkał wyjątek wynikający z `FaultException` wywołania podczas wywoływania metody.</span><span class="sxs-lookup"><span data-stu-id="ecf1b-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ecf1b-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="ecf1b-114">Message</span></span>  

 <span data-ttu-id="ecf1b-115">Metoda "%1" zgłosiła wyjątek FaultException w przypadku wywołania przez OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="ecf1b-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="ecf1b-116">Czas trwania wywołania metody to "%2" MS.</span><span class="sxs-lookup"><span data-stu-id="ecf1b-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ecf1b-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ecf1b-117">Details</span></span>  
  
|<span data-ttu-id="ecf1b-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="ecf1b-118">Data Item Name</span></span>|<span data-ttu-id="ecf1b-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="ecf1b-119">Data Item Type</span></span>|<span data-ttu-id="ecf1b-120">Opis</span><span class="sxs-lookup"><span data-stu-id="ecf1b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ecf1b-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="ecf1b-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="ecf1b-122">Nazwa środowiska CLR metody, która została wywołana przez `OperationInvoker` .</span><span class="sxs-lookup"><span data-stu-id="ecf1b-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="ecf1b-123">Czas trwania</span><span class="sxs-lookup"><span data-stu-id="ecf1b-123">Duration</span></span>|`xs:long`|<span data-ttu-id="ecf1b-124">Czas (w milisekundach), przez który miało `OperationInvoker` wywołać metodę.</span><span class="sxs-lookup"><span data-stu-id="ecf1b-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="ecf1b-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="ecf1b-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="ecf1b-126">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="ecf1b-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ecf1b-127">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="ecf1b-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ecf1b-128">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="ecf1b-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ecf1b-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="ecf1b-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ecf1b-130">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ecf1b-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
