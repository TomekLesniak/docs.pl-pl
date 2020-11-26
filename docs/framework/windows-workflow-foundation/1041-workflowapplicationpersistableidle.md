---
title: 1041 — WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 9995823753fc78ca3f278cd635fcf6c7d2b84325
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238941"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="59c59-102">1041 — WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="59c59-102">1041 - WorkflowApplicationPersistableIdle</span></span>

## <a name="properties"></a><span data-ttu-id="59c59-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="59c59-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59c59-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="59c59-104">ID</span></span>|<span data-ttu-id="59c59-105">1041</span><span class="sxs-lookup"><span data-stu-id="59c59-105">1041</span></span>|  
|<span data-ttu-id="59c59-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="59c59-106">Keywords</span></span>|<span data-ttu-id="59c59-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="59c59-107">WFRuntime</span></span>|  
|<span data-ttu-id="59c59-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="59c59-108">Level</span></span>|<span data-ttu-id="59c59-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="59c59-109">Information</span></span>|  
|<span data-ttu-id="59c59-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="59c59-110">Channel</span></span>|<span data-ttu-id="59c59-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="59c59-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="59c59-112">Opis</span><span class="sxs-lookup"><span data-stu-id="59c59-112">Description</span></span>  

 <span data-ttu-id="59c59-113">Wskazuje, że aplikacja przepływu pracy jest bezczynna i trwała.</span><span class="sxs-lookup"><span data-stu-id="59c59-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="59c59-114">Aplikacja przepływu pracy zostanie przeaktywna lub utrwalona.</span><span class="sxs-lookup"><span data-stu-id="59c59-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="59c59-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="59c59-115">Message</span></span>  

 <span data-ttu-id="59c59-116">Obiekt WorkflowApplication o identyfikatorze: "%1" jest bezczynny i trwały.</span><span class="sxs-lookup"><span data-stu-id="59c59-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="59c59-117">Zostanie podjęta następująca akcja: %2.</span><span class="sxs-lookup"><span data-stu-id="59c59-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="59c59-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="59c59-118">Details</span></span>  
  
|<span data-ttu-id="59c59-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="59c59-119">Data Item Name</span></span>|<span data-ttu-id="59c59-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="59c59-120">Data Item Type</span></span>|<span data-ttu-id="59c59-121">Opis</span><span class="sxs-lookup"><span data-stu-id="59c59-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="59c59-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="59c59-122">WorkflowApplicationId</span></span>|<span data-ttu-id="59c59-123">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="59c59-123">xs:string</span></span>|<span data-ttu-id="59c59-124">Identyfikator aplikacji przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="59c59-124">The workflow application id</span></span>|  
|<span data-ttu-id="59c59-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="59c59-125">ActionTaken</span></span>|<span data-ttu-id="59c59-126">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="59c59-126">xs:string</span></span>|<span data-ttu-id="59c59-127">Akcja, która zostanie wykonana w aplikacji przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="59c59-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="59c59-128">Wywołując</span><span class="sxs-lookup"><span data-stu-id="59c59-128">AppDomain</span></span>|<span data-ttu-id="59c59-129">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="59c59-129">xs:string</span></span>|<span data-ttu-id="59c59-130">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="59c59-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
