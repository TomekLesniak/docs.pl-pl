---
title: 1008 — WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: 6ea121e7901d877d4f0d8f9f5bfd259c2f93696d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239824"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="f5eb7-102">1008 — WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="f5eb7-102">1008 - WorkflowApplicationUnloaded</span></span>

## <a name="properties"></a><span data-ttu-id="f5eb7-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="f5eb7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5eb7-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="f5eb7-104">ID</span></span>|<span data-ttu-id="f5eb7-105">1008</span><span class="sxs-lookup"><span data-stu-id="f5eb7-105">1008</span></span>|  
|<span data-ttu-id="f5eb7-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="f5eb7-106">Keywords</span></span>|<span data-ttu-id="f5eb7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f5eb7-107">WFRuntime</span></span>|  
|<span data-ttu-id="f5eb7-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="f5eb7-108">Level</span></span>|<span data-ttu-id="f5eb7-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="f5eb7-109">Information</span></span>|  
|<span data-ttu-id="f5eb7-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="f5eb7-110">Channel</span></span>|<span data-ttu-id="f5eb7-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="f5eb7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f5eb7-112">Opis</span><span class="sxs-lookup"><span data-stu-id="f5eb7-112">Description</span></span>  

 <span data-ttu-id="f5eb7-113">Wskazuje, że aplikacja przepływu pracy została zwolniona.</span><span class="sxs-lookup"><span data-stu-id="f5eb7-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f5eb7-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="f5eb7-114">Message</span></span>  

 <span data-ttu-id="f5eb7-115">Działanie obiektu WorkflowInstance o identyfikatorze: %1 zostało zwolnione.</span><span class="sxs-lookup"><span data-stu-id="f5eb7-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f5eb7-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f5eb7-116">Details</span></span>  
  
|<span data-ttu-id="f5eb7-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="f5eb7-117">Data Item Name</span></span>|<span data-ttu-id="f5eb7-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="f5eb7-118">Data Item Type</span></span>|<span data-ttu-id="f5eb7-119">Opis</span><span class="sxs-lookup"><span data-stu-id="f5eb7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f5eb7-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f5eb7-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="f5eb7-121">Identyfikator wystąpienia przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="f5eb7-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="f5eb7-122">Wywołując</span><span class="sxs-lookup"><span data-stu-id="f5eb7-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f5eb7-123">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f5eb7-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
