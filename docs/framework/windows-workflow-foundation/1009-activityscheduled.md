---
title: 1009 — ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 812531d4206dfee20f183b9461330e71263b0bf8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239773"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="5ae72-102">1009 — ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="5ae72-102">1009 - ActivityScheduled</span></span>

## <a name="properties"></a><span data-ttu-id="5ae72-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="5ae72-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ae72-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="5ae72-104">ID</span></span>|<span data-ttu-id="5ae72-105">1009</span><span class="sxs-lookup"><span data-stu-id="5ae72-105">1009</span></span>|  
|<span data-ttu-id="5ae72-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="5ae72-106">Keywords</span></span>|<span data-ttu-id="5ae72-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5ae72-107">WFRuntime</span></span>|  
|<span data-ttu-id="5ae72-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="5ae72-108">Level</span></span>|<span data-ttu-id="5ae72-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="5ae72-109">Information</span></span>|  
|<span data-ttu-id="5ae72-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="5ae72-110">Channel</span></span>|<span data-ttu-id="5ae72-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="5ae72-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5ae72-112">Opis</span><span class="sxs-lookup"><span data-stu-id="5ae72-112">Description</span></span>  

 <span data-ttu-id="5ae72-113">Wskazuje, że działanie jest zaplanowane do wykonania.</span><span class="sxs-lookup"><span data-stu-id="5ae72-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5ae72-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="5ae72-114">Message</span></span>  

 <span data-ttu-id="5ae72-115">Działanie nadrzędne ' %1 ', nazwa wyświetlana: ' %2 ', identyfikator wystąpienia: ' %3 ' zaplanowane działanie podrzędne ' %4 ', DisplayName: ' %5 ', identyfikator wystąpienia: ' %6 '.</span><span class="sxs-lookup"><span data-stu-id="5ae72-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5ae72-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="5ae72-116">Details</span></span>  
  
|<span data-ttu-id="5ae72-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="5ae72-117">Data Item Name</span></span>|<span data-ttu-id="5ae72-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="5ae72-118">Data Item Type</span></span>|<span data-ttu-id="5ae72-119">Opis</span><span class="sxs-lookup"><span data-stu-id="5ae72-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5ae72-120">Element nadrzędny</span><span class="sxs-lookup"><span data-stu-id="5ae72-120">ParentActivity</span></span>|<span data-ttu-id="5ae72-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ae72-121">xs:string</span></span>|<span data-ttu-id="5ae72-122">Nazwa typu działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="5ae72-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="5ae72-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="5ae72-123">ParentDisplayName</span></span>|<span data-ttu-id="5ae72-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ae72-124">xs:string</span></span>|<span data-ttu-id="5ae72-125">Nazwa wyświetlana działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="5ae72-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="5ae72-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="5ae72-126">ParentInstanceId</span></span>|<span data-ttu-id="5ae72-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ae72-127">xs:string</span></span>|<span data-ttu-id="5ae72-128">Identyfikator wystąpienia działania nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="5ae72-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="5ae72-129">Tabela podrzędna</span><span class="sxs-lookup"><span data-stu-id="5ae72-129">ChildActivity</span></span>|<span data-ttu-id="5ae72-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ae72-130">xs:string</span></span>|<span data-ttu-id="5ae72-131">Nazwa typu zaplanowanego działania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="5ae72-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="5ae72-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="5ae72-132">ChildDisplayName</span></span>|<span data-ttu-id="5ae72-133">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ae72-133">xs:string</span></span>|<span data-ttu-id="5ae72-134">Nazwa wyświetlana zaplanowanego działania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="5ae72-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="5ae72-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="5ae72-135">ChildInstanceId</span></span>|<span data-ttu-id="5ae72-136">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ae72-136">xs:string</span></span>|<span data-ttu-id="5ae72-137">Identyfikator wystąpienia zaplanowanego działania podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="5ae72-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="5ae72-138">Wywołując</span><span class="sxs-lookup"><span data-stu-id="5ae72-138">AppDomain</span></span>|<span data-ttu-id="5ae72-139">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="5ae72-139">xs:string</span></span>|<span data-ttu-id="5ae72-140">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5ae72-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
