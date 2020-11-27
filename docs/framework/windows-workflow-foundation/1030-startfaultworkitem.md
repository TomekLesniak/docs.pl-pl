---
title: 1030 — StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 52034f7cc7c6f6749fbbbf06db9267ecb6279ee1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281862"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="5ec11-102">1030 — StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="5ec11-102">1030 - StartFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="5ec11-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="5ec11-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ec11-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="5ec11-104">ID</span></span>|<span data-ttu-id="5ec11-105">1030</span><span class="sxs-lookup"><span data-stu-id="5ec11-105">1030</span></span>|  
|<span data-ttu-id="5ec11-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="5ec11-106">Keywords</span></span>|<span data-ttu-id="5ec11-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5ec11-107">WFRuntime</span></span>|  
|<span data-ttu-id="5ec11-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="5ec11-108">Level</span></span>|<span data-ttu-id="5ec11-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="5ec11-109">Verbose</span></span>|  
|<span data-ttu-id="5ec11-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="5ec11-110">Channel</span></span>|<span data-ttu-id="5ec11-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="5ec11-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5ec11-112">Opis</span><span class="sxs-lookup"><span data-stu-id="5ec11-112">Description</span></span>  

 <span data-ttu-id="5ec11-113">Wskazuje, że FaultWorkItem rozpoczyna wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="5ec11-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5ec11-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="5ec11-114">Message</span></span>  

 <span data-ttu-id="5ec11-115">Rozpoczynanie wykonywania elementu FaultWorkItem dla działania "%1", nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="5ec11-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="5ec11-116">Wyjątek został rozpropagowany z działania "%4", nazwa wyświetlana: "%5", identyfikator wystąpienia: "%6".</span><span class="sxs-lookup"><span data-stu-id="5ec11-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5ec11-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="5ec11-117">Details</span></span>  
  
|<span data-ttu-id="5ec11-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="5ec11-118">Data Item Name</span></span>|<span data-ttu-id="5ec11-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="5ec11-119">Data Item Type</span></span>|<span data-ttu-id="5ec11-120">Opis</span><span class="sxs-lookup"><span data-stu-id="5ec11-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5ec11-121">Błąd</span><span class="sxs-lookup"><span data-stu-id="5ec11-121">FaultActivity</span></span>|<span data-ttu-id="5ec11-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ec11-122">xs:string</span></span>|<span data-ttu-id="5ec11-123">Nazwa typu działania dotyczącego błędu.</span><span class="sxs-lookup"><span data-stu-id="5ec11-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="5ec11-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="5ec11-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="5ec11-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ec11-125">xs:string</span></span>|<span data-ttu-id="5ec11-126">Nazwa wyświetlana działania dotyczącego błędu.</span><span class="sxs-lookup"><span data-stu-id="5ec11-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="5ec11-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="5ec11-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="5ec11-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ec11-128">xs:string</span></span>|<span data-ttu-id="5ec11-129">Identyfikator wystąpienia działania błędu.</span><span class="sxs-lookup"><span data-stu-id="5ec11-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="5ec11-130">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="5ec11-130">ExceptionActivity</span></span>|<span data-ttu-id="5ec11-131">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ec11-131">xs:string</span></span>|<span data-ttu-id="5ec11-132">Nazwa typu działania, które wywołało wyjątek.</span><span class="sxs-lookup"><span data-stu-id="5ec11-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="5ec11-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="5ec11-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="5ec11-134">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ec11-134">xs:string</span></span>|<span data-ttu-id="5ec11-135">Nazwa wyświetlana działania, które wywołało wyjątek.</span><span class="sxs-lookup"><span data-stu-id="5ec11-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="5ec11-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="5ec11-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="5ec11-137">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ec11-137">xs:string</span></span>|<span data-ttu-id="5ec11-138">Identyfikator wystąpienia działania, które wywołało wyjątek.</span><span class="sxs-lookup"><span data-stu-id="5ec11-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="5ec11-139">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="5ec11-139">Exception</span></span>|<span data-ttu-id="5ec11-140">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ec11-140">xs:string</span></span>|<span data-ttu-id="5ec11-141">Szczegóły wyjątku dla wyjątku</span><span class="sxs-lookup"><span data-stu-id="5ec11-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="5ec11-142">Wywołując</span><span class="sxs-lookup"><span data-stu-id="5ec11-142">AppDomain</span></span>|<span data-ttu-id="5ec11-143">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ec11-143">xs:string</span></span>|<span data-ttu-id="5ec11-144">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5ec11-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
