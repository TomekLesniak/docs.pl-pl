---
title: 3552 — MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: bd3e7539922e6c430c4ffe5bd96ef1ac7dbd098f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261166"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="3e5c3-102">3552 — MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="3e5c3-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="3e5c3-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="3e5c3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e5c3-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="3e5c3-104">ID</span></span>|<span data-ttu-id="3e5c3-105">3552</span><span class="sxs-lookup"><span data-stu-id="3e5c3-105">3552</span></span>|  
|<span data-ttu-id="3e5c3-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="3e5c3-106">Keywords</span></span>|<span data-ttu-id="3e5c3-107">Przydział, WFServices</span><span class="sxs-lookup"><span data-stu-id="3e5c3-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="3e5c3-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="3e5c3-108">Level</span></span>|<span data-ttu-id="3e5c3-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="3e5c3-109">Warning</span></span>|  
|<span data-ttu-id="3e5c3-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="3e5c3-110">Channel</span></span>|<span data-ttu-id="3e5c3-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="3e5c3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3e5c3-112">Opis</span><span class="sxs-lookup"><span data-stu-id="3e5c3-112">Description</span></span>  

 <span data-ttu-id="3e5c3-113">Wskazuje, że osiągnięto limit ograniczania przepustowości "MaxPendingMessagesPerChannel".</span><span class="sxs-lookup"><span data-stu-id="3e5c3-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3e5c3-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="3e5c3-114">Message</span></span>  

 <span data-ttu-id="3e5c3-115">Osiągnięto limit "%1" dławienia "MaxPendingMessagesPerChannel".</span><span class="sxs-lookup"><span data-stu-id="3e5c3-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="3e5c3-116">Aby zwiększyć ten limit, Dostosuj Właściwość MaxPendingMessagesPerChannel w BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3e5c3-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3e5c3-117">Details</span></span>  
  
|<span data-ttu-id="3e5c3-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="3e5c3-118">Data Item Name</span></span>|<span data-ttu-id="3e5c3-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="3e5c3-119">Data Item Type</span></span>|<span data-ttu-id="3e5c3-120">Opis</span><span class="sxs-lookup"><span data-stu-id="3e5c3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3e5c3-121">Limit</span><span class="sxs-lookup"><span data-stu-id="3e5c3-121">Limit</span></span>|<span data-ttu-id="3e5c3-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3e5c3-122">xs:string</span></span>|<span data-ttu-id="3e5c3-123">Limit ograniczenia MaxPendingMessagesPerChannel.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="3e5c3-124">Wywołując</span><span class="sxs-lookup"><span data-stu-id="3e5c3-124">AppDomain</span></span>|<span data-ttu-id="3e5c3-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3e5c3-125">xs:string</span></span>|<span data-ttu-id="3e5c3-126">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
