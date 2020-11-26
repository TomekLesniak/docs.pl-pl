---
title: 1102 — WorkflowActivityStop
ms.date: 03/30/2017
ms.assetid: 285e5cb8-e90d-4914-ac06-e9b176ffefa2
ms.openlocfilehash: 7b5c7874946ae494f41e73f3e7c90f3944a3521d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238694"
---
# <a name="1102---workflowactivitystop"></a><span data-ttu-id="ced87-102">1102 — WorkflowActivityStop</span><span class="sxs-lookup"><span data-stu-id="ced87-102">1102 - WorkflowActivityStop</span></span>

## <a name="properties"></a><span data-ttu-id="ced87-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ced87-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ced87-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="ced87-104">ID</span></span>|<span data-ttu-id="ced87-105">1102</span><span class="sxs-lookup"><span data-stu-id="ced87-105">1102</span></span>|  
|<span data-ttu-id="ced87-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="ced87-106">Keywords</span></span>|<span data-ttu-id="ced87-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ced87-107">WFRuntime</span></span>|  
|<span data-ttu-id="ced87-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="ced87-108">Level</span></span>|<span data-ttu-id="ced87-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="ced87-109">Information</span></span>|  
|<span data-ttu-id="ced87-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="ced87-110">Channel</span></span>|<span data-ttu-id="ced87-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="ced87-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ced87-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ced87-112">Description</span></span>  

 <span data-ttu-id="ced87-113">Wskazuje, że działanie przepływu pracy zostało zatrzymane.</span><span class="sxs-lookup"><span data-stu-id="ced87-113">Indicates a workflow activity has stopped.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ced87-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="ced87-114">Message</span></span>  

 <span data-ttu-id="ced87-115">Działanie E2E obiektu WorkflowInstance o identyfikatorze: "%1"</span><span class="sxs-lookup"><span data-stu-id="ced87-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="ced87-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ced87-116">Details</span></span>  
  
|<span data-ttu-id="ced87-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="ced87-117">Data Item Name</span></span>|<span data-ttu-id="ced87-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="ced87-118">Data Item Type</span></span>|<span data-ttu-id="ced87-119">Opis</span><span class="sxs-lookup"><span data-stu-id="ced87-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ced87-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="ced87-120">WorkflowInstanceId</span></span>|<span data-ttu-id="ced87-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ced87-121">xs:string</span></span>|<span data-ttu-id="ced87-122">Identyfikator wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="ced87-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="ced87-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="ced87-123">AppDomain</span></span>|<span data-ttu-id="ced87-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ced87-124">xs:string</span></span>|<span data-ttu-id="ced87-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ced87-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
