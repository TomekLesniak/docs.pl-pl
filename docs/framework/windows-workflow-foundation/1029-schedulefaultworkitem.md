---
title: 1029 — ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: 5c109607b2d353d3d4a5a693f29ab66bb76c8398
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275092"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="ffb36-102">1029 — ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="ffb36-102">1029 - ScheduleFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="ffb36-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ffb36-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ffb36-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="ffb36-104">ID</span></span>|<span data-ttu-id="ffb36-105">1029</span><span class="sxs-lookup"><span data-stu-id="ffb36-105">1029</span></span>|  
|<span data-ttu-id="ffb36-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="ffb36-106">Keywords</span></span>|<span data-ttu-id="ffb36-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ffb36-107">WFRuntime</span></span>|  
|<span data-ttu-id="ffb36-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="ffb36-108">Level</span></span>|<span data-ttu-id="ffb36-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="ffb36-109">Verbose</span></span>|  
|<span data-ttu-id="ffb36-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="ffb36-110">Channel</span></span>|<span data-ttu-id="ffb36-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="ffb36-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ffb36-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ffb36-112">Description</span></span>  

 <span data-ttu-id="ffb36-113">Wskazuje, że zaplanowano FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="ffb36-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ffb36-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="ffb36-114">Message</span></span>  

 <span data-ttu-id="ffb36-115">FaultWorkItem zaplanowano dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="ffb36-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="ffb36-116">Wyjątek został rozpropagowany z działania "%4", nazwa wyświetlana: "%5", identyfikator wystąpienia: "%6".</span><span class="sxs-lookup"><span data-stu-id="ffb36-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ffb36-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ffb36-117">Details</span></span>  
  
|<span data-ttu-id="ffb36-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="ffb36-118">Data Item Name</span></span>|<span data-ttu-id="ffb36-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="ffb36-119">Data Item Type</span></span>|<span data-ttu-id="ffb36-120">Opis</span><span class="sxs-lookup"><span data-stu-id="ffb36-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ffb36-121">Błąd</span><span class="sxs-lookup"><span data-stu-id="ffb36-121">FaultActivity</span></span>|<span data-ttu-id="ffb36-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ffb36-122">xs:string</span></span>|<span data-ttu-id="ffb36-123">Nazwa typu działania dotyczącego błędu.</span><span class="sxs-lookup"><span data-stu-id="ffb36-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="ffb36-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ffb36-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="ffb36-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ffb36-125">xs:string</span></span>|<span data-ttu-id="ffb36-126">Nazwa wyświetlana działania dotyczącego błędu.</span><span class="sxs-lookup"><span data-stu-id="ffb36-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="ffb36-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ffb36-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="ffb36-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ffb36-128">xs:string</span></span>|<span data-ttu-id="ffb36-129">Identyfikator wystąpienia działania błędu.</span><span class="sxs-lookup"><span data-stu-id="ffb36-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="ffb36-130">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="ffb36-130">ExceptionActivity</span></span>|<span data-ttu-id="ffb36-131">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ffb36-131">xs:string</span></span>|<span data-ttu-id="ffb36-132">Nazwa typu działania, które wywołało wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ffb36-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ffb36-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ffb36-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="ffb36-134">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ffb36-134">xs:string</span></span>|<span data-ttu-id="ffb36-135">Nazwa wyświetlana działania, które wywołało wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ffb36-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ffb36-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ffb36-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="ffb36-137">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ffb36-137">xs:string</span></span>|<span data-ttu-id="ffb36-138">Identyfikator wystąpienia działania, które wywołało wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ffb36-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ffb36-139">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="ffb36-139">Exception</span></span>|<span data-ttu-id="ffb36-140">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ffb36-140">xs:string</span></span>|<span data-ttu-id="ffb36-141">Szczegóły wyjątku dla wyjątku</span><span class="sxs-lookup"><span data-stu-id="ffb36-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="ffb36-142">Wywołując</span><span class="sxs-lookup"><span data-stu-id="ffb36-142">AppDomain</span></span>|<span data-ttu-id="ffb36-143">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ffb36-143">xs:string</span></span>|<span data-ttu-id="ffb36-144">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ffb36-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
