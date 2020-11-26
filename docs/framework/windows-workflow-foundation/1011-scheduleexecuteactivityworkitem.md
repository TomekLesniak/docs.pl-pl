---
title: 1011 — ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: dc209fc41dc6b076dfb897880f753be51f7fb0ce
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239695"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="55a99-102">1011 — ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="55a99-102">1011 - ScheduleExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="55a99-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="55a99-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55a99-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="55a99-104">ID</span></span>|<span data-ttu-id="55a99-105">1011</span><span class="sxs-lookup"><span data-stu-id="55a99-105">1011</span></span>|  
|<span data-ttu-id="55a99-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="55a99-106">Keywords</span></span>|<span data-ttu-id="55a99-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="55a99-107">WFRuntime</span></span>|  
|<span data-ttu-id="55a99-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="55a99-108">Level</span></span>|<span data-ttu-id="55a99-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="55a99-109">Verbose</span></span>|  
|<span data-ttu-id="55a99-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="55a99-110">Channel</span></span>|<span data-ttu-id="55a99-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="55a99-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="55a99-112">Opis</span><span class="sxs-lookup"><span data-stu-id="55a99-112">Description</span></span>  

 <span data-ttu-id="55a99-113">Wskazuje, że zaplanowano roboczego ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="55a99-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="55a99-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="55a99-114">Message</span></span>  

 <span data-ttu-id="55a99-115">Roboczego ExecuteActivityWorkItem zaplanowano dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="55a99-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="55a99-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="55a99-116">Details</span></span>  
  
|<span data-ttu-id="55a99-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="55a99-117">Data Item Name</span></span>|<span data-ttu-id="55a99-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="55a99-118">Data Item Type</span></span>|<span data-ttu-id="55a99-119">Opis</span><span class="sxs-lookup"><span data-stu-id="55a99-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="55a99-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="55a99-120">Activity</span></span>|<span data-ttu-id="55a99-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="55a99-121">xs:string</span></span>|<span data-ttu-id="55a99-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="55a99-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="55a99-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="55a99-123">DisplayName</span></span>|<span data-ttu-id="55a99-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="55a99-124">xs:string</span></span>|<span data-ttu-id="55a99-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="55a99-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="55a99-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="55a99-126">InstanceId</span></span>|<span data-ttu-id="55a99-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="55a99-127">xs:string</span></span>|<span data-ttu-id="55a99-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="55a99-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="55a99-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="55a99-129">AppDomain</span></span>|<span data-ttu-id="55a99-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="55a99-130">xs:string</span></span>|<span data-ttu-id="55a99-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="55a99-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
