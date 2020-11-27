---
title: 205 — OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: c36294a4a430c3e372e8213246e85dba45ce03c8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286022"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="f72a0-102">205 — OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="f72a0-102">205 - OperationInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="f72a0-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="f72a0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f72a0-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="f72a0-104">ID</span></span>|<span data-ttu-id="f72a0-105">205</span><span class="sxs-lookup"><span data-stu-id="f72a0-105">205</span></span>|  
|<span data-ttu-id="f72a0-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="f72a0-106">Keywords</span></span>|<span data-ttu-id="f72a0-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f72a0-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f72a0-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="f72a0-108">Level</span></span>|<span data-ttu-id="f72a0-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="f72a0-109">Information</span></span>|  
|<span data-ttu-id="f72a0-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="f72a0-110">Channel</span></span>|<span data-ttu-id="f72a0-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="f72a0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f72a0-112">Opis</span><span class="sxs-lookup"><span data-stu-id="f72a0-112">Description</span></span>  

 <span data-ttu-id="f72a0-113">To zdarzenie jest emitowane tuż przed rozpoczęciem domyślnego modelu usługi `OperationInvoker` wywołanie metody.</span><span class="sxs-lookup"><span data-stu-id="f72a0-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f72a0-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="f72a0-114">Message</span></span>  

 <span data-ttu-id="f72a0-115">OperationInvoker wywołała metodę ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="f72a0-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="f72a0-116">Informacje o wywołującym: ' %2 '.</span><span class="sxs-lookup"><span data-stu-id="f72a0-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f72a0-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f72a0-117">Details</span></span>  
  
|<span data-ttu-id="f72a0-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="f72a0-118">Data Item Name</span></span>|<span data-ttu-id="f72a0-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="f72a0-119">Data Item Type</span></span>|<span data-ttu-id="f72a0-120">Opis</span><span class="sxs-lookup"><span data-stu-id="f72a0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f72a0-121">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="f72a0-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="f72a0-122">Nazwa środowiska CLR metody, która została wywołana przez `OperationInvoker` .</span><span class="sxs-lookup"><span data-stu-id="f72a0-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="f72a0-123">Informacje o wywołującym</span><span class="sxs-lookup"><span data-stu-id="f72a0-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="f72a0-124">Adres IP i numer portu klienta w formacie "IPAddress: numer_portu".</span><span class="sxs-lookup"><span data-stu-id="f72a0-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="f72a0-125">Dwie wartości są pobierane z właściwości komunikatu "System. ServiceModel. Channels. RemoteEndpointMessageProperty" w ramach kontekstu operacji.</span><span class="sxs-lookup"><span data-stu-id="f72a0-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="f72a0-126">Należy pamiętać, że w przypadku powiązań innych niż TCP ta wartość `null` .</span><span class="sxs-lookup"><span data-stu-id="f72a0-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="f72a0-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="f72a0-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="f72a0-128">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="f72a0-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f72a0-129">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="f72a0-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f72a0-130">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="f72a0-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f72a0-131">Wywołując</span><span class="sxs-lookup"><span data-stu-id="f72a0-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f72a0-132">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f72a0-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
