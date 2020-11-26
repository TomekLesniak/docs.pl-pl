---
title: 1101 — WorkflowActivityStart
ms.date: 03/30/2017
ms.assetid: 831cd386-b9b5-47a9-9690-aff6292ff348
ms.openlocfilehash: 6e43b0ab1e2d35657bae43e7239a677643154fa9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238733"
---
# <a name="1101---workflowactivitystart"></a><span data-ttu-id="ec093-102">1101 — WorkflowActivityStart</span><span class="sxs-lookup"><span data-stu-id="ec093-102">1101 - WorkflowActivityStart</span></span>

## <a name="properties"></a><span data-ttu-id="ec093-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ec093-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec093-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="ec093-104">ID</span></span>|<span data-ttu-id="ec093-105">1101</span><span class="sxs-lookup"><span data-stu-id="ec093-105">1101</span></span>|  
|<span data-ttu-id="ec093-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="ec093-106">Keywords</span></span>|<span data-ttu-id="ec093-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ec093-107">WFRuntime</span></span>|  
|<span data-ttu-id="ec093-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="ec093-108">Level</span></span>|<span data-ttu-id="ec093-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="ec093-109">Information</span></span>|  
|<span data-ttu-id="ec093-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="ec093-110">Channel</span></span>|<span data-ttu-id="ec093-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="ec093-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ec093-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ec093-112">Description</span></span>  

 <span data-ttu-id="ec093-113">Wskazuje, że działanie przepływu pracy zostało rozpoczęte.</span><span class="sxs-lookup"><span data-stu-id="ec093-113">Indicates a workflow activity has started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ec093-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="ec093-114">Message</span></span>  

 <span data-ttu-id="ec093-115">Działanie E2E obiektu WorkflowInstance o identyfikatorze: "%1"</span><span class="sxs-lookup"><span data-stu-id="ec093-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="ec093-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ec093-116">Details</span></span>  
  
|<span data-ttu-id="ec093-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="ec093-117">Data Item Name</span></span>|<span data-ttu-id="ec093-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="ec093-118">Data Item Type</span></span>|<span data-ttu-id="ec093-119">Opis</span><span class="sxs-lookup"><span data-stu-id="ec093-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ec093-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="ec093-120">WorkflowInstanceId</span></span>|<span data-ttu-id="ec093-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ec093-121">xs:string</span></span>|<span data-ttu-id="ec093-122">Identyfikator wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="ec093-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="ec093-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="ec093-123">AppDomain</span></span>|<span data-ttu-id="ec093-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ec093-124">xs:string</span></span>|<span data-ttu-id="ec093-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ec093-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
