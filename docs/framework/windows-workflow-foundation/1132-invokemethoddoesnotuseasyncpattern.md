---
title: 1132 — InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 9249bdd0fe996ee7c1b04783ac8fef2c48063cc0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294160"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="15058-102">1132 — InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="15058-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="15058-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="15058-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15058-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="15058-104">ID</span></span>|<span data-ttu-id="15058-105">1132</span><span class="sxs-lookup"><span data-stu-id="15058-105">1132</span></span>|  
|<span data-ttu-id="15058-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="15058-106">Keywords</span></span>|<span data-ttu-id="15058-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="15058-107">WFRuntime</span></span>|  
|<span data-ttu-id="15058-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="15058-108">Level</span></span>|<span data-ttu-id="15058-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="15058-109">Information</span></span>|  
|<span data-ttu-id="15058-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="15058-110">Channel</span></span>|<span data-ttu-id="15058-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="15058-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="15058-112">Opis</span><span class="sxs-lookup"><span data-stu-id="15058-112">Description</span></span>  

 <span data-ttu-id="15058-113">Podczas wykonywania kroku wywołaniem metody CacheMetadata działanie InvokeMethod wskazuje, że nie używa wzorca asynchronicznego podczas wywoływania metody.</span><span class="sxs-lookup"><span data-stu-id="15058-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="15058-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="15058-114">Message</span></span>  

 <span data-ttu-id="15058-115">InvokeMethod "%1" — Metoda nie korzysta ze wzorca asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="15058-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="15058-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="15058-116">Details</span></span>  
  
|<span data-ttu-id="15058-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="15058-117">Data Item Name</span></span>|<span data-ttu-id="15058-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="15058-118">Data Item Type</span></span>|<span data-ttu-id="15058-119">Opis</span><span class="sxs-lookup"><span data-stu-id="15058-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="15058-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="15058-120">InvokeMethod</span></span>|<span data-ttu-id="15058-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="15058-121">xs:string</span></span>|<span data-ttu-id="15058-122">Nazwa wyświetlana działania InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="15058-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="15058-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="15058-123">AppDomain</span></span>|<span data-ttu-id="15058-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="15058-124">xs:string</span></span>|<span data-ttu-id="15058-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="15058-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
