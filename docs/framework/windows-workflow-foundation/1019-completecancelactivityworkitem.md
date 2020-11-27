---
title: 1019 — CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 903b497fb3f244fd40c6888829ef71dddd455251
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275482"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="aa4d4-102">1019 — CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="aa4d4-102">1019 - CompleteCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="aa4d4-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="aa4d4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa4d4-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="aa4d4-104">ID</span></span>|<span data-ttu-id="aa4d4-105">1019</span><span class="sxs-lookup"><span data-stu-id="aa4d4-105">1019</span></span>|  
|<span data-ttu-id="aa4d4-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="aa4d4-106">Keywords</span></span>|<span data-ttu-id="aa4d4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="aa4d4-107">WFRuntime</span></span>|  
|<span data-ttu-id="aa4d4-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="aa4d4-108">Level</span></span>|<span data-ttu-id="aa4d4-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="aa4d4-109">Verbose</span></span>|  
|<span data-ttu-id="aa4d4-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="aa4d4-110">Channel</span></span>|<span data-ttu-id="aa4d4-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="aa4d4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aa4d4-112">Opis</span><span class="sxs-lookup"><span data-stu-id="aa4d4-112">Description</span></span>  

 <span data-ttu-id="aa4d4-113">Wskazuje, że roboczego cancelactivityworkitem został ukończony.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aa4d4-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="aa4d4-114">Message</span></span>  

 <span data-ttu-id="aa4d4-115">Roboczego cancelactivityworkitem dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aa4d4-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="aa4d4-116">Details</span></span>  
  
|<span data-ttu-id="aa4d4-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="aa4d4-117">Data Item Name</span></span>|<span data-ttu-id="aa4d4-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="aa4d4-118">Data Item Type</span></span>|<span data-ttu-id="aa4d4-119">Opis</span><span class="sxs-lookup"><span data-stu-id="aa4d4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aa4d4-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="aa4d4-120">Activity</span></span>|<span data-ttu-id="aa4d4-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="aa4d4-121">xs:string</span></span>|<span data-ttu-id="aa4d4-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="aa4d4-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="aa4d4-123">DisplayName</span></span>|<span data-ttu-id="aa4d4-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="aa4d4-124">xs:string</span></span>|<span data-ttu-id="aa4d4-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="aa4d4-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="aa4d4-126">InstanceId</span></span>|<span data-ttu-id="aa4d4-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="aa4d4-127">xs:string</span></span>|<span data-ttu-id="aa4d4-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="aa4d4-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="aa4d4-129">AppDomain</span></span>|<span data-ttu-id="aa4d4-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="aa4d4-130">xs:string</span></span>|<span data-ttu-id="aa4d4-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
