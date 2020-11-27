---
title: 1126 — InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 7caaebe42f49a62fec61ba17a4d3fe3a538e2ab4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262843"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="48dbd-102">1126 — InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="48dbd-102">1126 - InvokedMethodThrewException</span></span>

## <a name="properties"></a><span data-ttu-id="48dbd-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="48dbd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48dbd-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="48dbd-104">ID</span></span>|<span data-ttu-id="48dbd-105">1126</span><span class="sxs-lookup"><span data-stu-id="48dbd-105">1126</span></span>|  
|<span data-ttu-id="48dbd-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="48dbd-106">Keywords</span></span>|<span data-ttu-id="48dbd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="48dbd-107">WFRuntime</span></span>|  
|<span data-ttu-id="48dbd-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="48dbd-108">Level</span></span>|<span data-ttu-id="48dbd-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="48dbd-109">Information</span></span>|  
|<span data-ttu-id="48dbd-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="48dbd-110">Channel</span></span>|<span data-ttu-id="48dbd-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="48dbd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48dbd-112">Opis</span><span class="sxs-lookup"><span data-stu-id="48dbd-112">Description</span></span>  

 <span data-ttu-id="48dbd-113">Wskazuje, że wyjątek został zgłoszony przez metodę wywoływaną przez działanie InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="48dbd-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48dbd-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="48dbd-114">Message</span></span>  

 <span data-ttu-id="48dbd-115">Zgłoszono wyjątek w metodzie wywoływanej przez działanie "%1".</span><span class="sxs-lookup"><span data-stu-id="48dbd-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="48dbd-116">%2</span><span class="sxs-lookup"><span data-stu-id="48dbd-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="48dbd-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="48dbd-117">Details</span></span>  
  
|<span data-ttu-id="48dbd-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="48dbd-118">Data Item Name</span></span>|<span data-ttu-id="48dbd-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="48dbd-119">Data Item Type</span></span>|<span data-ttu-id="48dbd-120">Opis</span><span class="sxs-lookup"><span data-stu-id="48dbd-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48dbd-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="48dbd-121">InvokeMethod</span></span>|<span data-ttu-id="48dbd-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="48dbd-122">xs:string</span></span>|<span data-ttu-id="48dbd-123">Nazwa wyświetlana działania InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="48dbd-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="48dbd-124">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="48dbd-124">Exception</span></span>|<span data-ttu-id="48dbd-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="48dbd-125">xs:string</span></span>|<span data-ttu-id="48dbd-126">Szczegóły wyjątku dla wyjątku</span><span class="sxs-lookup"><span data-stu-id="48dbd-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="48dbd-127">Wywołując</span><span class="sxs-lookup"><span data-stu-id="48dbd-127">AppDomain</span></span>|<span data-ttu-id="48dbd-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="48dbd-128">xs:string</span></span>|<span data-ttu-id="48dbd-129">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="48dbd-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
