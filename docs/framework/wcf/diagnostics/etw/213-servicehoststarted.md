---
title: 213 — ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 87a98d30f5ecde6f81580a95e337df22341c23d4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279028"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="41303-102">213 — ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="41303-102">213 - ServiceHostStarted</span></span>

## <a name="properties"></a><span data-ttu-id="41303-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="41303-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41303-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="41303-104">ID</span></span>|<span data-ttu-id="41303-105">213</span><span class="sxs-lookup"><span data-stu-id="41303-105">213</span></span>|  
|<span data-ttu-id="41303-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="41303-106">Keywords</span></span>|<span data-ttu-id="41303-107">EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="41303-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="41303-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="41303-108">Level</span></span>|<span data-ttu-id="41303-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="41303-109">LogAlways</span></span>|  
|<span data-ttu-id="41303-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="41303-110">Channel</span></span>|<span data-ttu-id="41303-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="41303-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="41303-112">Opis</span><span class="sxs-lookup"><span data-stu-id="41303-112">Description</span></span>  

 <span data-ttu-id="41303-113">To zdarzenie jest emitowane po uruchomieniu hosta usługi hostowanej w sieci Web.</span><span class="sxs-lookup"><span data-stu-id="41303-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="41303-114">Zwykle dzieje się tak, gdy usługa jest aktywowana przez komunikat.</span><span class="sxs-lookup"><span data-stu-id="41303-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="41303-115">Może się tak zdarzyć, jeśli usługa jest skonfigurowana do automatycznego uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="41303-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="41303-116">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="41303-116">Message</span></span>  

 <span data-ttu-id="41303-117">Uruchomiono ServiceHost: ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="41303-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="41303-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="41303-118">Details</span></span>  
  
|<span data-ttu-id="41303-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="41303-119">Data Item Name</span></span>|<span data-ttu-id="41303-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="41303-120">Data Item Type</span></span>|<span data-ttu-id="41303-121">Opis</span><span class="sxs-lookup"><span data-stu-id="41303-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="41303-122">Nazwa typu usługi</span><span class="sxs-lookup"><span data-stu-id="41303-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="41303-123">FullName CLR typu implementacji usługi.</span><span class="sxs-lookup"><span data-stu-id="41303-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="41303-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="41303-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="41303-125">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="41303-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="41303-126">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="41303-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="41303-127">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="41303-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="41303-128">Wywołując</span><span class="sxs-lookup"><span data-stu-id="41303-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="41303-129">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="41303-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
