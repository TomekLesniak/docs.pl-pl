---
title: 1028 — CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 2fc509dac7e13f30f74c24d8b98cba55ed5f8e1d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275118"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="e096e-102">1028 — CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="e096e-102">1028 - CompleteTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="e096e-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="e096e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e096e-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="e096e-104">ID</span></span>|<span data-ttu-id="e096e-105">1028</span><span class="sxs-lookup"><span data-stu-id="e096e-105">1028</span></span>|  
|<span data-ttu-id="e096e-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="e096e-106">Keywords</span></span>|<span data-ttu-id="e096e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e096e-107">WFRuntime</span></span>|  
|<span data-ttu-id="e096e-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="e096e-108">Level</span></span>|<span data-ttu-id="e096e-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="e096e-109">Verbose</span></span>|  
|<span data-ttu-id="e096e-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="e096e-110">Channel</span></span>|<span data-ttu-id="e096e-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="e096e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e096e-112">Opis</span><span class="sxs-lookup"><span data-stu-id="e096e-112">Description</span></span>  

 <span data-ttu-id="e096e-113">Wskazuje, że roboczego TransactionContextWorkItem został ukończony.</span><span class="sxs-lookup"><span data-stu-id="e096e-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e096e-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="e096e-114">Message</span></span>  

 <span data-ttu-id="e096e-115">Roboczego TransactionContextWorkItem dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="e096e-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e096e-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="e096e-116">Details</span></span>  
  
|<span data-ttu-id="e096e-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="e096e-117">Data Item Name</span></span>|<span data-ttu-id="e096e-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="e096e-118">Data Item Type</span></span>|<span data-ttu-id="e096e-119">Opis</span><span class="sxs-lookup"><span data-stu-id="e096e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e096e-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="e096e-120">Activity</span></span>|<span data-ttu-id="e096e-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e096e-121">xs:string</span></span>|<span data-ttu-id="e096e-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="e096e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="e096e-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="e096e-123">DisplayName</span></span>|<span data-ttu-id="e096e-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e096e-124">xs:string</span></span>|<span data-ttu-id="e096e-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="e096e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="e096e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e096e-126">InstanceId</span></span>|<span data-ttu-id="e096e-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e096e-127">xs:string</span></span>|<span data-ttu-id="e096e-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="e096e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e096e-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="e096e-129">AppDomain</span></span>|<span data-ttu-id="e096e-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e096e-130">xs:string</span></span>|<span data-ttu-id="e096e-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e096e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
