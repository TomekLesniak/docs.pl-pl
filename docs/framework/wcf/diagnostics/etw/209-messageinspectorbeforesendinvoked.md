---
title: 209 — MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 50a9424f445781cac70d7d7fde58beea10231cfa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267757"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="630fb-102">209 — MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="630fb-102">209 - MessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="630fb-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="630fb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="630fb-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="630fb-104">ID</span></span>|<span data-ttu-id="630fb-105">209</span><span class="sxs-lookup"><span data-stu-id="630fb-105">209</span></span>|  
|<span data-ttu-id="630fb-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="630fb-106">Keywords</span></span>|<span data-ttu-id="630fb-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="630fb-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="630fb-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="630fb-108">Level</span></span>|<span data-ttu-id="630fb-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="630fb-109">Information</span></span>|  
|<span data-ttu-id="630fb-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="630fb-110">Channel</span></span>|<span data-ttu-id="630fb-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="630fb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="630fb-112">Opis</span><span class="sxs-lookup"><span data-stu-id="630fb-112">Description</span></span>  

 <span data-ttu-id="630fb-113">To zdarzenie jest emitowane po wywołaniu metody przez model usługi `BeforeSend` w Inspektorze komunikatów.</span><span class="sxs-lookup"><span data-stu-id="630fb-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="630fb-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="630fb-114">Message</span></span>  

 <span data-ttu-id="630fb-115">Dyspozytor wywołał element "BeforeSendRequest" na MessageInspector typu "%1".</span><span class="sxs-lookup"><span data-stu-id="630fb-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="630fb-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="630fb-116">Details</span></span>  
  
|<span data-ttu-id="630fb-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="630fb-117">Data Item Name</span></span>|<span data-ttu-id="630fb-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="630fb-118">Data Item Type</span></span>|<span data-ttu-id="630fb-119">Opis</span><span class="sxs-lookup"><span data-stu-id="630fb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="630fb-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="630fb-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="630fb-121">FullName CLR typu wywoływanego `MessageInspector` .</span><span class="sxs-lookup"><span data-stu-id="630fb-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="630fb-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="630fb-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="630fb-123">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="630fb-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="630fb-124">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="630fb-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="630fb-125">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="630fb-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="630fb-126">Wywołując</span><span class="sxs-lookup"><span data-stu-id="630fb-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="630fb-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="630fb-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
