---
title: 4211 — QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ff8a1e099934f5bf71fef0afbb7e54c0d1851fae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267185"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="3cfa4-102">4211 — QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="3cfa4-102">4211 - QueuingSqlRetry</span></span>

## <a name="properties"></a><span data-ttu-id="3cfa4-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="3cfa4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3cfa4-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="3cfa4-104">ID</span></span>|<span data-ttu-id="3cfa4-105">4211</span><span class="sxs-lookup"><span data-stu-id="3cfa4-105">4211</span></span>|  
|<span data-ttu-id="3cfa4-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="3cfa4-106">Keywords</span></span>|<span data-ttu-id="3cfa4-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="3cfa4-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="3cfa4-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="3cfa4-108">Level</span></span>|<span data-ttu-id="3cfa4-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="3cfa4-109">Warning</span></span>|  
|<span data-ttu-id="3cfa4-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="3cfa4-110">Channel</span></span>|<span data-ttu-id="3cfa4-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="3cfa4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3cfa4-112">Opis</span><span class="sxs-lookup"><span data-stu-id="3cfa4-112">Description</span></span>  

 <span data-ttu-id="3cfa4-113">Wskazuje, że usługa MSMQ ponawia próbę.</span><span class="sxs-lookup"><span data-stu-id="3cfa4-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3cfa4-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="3cfa4-114">Message</span></span>  

 <span data-ttu-id="3cfa4-115">Usługa kolejkowania ponów próbę wykonania instrukcji SQL z opóźnieniem %1 milisekund.</span><span class="sxs-lookup"><span data-stu-id="3cfa4-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3cfa4-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3cfa4-116">Details</span></span>  
  
|<span data-ttu-id="3cfa4-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="3cfa4-117">Data Item Name</span></span>|<span data-ttu-id="3cfa4-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="3cfa4-118">Data Item Type</span></span>|<span data-ttu-id="3cfa4-119">Opis</span><span class="sxs-lookup"><span data-stu-id="3cfa4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3cfa4-120">Opóźnienie</span><span class="sxs-lookup"><span data-stu-id="3cfa4-120">Delay</span></span>|<span data-ttu-id="3cfa4-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3cfa4-121">xs:string</span></span>|<span data-ttu-id="3cfa4-122">Opóźnienie między ponownymi próbami.</span><span class="sxs-lookup"><span data-stu-id="3cfa4-122">The delay between retries.</span></span>|  
|<span data-ttu-id="3cfa4-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="3cfa4-123">AppDomain</span></span>|<span data-ttu-id="3cfa4-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3cfa4-124">xs:string</span></span>|<span data-ttu-id="3cfa4-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3cfa4-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
