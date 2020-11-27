---
title: 217 — ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: e8aaf65bdff0718e932d07937e052541b7134f11
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278885"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="0d88d-102">217 — ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="0d88d-102">217 - ClientOperationPrepared</span></span>

## <a name="properties"></a><span data-ttu-id="0d88d-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="0d88d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d88d-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="0d88d-104">ID</span></span>|<span data-ttu-id="0d88d-105">217</span><span class="sxs-lookup"><span data-stu-id="0d88d-105">217</span></span>|  
|<span data-ttu-id="0d88d-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="0d88d-106">Keywords</span></span>|<span data-ttu-id="0d88d-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0d88d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0d88d-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="0d88d-108">Level</span></span>|<span data-ttu-id="0d88d-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="0d88d-109">Information</span></span>|  
|<span data-ttu-id="0d88d-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="0d88d-110">Channel</span></span>|<span data-ttu-id="0d88d-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="0d88d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0d88d-112">Opis</span><span class="sxs-lookup"><span data-stu-id="0d88d-112">Description</span></span>  

 <span data-ttu-id="0d88d-113">To zdarzenie jest emitowane przez klientów tuż przed wysłaniem operacji do usługi.</span><span class="sxs-lookup"><span data-stu-id="0d88d-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0d88d-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="0d88d-114">Message</span></span>  

 <span data-ttu-id="0d88d-115">Klient wykonuje akcję "%1" skojarzoną z kontraktem "%2".</span><span class="sxs-lookup"><span data-stu-id="0d88d-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="0d88d-116">Komunikat zostanie wysłany do "%3".</span><span class="sxs-lookup"><span data-stu-id="0d88d-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0d88d-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="0d88d-117">Details</span></span>  
  
|<span data-ttu-id="0d88d-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="0d88d-118">Data Item Name</span></span>|<span data-ttu-id="0d88d-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="0d88d-119">Data Item Type</span></span>|<span data-ttu-id="0d88d-120">Opis</span><span class="sxs-lookup"><span data-stu-id="0d88d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0d88d-121">Akcja</span><span class="sxs-lookup"><span data-stu-id="0d88d-121">Action</span></span>|`xs:string`|<span data-ttu-id="0d88d-122">Nagłówek akcji protokołu SOAP wiadomości wychodzącej.</span><span class="sxs-lookup"><span data-stu-id="0d88d-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="0d88d-123">Nazwa kontraktu</span><span class="sxs-lookup"><span data-stu-id="0d88d-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="0d88d-124">Nazwa kontraktu.</span><span class="sxs-lookup"><span data-stu-id="0d88d-124">The name of the contract.</span></span> <span data-ttu-id="0d88d-125">Przykład: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="0d88d-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="0d88d-126">Element docelowy</span><span class="sxs-lookup"><span data-stu-id="0d88d-126">Destination</span></span>|`xs:string`|<span data-ttu-id="0d88d-127">Adres punktu końcowego usługi, do którego zostanie wysłana wiadomość.</span><span class="sxs-lookup"><span data-stu-id="0d88d-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="0d88d-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="0d88d-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="0d88d-129">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="0d88d-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0d88d-130">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="0d88d-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0d88d-131">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="0d88d-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0d88d-132">Wywołując</span><span class="sxs-lookup"><span data-stu-id="0d88d-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0d88d-133">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0d88d-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
