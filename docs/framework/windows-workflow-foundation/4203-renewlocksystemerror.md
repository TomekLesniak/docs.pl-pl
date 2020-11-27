---
title: 4203 — RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 17617e25c5cf8cecae608438529e9ce1a7d506f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251272"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="c61a5-102">4203 — RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="c61a5-102">4203 - RenewLockSystemError</span></span>

## <a name="properties"></a><span data-ttu-id="c61a5-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="c61a5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c61a5-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="c61a5-104">ID</span></span>|<span data-ttu-id="c61a5-105">4203</span><span class="sxs-lookup"><span data-stu-id="c61a5-105">4203</span></span>|  
|<span data-ttu-id="c61a5-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="c61a5-106">Keywords</span></span>|<span data-ttu-id="c61a5-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c61a5-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c61a5-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="c61a5-108">Level</span></span>|<span data-ttu-id="c61a5-109">Błąd</span><span class="sxs-lookup"><span data-stu-id="c61a5-109">Error</span></span>|  
|<span data-ttu-id="c61a5-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="c61a5-110">Channel</span></span>|<span data-ttu-id="c61a5-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="c61a5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c61a5-112">Opis</span><span class="sxs-lookup"><span data-stu-id="c61a5-112">Description</span></span>  

 <span data-ttu-id="c61a5-113">Wskazuje, że dostawca SQL nie może zwiększyć wygaśnięcia blokady z powodu wygaśnięcia blokady lub usunięcia właściciela blokady.</span><span class="sxs-lookup"><span data-stu-id="c61a5-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="c61a5-114">Obiekt SqlWorkflowInstanceStore zostanie przerwana.</span><span class="sxs-lookup"><span data-stu-id="c61a5-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c61a5-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="c61a5-115">Message</span></span>  

 <span data-ttu-id="c61a5-116">Nie można zwiększyć ważności blokady, upłynął już okres ważności blokady lub właściciel blokady został usunięty.</span><span class="sxs-lookup"><span data-stu-id="c61a5-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="c61a5-117">Przerywanie obiekt SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="c61a5-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c61a5-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="c61a5-118">Details</span></span>  
  
|<span data-ttu-id="c61a5-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="c61a5-119">Data Item Name</span></span>|<span data-ttu-id="c61a5-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="c61a5-120">Data Item Type</span></span>|<span data-ttu-id="c61a5-121">Opis</span><span class="sxs-lookup"><span data-stu-id="c61a5-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c61a5-122">Wywołując</span><span class="sxs-lookup"><span data-stu-id="c61a5-122">AppDomain</span></span>|<span data-ttu-id="c61a5-123">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c61a5-123">xs:string</span></span>|<span data-ttu-id="c61a5-124">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c61a5-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
