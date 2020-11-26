---
title: 1012 — StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: b9cfceb12d56f93c0f9726849e34f4333f1399ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239643"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="df0ad-102">1012 — StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="df0ad-102">1012 - StartExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="df0ad-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="df0ad-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df0ad-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="df0ad-104">ID</span></span>|<span data-ttu-id="df0ad-105">1012</span><span class="sxs-lookup"><span data-stu-id="df0ad-105">1012</span></span>|  
|<span data-ttu-id="df0ad-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="df0ad-106">Keywords</span></span>|<span data-ttu-id="df0ad-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="df0ad-107">WFRuntime</span></span>|  
|<span data-ttu-id="df0ad-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="df0ad-108">Level</span></span>|<span data-ttu-id="df0ad-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="df0ad-109">Verbose</span></span>|  
|<span data-ttu-id="df0ad-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="df0ad-110">Channel</span></span>|<span data-ttu-id="df0ad-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="df0ad-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="df0ad-112">Opis</span><span class="sxs-lookup"><span data-stu-id="df0ad-112">Description</span></span>  

 <span data-ttu-id="df0ad-113">Wskazuje, że roboczego ExecuteActivityWorkItem rozpoczyna wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="df0ad-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="df0ad-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="df0ad-114">Message</span></span>  

 <span data-ttu-id="df0ad-115">Rozpoczynanie wykonywania elementu roboczego ExecuteActivityWorkItem dla działania "%1", nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="df0ad-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="df0ad-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="df0ad-116">Details</span></span>  
  
|<span data-ttu-id="df0ad-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="df0ad-117">Data Item Name</span></span>|<span data-ttu-id="df0ad-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="df0ad-118">Data Item Type</span></span>|<span data-ttu-id="df0ad-119">Opis</span><span class="sxs-lookup"><span data-stu-id="df0ad-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="df0ad-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="df0ad-120">Activity</span></span>|<span data-ttu-id="df0ad-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="df0ad-121">xs:string</span></span>|<span data-ttu-id="df0ad-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="df0ad-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="df0ad-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="df0ad-123">DisplayName</span></span>|<span data-ttu-id="df0ad-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="df0ad-124">xs:string</span></span>|<span data-ttu-id="df0ad-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="df0ad-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="df0ad-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="df0ad-126">InstanceId</span></span>|<span data-ttu-id="df0ad-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="df0ad-127">xs:string</span></span>|<span data-ttu-id="df0ad-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="df0ad-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="df0ad-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="df0ad-129">AppDomain</span></span>|<span data-ttu-id="df0ad-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="df0ad-130">xs:string</span></span>|<span data-ttu-id="df0ad-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="df0ad-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
