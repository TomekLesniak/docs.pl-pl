---
title: 1103 — WorkflowActivitySuspend
ms.date: 03/30/2017
ms.assetid: b64e15c2-cb2c-4314-9074-ce2c6717232e
ms.openlocfilehash: 2fede703d086ed9653734f626fc38f56e073e416
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243576"
---
# <a name="1103---workflowactivitysuspend"></a><span data-ttu-id="32226-102">1103 — WorkflowActivitySuspend</span><span class="sxs-lookup"><span data-stu-id="32226-102">1103 - WorkflowActivitySuspend</span></span>

## <a name="properties"></a><span data-ttu-id="32226-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="32226-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32226-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="32226-104">ID</span></span>|<span data-ttu-id="32226-105">1103</span><span class="sxs-lookup"><span data-stu-id="32226-105">1103</span></span>|  
|<span data-ttu-id="32226-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="32226-106">Keywords</span></span>|<span data-ttu-id="32226-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="32226-107">WFRuntime</span></span>|  
|<span data-ttu-id="32226-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="32226-108">Level</span></span>|<span data-ttu-id="32226-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="32226-109">Information</span></span>|  
|<span data-ttu-id="32226-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="32226-110">Channel</span></span>|<span data-ttu-id="32226-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="32226-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="32226-112">Opis</span><span class="sxs-lookup"><span data-stu-id="32226-112">Description</span></span>  

 <span data-ttu-id="32226-113">Wskazuje, że działanie przepływu pracy zostało zawieszone.</span><span class="sxs-lookup"><span data-stu-id="32226-113">Indicates a workflow activity has been suspended.</span></span>  
  
## <a name="message"></a><span data-ttu-id="32226-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="32226-114">Message</span></span>  

 <span data-ttu-id="32226-115">Działanie E2E obiektu WorkflowInstance o identyfikatorze: "%1"</span><span class="sxs-lookup"><span data-stu-id="32226-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="32226-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="32226-116">Details</span></span>  
  
|<span data-ttu-id="32226-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="32226-117">Data Item Name</span></span>|<span data-ttu-id="32226-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="32226-118">Data Item Type</span></span>|<span data-ttu-id="32226-119">Opis</span><span class="sxs-lookup"><span data-stu-id="32226-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="32226-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="32226-120">WorkflowInstanceId</span></span>|<span data-ttu-id="32226-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="32226-121">xs:string</span></span>|<span data-ttu-id="32226-122">Identyfikator wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="32226-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="32226-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="32226-123">AppDomain</span></span>|<span data-ttu-id="32226-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="32226-124">xs:string</span></span>|<span data-ttu-id="32226-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="32226-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
