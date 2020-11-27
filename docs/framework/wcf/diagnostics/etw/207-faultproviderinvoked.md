---
title: 207 — FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 71381c9eee6aed4792500c8558db88e239bf89f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295174"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="39550-102">207 — FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="39550-102">207 - FaultProviderInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="39550-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="39550-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39550-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="39550-104">ID</span></span>|<span data-ttu-id="39550-105">207</span><span class="sxs-lookup"><span data-stu-id="39550-105">207</span></span>|  
|<span data-ttu-id="39550-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="39550-106">Keywords</span></span>|<span data-ttu-id="39550-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="39550-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="39550-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="39550-108">Level</span></span>|<span data-ttu-id="39550-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="39550-109">Information</span></span>|  
|<span data-ttu-id="39550-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="39550-110">Channel</span></span>|<span data-ttu-id="39550-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="39550-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="39550-112">Opis</span><span class="sxs-lookup"><span data-stu-id="39550-112">Description</span></span>  

 <span data-ttu-id="39550-113">To zdarzenie jest emitowane po `FaultProvider` wywołaniu.</span><span class="sxs-lookup"><span data-stu-id="39550-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="39550-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="39550-114">Message</span></span>  

 <span data-ttu-id="39550-115">Dyspozytor wywołał wywołał obiekt faultprovider typu ' %1 ' z wyjątkiem typu ' %2 '.</span><span class="sxs-lookup"><span data-stu-id="39550-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="39550-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="39550-116">Details</span></span>  
  
|<span data-ttu-id="39550-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="39550-117">Data Item Name</span></span>|<span data-ttu-id="39550-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="39550-118">Data Item Type</span></span>|<span data-ttu-id="39550-119">Opis</span><span class="sxs-lookup"><span data-stu-id="39550-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="39550-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="39550-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="39550-121">FullName CLR typu wywoływanego `FaultProvider` .</span><span class="sxs-lookup"><span data-stu-id="39550-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="39550-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="39550-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="39550-123">Środowisko CLR FullName wyjątek, na którym działa `FaultProvider` .</span><span class="sxs-lookup"><span data-stu-id="39550-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="39550-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="39550-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="39550-125">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="39550-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="39550-126">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="39550-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="39550-127">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="39550-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="39550-128">Wywołując</span><span class="sxs-lookup"><span data-stu-id="39550-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="39550-129">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="39550-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
