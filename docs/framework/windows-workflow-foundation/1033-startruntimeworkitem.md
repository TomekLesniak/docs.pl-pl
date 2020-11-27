---
title: 1033 — StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: 46a3dc8d313ec72ac90abc2e2e333b274dad2e4c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294303"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="da933-102">1033 — StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="da933-102">1033 - StartRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="da933-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="da933-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da933-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="da933-104">ID</span></span>|<span data-ttu-id="da933-105">1045</span><span class="sxs-lookup"><span data-stu-id="da933-105">1033</span></span>|  
|<span data-ttu-id="da933-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="da933-106">Keywords</span></span>|<span data-ttu-id="da933-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="da933-107">WFRuntime</span></span>|  
|<span data-ttu-id="da933-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="da933-108">Level</span></span>|<span data-ttu-id="da933-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="da933-109">Verbose</span></span>|  
|<span data-ttu-id="da933-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="da933-110">Channel</span></span>|<span data-ttu-id="da933-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="da933-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="da933-112">Opis</span><span class="sxs-lookup"><span data-stu-id="da933-112">Description</span></span>  

 <span data-ttu-id="da933-113">Wskazuje, że RuntimeWorkItem rozpoczyna wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="da933-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="da933-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="da933-114">Message</span></span>  

 <span data-ttu-id="da933-115">Rozpoczynanie wykonywania elementu pracy środowiska uruchomieniowego dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="da933-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da933-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="da933-116">Details</span></span>  
  
|<span data-ttu-id="da933-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="da933-117">Data Item Name</span></span>|<span data-ttu-id="da933-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="da933-118">Data Item Type</span></span>|<span data-ttu-id="da933-119">Opis</span><span class="sxs-lookup"><span data-stu-id="da933-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="da933-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="da933-120">Activity</span></span>|<span data-ttu-id="da933-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da933-121">xs:string</span></span>|<span data-ttu-id="da933-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="da933-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="da933-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="da933-123">DisplayName</span></span>|<span data-ttu-id="da933-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da933-124">xs:string</span></span>|<span data-ttu-id="da933-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="da933-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="da933-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="da933-126">InstanceId</span></span>|<span data-ttu-id="da933-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da933-127">xs:string</span></span>|<span data-ttu-id="da933-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="da933-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="da933-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="da933-129">AppDomain</span></span>|<span data-ttu-id="da933-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="da933-130">xs:string</span></span>|<span data-ttu-id="da933-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="da933-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
