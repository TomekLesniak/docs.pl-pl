---
title: 1005 — WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 3b7210246b7fb754145c8aa6128da3183cea9f91
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239864"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="2a646-102">1005 — WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="2a646-102">1005 - WorkflowApplicationIdled</span></span>

## <a name="properties"></a><span data-ttu-id="2a646-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="2a646-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a646-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="2a646-104">ID</span></span>|<span data-ttu-id="2a646-105">1005</span><span class="sxs-lookup"><span data-stu-id="2a646-105">1005</span></span>|  
|<span data-ttu-id="2a646-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="2a646-106">Keywords</span></span>|<span data-ttu-id="2a646-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2a646-107">WFRuntime</span></span>|  
|<span data-ttu-id="2a646-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="2a646-108">Level</span></span>|<span data-ttu-id="2a646-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="2a646-109">Information</span></span>|  
|<span data-ttu-id="2a646-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="2a646-110">Channel</span></span>|<span data-ttu-id="2a646-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="2a646-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2a646-112">Opis</span><span class="sxs-lookup"><span data-stu-id="2a646-112">Description</span></span>  

 <span data-ttu-id="2a646-113">Wskazuje, że aplikacja przepływu pracy jest w stanie bezczynności.</span><span class="sxs-lookup"><span data-stu-id="2a646-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2a646-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="2a646-114">Message</span></span>  

 <span data-ttu-id="2a646-115">Obiekt WorkflowApplication o identyfikatorze: "%1" był bezczynny.</span><span class="sxs-lookup"><span data-stu-id="2a646-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2a646-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="2a646-116">Details</span></span>  
  
|<span data-ttu-id="2a646-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="2a646-117">Data Item Name</span></span>|<span data-ttu-id="2a646-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="2a646-118">Data Item Type</span></span>|<span data-ttu-id="2a646-119">Opis</span><span class="sxs-lookup"><span data-stu-id="2a646-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2a646-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="2a646-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="2a646-121">Identyfikator aplikacji przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="2a646-121">The workflow application id</span></span>|  
|<span data-ttu-id="2a646-122">Wywołując</span><span class="sxs-lookup"><span data-stu-id="2a646-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2a646-123">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2a646-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
