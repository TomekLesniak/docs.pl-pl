---
title: 1026 — ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 7ba2ada1fbd5217592b4e4e3cffd813ffbe978ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275248"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="a3489-102">1026 — ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="a3489-102">1026 - ScheduleTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="a3489-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="a3489-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3489-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="a3489-104">ID</span></span>|<span data-ttu-id="a3489-105">1026</span><span class="sxs-lookup"><span data-stu-id="a3489-105">1026</span></span>|  
|<span data-ttu-id="a3489-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="a3489-106">Keywords</span></span>|<span data-ttu-id="a3489-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a3489-107">WFRuntime</span></span>|  
|<span data-ttu-id="a3489-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="a3489-108">Level</span></span>|<span data-ttu-id="a3489-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="a3489-109">Verbose</span></span>|  
|<span data-ttu-id="a3489-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="a3489-110">Channel</span></span>|<span data-ttu-id="a3489-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="a3489-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a3489-112">Opis</span><span class="sxs-lookup"><span data-stu-id="a3489-112">Description</span></span>  

 <span data-ttu-id="a3489-113">Wskazuje, że zaplanowano roboczego TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="a3489-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a3489-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="a3489-114">Message</span></span>  

 <span data-ttu-id="a3489-115">Roboczego TransactionContextWorkItem zaplanowano dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="a3489-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a3489-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="a3489-116">Details</span></span>  
  
|<span data-ttu-id="a3489-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="a3489-117">Data Item Name</span></span>|<span data-ttu-id="a3489-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="a3489-118">Data Item Type</span></span>|<span data-ttu-id="a3489-119">Opis</span><span class="sxs-lookup"><span data-stu-id="a3489-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a3489-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="a3489-120">Activity</span></span>|<span data-ttu-id="a3489-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="a3489-121">xs:string</span></span>|<span data-ttu-id="a3489-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="a3489-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="a3489-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="a3489-123">DisplayName</span></span>|<span data-ttu-id="a3489-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="a3489-124">xs:string</span></span>|<span data-ttu-id="a3489-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="a3489-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="a3489-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a3489-126">InstanceId</span></span>|<span data-ttu-id="a3489-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="a3489-127">xs:string</span></span>|<span data-ttu-id="a3489-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="a3489-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a3489-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="a3489-129">AppDomain</span></span>|<span data-ttu-id="a3489-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="a3489-130">xs:string</span></span>|<span data-ttu-id="a3489-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a3489-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
