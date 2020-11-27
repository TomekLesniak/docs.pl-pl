---
title: 1016 — CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: a192ffe19777ca3e2e9784f6506a0c2929ced000
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275534"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="e069a-102">1016 — CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="e069a-102">1016 - CompleteCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="e069a-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="e069a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e069a-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="e069a-104">ID</span></span>|<span data-ttu-id="e069a-105">1016</span><span class="sxs-lookup"><span data-stu-id="e069a-105">1016</span></span>|  
|<span data-ttu-id="e069a-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="e069a-106">Keywords</span></span>|<span data-ttu-id="e069a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e069a-107">WFRuntime</span></span>|  
|<span data-ttu-id="e069a-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="e069a-108">Level</span></span>|<span data-ttu-id="e069a-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="e069a-109">Verbose</span></span>|  
|<span data-ttu-id="e069a-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="e069a-110">Channel</span></span>|<span data-ttu-id="e069a-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="e069a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e069a-112">Opis</span><span class="sxs-lookup"><span data-stu-id="e069a-112">Description</span></span>  

 <span data-ttu-id="e069a-113">Wskazuje, że CompletionWorkItem został ukończony.</span><span class="sxs-lookup"><span data-stu-id="e069a-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e069a-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="e069a-114">Message</span></span>  

 <span data-ttu-id="e069a-115">Ukończono CompletionWorkItem dla działania nadrzędnego "%1", nazwa wyświetlana: "%2", identyfikator wystąpienia: "%3".</span><span class="sxs-lookup"><span data-stu-id="e069a-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="e069a-116">Działanie zakończone ' %4 ', nazwa wyświetlana: ' %5 ', identyfikator wystąpienia: ' %6 '.</span><span class="sxs-lookup"><span data-stu-id="e069a-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e069a-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="e069a-117">Details</span></span>  
  
|<span data-ttu-id="e069a-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="e069a-118">Data Item Name</span></span>|<span data-ttu-id="e069a-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="e069a-119">Data Item Type</span></span>|<span data-ttu-id="e069a-120">Opis</span><span class="sxs-lookup"><span data-stu-id="e069a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e069a-121">Element nadrzędny</span><span class="sxs-lookup"><span data-stu-id="e069a-121">ParentActivity</span></span>|<span data-ttu-id="e069a-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e069a-122">xs:string</span></span>|<span data-ttu-id="e069a-123">Nazwa typu działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="e069a-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="e069a-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="e069a-124">ParentDisplayName</span></span>|<span data-ttu-id="e069a-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e069a-125">xs:string</span></span>|<span data-ttu-id="e069a-126">Nazwa wyświetlana działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="e069a-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="e069a-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="e069a-127">ParentInstanceId</span></span>|<span data-ttu-id="e069a-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e069a-128">xs:string</span></span>|<span data-ttu-id="e069a-129">Identyfikator wystąpienia działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="e069a-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="e069a-130">Zakończenie</span><span class="sxs-lookup"><span data-stu-id="e069a-130">CompletedActivity</span></span>|<span data-ttu-id="e069a-131">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e069a-131">xs:string</span></span>|<span data-ttu-id="e069a-132">Nazwa typu działania zakończonego.</span><span class="sxs-lookup"><span data-stu-id="e069a-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="e069a-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="e069a-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="e069a-134">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e069a-134">xs:string</span></span>|<span data-ttu-id="e069a-135">Nazwa wyświetlana działania zakończonego.</span><span class="sxs-lookup"><span data-stu-id="e069a-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="e069a-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="e069a-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="e069a-137">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e069a-137">xs:string</span></span>|<span data-ttu-id="e069a-138">Identyfikator wystąpienia ukończonego działania.</span><span class="sxs-lookup"><span data-stu-id="e069a-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="e069a-139">Wywołując</span><span class="sxs-lookup"><span data-stu-id="e069a-139">AppDomain</span></span>|<span data-ttu-id="e069a-140">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e069a-140">xs:string</span></span>|<span data-ttu-id="e069a-141">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e069a-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
