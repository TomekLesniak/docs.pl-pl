---
title: 216 — MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: b3e9e1a48951ad5a2e5e7820dc1828c20e310635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278911"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="5ec52-102">216 — MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="5ec52-102">216 - MessageSentByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="5ec52-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="5ec52-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ec52-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="5ec52-104">ID</span></span>|<span data-ttu-id="5ec52-105">216</span><span class="sxs-lookup"><span data-stu-id="5ec52-105">216</span></span>|  
|<span data-ttu-id="5ec52-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="5ec52-106">Keywords</span></span>|<span data-ttu-id="5ec52-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5ec52-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5ec52-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="5ec52-108">Level</span></span>|<span data-ttu-id="5ec52-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="5ec52-109">Information</span></span>|  
|<span data-ttu-id="5ec52-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="5ec52-110">Channel</span></span>|<span data-ttu-id="5ec52-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="5ec52-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5ec52-112">Opis</span><span class="sxs-lookup"><span data-stu-id="5ec52-112">Description</span></span>  

 <span data-ttu-id="5ec52-113">To zdarzenie występuje, gdy transport oparty na protokole TCP wysyła komunikat.</span><span class="sxs-lookup"><span data-stu-id="5ec52-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="5ec52-114">Należy pamiętać, że na poziomie transportu wiele komunikatów może być wymienianych między klientami i usługami w ramach jednej operacji.</span><span class="sxs-lookup"><span data-stu-id="5ec52-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="5ec52-115">Może to być spowodowane zachowaniem infrastruktury, dobrym przykładem.</span><span class="sxs-lookup"><span data-stu-id="5ec52-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="5ec52-116">W związku z tym liczba zdarzeń **MessageSentByTransport** , które są emitowane, różni się w zależności od powiązania i konfiguracji usługi.</span><span class="sxs-lookup"><span data-stu-id="5ec52-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5ec52-117">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="5ec52-117">Message</span></span>  

 <span data-ttu-id="5ec52-118">Transport wysłał komunikat do "%1".</span><span class="sxs-lookup"><span data-stu-id="5ec52-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5ec52-119">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="5ec52-119">Details</span></span>  
  
|<span data-ttu-id="5ec52-120">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="5ec52-120">Data Item Name</span></span>|<span data-ttu-id="5ec52-121">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="5ec52-121">Data Item Type</span></span>|<span data-ttu-id="5ec52-122">Opis</span><span class="sxs-lookup"><span data-stu-id="5ec52-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5ec52-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="5ec52-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="5ec52-124">Adres, na który jest wysyłany komunikat żądania.</span><span class="sxs-lookup"><span data-stu-id="5ec52-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="5ec52-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="5ec52-125">HostReference</span></span>|<span data-ttu-id="5ec52-126">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ec52-126">xs:string</span></span>|<span data-ttu-id="5ec52-127">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="5ec52-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5ec52-128">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="5ec52-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5ec52-129">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="5ec52-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5ec52-130">Wywołując</span><span class="sxs-lookup"><span data-stu-id="5ec52-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5ec52-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5ec52-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
