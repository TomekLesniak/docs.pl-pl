---
title: 1124 — InvokeMethodIsStatic
ms.date: 03/30/2017
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
ms.openlocfilehash: d7ad99131f9813c2102f52784fc33605bed37557
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242126"
---
# <a name="1124---invokemethodisstatic"></a><span data-ttu-id="28b92-102">1124 — InvokeMethodIsStatic</span><span class="sxs-lookup"><span data-stu-id="28b92-102">1124 - InvokeMethodIsStatic</span></span>

## <a name="properties"></a><span data-ttu-id="28b92-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="28b92-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28b92-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="28b92-104">ID</span></span>|<span data-ttu-id="28b92-105">1124</span><span class="sxs-lookup"><span data-stu-id="28b92-105">1124</span></span>|  
|<span data-ttu-id="28b92-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="28b92-106">Keywords</span></span>|<span data-ttu-id="28b92-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="28b92-107">WFRuntime</span></span>|  
|<span data-ttu-id="28b92-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="28b92-108">Level</span></span>|<span data-ttu-id="28b92-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="28b92-109">Information</span></span>|  
|<span data-ttu-id="28b92-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="28b92-110">Channel</span></span>|<span data-ttu-id="28b92-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="28b92-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="28b92-112">Opis</span><span class="sxs-lookup"><span data-stu-id="28b92-112">Description</span></span>  

 <span data-ttu-id="28b92-113">Podczas kroku wywołaniem metody CacheMetadata działanie InvokeMethod wskazuje, że wywoływana metoda jest statyczna.</span><span class="sxs-lookup"><span data-stu-id="28b92-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="28b92-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="28b92-114">Message</span></span>  

 <span data-ttu-id="28b92-115">InvokeMethod "%1" — Metoda jest statyczna.</span><span class="sxs-lookup"><span data-stu-id="28b92-115">InvokeMethod '%1' - method is Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="28b92-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="28b92-116">Details</span></span>  
  
|<span data-ttu-id="28b92-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="28b92-117">Data Item Name</span></span>|<span data-ttu-id="28b92-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="28b92-118">Data Item Type</span></span>|<span data-ttu-id="28b92-119">Opis</span><span class="sxs-lookup"><span data-stu-id="28b92-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="28b92-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="28b92-120">InvokeMethod</span></span>|<span data-ttu-id="28b92-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="28b92-121">xs:string</span></span>|<span data-ttu-id="28b92-122">Nazwa wyświetlana działania InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="28b92-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="28b92-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="28b92-123">AppDomain</span></span>|<span data-ttu-id="28b92-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="28b92-124">xs:string</span></span>|<span data-ttu-id="28b92-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="28b92-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
