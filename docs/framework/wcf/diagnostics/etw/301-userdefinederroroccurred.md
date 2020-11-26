---
title: 301 — UserDefinedErrorOccurred
ms.date: 03/30/2017
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
ms.openlocfilehash: 2c3ff1905a1d17413211246f5b3cc156bcbb7320
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243459"
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="fac93-102">301 — UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="fac93-102">301 - UserDefinedErrorOccurred</span></span>

## <a name="properties"></a><span data-ttu-id="fac93-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="fac93-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fac93-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="fac93-104">ID</span></span>|<span data-ttu-id="fac93-105">301</span><span class="sxs-lookup"><span data-stu-id="fac93-105">301</span></span>|  
|<span data-ttu-id="fac93-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="fac93-106">Keywords</span></span>|<span data-ttu-id="fac93-107">Rozwiązywanie problemów, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="fac93-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="fac93-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="fac93-108">Level</span></span>|<span data-ttu-id="fac93-109">Błąd</span><span class="sxs-lookup"><span data-stu-id="fac93-109">Error</span></span>|  
|<span data-ttu-id="fac93-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="fac93-110">Channel</span></span>|<span data-ttu-id="fac93-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="fac93-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fac93-112">Opis</span><span class="sxs-lookup"><span data-stu-id="fac93-112">Description</span></span>  

 <span data-ttu-id="fac93-113">To zdarzenie jest emitowane z kodu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fac93-113">This event is emitted from user code.</span></span> <span data-ttu-id="fac93-114">Deweloperzy mogą emitować to zdarzenie, gdy w swojej usłudze wystąpi błąd zdefiniowany przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fac93-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="fac93-115">Można to zrobić za pomocą <xref:System.Diagnostics.Eventing> interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="fac93-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="fac93-116">Ponadto istnieje przykład WCF, który otacza ten interfejs API i pokazuje, jak prawidłowo emitować to zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="fac93-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fac93-117">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="fac93-117">Message</span></span>  

 <span data-ttu-id="fac93-118">Nazwa: ' %1 ', odwołanie: ' %2 ', ładunek: %3</span><span class="sxs-lookup"><span data-stu-id="fac93-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="fac93-119">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="fac93-119">Details</span></span>  
  
|<span data-ttu-id="fac93-120">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="fac93-120">Data Item Name</span></span>|<span data-ttu-id="fac93-121">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="fac93-121">Data Item Type</span></span>|<span data-ttu-id="fac93-122">Opis</span><span class="sxs-lookup"><span data-stu-id="fac93-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fac93-123">Nazwa</span><span class="sxs-lookup"><span data-stu-id="fac93-123">Name</span></span>|`xs:string`|<span data-ttu-id="fac93-124">Zdefiniowana przez użytkownika nazwa zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="fac93-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="fac93-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="fac93-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="fac93-126">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="fac93-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fac93-127">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="fac93-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fac93-128">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="fac93-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fac93-129">Ładunku</span><span class="sxs-lookup"><span data-stu-id="fac93-129">Payload</span></span>|`xs:string`|<span data-ttu-id="fac93-130">Zdefiniowany przez użytkownika ładunek zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="fac93-130">The user-defined payload of the event.</span></span>|
