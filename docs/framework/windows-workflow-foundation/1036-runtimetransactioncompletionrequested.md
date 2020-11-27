---
title: 1036 — RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 96ea253fd61652a3719eaf8b1a4d31aa88337eeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294264"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="ecfa0-102">1036 — RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="ecfa0-102">1036 - RuntimeTransactionCompletionRequested</span></span>

## <a name="properties"></a><span data-ttu-id="ecfa0-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ecfa0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecfa0-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="ecfa0-104">ID</span></span>|<span data-ttu-id="ecfa0-105">1036</span><span class="sxs-lookup"><span data-stu-id="ecfa0-105">1036</span></span>|  
|<span data-ttu-id="ecfa0-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="ecfa0-106">Keywords</span></span>|<span data-ttu-id="ecfa0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ecfa0-107">WFRuntime</span></span>|  
|<span data-ttu-id="ecfa0-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="ecfa0-108">Level</span></span>|<span data-ttu-id="ecfa0-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="ecfa0-109">Verbose</span></span>|  
|<span data-ttu-id="ecfa0-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="ecfa0-110">Channel</span></span>|<span data-ttu-id="ecfa0-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="ecfa0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ecfa0-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ecfa0-112">Description</span></span>  

 <span data-ttu-id="ecfa0-113">Wskazuje, że działanie zaplanował ukończenie transakcji środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="ecfa0-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ecfa0-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="ecfa0-114">Message</span></span>  

 <span data-ttu-id="ecfa0-115">Działanie %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3, ma zaplanowane zakończenie transakcji środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="ecfa0-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ecfa0-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ecfa0-116">Details</span></span>  
  
|<span data-ttu-id="ecfa0-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="ecfa0-117">Data Item Name</span></span>|<span data-ttu-id="ecfa0-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="ecfa0-118">Data Item Type</span></span>|<span data-ttu-id="ecfa0-119">Opis</span><span class="sxs-lookup"><span data-stu-id="ecfa0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ecfa0-120">Działanie</span><span class="sxs-lookup"><span data-stu-id="ecfa0-120">Activity</span></span>|<span data-ttu-id="ecfa0-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ecfa0-121">xs:string</span></span>|<span data-ttu-id="ecfa0-122">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="ecfa0-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ecfa0-123">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="ecfa0-123">DisplayName</span></span>|<span data-ttu-id="ecfa0-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ecfa0-124">xs:string</span></span>|<span data-ttu-id="ecfa0-125">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="ecfa0-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ecfa0-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ecfa0-126">InstanceId</span></span>|<span data-ttu-id="ecfa0-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ecfa0-127">xs:string</span></span>|<span data-ttu-id="ecfa0-128">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="ecfa0-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ecfa0-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="ecfa0-129">AppDomain</span></span>|<span data-ttu-id="ecfa0-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ecfa0-130">xs:string</span></span>|<span data-ttu-id="ecfa0-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ecfa0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
