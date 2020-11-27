---
title: 4212 — LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 43ec434064f768fc976232c6d3013f17c80fe053
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267172"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="04305-102">4212 — LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="04305-102">4212 - LockRetryTimeout</span></span>

## <a name="properties"></a><span data-ttu-id="04305-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="04305-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04305-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="04305-104">ID</span></span>|<span data-ttu-id="04305-105">4212</span><span class="sxs-lookup"><span data-stu-id="04305-105">4212</span></span>|  
|<span data-ttu-id="04305-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="04305-106">Keywords</span></span>|<span data-ttu-id="04305-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="04305-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="04305-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="04305-108">Level</span></span>|<span data-ttu-id="04305-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="04305-109">Warning</span></span>|  
|<span data-ttu-id="04305-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="04305-110">Channel</span></span>|<span data-ttu-id="04305-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="04305-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="04305-112">Opis</span><span class="sxs-lookup"><span data-stu-id="04305-112">Description</span></span>  

 <span data-ttu-id="04305-113">Dostawca SQL napotkał przekroczenie limitu czasu podczas próby uzyskania blokady wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="04305-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="04305-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="04305-114">Message</span></span>  

 <span data-ttu-id="04305-115">Przekroczono limit czasu podczas próby uzyskania blokady wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="04305-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="04305-116">Operacja nie została ukończona w wyznaczonym limicie czasu wynoszącym %1.</span><span class="sxs-lookup"><span data-stu-id="04305-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="04305-117">Czas przydzielony na tę operację mógł być częścią dłuższego limitu czasu.</span><span class="sxs-lookup"><span data-stu-id="04305-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="04305-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="04305-118">Details</span></span>  
  
|<span data-ttu-id="04305-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="04305-119">Data Item Name</span></span>|<span data-ttu-id="04305-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="04305-120">Data Item Type</span></span>|<span data-ttu-id="04305-121">Opis</span><span class="sxs-lookup"><span data-stu-id="04305-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="04305-122">Opóźnienie</span><span class="sxs-lookup"><span data-stu-id="04305-122">Delay</span></span>|<span data-ttu-id="04305-123">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="04305-123">xs:string</span></span>|<span data-ttu-id="04305-124">Opóźnienie między ponownymi próbami.</span><span class="sxs-lookup"><span data-stu-id="04305-124">The delay between retries.</span></span>|  
|<span data-ttu-id="04305-125">Wywołując</span><span class="sxs-lookup"><span data-stu-id="04305-125">AppDomain</span></span>|<span data-ttu-id="04305-126">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="04305-126">xs:string</span></span>|<span data-ttu-id="04305-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="04305-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
