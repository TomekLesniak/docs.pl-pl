---
title: 1018 — StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: c1558e19b0de2dc5d22d4356b0f80c35e5b4fbc1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275508"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="63243-102">1018 — StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="63243-102">1018 - StartCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="63243-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="63243-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="63243-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="63243-104">ID</span></span>|<span data-ttu-id="63243-105">1018</span><span class="sxs-lookup"><span data-stu-id="63243-105">1018</span></span>|  
|<span data-ttu-id="63243-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="63243-106">Keywords</span></span>|<span data-ttu-id="63243-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="63243-107">WFRuntime</span></span>|  
|<span data-ttu-id="63243-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="63243-108">Level</span></span>|<span data-ttu-id="63243-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="63243-109">Verbose</span></span>|  
|<span data-ttu-id="63243-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="63243-110">Channel</span></span>|<span data-ttu-id="63243-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="63243-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="63243-112">Opis</span><span class="sxs-lookup"><span data-stu-id="63243-112">Description</span></span>  

 <span data-ttu-id="63243-113">Wskazuje, że roboczego cancelactivityworkitem rozpoczyna wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="63243-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="63243-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="63243-114">Message</span></span>  

 <span data-ttu-id="63243-115">Rozpoczynanie wykonywania elementu roboczego cancelactivityworkitem dla działania "%1", nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="63243-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="63243-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="63243-116">Details</span></span>  
  
|<span data-ttu-id="63243-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="63243-117">Data Item Name</span></span>|<span data-ttu-id="63243-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="63243-118">Data Item Type</span></span>|<span data-ttu-id="63243-119">Opis</span><span class="sxs-lookup"><span data-stu-id="63243-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="63243-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="63243-120">Activity</span></span>|<span data-ttu-id="63243-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="63243-121">xs:string</span></span>|<span data-ttu-id="63243-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="63243-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="63243-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="63243-123">DisplayName</span></span>|<span data-ttu-id="63243-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="63243-124">xs:string</span></span>|<span data-ttu-id="63243-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="63243-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="63243-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="63243-126">InstanceId</span></span>|<span data-ttu-id="63243-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="63243-127">xs:string</span></span>|<span data-ttu-id="63243-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="63243-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="63243-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="63243-129">AppDomain</span></span>|<span data-ttu-id="63243-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="63243-130">xs:string</span></span>|<span data-ttu-id="63243-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="63243-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
