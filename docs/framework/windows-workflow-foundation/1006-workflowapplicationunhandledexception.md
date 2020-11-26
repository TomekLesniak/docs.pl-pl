---
title: 1006 — WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 4bb76a93ec7a07a735def1f1d5dc79decb7792ad
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239838"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="54fe6-102">1006 — WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="54fe6-102">1006 - WorkflowApplicationUnhandledException</span></span>

## <a name="properties"></a><span data-ttu-id="54fe6-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="54fe6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54fe6-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="54fe6-104">ID</span></span>|<span data-ttu-id="54fe6-105">1006</span><span class="sxs-lookup"><span data-stu-id="54fe6-105">1006</span></span>|  
|<span data-ttu-id="54fe6-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="54fe6-106">Keywords</span></span>|<span data-ttu-id="54fe6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="54fe6-107">WFRuntime</span></span>|  
|<span data-ttu-id="54fe6-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="54fe6-108">Level</span></span>|<span data-ttu-id="54fe6-109">Błąd</span><span class="sxs-lookup"><span data-stu-id="54fe6-109">Error</span></span>|  
|<span data-ttu-id="54fe6-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="54fe6-110">Channel</span></span>|<span data-ttu-id="54fe6-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="54fe6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="54fe6-112">Opis</span><span class="sxs-lookup"><span data-stu-id="54fe6-112">Description</span></span>  

 <span data-ttu-id="54fe6-113">Wskazuje, że aplikacja przepływu pracy napotkała nieobsłużony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="54fe6-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="54fe6-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="54fe6-114">Message</span></span>  

 <span data-ttu-id="54fe6-115">Działanie obiektu WorkflowInstance o identyfikatorze: %1 napotkało nieobsługiwany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="54fe6-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="54fe6-116">Wyjątek pochodzący z działania ' %2 ', DisplayName: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="54fe6-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="54fe6-117">Zostanie podjęta następująca akcja: %4.</span><span class="sxs-lookup"><span data-stu-id="54fe6-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="54fe6-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="54fe6-118">Details</span></span>  
  
|<span data-ttu-id="54fe6-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="54fe6-119">Data Item Name</span></span>|<span data-ttu-id="54fe6-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="54fe6-120">Data Item Type</span></span>|<span data-ttu-id="54fe6-121">Opis</span><span class="sxs-lookup"><span data-stu-id="54fe6-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="54fe6-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="54fe6-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="54fe6-123">Identyfikator wystąpienia przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="54fe6-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="54fe6-124">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="54fe6-124">Exception</span></span>|`xs:string`|<span data-ttu-id="54fe6-125">Szczegóły wyjątku dla wyjątku</span><span class="sxs-lookup"><span data-stu-id="54fe6-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="54fe6-126">Wywołując</span><span class="sxs-lookup"><span data-stu-id="54fe6-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="54fe6-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="54fe6-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
