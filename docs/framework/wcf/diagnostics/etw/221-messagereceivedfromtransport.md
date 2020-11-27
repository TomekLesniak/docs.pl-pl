---
title: 221 — MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 47e871b70e3ef2419543b4710c2988736665cb46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263103"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="218bb-102">221 — MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="218bb-102">221 - MessageReceivedFromTransport</span></span>

## <a name="properties"></a><span data-ttu-id="218bb-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="218bb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="218bb-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="218bb-104">ID</span></span>|<span data-ttu-id="218bb-105">221</span><span class="sxs-lookup"><span data-stu-id="218bb-105">221</span></span>|  
|<span data-ttu-id="218bb-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="218bb-106">Keywords</span></span>|<span data-ttu-id="218bb-107">EndToEndMonitoring, rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="218bb-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="218bb-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="218bb-108">Level</span></span>|<span data-ttu-id="218bb-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="218bb-109">Information</span></span>|  
|<span data-ttu-id="218bb-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="218bb-110">Channel</span></span>|<span data-ttu-id="218bb-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="218bb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="218bb-112">Opis</span><span class="sxs-lookup"><span data-stu-id="218bb-112">Description</span></span>  

 <span data-ttu-id="218bb-113">To zdarzenie jest emitowane, gdy model usługi odbiera komunikat z transportu.</span><span class="sxs-lookup"><span data-stu-id="218bb-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="218bb-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="218bb-114">Message</span></span>  

 <span data-ttu-id="218bb-115">Dyspozytor odebrał komunikat z transportu.</span><span class="sxs-lookup"><span data-stu-id="218bb-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="218bb-116">Identyfikator korelacji = = ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="218bb-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="218bb-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="218bb-117">Details</span></span>  
  
|<span data-ttu-id="218bb-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="218bb-118">Data Item Name</span></span>|<span data-ttu-id="218bb-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="218bb-119">Data Item Type</span></span>|<span data-ttu-id="218bb-120">Opis</span><span class="sxs-lookup"><span data-stu-id="218bb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="218bb-121">Identyfikator korelacji</span><span class="sxs-lookup"><span data-stu-id="218bb-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="218bb-122">Identyfikator działania służący do skorelowania `MessageSentToTransport` zdarzenia z usługi lub klienta do jego odpowiadającego `MessageReceivedFromTransport` na drugim końcu.</span><span class="sxs-lookup"><span data-stu-id="218bb-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="218bb-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="218bb-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="218bb-124">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="218bb-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="218bb-125">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="218bb-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="218bb-126">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="218bb-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="218bb-127">Wywołując</span><span class="sxs-lookup"><span data-stu-id="218bb-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="218bb-128">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="218bb-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
