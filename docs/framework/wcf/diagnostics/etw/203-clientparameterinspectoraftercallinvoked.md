---
title: 203 — ClientParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
ms.openlocfilehash: b964c26c9684cedef0fbe427bfd9ad232d199f12
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251532"
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="7c93e-102">203 — ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="7c93e-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="7c93e-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="7c93e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c93e-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="7c93e-104">ID</span></span>|<span data-ttu-id="7c93e-105">203</span><span class="sxs-lookup"><span data-stu-id="7c93e-105">203</span></span>|  
|<span data-ttu-id="7c93e-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="7c93e-106">Keywords</span></span>|<span data-ttu-id="7c93e-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7c93e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7c93e-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="7c93e-108">Level</span></span>|<span data-ttu-id="7c93e-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="7c93e-109">Information</span></span>|  
|<span data-ttu-id="7c93e-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="7c93e-110">Channel</span></span>|<span data-ttu-id="7c93e-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="7c93e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7c93e-112">Opis</span><span class="sxs-lookup"><span data-stu-id="7c93e-112">Description</span></span>  

 <span data-ttu-id="7c93e-113">To zdarzenie jest emitowane po wywołaniu metody przez model usługi `AfterCall` w Inspektorze parametrów klienta.</span><span class="sxs-lookup"><span data-stu-id="7c93e-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7c93e-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="7c93e-114">Message</span></span>  

 <span data-ttu-id="7c93e-115">Dyspozytor wywołał element "AfterCall" na ClientParameterInspector typu "%1".</span><span class="sxs-lookup"><span data-stu-id="7c93e-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7c93e-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="7c93e-116">Details</span></span>  
  
|<span data-ttu-id="7c93e-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="7c93e-117">Data Item Name</span></span>|<span data-ttu-id="7c93e-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="7c93e-118">Data Item Type</span></span>|<span data-ttu-id="7c93e-119">Opis</span><span class="sxs-lookup"><span data-stu-id="7c93e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7c93e-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="7c93e-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="7c93e-121">FullName CLR dla wywoływanego typu inspektora.</span><span class="sxs-lookup"><span data-stu-id="7c93e-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="7c93e-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="7c93e-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="7c93e-123">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="7c93e-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7c93e-124">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="7c93e-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7c93e-125">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="7c93e-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7c93e-126">Wywołując</span><span class="sxs-lookup"><span data-stu-id="7c93e-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7c93e-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7c93e-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
