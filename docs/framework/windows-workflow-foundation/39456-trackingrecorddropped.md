---
title: 39456 — TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: d958b506e057bc0d59f954debdc9da6015bf5f1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273103"
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="1f584-102">39456 — TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="1f584-102">39456 - TrackingRecordDropped</span></span>

## <a name="properties"></a><span data-ttu-id="1f584-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="1f584-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1f584-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="1f584-104">ID</span></span>|<span data-ttu-id="1f584-105">39456</span><span class="sxs-lookup"><span data-stu-id="1f584-105">39456</span></span>|  
|<span data-ttu-id="1f584-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="1f584-106">Keywords</span></span>|<span data-ttu-id="1f584-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="1f584-107">WFTracking</span></span>|  
|<span data-ttu-id="1f584-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="1f584-108">Level</span></span>|<span data-ttu-id="1f584-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="1f584-109">Warning</span></span>|  
|<span data-ttu-id="1f584-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="1f584-110">Channel</span></span>|<span data-ttu-id="1f584-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="1f584-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1f584-112">Opis</span><span class="sxs-lookup"><span data-stu-id="1f584-112">Description</span></span>  

 <span data-ttu-id="1f584-113">Wskazuje, że rekord śledzenia został porzucony, ponieważ jego rozmiar przekracza wartość maksymalną dozwoloną przez dostawcę sesji ETW.</span><span class="sxs-lookup"><span data-stu-id="1f584-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1f584-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="1f584-114">Message</span></span>  

 <span data-ttu-id="1f584-115">Rozmiar rekordu śledzenia %1 przekracza maksymalną dozwoloną przez sesję ETW dla dostawcy %2</span><span class="sxs-lookup"><span data-stu-id="1f584-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="1f584-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="1f584-116">Details</span></span>  
  
|<span data-ttu-id="1f584-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="1f584-117">Data Item Name</span></span>|<span data-ttu-id="1f584-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="1f584-118">Data Item Type</span></span>|<span data-ttu-id="1f584-119">Opis</span><span class="sxs-lookup"><span data-stu-id="1f584-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1f584-120">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="1f584-120">Exception</span></span>|<span data-ttu-id="1f584-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="1f584-121">xs:string</span></span>|<span data-ttu-id="1f584-122">Szczegóły wyjątku dla wyjątku</span><span class="sxs-lookup"><span data-stu-id="1f584-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="1f584-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="1f584-123">AppDomain</span></span>|<span data-ttu-id="1f584-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="1f584-124">xs:string</span></span>|<span data-ttu-id="1f584-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1f584-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
