---
title: 211 — ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: 7027b6557520a9ccb587f8d383d3598571da5838
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279067"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="6ccfe-102">211 — ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="6ccfe-102">211 - ParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="6ccfe-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="6ccfe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6ccfe-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="6ccfe-104">ID</span></span>|<span data-ttu-id="6ccfe-105">211</span><span class="sxs-lookup"><span data-stu-id="6ccfe-105">211</span></span>|  
|<span data-ttu-id="6ccfe-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="6ccfe-106">Keywords</span></span>|<span data-ttu-id="6ccfe-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6ccfe-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="6ccfe-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="6ccfe-108">Level</span></span>|<span data-ttu-id="6ccfe-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="6ccfe-109">Information</span></span>|  
|<span data-ttu-id="6ccfe-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="6ccfe-110">Channel</span></span>|<span data-ttu-id="6ccfe-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="6ccfe-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6ccfe-112">Opis</span><span class="sxs-lookup"><span data-stu-id="6ccfe-112">Description</span></span>  

 <span data-ttu-id="6ccfe-113">To zdarzenie jest emitowane po wywołaniu metody przez model usługi `AfterCall` `ParameterInspector` .</span><span class="sxs-lookup"><span data-stu-id="6ccfe-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6ccfe-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="6ccfe-114">Message</span></span>  

 <span data-ttu-id="6ccfe-115">Dyspozytor wywołał element "AfterCall" na ParameterInspector typu "%1".</span><span class="sxs-lookup"><span data-stu-id="6ccfe-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6ccfe-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="6ccfe-116">Details</span></span>  
  
|<span data-ttu-id="6ccfe-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="6ccfe-117">Data Item Name</span></span>|<span data-ttu-id="6ccfe-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="6ccfe-118">Data Item Type</span></span>|<span data-ttu-id="6ccfe-119">Opis</span><span class="sxs-lookup"><span data-stu-id="6ccfe-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6ccfe-120">Nazwa typu</span><span class="sxs-lookup"><span data-stu-id="6ccfe-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="6ccfe-121">FullName CLR typu wywoływanego `ParameterInspector` .</span><span class="sxs-lookup"><span data-stu-id="6ccfe-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="6ccfe-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="6ccfe-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="6ccfe-123">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="6ccfe-124">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="6ccfe-125">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="6ccfe-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="6ccfe-126">Wywołując</span><span class="sxs-lookup"><span data-stu-id="6ccfe-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6ccfe-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6ccfe-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
