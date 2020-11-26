---
title: 1104 — WorkflowActivityResume
ms.date: 03/30/2017
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
ms.openlocfilehash: 2a9c40e2c403d43dc980af116e4b6e98b3b2090b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243563"
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="137b9-102">1104 — WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="137b9-102">1104 - WorkflowActivityResume</span></span>

## <a name="properties"></a><span data-ttu-id="137b9-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="137b9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="137b9-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="137b9-104">ID</span></span>|<span data-ttu-id="137b9-105">1104</span><span class="sxs-lookup"><span data-stu-id="137b9-105">1104</span></span>|  
|<span data-ttu-id="137b9-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="137b9-106">Keywords</span></span>|<span data-ttu-id="137b9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="137b9-107">WFRuntime</span></span>|  
|<span data-ttu-id="137b9-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="137b9-108">Level</span></span>|<span data-ttu-id="137b9-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="137b9-109">Information</span></span>|  
|<span data-ttu-id="137b9-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="137b9-110">Channel</span></span>|<span data-ttu-id="137b9-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="137b9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="137b9-112">Opis</span><span class="sxs-lookup"><span data-stu-id="137b9-112">Description</span></span>  

 <span data-ttu-id="137b9-113">Wskazuje, że działanie przepływu pracy zostało wznowione.</span><span class="sxs-lookup"><span data-stu-id="137b9-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="137b9-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="137b9-114">Message</span></span>  

 <span data-ttu-id="137b9-115">Działanie E2E obiektu WorkflowInstance o identyfikatorze: "%1"</span><span class="sxs-lookup"><span data-stu-id="137b9-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="137b9-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="137b9-116">Details</span></span>  
  
|<span data-ttu-id="137b9-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="137b9-117">Data Item Name</span></span>|<span data-ttu-id="137b9-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="137b9-118">Data Item Type</span></span>|<span data-ttu-id="137b9-119">Opis</span><span class="sxs-lookup"><span data-stu-id="137b9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="137b9-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="137b9-120">WorkflowInstanceId</span></span>|<span data-ttu-id="137b9-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="137b9-121">xs:string</span></span>|<span data-ttu-id="137b9-122">Identyfikator wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="137b9-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="137b9-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="137b9-123">AppDomain</span></span>|<span data-ttu-id="137b9-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="137b9-124">xs:string</span></span>|<span data-ttu-id="137b9-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="137b9-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
