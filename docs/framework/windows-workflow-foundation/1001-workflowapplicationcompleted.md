---
title: 1001 — WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: be97991be9b61908a23486da0ef255ebfbdc5485
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239955"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="55351-102">1001 — WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="55351-102">1001 - WorkflowApplicationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="55351-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="55351-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55351-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="55351-104">ID</span></span>|<span data-ttu-id="55351-105">1001</span><span class="sxs-lookup"><span data-stu-id="55351-105">1001</span></span>|  
|<span data-ttu-id="55351-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="55351-106">Keywords</span></span>|<span data-ttu-id="55351-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="55351-107">WFRuntime</span></span>|  
|<span data-ttu-id="55351-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="55351-108">Level</span></span>|<span data-ttu-id="55351-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="55351-109">Information</span></span>|  
|<span data-ttu-id="55351-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="55351-110">Channel</span></span>|<span data-ttu-id="55351-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="55351-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="55351-112">Opis</span><span class="sxs-lookup"><span data-stu-id="55351-112">Description</span></span>  

 <span data-ttu-id="55351-113">Wskazuje, że aplikacja przepływu pracy została ukończona w stanie zamkniętym.</span><span class="sxs-lookup"><span data-stu-id="55351-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="55351-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="55351-114">Message</span></span>  

 <span data-ttu-id="55351-115">Działanie obiektu WorkflowInstance o identyfikatorze: %1 zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="55351-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="55351-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="55351-116">Details</span></span>  
  
|<span data-ttu-id="55351-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="55351-117">Data Item Name</span></span>|<span data-ttu-id="55351-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="55351-118">Data Item Type</span></span>|<span data-ttu-id="55351-119">Opis</span><span class="sxs-lookup"><span data-stu-id="55351-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="55351-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="55351-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="55351-121">Identyfikator wystąpienia przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="55351-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="55351-122">Wywołując</span><span class="sxs-lookup"><span data-stu-id="55351-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="55351-123">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="55351-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
