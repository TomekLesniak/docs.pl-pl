---
title: 1125 — InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 0405b4e1207db5c056fbd478b98c408258daf0c3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294212"
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="db2d9-102">1125 — InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="db2d9-102">1125 - InvokeMethodIsNotStatic</span></span>

## <a name="properties"></a><span data-ttu-id="db2d9-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="db2d9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="db2d9-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="db2d9-104">ID</span></span>|<span data-ttu-id="db2d9-105">1125</span><span class="sxs-lookup"><span data-stu-id="db2d9-105">1125</span></span>|  
|<span data-ttu-id="db2d9-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="db2d9-106">Keywords</span></span>|<span data-ttu-id="db2d9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="db2d9-107">WFRuntime</span></span>|  
|<span data-ttu-id="db2d9-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="db2d9-108">Level</span></span>|<span data-ttu-id="db2d9-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="db2d9-109">Information</span></span>|  
|<span data-ttu-id="db2d9-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="db2d9-110">Channel</span></span>|<span data-ttu-id="db2d9-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="db2d9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="db2d9-112">Opis</span><span class="sxs-lookup"><span data-stu-id="db2d9-112">Description</span></span>  

 <span data-ttu-id="db2d9-113">Podczas kroku wywołaniem metody CacheMetadata działanie InvokeMethod wskazuje, że metoda wywoływana nie jest statyczna.</span><span class="sxs-lookup"><span data-stu-id="db2d9-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="db2d9-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="db2d9-114">Message</span></span>  

 <span data-ttu-id="db2d9-115">InvokeMethod "%1" — Metoda nie jest statyczna.</span><span class="sxs-lookup"><span data-stu-id="db2d9-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="db2d9-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="db2d9-116">Details</span></span>  
  
|<span data-ttu-id="db2d9-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="db2d9-117">Data Item Name</span></span>|<span data-ttu-id="db2d9-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="db2d9-118">Data Item Type</span></span>|<span data-ttu-id="db2d9-119">Opis</span><span class="sxs-lookup"><span data-stu-id="db2d9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="db2d9-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="db2d9-120">InvokeMethod</span></span>|<span data-ttu-id="db2d9-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="db2d9-121">xs:string</span></span>|<span data-ttu-id="db2d9-122">Nazwa wyświetlana działania InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="db2d9-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="db2d9-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="db2d9-123">AppDomain</span></span>|<span data-ttu-id="db2d9-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="db2d9-124">xs:string</span></span>|<span data-ttu-id="db2d9-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="db2d9-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
