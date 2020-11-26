---
title: 302 — UserDefinedWarningOccurred
ms.date: 03/30/2017
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
ms.openlocfilehash: b942b2e9716713371b8679fc9df9b9634dfc7283
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243446"
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="0e5dc-102">302 — UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="0e5dc-102">302 - UserDefinedWarningOccurred</span></span>

## <a name="properties"></a><span data-ttu-id="0e5dc-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="0e5dc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e5dc-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="0e5dc-104">ID</span></span>|<span data-ttu-id="0e5dc-105">302</span><span class="sxs-lookup"><span data-stu-id="0e5dc-105">302</span></span>|  
|<span data-ttu-id="0e5dc-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="0e5dc-106">Keywords</span></span>|<span data-ttu-id="0e5dc-107">Rozwiązywanie problemów, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="0e5dc-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="0e5dc-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="0e5dc-108">Level</span></span>|<span data-ttu-id="0e5dc-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="0e5dc-109">Warning</span></span>|  
|<span data-ttu-id="0e5dc-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="0e5dc-110">Channel</span></span>|<span data-ttu-id="0e5dc-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="0e5dc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0e5dc-112">Opis</span><span class="sxs-lookup"><span data-stu-id="0e5dc-112">Description</span></span>  

 <span data-ttu-id="0e5dc-113">To zdarzenie jest emitowane z kodu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-113">This event is emitted from user code.</span></span> <span data-ttu-id="0e5dc-114">Deweloperzy mogą emitować to zdarzenie, gdy w usłudze występuje niestandardowe zdarzenie ostrzegawcze.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="0e5dc-115">Można to zrobić za pomocą <xref:System.Diagnostics.Eventing> interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="0e5dc-116">Ponadto istnieje przykład WCF, który otacza ten interfejs API i pokazuje, jak prawidłowo emitować to zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0e5dc-117">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="0e5dc-117">Message</span></span>  

 <span data-ttu-id="0e5dc-118">Nazwa: ' %1 ', odwołanie: ' %2 ', ładunek: %3</span><span class="sxs-lookup"><span data-stu-id="0e5dc-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="0e5dc-119">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="0e5dc-119">Details</span></span>  
  
|<span data-ttu-id="0e5dc-120">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="0e5dc-120">Data Item Name</span></span>|<span data-ttu-id="0e5dc-121">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="0e5dc-121">Data Item Type</span></span>|<span data-ttu-id="0e5dc-122">Opis</span><span class="sxs-lookup"><span data-stu-id="0e5dc-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0e5dc-123">Nazwa</span><span class="sxs-lookup"><span data-stu-id="0e5dc-123">Name</span></span>|`xs:string`|<span data-ttu-id="0e5dc-124">Zdefiniowana przez użytkownika nazwa zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="0e5dc-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="0e5dc-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="0e5dc-126">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0e5dc-127">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0e5dc-128">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="0e5dc-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0e5dc-129">Ładunku</span><span class="sxs-lookup"><span data-stu-id="0e5dc-129">Payload</span></span>|`xs:string`|<span data-ttu-id="0e5dc-130">Zdefiniowany przez użytkownika ładunek zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-130">The user-defined payload of the event.</span></span>|
