---
title: 1007 — WorkflowApplicationPersisted
ms.date: 03/30/2017
ms.assetid: f4ea4452-28e3-4e66-93c6-eb12ee29bcb1
ms.openlocfilehash: aa4c7b2c98924eb43f78ab23a145b93906e302fc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239813"
---
# <a name="1007---workflowapplicationpersisted"></a><span data-ttu-id="0a303-102">1007 — WorkflowApplicationPersisted</span><span class="sxs-lookup"><span data-stu-id="0a303-102">1007 - WorkflowApplicationPersisted</span></span>

## <a name="properties"></a><span data-ttu-id="0a303-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="0a303-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a303-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="0a303-104">ID</span></span>|<span data-ttu-id="0a303-105">1007</span><span class="sxs-lookup"><span data-stu-id="0a303-105">1007</span></span>|  
|<span data-ttu-id="0a303-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="0a303-106">Keywords</span></span>|<span data-ttu-id="0a303-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0a303-107">WFRuntime</span></span>|  
|<span data-ttu-id="0a303-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="0a303-108">Level</span></span>|<span data-ttu-id="0a303-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="0a303-109">Information</span></span>|  
|<span data-ttu-id="0a303-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="0a303-110">Channel</span></span>|<span data-ttu-id="0a303-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="0a303-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0a303-112">Opis</span><span class="sxs-lookup"><span data-stu-id="0a303-112">Description</span></span>  

 <span data-ttu-id="0a303-113">Wskazuje, że aplikacja przepływu pracy została utrwalona.</span><span class="sxs-lookup"><span data-stu-id="0a303-113">Indicates a workflow application has persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0a303-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="0a303-114">Message</span></span>  

 <span data-ttu-id="0a303-115">Obiekt WorkflowApplication o identyfikatorze: %1 został utrwalony.</span><span class="sxs-lookup"><span data-stu-id="0a303-115">WorkflowApplication Id: '%1' was Persisted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0a303-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="0a303-116">Details</span></span>  
  
|<span data-ttu-id="0a303-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="0a303-117">Data Item Name</span></span>|<span data-ttu-id="0a303-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="0a303-118">Data Item Type</span></span>|<span data-ttu-id="0a303-119">Opis</span><span class="sxs-lookup"><span data-stu-id="0a303-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0a303-120">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="0a303-120">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="0a303-121">Identyfikator aplikacji przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="0a303-121">The workflow application id</span></span>|  
|<span data-ttu-id="0a303-122">Wywołując</span><span class="sxs-lookup"><span data-stu-id="0a303-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0a303-123">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0a303-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
