---
title: 499 — TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: dc47aa36b5a409c89aaf7963ce51f11cdf84b0fc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247580"
---
# <a name="499---transferemitted"></a><span data-ttu-id="bf7ac-102">499 — TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="bf7ac-102">499 - TransferEmitted</span></span>

## <a name="properties"></a><span data-ttu-id="bf7ac-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="bf7ac-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf7ac-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="bf7ac-104">ID</span></span>|<span data-ttu-id="bf7ac-105">499</span><span class="sxs-lookup"><span data-stu-id="bf7ac-105">499</span></span>|  
|<span data-ttu-id="bf7ac-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="bf7ac-106">Keywords</span></span>|<span data-ttu-id="bf7ac-107">Rozwiązywanie problemów, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="bf7ac-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="bf7ac-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="bf7ac-108">Level</span></span>|<span data-ttu-id="bf7ac-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="bf7ac-109">LogAlways</span></span>|  
|<span data-ttu-id="bf7ac-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="bf7ac-110">Channel</span></span>|<span data-ttu-id="bf7ac-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="bf7ac-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bf7ac-112">Opis</span><span class="sxs-lookup"><span data-stu-id="bf7ac-112">Description</span></span>  

 <span data-ttu-id="bf7ac-113">To zdarzenie jest emitowane, gdy następuje zdarzenie transferu.</span><span class="sxs-lookup"><span data-stu-id="bf7ac-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bf7ac-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="bf7ac-114">Message</span></span>  

 <span data-ttu-id="bf7ac-115">Wyemitowano zdarzenie transferu.</span><span class="sxs-lookup"><span data-stu-id="bf7ac-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bf7ac-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="bf7ac-116">Details</span></span>  
  
|<span data-ttu-id="bf7ac-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="bf7ac-117">Data Item Name</span></span>|<span data-ttu-id="bf7ac-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="bf7ac-118">Data Item Type</span></span>|<span data-ttu-id="bf7ac-119">Opis</span><span class="sxs-lookup"><span data-stu-id="bf7ac-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bf7ac-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="bf7ac-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="bf7ac-121">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="bf7ac-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="bf7ac-122">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="bf7ac-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="bf7ac-123">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="bf7ac-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="bf7ac-124">Wywołując</span><span class="sxs-lookup"><span data-stu-id="bf7ac-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bf7ac-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bf7ac-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
