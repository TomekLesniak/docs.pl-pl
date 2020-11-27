---
title: 1014 — ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 7fd93683851c5a8c4ab253272c3f2129b3f0bb49
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275560"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="110e5-102">1014 — ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="110e5-102">1014 - ScheduleCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="110e5-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="110e5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="110e5-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="110e5-104">ID</span></span>|<span data-ttu-id="110e5-105">1014</span><span class="sxs-lookup"><span data-stu-id="110e5-105">1014</span></span>|  
|<span data-ttu-id="110e5-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="110e5-106">Keywords</span></span>|<span data-ttu-id="110e5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="110e5-107">WFRuntime</span></span>|  
|<span data-ttu-id="110e5-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="110e5-108">Level</span></span>|<span data-ttu-id="110e5-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="110e5-109">Verbose</span></span>|  
|<span data-ttu-id="110e5-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="110e5-110">Channel</span></span>|<span data-ttu-id="110e5-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="110e5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="110e5-112">Opis</span><span class="sxs-lookup"><span data-stu-id="110e5-112">Description</span></span>  

 <span data-ttu-id="110e5-113">Wskazuje, że zaplanowano CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="110e5-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="110e5-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="110e5-114">Message</span></span>  

 <span data-ttu-id="110e5-115">Zaplanowano CompletionWorkItem dla działania nadrzędnego "%1", nazwa wyświetlana: "%2", identyfikator wystąpienia: "%3".</span><span class="sxs-lookup"><span data-stu-id="110e5-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="110e5-116">Działanie zakończone ' %4 ', nazwa wyświetlana: ' %5 ', identyfikator wystąpienia: ' %6 '.</span><span class="sxs-lookup"><span data-stu-id="110e5-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="110e5-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="110e5-117">Details</span></span>  
  
|<span data-ttu-id="110e5-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="110e5-118">Data Item Name</span></span>|<span data-ttu-id="110e5-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="110e5-119">Data Item Type</span></span>|<span data-ttu-id="110e5-120">Opis</span><span class="sxs-lookup"><span data-stu-id="110e5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="110e5-121">Element nadrzędny</span><span class="sxs-lookup"><span data-stu-id="110e5-121">ParentActivity</span></span>|<span data-ttu-id="110e5-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="110e5-122">xs:string</span></span>|<span data-ttu-id="110e5-123">Nazwa typu działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="110e5-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="110e5-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="110e5-124">ParentDisplayName</span></span>|<span data-ttu-id="110e5-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="110e5-125">xs:string</span></span>|<span data-ttu-id="110e5-126">Nazwa wyświetlana działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="110e5-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="110e5-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="110e5-127">ParentInstanceId</span></span>|<span data-ttu-id="110e5-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="110e5-128">xs:string</span></span>|<span data-ttu-id="110e5-129">Identyfikator wystąpienia działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="110e5-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="110e5-130">Zakończenie</span><span class="sxs-lookup"><span data-stu-id="110e5-130">CompletedActivity</span></span>|<span data-ttu-id="110e5-131">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="110e5-131">xs:string</span></span>|<span data-ttu-id="110e5-132">Nazwa typu działania zakończonego.</span><span class="sxs-lookup"><span data-stu-id="110e5-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="110e5-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="110e5-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="110e5-134">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="110e5-134">xs:string</span></span>|<span data-ttu-id="110e5-135">Nazwa wyświetlana działania zakończonego.</span><span class="sxs-lookup"><span data-stu-id="110e5-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="110e5-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="110e5-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="110e5-137">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="110e5-137">xs:string</span></span>|<span data-ttu-id="110e5-138">Identyfikator wystąpienia ukończonego działania.</span><span class="sxs-lookup"><span data-stu-id="110e5-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="110e5-139">Wywołując</span><span class="sxs-lookup"><span data-stu-id="110e5-139">AppDomain</span></span>|<span data-ttu-id="110e5-140">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="110e5-140">xs:string</span></span>|<span data-ttu-id="110e5-141">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="110e5-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
