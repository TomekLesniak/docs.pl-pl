---
title: 225 — TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 04c5e0f4fbf3b95485e5bf4aae53aa2e4912d893
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294498"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="fdc5a-102">225 — TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="fdc5a-102">225 - TraceCorrelationKeys</span></span>

## <a name="properties"></a><span data-ttu-id="fdc5a-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="fdc5a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fdc5a-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="fdc5a-104">ID</span></span>|<span data-ttu-id="fdc5a-105">225</span><span class="sxs-lookup"><span data-stu-id="fdc5a-105">225</span></span>|  
|<span data-ttu-id="fdc5a-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="fdc5a-106">Keywords</span></span>|<span data-ttu-id="fdc5a-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fdc5a-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="fdc5a-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="fdc5a-108">Level</span></span>|<span data-ttu-id="fdc5a-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="fdc5a-109">Information</span></span>|  
|<span data-ttu-id="fdc5a-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="fdc5a-110">Channel</span></span>|<span data-ttu-id="fdc5a-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="fdc5a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fdc5a-112">Opis</span><span class="sxs-lookup"><span data-stu-id="fdc5a-112">Description</span></span>  

 <span data-ttu-id="fdc5a-113">To zdarzenie jest emitowane, gdy korelacja oparta na zawartości jest używana dla usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="fdc5a-114">Zawiera on klucze korelacji, które są stosowane do skorelowania komunikatu z wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fdc5a-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="fdc5a-115">Message</span></span>  

 <span data-ttu-id="fdc5a-116">Obliczony klucz korelacji "%1" używa wartości "%2" w zakresie nadrzędnym "%3".</span><span class="sxs-lookup"><span data-stu-id="fdc5a-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fdc5a-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="fdc5a-117">Details</span></span>  
  
|<span data-ttu-id="fdc5a-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="fdc5a-118">Data Item Name</span></span>|<span data-ttu-id="fdc5a-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="fdc5a-119">Data Item Type</span></span>|<span data-ttu-id="fdc5a-120">Opis</span><span class="sxs-lookup"><span data-stu-id="fdc5a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fdc5a-121">Klucz wystąpienia</span><span class="sxs-lookup"><span data-stu-id="fdc5a-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="fdc5a-122">Klucz, który został wygenerowany na podstawie wartości korelacji.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="fdc5a-123">Wartości</span><span class="sxs-lookup"><span data-stu-id="fdc5a-123">Values</span></span>|`xs:string`|<span data-ttu-id="fdc5a-124">Wartości, które były używane do obliczania klucza wystąpienia korelacji.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="fdc5a-125">Zakres nadrzędny</span><span class="sxs-lookup"><span data-stu-id="fdc5a-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="fdc5a-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="fdc5a-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="fdc5a-127">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fdc5a-128">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fdc5a-129">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="fdc5a-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fdc5a-130">Wywołując</span><span class="sxs-lookup"><span data-stu-id="fdc5a-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fdc5a-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
