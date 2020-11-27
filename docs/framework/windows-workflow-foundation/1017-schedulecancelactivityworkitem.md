---
title: 1017 — ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 6aed9773aa45251075520a0f955e9d71234f1357
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275622"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="c534a-102">1017 — ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="c534a-102">1017 - ScheduleCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="c534a-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="c534a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c534a-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="c534a-104">ID</span></span>|<span data-ttu-id="c534a-105">1017</span><span class="sxs-lookup"><span data-stu-id="c534a-105">1017</span></span>|  
|<span data-ttu-id="c534a-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="c534a-106">Keywords</span></span>|<span data-ttu-id="c534a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c534a-107">WFRuntime</span></span>|  
|<span data-ttu-id="c534a-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="c534a-108">Level</span></span>|<span data-ttu-id="c534a-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="c534a-109">Verbose</span></span>|  
|<span data-ttu-id="c534a-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="c534a-110">Channel</span></span>|<span data-ttu-id="c534a-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="c534a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c534a-112">Opis</span><span class="sxs-lookup"><span data-stu-id="c534a-112">Description</span></span>  

 <span data-ttu-id="c534a-113">Wskazuje, że zaplanowano roboczego cancelactivityworkitem.</span><span class="sxs-lookup"><span data-stu-id="c534a-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c534a-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="c534a-114">Message</span></span>  

 <span data-ttu-id="c534a-115">Roboczego cancelactivityworkitem zaplanowano dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="c534a-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c534a-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="c534a-116">Details</span></span>  
  
|<span data-ttu-id="c534a-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="c534a-117">Data Item Name</span></span>|<span data-ttu-id="c534a-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="c534a-118">Data Item Type</span></span>|<span data-ttu-id="c534a-119">Opis</span><span class="sxs-lookup"><span data-stu-id="c534a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c534a-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="c534a-120">Activity</span></span>|<span data-ttu-id="c534a-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c534a-121">xs:string</span></span>|<span data-ttu-id="c534a-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="c534a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c534a-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="c534a-123">DisplayName</span></span>|<span data-ttu-id="c534a-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c534a-124">xs:string</span></span>|<span data-ttu-id="c534a-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="c534a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c534a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c534a-126">InstanceId</span></span>|<span data-ttu-id="c534a-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c534a-127">xs:string</span></span>|<span data-ttu-id="c534a-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="c534a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c534a-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="c534a-129">AppDomain</span></span>|<span data-ttu-id="c534a-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c534a-130">xs:string</span></span>|<span data-ttu-id="c534a-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c534a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
