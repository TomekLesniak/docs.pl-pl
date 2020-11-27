---
title: 57398 — MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: bd490aad24fba4550bc778799cd6f836dcfd466c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289181"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="1dbc9-102">57398 — MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="1dbc9-102">57398 - MaxInstancesExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="1dbc9-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="1dbc9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1dbc9-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="1dbc9-104">ID</span></span>|<span data-ttu-id="1dbc9-105">57398</span><span class="sxs-lookup"><span data-stu-id="1dbc9-105">57398</span></span>|  
|<span data-ttu-id="1dbc9-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="1dbc9-106">Keywords</span></span>|<span data-ttu-id="1dbc9-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="1dbc9-107">WFServices</span></span>|  
|<span data-ttu-id="1dbc9-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="1dbc9-108">Level</span></span>|<span data-ttu-id="1dbc9-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="1dbc9-109">Warning</span></span>|  
|<span data-ttu-id="1dbc9-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="1dbc9-110">Channel</span></span>|<span data-ttu-id="1dbc9-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="1dbc9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1dbc9-112">Opis</span><span class="sxs-lookup"><span data-stu-id="1dbc9-112">Description</span></span>  

 <span data-ttu-id="1dbc9-113">Wskazuje, że system osiągnął limit ustawiony dla dławienia "MaxConcurrentInstances".</span><span class="sxs-lookup"><span data-stu-id="1dbc9-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1dbc9-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="1dbc9-114">Message</span></span>  

 <span data-ttu-id="1dbc9-115">System osiągnął limit ustawiony dla dławienia "MaxConcurrentInstances".</span><span class="sxs-lookup"><span data-stu-id="1dbc9-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="1dbc9-116">Limit dla tego dławienia został ustawiony na %1.</span><span class="sxs-lookup"><span data-stu-id="1dbc9-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="1dbc9-117">Wartość ograniczenia można zmienić, modyfikując atrybut "maxConcurrentInstances" w elemencie servicedławienia lub modyfikując właściwość "MaxConcurrentInstances" w przypadku zachowania elementu ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="1dbc9-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1dbc9-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="1dbc9-118">Details</span></span>  
  
|<span data-ttu-id="1dbc9-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="1dbc9-119">Data Item Name</span></span>|<span data-ttu-id="1dbc9-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="1dbc9-120">Data Item Type</span></span>|<span data-ttu-id="1dbc9-121">Opis</span><span class="sxs-lookup"><span data-stu-id="1dbc9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1dbc9-122">Nazwa</span><span class="sxs-lookup"><span data-stu-id="1dbc9-122">Name</span></span>|<span data-ttu-id="1dbc9-123">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="1dbc9-123">xs:string</span></span>|<span data-ttu-id="1dbc9-124">Nazwa elementu .</span><span class="sxs-lookup"><span data-stu-id="1dbc9-124">The name of the item.</span></span>|  
|<span data-ttu-id="1dbc9-125">Wywołując</span><span class="sxs-lookup"><span data-stu-id="1dbc9-125">AppDomain</span></span>|<span data-ttu-id="1dbc9-126">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="1dbc9-126">xs:string</span></span>|<span data-ttu-id="1dbc9-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1dbc9-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
