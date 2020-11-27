---
title: 214 — OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: 6147c70448efb122cb43a2b42a1e9b59980fab29
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278950"
---
# <a name="214---operationcompleted"></a><span data-ttu-id="42a29-102">214 — OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="42a29-102">214 - OperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="42a29-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="42a29-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42a29-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="42a29-104">ID</span></span>|<span data-ttu-id="42a29-105">214</span><span class="sxs-lookup"><span data-stu-id="42a29-105">214</span></span>|  
|<span data-ttu-id="42a29-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="42a29-106">Keywords</span></span>|<span data-ttu-id="42a29-107">HealthMonitoring, EndToEndMonitoring, rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="42a29-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="42a29-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="42a29-108">Level</span></span>|<span data-ttu-id="42a29-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="42a29-109">Information</span></span>|  
|<span data-ttu-id="42a29-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="42a29-110">Channel</span></span>|<span data-ttu-id="42a29-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="42a29-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="42a29-112">Opis</span><span class="sxs-lookup"><span data-stu-id="42a29-112">Description</span></span>  

 <span data-ttu-id="42a29-113">To zdarzenie jest emitowane, gdy domyślny model usług `OperationInvoker` zakończył wywołanie metody bez zgłaszania wyjątku przez tę metodę.</span><span class="sxs-lookup"><span data-stu-id="42a29-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="42a29-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="42a29-114">Message</span></span>  

 <span data-ttu-id="42a29-115">OperationInvoker ukończył wywołanie metody "%1".</span><span class="sxs-lookup"><span data-stu-id="42a29-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="42a29-116">Czas trwania wywołania metody to "%2" MS.</span><span class="sxs-lookup"><span data-stu-id="42a29-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="42a29-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="42a29-117">Details</span></span>  
  
|<span data-ttu-id="42a29-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="42a29-118">Data Item Name</span></span>|<span data-ttu-id="42a29-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="42a29-119">Data Item Type</span></span>|<span data-ttu-id="42a29-120">Opis</span><span class="sxs-lookup"><span data-stu-id="42a29-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="42a29-121">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="42a29-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="42a29-122">Nazwa środowiska CLR metody, która została wywołana przez `OperationInvoker` .</span><span class="sxs-lookup"><span data-stu-id="42a29-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="42a29-123">Czas trwania</span><span class="sxs-lookup"><span data-stu-id="42a29-123">Duration</span></span>|`xs:long`|<span data-ttu-id="42a29-124">Czas (w milisekundach), przez który miało `OperationInvoker` wywołać metodę.</span><span class="sxs-lookup"><span data-stu-id="42a29-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="42a29-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="42a29-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="42a29-126">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="42a29-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="42a29-127">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="42a29-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="42a29-128">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="42a29-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="42a29-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="42a29-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="42a29-130">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="42a29-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
