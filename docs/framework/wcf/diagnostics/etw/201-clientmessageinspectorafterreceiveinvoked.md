---
title: 201 — ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: d84f6c6f38868f7915caaaf87e15885099b65456
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266678"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="16e31-102">201 — ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="16e31-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="16e31-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="16e31-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="16e31-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="16e31-104">ID</span></span>|<span data-ttu-id="16e31-105">201</span><span class="sxs-lookup"><span data-stu-id="16e31-105">201</span></span>|  
|<span data-ttu-id="16e31-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="16e31-106">Keywords</span></span>|<span data-ttu-id="16e31-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="16e31-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="16e31-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="16e31-108">Level</span></span>|<span data-ttu-id="16e31-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="16e31-109">Information</span></span>|  
|<span data-ttu-id="16e31-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="16e31-110">Channel</span></span>|<span data-ttu-id="16e31-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="16e31-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="16e31-112">Opis</span><span class="sxs-lookup"><span data-stu-id="16e31-112">Description</span></span>  

 <span data-ttu-id="16e31-113">To zdarzenie jest emitowane po wywołaniu metody przez model usługi `AfterReceiveReply` w Inspektorze komunikatów klienta.</span><span class="sxs-lookup"><span data-stu-id="16e31-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="16e31-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="16e31-114">Message</span></span>  

 <span data-ttu-id="16e31-115">Dyspozytor wywołał element "AfterReceiveReply" na ClientMessageInspector typu "%1".</span><span class="sxs-lookup"><span data-stu-id="16e31-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="16e31-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="16e31-116">Details</span></span>  
  
|<span data-ttu-id="16e31-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="16e31-117">Data Item Name</span></span>|<span data-ttu-id="16e31-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="16e31-118">Data Item Type</span></span>|<span data-ttu-id="16e31-119">Opis</span><span class="sxs-lookup"><span data-stu-id="16e31-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="16e31-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="16e31-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="16e31-121">FullName CLR dla wywoływanego typu inspektora.</span><span class="sxs-lookup"><span data-stu-id="16e31-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="16e31-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="16e31-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="16e31-123">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="16e31-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="16e31-124">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="16e31-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="16e31-125">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="16e31-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="16e31-126">Wywołując</span><span class="sxs-lookup"><span data-stu-id="16e31-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="16e31-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="16e31-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
