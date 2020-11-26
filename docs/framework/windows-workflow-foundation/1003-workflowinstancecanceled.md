---
title: 1003 — WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: bd8abf173ab6588d4a35ba59c6cd14fb53445e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239903"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="7bde4-102">1003 — WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="7bde4-102">1003 - WorkflowInstanceCanceled</span></span>

## <a name="properties"></a><span data-ttu-id="7bde4-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="7bde4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7bde4-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="7bde4-104">ID</span></span>|<span data-ttu-id="7bde4-105">1003</span><span class="sxs-lookup"><span data-stu-id="7bde4-105">1003</span></span>|  
|<span data-ttu-id="7bde4-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="7bde4-106">Keywords</span></span>|<span data-ttu-id="7bde4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7bde4-107">WFRuntime</span></span>|  
|<span data-ttu-id="7bde4-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="7bde4-108">Level</span></span>|<span data-ttu-id="7bde4-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="7bde4-109">Information</span></span>|  
|<span data-ttu-id="7bde4-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="7bde4-110">Channel</span></span>|<span data-ttu-id="7bde4-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="7bde4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7bde4-112">Opis</span><span class="sxs-lookup"><span data-stu-id="7bde4-112">Description</span></span>  

 <span data-ttu-id="7bde4-113">Wskazuje, że wystąpienie przepływu pracy zostało zakończone w stanie anulowanym.</span><span class="sxs-lookup"><span data-stu-id="7bde4-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7bde4-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="7bde4-114">Message</span></span>  

 <span data-ttu-id="7bde4-115">Działanie obiektu WorkflowInstance o identyfikatorze: "%1" zostało anulowane.</span><span class="sxs-lookup"><span data-stu-id="7bde4-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7bde4-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="7bde4-116">Details</span></span>  
  
|<span data-ttu-id="7bde4-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="7bde4-117">Data Item Name</span></span>|<span data-ttu-id="7bde4-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="7bde4-118">Data Item Type</span></span>|<span data-ttu-id="7bde4-119">Opis</span><span class="sxs-lookup"><span data-stu-id="7bde4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7bde4-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="7bde4-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="7bde4-121">Identyfikator wystąpienia przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="7bde4-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="7bde4-122">Wywołując</span><span class="sxs-lookup"><span data-stu-id="7bde4-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7bde4-123">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7bde4-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
