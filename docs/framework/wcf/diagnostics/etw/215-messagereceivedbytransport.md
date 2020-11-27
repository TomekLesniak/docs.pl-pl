---
title: 215 — MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: 2f247e751a0690f13d059eff29d633c6d047775d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279080"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="c532c-102">215 — MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="c532c-102">215 - MessageReceivedByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="c532c-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="c532c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c532c-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="c532c-104">ID</span></span>|<span data-ttu-id="c532c-105">215</span><span class="sxs-lookup"><span data-stu-id="c532c-105">215</span></span>|  
|<span data-ttu-id="c532c-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="c532c-106">Keywords</span></span>|<span data-ttu-id="c532c-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c532c-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="c532c-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="c532c-108">Level</span></span>|<span data-ttu-id="c532c-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="c532c-109">Information</span></span>|  
|<span data-ttu-id="c532c-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="c532c-110">Channel</span></span>|<span data-ttu-id="c532c-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="c532c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c532c-112">Opis</span><span class="sxs-lookup"><span data-stu-id="c532c-112">Description</span></span>  

 <span data-ttu-id="c532c-113">To zdarzenie występuje, gdy transport oparty na protokole TCP odbierze komunikat.</span><span class="sxs-lookup"><span data-stu-id="c532c-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="c532c-114">Należy pamiętać, że na poziomie transportu wiele komunikatów może być wymienianych między klientami i usługami w ramach jednej operacji.</span><span class="sxs-lookup"><span data-stu-id="c532c-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="c532c-115">Może to być spowodowane zachowaniem infrastruktury, tym dobrym przykładem.</span><span class="sxs-lookup"><span data-stu-id="c532c-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="c532c-116">W związku z tym liczba `MessageReceivedByTransport` wyemitowanych zdarzeń zależy od powiązania usługi i jego konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c532c-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c532c-117">To zdarzenie nie jest emitowane w przypadku transportów jednokierunkowych.</span><span class="sxs-lookup"><span data-stu-id="c532c-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c532c-118">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="c532c-118">Message</span></span>  

 <span data-ttu-id="c532c-119">Transport odebrał komunikat z ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="c532c-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c532c-120">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="c532c-120">Details</span></span>  
  
|<span data-ttu-id="c532c-121">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="c532c-121">Data Item Name</span></span>|<span data-ttu-id="c532c-122">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="c532c-122">Data Item Type</span></span>|<span data-ttu-id="c532c-123">Opis</span><span class="sxs-lookup"><span data-stu-id="c532c-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c532c-124">Adres nasłuchiwania</span><span class="sxs-lookup"><span data-stu-id="c532c-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="c532c-125">Adres, który odebrał wiadomość.</span><span class="sxs-lookup"><span data-stu-id="c532c-125">The address that received the message.</span></span>|  
|<span data-ttu-id="c532c-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="c532c-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="c532c-127">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="c532c-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="c532c-128">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="c532c-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="c532c-129">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="c532c-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="c532c-130">Wywołując</span><span class="sxs-lookup"><span data-stu-id="c532c-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c532c-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c532c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
