---
title: 1002 — WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: e7c92dcc9ce472c50af6f0aa26c59f55d62fbb9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239942"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="3a1e1-102">1002 — WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="3a1e1-102">1002 - WorkflowApplicationTerminated</span></span>

## <a name="properties"></a><span data-ttu-id="3a1e1-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="3a1e1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a1e1-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="3a1e1-104">ID</span></span>|<span data-ttu-id="3a1e1-105">1002</span><span class="sxs-lookup"><span data-stu-id="3a1e1-105">1002</span></span>|  
|<span data-ttu-id="3a1e1-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="3a1e1-106">Keywords</span></span>|<span data-ttu-id="3a1e1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3a1e1-107">WFRuntime</span></span>|  
|<span data-ttu-id="3a1e1-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="3a1e1-108">Level</span></span>|<span data-ttu-id="3a1e1-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="3a1e1-109">Information</span></span>|  
|<span data-ttu-id="3a1e1-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="3a1e1-110">Channel</span></span>|<span data-ttu-id="3a1e1-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="3a1e1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3a1e1-112">Opis</span><span class="sxs-lookup"><span data-stu-id="3a1e1-112">Description</span></span>  

 <span data-ttu-id="3a1e1-113">Wskazuje, że aplikacja przepływu pracy została przerwana w stanie awarii z wyjątkiem.</span><span class="sxs-lookup"><span data-stu-id="3a1e1-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3a1e1-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="3a1e1-114">Message</span></span>  

 <span data-ttu-id="3a1e1-115">Obiekt WorkflowApplication o identyfikatorze: %1 został zakończony.</span><span class="sxs-lookup"><span data-stu-id="3a1e1-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="3a1e1-116">Zakończono w stanie awarii z wyjątkiem.</span><span class="sxs-lookup"><span data-stu-id="3a1e1-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3a1e1-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3a1e1-117">Details</span></span>  
  
|<span data-ttu-id="3a1e1-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="3a1e1-118">Data Item Name</span></span>|<span data-ttu-id="3a1e1-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="3a1e1-119">Data Item Type</span></span>|<span data-ttu-id="3a1e1-120">Opis</span><span class="sxs-lookup"><span data-stu-id="3a1e1-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3a1e1-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="3a1e1-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="3a1e1-122">Identyfikator aplikacji przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="3a1e1-122">The workflow application id</span></span>|  
|<span data-ttu-id="3a1e1-123">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="3a1e1-123">Exception</span></span>|`xs:string`|<span data-ttu-id="3a1e1-124">Szczegóły wyjątku dla wyjątku</span><span class="sxs-lookup"><span data-stu-id="3a1e1-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="3a1e1-125">Wywołując</span><span class="sxs-lookup"><span data-stu-id="3a1e1-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3a1e1-126">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3a1e1-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
