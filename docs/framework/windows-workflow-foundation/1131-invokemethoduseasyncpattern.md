---
title: 1131 — InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 2192b63b8a08657b69f6e3984f898bd6baddbc5f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294186"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="c10f2-102">1131 — InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="c10f2-102">1131 - InvokeMethodUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="c10f2-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="c10f2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c10f2-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="c10f2-104">ID</span></span>|<span data-ttu-id="c10f2-105">1131</span><span class="sxs-lookup"><span data-stu-id="c10f2-105">1131</span></span>|  
|<span data-ttu-id="c10f2-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="c10f2-106">Keywords</span></span>|<span data-ttu-id="c10f2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c10f2-107">WFRuntime</span></span>|  
|<span data-ttu-id="c10f2-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="c10f2-108">Level</span></span>|<span data-ttu-id="c10f2-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="c10f2-109">Information</span></span>|  
|<span data-ttu-id="c10f2-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="c10f2-110">Channel</span></span>|<span data-ttu-id="c10f2-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="c10f2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c10f2-112">Opis</span><span class="sxs-lookup"><span data-stu-id="c10f2-112">Description</span></span>  

 <span data-ttu-id="c10f2-113">Podczas wykonywania kroku wywołaniem metody CacheMetadata działanie InvokeMethod wskazuje, że jest używany wzorzec asynchroniczny podczas wywoływania metody.</span><span class="sxs-lookup"><span data-stu-id="c10f2-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c10f2-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="c10f2-114">Message</span></span>  

 <span data-ttu-id="c10f2-115">InvokeMethod "%1" — Metoda używa wzorca asynchronicznego dla "%2" i "%3".</span><span class="sxs-lookup"><span data-stu-id="c10f2-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c10f2-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="c10f2-116">Details</span></span>  
  
|<span data-ttu-id="c10f2-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="c10f2-117">Data Item Name</span></span>|<span data-ttu-id="c10f2-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="c10f2-118">Data Item Type</span></span>|<span data-ttu-id="c10f2-119">Opis</span><span class="sxs-lookup"><span data-stu-id="c10f2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c10f2-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="c10f2-120">InvokeMethod</span></span>|<span data-ttu-id="c10f2-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c10f2-121">xs:string</span></span>|<span data-ttu-id="c10f2-122">Nazwa wyświetlana działania InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="c10f2-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="c10f2-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="c10f2-123">BeginMethod</span></span>|<span data-ttu-id="c10f2-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c10f2-124">xs:string</span></span>|<span data-ttu-id="c10f2-125">Nazwa metody BEGIN.</span><span class="sxs-lookup"><span data-stu-id="c10f2-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="c10f2-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="c10f2-126">EndMethod</span></span>|<span data-ttu-id="c10f2-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c10f2-127">xs:string</span></span>|<span data-ttu-id="c10f2-128">Nazwa metody end.</span><span class="sxs-lookup"><span data-stu-id="c10f2-128">The name of the end method.</span></span>|  
|<span data-ttu-id="c10f2-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="c10f2-129">AppDomain</span></span>|<span data-ttu-id="c10f2-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c10f2-130">xs:string</span></span>|<span data-ttu-id="c10f2-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c10f2-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
