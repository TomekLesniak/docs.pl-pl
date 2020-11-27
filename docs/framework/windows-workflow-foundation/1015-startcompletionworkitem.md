---
title: 1015 — StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: c0d8572f192a8faa22327fd671cd9ea49c5054ca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275547"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="da787-102">1015 — StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="da787-102">1015 - StartCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="da787-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="da787-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da787-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="da787-104">ID</span></span>|<span data-ttu-id="da787-105">1015</span><span class="sxs-lookup"><span data-stu-id="da787-105">1015</span></span>|  
|<span data-ttu-id="da787-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="da787-106">Keywords</span></span>|<span data-ttu-id="da787-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="da787-107">WFRuntime</span></span>|  
|<span data-ttu-id="da787-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="da787-108">Level</span></span>|<span data-ttu-id="da787-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="da787-109">Verbose</span></span>|  
|<span data-ttu-id="da787-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="da787-110">Channel</span></span>|<span data-ttu-id="da787-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="da787-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="da787-112">Opis</span><span class="sxs-lookup"><span data-stu-id="da787-112">Description</span></span>  

 <span data-ttu-id="da787-113">Wskazuje, że CompletionWorkItem rozpoczyna wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="da787-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="da787-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="da787-114">Message</span></span>  

 <span data-ttu-id="da787-115">Rozpoczynanie wykonywania elementu CompletionWorkItem dla działania nadrzędnego "%1", nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="da787-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="da787-116">Działanie zakończone ' %4 ', nazwa wyświetlana: ' %5 ', identyfikator wystąpienia: ' %6 '.</span><span class="sxs-lookup"><span data-stu-id="da787-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da787-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="da787-117">Details</span></span>  
  
|<span data-ttu-id="da787-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="da787-118">Data Item Name</span></span>|<span data-ttu-id="da787-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="da787-119">Data Item Type</span></span>|<span data-ttu-id="da787-120">Opis</span><span class="sxs-lookup"><span data-stu-id="da787-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="da787-121">Element nadrzędny</span><span class="sxs-lookup"><span data-stu-id="da787-121">ParentActivity</span></span>|<span data-ttu-id="da787-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da787-122">xs:string</span></span>|<span data-ttu-id="da787-123">Nazwa typu działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="da787-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="da787-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="da787-124">ParentDisplayName</span></span>|<span data-ttu-id="da787-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da787-125">xs:string</span></span>|<span data-ttu-id="da787-126">Nazwa wyświetlana działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="da787-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="da787-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="da787-127">ParentInstanceId</span></span>|<span data-ttu-id="da787-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da787-128">xs:string</span></span>|<span data-ttu-id="da787-129">Identyfikator wystąpienia działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="da787-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="da787-130">Zakończenie</span><span class="sxs-lookup"><span data-stu-id="da787-130">CompletedActivity</span></span>|<span data-ttu-id="da787-131">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da787-131">xs:string</span></span>|<span data-ttu-id="da787-132">Nazwa typu działania zakończonego.</span><span class="sxs-lookup"><span data-stu-id="da787-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="da787-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="da787-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="da787-134">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da787-134">xs:string</span></span>|<span data-ttu-id="da787-135">Nazwa wyświetlana działania zakończonego.</span><span class="sxs-lookup"><span data-stu-id="da787-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="da787-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="da787-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="da787-137">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da787-137">xs:string</span></span>|<span data-ttu-id="da787-138">Identyfikator wystąpienia ukończonego działania.</span><span class="sxs-lookup"><span data-stu-id="da787-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="da787-139">Wywołując</span><span class="sxs-lookup"><span data-stu-id="da787-139">AppDomain</span></span>|<span data-ttu-id="da787-140">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da787-140">xs:string</span></span>|<span data-ttu-id="da787-141">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="da787-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
