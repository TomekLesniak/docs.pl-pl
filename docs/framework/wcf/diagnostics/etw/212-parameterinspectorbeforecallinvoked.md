---
title: 212 — ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 28c2aca4555d2e4ff498e450deae55ad6a87743c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279041"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="bbc52-102">212 — ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="bbc52-102">212 - ParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="bbc52-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="bbc52-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bbc52-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="bbc52-104">ID</span></span>|<span data-ttu-id="bbc52-105">212</span><span class="sxs-lookup"><span data-stu-id="bbc52-105">212</span></span>|  
|<span data-ttu-id="bbc52-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="bbc52-106">Keywords</span></span>|<span data-ttu-id="bbc52-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bbc52-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="bbc52-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="bbc52-108">Level</span></span>|<span data-ttu-id="bbc52-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="bbc52-109">Information</span></span>|  
|<span data-ttu-id="bbc52-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="bbc52-110">Channel</span></span>|<span data-ttu-id="bbc52-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="bbc52-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bbc52-112">Opis</span><span class="sxs-lookup"><span data-stu-id="bbc52-112">Description</span></span>  

 <span data-ttu-id="bbc52-113">To zdarzenie jest emitowane po wywołaniu metody przez model usługi `BeforeCall` `ParameterInspector` .</span><span class="sxs-lookup"><span data-stu-id="bbc52-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bbc52-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="bbc52-114">Message</span></span>  

 <span data-ttu-id="bbc52-115">Dyspozytor wywołał element "BeforeCall" na ParameterInspector typu "%1".</span><span class="sxs-lookup"><span data-stu-id="bbc52-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bbc52-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="bbc52-116">Details</span></span>  
  
|<span data-ttu-id="bbc52-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="bbc52-117">Data Item Name</span></span>|<span data-ttu-id="bbc52-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="bbc52-118">Data Item Type</span></span>|<span data-ttu-id="bbc52-119">Opis</span><span class="sxs-lookup"><span data-stu-id="bbc52-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bbc52-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="bbc52-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="bbc52-121">FullName CLR dla wywoływanego typu inspektora.</span><span class="sxs-lookup"><span data-stu-id="bbc52-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="bbc52-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="bbc52-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="bbc52-123">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="bbc52-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="bbc52-124">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="bbc52-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="bbc52-125">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="bbc52-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="bbc52-126">Wywołując</span><span class="sxs-lookup"><span data-stu-id="bbc52-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bbc52-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bbc52-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
