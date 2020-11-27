---
title: 1027 — StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: cb5671ce7a30a7096104ba0ca6c4f36bed6b93f9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275235"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="a656b-102">1027 — StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="a656b-102">1027 - StartTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="a656b-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="a656b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a656b-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="a656b-104">ID</span></span>|<span data-ttu-id="a656b-105">1027</span><span class="sxs-lookup"><span data-stu-id="a656b-105">1027</span></span>|  
|<span data-ttu-id="a656b-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="a656b-106">Keywords</span></span>|<span data-ttu-id="a656b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a656b-107">WFRuntime</span></span>|  
|<span data-ttu-id="a656b-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="a656b-108">Level</span></span>|<span data-ttu-id="a656b-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="a656b-109">Verbose</span></span>|  
|<span data-ttu-id="a656b-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="a656b-110">Channel</span></span>|<span data-ttu-id="a656b-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="a656b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a656b-112">Opis</span><span class="sxs-lookup"><span data-stu-id="a656b-112">Description</span></span>  

 <span data-ttu-id="a656b-113">Wskazuje, że roboczego TransactionContextWorkItem rozpoczyna wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="a656b-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a656b-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="a656b-114">Message</span></span>  

 <span data-ttu-id="a656b-115">Rozpoczynanie wykonywania elementu roboczego TransactionContextWorkItem dla działania "%1", nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="a656b-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a656b-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="a656b-116">Details</span></span>  
  
|<span data-ttu-id="a656b-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="a656b-117">Data Item Name</span></span>|<span data-ttu-id="a656b-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="a656b-118">Data Item Type</span></span>|<span data-ttu-id="a656b-119">Opis</span><span class="sxs-lookup"><span data-stu-id="a656b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a656b-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="a656b-120">Activity</span></span>|<span data-ttu-id="a656b-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="a656b-121">xs:string</span></span>|<span data-ttu-id="a656b-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="a656b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="a656b-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="a656b-123">DisplayName</span></span>|<span data-ttu-id="a656b-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="a656b-124">xs:string</span></span>|<span data-ttu-id="a656b-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="a656b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="a656b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a656b-126">InstanceId</span></span>|<span data-ttu-id="a656b-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="a656b-127">xs:string</span></span>|<span data-ttu-id="a656b-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="a656b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a656b-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="a656b-129">AppDomain</span></span>|<span data-ttu-id="a656b-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="a656b-130">xs:string</span></span>|<span data-ttu-id="a656b-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a656b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
