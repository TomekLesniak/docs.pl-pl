---
title: 202 — ClientMessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
ms.openlocfilehash: f05a0f817b8cb4857a4fa50eada15d3ff9e06855
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266626"
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="aceba-102">202 — ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="aceba-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="aceba-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="aceba-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aceba-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="aceba-104">ID</span></span>|<span data-ttu-id="aceba-105">202</span><span class="sxs-lookup"><span data-stu-id="aceba-105">202</span></span>|  
|<span data-ttu-id="aceba-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="aceba-106">Keywords</span></span>|<span data-ttu-id="aceba-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aceba-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="aceba-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="aceba-108">Level</span></span>|<span data-ttu-id="aceba-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="aceba-109">Information</span></span>|  
|<span data-ttu-id="aceba-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="aceba-110">Channel</span></span>|<span data-ttu-id="aceba-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="aceba-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aceba-112">Opis</span><span class="sxs-lookup"><span data-stu-id="aceba-112">Description</span></span>  

 <span data-ttu-id="aceba-113">To zdarzenie jest emitowane po wywołaniu metody przez model usługi `BeforeSendRequest` w Inspektorze komunikatów klienta.</span><span class="sxs-lookup"><span data-stu-id="aceba-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aceba-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="aceba-114">Message</span></span>  

 <span data-ttu-id="aceba-115">Dyspozytor wywołał element "BeforeSendRequest" na ClientMessageInspector typu "%1".</span><span class="sxs-lookup"><span data-stu-id="aceba-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aceba-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="aceba-116">Details</span></span>  
  
|<span data-ttu-id="aceba-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="aceba-117">Data Item Name</span></span>|<span data-ttu-id="aceba-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="aceba-118">Data Item Type</span></span>|<span data-ttu-id="aceba-119">Opis</span><span class="sxs-lookup"><span data-stu-id="aceba-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aceba-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="aceba-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="aceba-121">FullName CLR dla wywoływanego typu inspektora.</span><span class="sxs-lookup"><span data-stu-id="aceba-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="aceba-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="aceba-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="aceba-123">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="aceba-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="aceba-124">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="aceba-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="aceba-125">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="aceba-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="aceba-126">Wywołując</span><span class="sxs-lookup"><span data-stu-id="aceba-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="aceba-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aceba-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
