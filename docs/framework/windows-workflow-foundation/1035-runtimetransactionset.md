---
title: 1035 — RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: b8bf8431c4e2b82c6aac95820eb45de2a404e976
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294277"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="ad575-102">1035 — RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="ad575-102">1035 - RuntimeTransactionSet</span></span>

## <a name="properties"></a><span data-ttu-id="ad575-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ad575-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad575-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="ad575-104">ID</span></span>|<span data-ttu-id="ad575-105">1035</span><span class="sxs-lookup"><span data-stu-id="ad575-105">1035</span></span>|  
|<span data-ttu-id="ad575-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="ad575-106">Keywords</span></span>|<span data-ttu-id="ad575-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ad575-107">WFRuntime</span></span>|  
|<span data-ttu-id="ad575-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="ad575-108">Level</span></span>|<span data-ttu-id="ad575-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="ad575-109">Verbose</span></span>|  
|<span data-ttu-id="ad575-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="ad575-110">Channel</span></span>|<span data-ttu-id="ad575-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="ad575-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ad575-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ad575-112">Description</span></span>  

 <span data-ttu-id="ad575-113">Wskazuje, że działanie ma ustawioną transakcję środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="ad575-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ad575-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="ad575-114">Message</span></span>  

 <span data-ttu-id="ad575-115">Transakcja środowiska uruchomieniowego została ustawiona przez działanie %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="ad575-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="ad575-116">Wykonanie odizolowane dla działania "%4", nazwa wyświetlana: "%5", identyfikator wystąpienia: "%6".</span><span class="sxs-lookup"><span data-stu-id="ad575-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ad575-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ad575-117">Details</span></span>  
  
|<span data-ttu-id="ad575-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="ad575-118">Data Item Name</span></span>|<span data-ttu-id="ad575-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="ad575-119">Data Item Type</span></span>|<span data-ttu-id="ad575-120">Opis</span><span class="sxs-lookup"><span data-stu-id="ad575-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ad575-121">Działanie</span><span class="sxs-lookup"><span data-stu-id="ad575-121">Activity</span></span>|<span data-ttu-id="ad575-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ad575-122">xs:string</span></span>|<span data-ttu-id="ad575-123">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="ad575-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="ad575-124">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="ad575-124">DisplayName</span></span>|<span data-ttu-id="ad575-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ad575-125">xs:string</span></span>|<span data-ttu-id="ad575-126">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="ad575-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="ad575-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ad575-127">InstanceId</span></span>|<span data-ttu-id="ad575-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ad575-128">xs:string</span></span>|<span data-ttu-id="ad575-129">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="ad575-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ad575-130">Wyizolowane</span><span class="sxs-lookup"><span data-stu-id="ad575-130">IsolatedActivity</span></span>|<span data-ttu-id="ad575-131">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ad575-131">xs:string</span></span>|<span data-ttu-id="ad575-132">Nazwa typu działania, z którym jest izolowana transakcja.</span><span class="sxs-lookup"><span data-stu-id="ad575-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="ad575-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ad575-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="ad575-134">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ad575-134">xs:string</span></span>|<span data-ttu-id="ad575-135">Nazwa wyświetlana działania, z którym jest izolowana transakcja.</span><span class="sxs-lookup"><span data-stu-id="ad575-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="ad575-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ad575-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="ad575-137">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ad575-137">xs:string</span></span>|<span data-ttu-id="ad575-138">Identyfikator wystąpienia działania, z którym jest izolowana transakcja.</span><span class="sxs-lookup"><span data-stu-id="ad575-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="ad575-139">Wywołując</span><span class="sxs-lookup"><span data-stu-id="ad575-139">AppDomain</span></span>|<span data-ttu-id="ad575-140">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ad575-140">xs:string</span></span>|<span data-ttu-id="ad575-141">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ad575-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
