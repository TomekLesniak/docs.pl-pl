---
title: 204 — ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: a7db8c9fa87518c59969f3089ff033fa8c912577
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275791"
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="e5140-102">204 — ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="e5140-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="e5140-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="e5140-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5140-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="e5140-104">ID</span></span>|<span data-ttu-id="e5140-105">204</span><span class="sxs-lookup"><span data-stu-id="e5140-105">204</span></span>|  
|<span data-ttu-id="e5140-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="e5140-106">Keywords</span></span>|<span data-ttu-id="e5140-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e5140-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e5140-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="e5140-108">Level</span></span>|<span data-ttu-id="e5140-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="e5140-109">Information</span></span>|  
|<span data-ttu-id="e5140-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="e5140-110">Channel</span></span>|<span data-ttu-id="e5140-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="e5140-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e5140-112">Opis</span><span class="sxs-lookup"><span data-stu-id="e5140-112">Description</span></span>  

 <span data-ttu-id="e5140-113">To zdarzenie jest emitowane po wywołaniu metody przez model usługi `BeforeCall` w Inspektorze parametrów klienta.</span><span class="sxs-lookup"><span data-stu-id="e5140-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e5140-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="e5140-114">Message</span></span>  

 <span data-ttu-id="e5140-115">Dyspozytor wywołał element "BeforeCall" na ClientParameterInspector typu "%1".</span><span class="sxs-lookup"><span data-stu-id="e5140-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e5140-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="e5140-116">Details</span></span>  
  
|<span data-ttu-id="e5140-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="e5140-117">Data Item Name</span></span>|<span data-ttu-id="e5140-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="e5140-118">Data Item Type</span></span>|<span data-ttu-id="e5140-119">Opis</span><span class="sxs-lookup"><span data-stu-id="e5140-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e5140-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="e5140-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="e5140-121">FullName CLR dla wywoływanego typu inspektora.</span><span class="sxs-lookup"><span data-stu-id="e5140-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="e5140-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="e5140-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="e5140-123">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="e5140-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e5140-124">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="e5140-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e5140-125">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="e5140-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e5140-126">Wywołując</span><span class="sxs-lookup"><span data-stu-id="e5140-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e5140-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e5140-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
