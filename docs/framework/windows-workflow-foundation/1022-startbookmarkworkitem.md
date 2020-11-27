---
title: 1022 — StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: ca1f4244fb1a5144cb2d86eaacb9b31137d317c2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275339"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="45fa6-102">1022 — StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="45fa6-102">1022 - StartBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="45fa6-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="45fa6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45fa6-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="45fa6-104">ID</span></span>|<span data-ttu-id="45fa6-105">1022</span><span class="sxs-lookup"><span data-stu-id="45fa6-105">1022</span></span>|  
|<span data-ttu-id="45fa6-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="45fa6-106">Keywords</span></span>|<span data-ttu-id="45fa6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="45fa6-107">WFRuntime</span></span>|  
|<span data-ttu-id="45fa6-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="45fa6-108">Level</span></span>|<span data-ttu-id="45fa6-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="45fa6-109">Verbose</span></span>|  
|<span data-ttu-id="45fa6-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="45fa6-110">Channel</span></span>|<span data-ttu-id="45fa6-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="45fa6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="45fa6-112">Opis</span><span class="sxs-lookup"><span data-stu-id="45fa6-112">Description</span></span>  

 <span data-ttu-id="45fa6-113">Wskazuje, że BookmarkWorkItem rozpoczyna wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="45fa6-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="45fa6-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="45fa6-114">Message</span></span>  

 <span data-ttu-id="45fa6-115">Rozpoczynanie wykonywania elementu BookmarkWorkItem dla działania "%1", nazwa wyświetlana: %2, identyfikator wystąpienia: %3.</span><span class="sxs-lookup"><span data-stu-id="45fa6-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="45fa6-116">Zakładkaname: %4, obiektem BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="45fa6-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="45fa6-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="45fa6-117">Details</span></span>  
  
|<span data-ttu-id="45fa6-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="45fa6-118">Data Item Name</span></span>|<span data-ttu-id="45fa6-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="45fa6-119">Data Item Type</span></span>|<span data-ttu-id="45fa6-120">Opis</span><span class="sxs-lookup"><span data-stu-id="45fa6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="45fa6-121">Działanie</span><span class="sxs-lookup"><span data-stu-id="45fa6-121">Activity</span></span>|<span data-ttu-id="45fa6-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="45fa6-122">xs:string</span></span>|<span data-ttu-id="45fa6-123">Nazwa typu działania.</span><span class="sxs-lookup"><span data-stu-id="45fa6-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="45fa6-124">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="45fa6-124">DisplayName</span></span>|<span data-ttu-id="45fa6-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="45fa6-125">xs:string</span></span>|<span data-ttu-id="45fa6-126">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="45fa6-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="45fa6-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="45fa6-127">InstanceId</span></span>|<span data-ttu-id="45fa6-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="45fa6-128">xs:string</span></span>|<span data-ttu-id="45fa6-129">Identyfikator wystąpienia działania.</span><span class="sxs-lookup"><span data-stu-id="45fa6-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="45fa6-130">Zakładkaname</span><span class="sxs-lookup"><span data-stu-id="45fa6-130">BookmarkName</span></span>|<span data-ttu-id="45fa6-131">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="45fa6-131">xs:string</span></span>|<span data-ttu-id="45fa6-132">Nazwa zakładki.</span><span class="sxs-lookup"><span data-stu-id="45fa6-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="45fa6-133">Obiektem BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="45fa6-133">BookmarkScope</span></span>|<span data-ttu-id="45fa6-134">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="45fa6-134">xs:string</span></span>|<span data-ttu-id="45fa6-135">Zakres zakładki.</span><span class="sxs-lookup"><span data-stu-id="45fa6-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="45fa6-136">Wywołując</span><span class="sxs-lookup"><span data-stu-id="45fa6-136">AppDomain</span></span>|<span data-ttu-id="45fa6-137">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="45fa6-137">xs:string</span></span>|<span data-ttu-id="45fa6-138">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="45fa6-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
