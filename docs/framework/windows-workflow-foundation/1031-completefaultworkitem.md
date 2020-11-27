---
title: 1031 — CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: 557155fab35a37bdbaa45efb26d6bc025ad825c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281836"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="314b4-102">1031 — CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="314b4-102">1031 - CompleteFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="314b4-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="314b4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="314b4-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="314b4-104">ID</span></span>|<span data-ttu-id="314b4-105">1031</span><span class="sxs-lookup"><span data-stu-id="314b4-105">1031</span></span>|  
|<span data-ttu-id="314b4-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="314b4-106">Keywords</span></span>|<span data-ttu-id="314b4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="314b4-107">WFRuntime</span></span>|  
|<span data-ttu-id="314b4-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="314b4-108">Level</span></span>|<span data-ttu-id="314b4-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="314b4-109">Verbose</span></span>|  
|<span data-ttu-id="314b4-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="314b4-110">Channel</span></span>|<span data-ttu-id="314b4-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="314b4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="314b4-112">Opis</span><span class="sxs-lookup"><span data-stu-id="314b4-112">Description</span></span>  

 <span data-ttu-id="314b4-113">Wskazuje, że FaultWorkItem został ukończony.</span><span class="sxs-lookup"><span data-stu-id="314b4-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="314b4-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="314b4-114">Message</span></span>  

 <span data-ttu-id="314b4-115">FaultWorkItem dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="314b4-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="314b4-116">Wyjątek został rozpropagowany z działania "%4", nazwa wyświetlana: "%5", identyfikator wystąpienia: "%6".</span><span class="sxs-lookup"><span data-stu-id="314b4-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="314b4-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="314b4-117">Details</span></span>  
  
|<span data-ttu-id="314b4-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="314b4-118">Data Item Name</span></span>|<span data-ttu-id="314b4-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="314b4-119">Data Item Type</span></span>|<span data-ttu-id="314b4-120">Opis</span><span class="sxs-lookup"><span data-stu-id="314b4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="314b4-121">Błąd</span><span class="sxs-lookup"><span data-stu-id="314b4-121">FaultActivity</span></span>|<span data-ttu-id="314b4-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="314b4-122">xs:string</span></span>|<span data-ttu-id="314b4-123">Nazwa typu działania dotyczącego błędu.</span><span class="sxs-lookup"><span data-stu-id="314b4-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="314b4-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="314b4-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="314b4-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="314b4-125">xs:string</span></span>|<span data-ttu-id="314b4-126">Nazwa wyświetlana działania dotyczącego błędu.</span><span class="sxs-lookup"><span data-stu-id="314b4-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="314b4-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="314b4-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="314b4-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="314b4-128">xs:string</span></span>|<span data-ttu-id="314b4-129">Identyfikator wystąpienia działania błędu.</span><span class="sxs-lookup"><span data-stu-id="314b4-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="314b4-130">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="314b4-130">ExceptionActivity</span></span>|<span data-ttu-id="314b4-131">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="314b4-131">xs:string</span></span>|<span data-ttu-id="314b4-132">Nazwa typu działania, które wywołało wyjątek.</span><span class="sxs-lookup"><span data-stu-id="314b4-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="314b4-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="314b4-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="314b4-134">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="314b4-134">xs:string</span></span>|<span data-ttu-id="314b4-135">Nazwa wyświetlana działania, które wywołało wyjątek.</span><span class="sxs-lookup"><span data-stu-id="314b4-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="314b4-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="314b4-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="314b4-137">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="314b4-137">xs:string</span></span>|<span data-ttu-id="314b4-138">Identyfikator wystąpienia działania, które wywołało wyjątek.</span><span class="sxs-lookup"><span data-stu-id="314b4-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="314b4-139">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="314b4-139">Exception</span></span>|<span data-ttu-id="314b4-140">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="314b4-140">xs:string</span></span>|<span data-ttu-id="314b4-141">Szczegóły wyjątku dla wyjątku</span><span class="sxs-lookup"><span data-stu-id="314b4-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="314b4-142">Wywołując</span><span class="sxs-lookup"><span data-stu-id="314b4-142">AppDomain</span></span>|<span data-ttu-id="314b4-143">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="314b4-143">xs:string</span></span>|<span data-ttu-id="314b4-144">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="314b4-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
