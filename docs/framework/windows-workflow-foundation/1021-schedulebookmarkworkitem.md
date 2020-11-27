---
title: 1021 — ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: 42ed23654622e29df8ffc210c8d5ba572fa69fd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275352"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="5c4c3-102">1021 — ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="5c4c3-102">1021 - ScheduleBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="5c4c3-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="5c4c3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5c4c3-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="5c4c3-104">ID</span></span>|<span data-ttu-id="5c4c3-105">1021</span><span class="sxs-lookup"><span data-stu-id="5c4c3-105">1021</span></span>|  
|<span data-ttu-id="5c4c3-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="5c4c3-106">Keywords</span></span>|<span data-ttu-id="5c4c3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5c4c3-107">WFRuntime</span></span>|  
|<span data-ttu-id="5c4c3-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="5c4c3-108">Level</span></span>|<span data-ttu-id="5c4c3-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="5c4c3-109">Verbose</span></span>|  
|<span data-ttu-id="5c4c3-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="5c4c3-110">Channel</span></span>|<span data-ttu-id="5c4c3-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="5c4c3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5c4c3-112">Opis</span><span class="sxs-lookup"><span data-stu-id="5c4c3-112">Description</span></span>  

 <span data-ttu-id="5c4c3-113">Wskazuje, że zaplanowano BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5c4c3-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="5c4c3-114">Message</span></span>  

 <span data-ttu-id="5c4c3-115">BookmarkWorkItem zaplanowano dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="5c4c3-116">Zakładkaname: %4, obiektem BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5c4c3-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="5c4c3-117">Details</span></span>  
  
|<span data-ttu-id="5c4c3-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="5c4c3-118">Data Item Name</span></span>|<span data-ttu-id="5c4c3-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="5c4c3-119">Data Item Type</span></span>|<span data-ttu-id="5c4c3-120">Opis</span><span class="sxs-lookup"><span data-stu-id="5c4c3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5c4c3-121">Działanie</span><span class="sxs-lookup"><span data-stu-id="5c4c3-121">Activity</span></span>|<span data-ttu-id="5c4c3-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5c4c3-122">xs:string</span></span>|<span data-ttu-id="5c4c3-123">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="5c4c3-124">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="5c4c3-124">DisplayName</span></span>|<span data-ttu-id="5c4c3-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5c4c3-125">xs:string</span></span>|<span data-ttu-id="5c4c3-126">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="5c4c3-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5c4c3-127">InstanceId</span></span>|<span data-ttu-id="5c4c3-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5c4c3-128">xs:string</span></span>|<span data-ttu-id="5c4c3-129">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5c4c3-130">Zakładkaname</span><span class="sxs-lookup"><span data-stu-id="5c4c3-130">BookmarkName</span></span>|<span data-ttu-id="5c4c3-131">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5c4c3-131">xs:string</span></span>|<span data-ttu-id="5c4c3-132">Nazwa zakładki.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="5c4c3-133">Obiektem BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="5c4c3-133">BookmarkScope</span></span>|<span data-ttu-id="5c4c3-134">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5c4c3-134">xs:string</span></span>|<span data-ttu-id="5c4c3-135">Zakres zakładki.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="5c4c3-136">Wywołując</span><span class="sxs-lookup"><span data-stu-id="5c4c3-136">AppDomain</span></span>|<span data-ttu-id="5c4c3-137">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5c4c3-137">xs:string</span></span>|<span data-ttu-id="5c4c3-138">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
