---
title: 1013 — CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: 654f961088c371ab53e4a81f40e3c63335efb1a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239591"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="3c7fb-102">1013 — CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="3c7fb-102">1013 - CompleteExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="3c7fb-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="3c7fb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c7fb-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="3c7fb-104">ID</span></span>|<span data-ttu-id="3c7fb-105">1013</span><span class="sxs-lookup"><span data-stu-id="3c7fb-105">1013</span></span>|  
|<span data-ttu-id="3c7fb-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="3c7fb-106">Keywords</span></span>|<span data-ttu-id="3c7fb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3c7fb-107">WFRuntime</span></span>|  
|<span data-ttu-id="3c7fb-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="3c7fb-108">Level</span></span>|<span data-ttu-id="3c7fb-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="3c7fb-109">Verbose</span></span>|  
|<span data-ttu-id="3c7fb-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="3c7fb-110">Channel</span></span>|<span data-ttu-id="3c7fb-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="3c7fb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3c7fb-112">Opis</span><span class="sxs-lookup"><span data-stu-id="3c7fb-112">Description</span></span>  

 <span data-ttu-id="3c7fb-113">Wskazuje, że roboczego ExecuteActivityWorkItem zakończył się</span><span class="sxs-lookup"><span data-stu-id="3c7fb-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="3c7fb-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="3c7fb-114">Message</span></span>  

 <span data-ttu-id="3c7fb-115">Roboczego ExecuteActivityWorkItem dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="3c7fb-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3c7fb-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3c7fb-116">Details</span></span>  
  
|<span data-ttu-id="3c7fb-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="3c7fb-117">Data Item Name</span></span>|<span data-ttu-id="3c7fb-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="3c7fb-118">Data Item Type</span></span>|<span data-ttu-id="3c7fb-119">Opis</span><span class="sxs-lookup"><span data-stu-id="3c7fb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3c7fb-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="3c7fb-120">Activity</span></span>|<span data-ttu-id="3c7fb-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3c7fb-121">xs:string</span></span>|<span data-ttu-id="3c7fb-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="3c7fb-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3c7fb-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="3c7fb-123">DisplayName</span></span>|<span data-ttu-id="3c7fb-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3c7fb-124">xs:string</span></span>|<span data-ttu-id="3c7fb-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="3c7fb-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3c7fb-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3c7fb-126">InstanceId</span></span>|<span data-ttu-id="3c7fb-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3c7fb-127">xs:string</span></span>|<span data-ttu-id="3c7fb-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="3c7fb-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3c7fb-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="3c7fb-129">AppDomain</span></span>|<span data-ttu-id="3c7fb-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3c7fb-130">xs:string</span></span>|<span data-ttu-id="3c7fb-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3c7fb-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
