---
title: 39458 — TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: f02a34673c51be6e0b127a64e4622131575d836f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275895"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="fd946-102">39458 — TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="fd946-102">39458 - TrackingRecordTruncated</span></span>

## <a name="properties"></a><span data-ttu-id="fd946-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="fd946-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd946-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="fd946-104">ID</span></span>|<span data-ttu-id="fd946-105">39458</span><span class="sxs-lookup"><span data-stu-id="fd946-105">39458</span></span>|  
|<span data-ttu-id="fd946-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="fd946-106">Keywords</span></span>|<span data-ttu-id="fd946-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="fd946-107">WFTracking</span></span>|  
|<span data-ttu-id="fd946-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="fd946-108">Level</span></span>|<span data-ttu-id="fd946-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="fd946-109">Warning</span></span>|  
|<span data-ttu-id="fd946-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="fd946-110">Channel</span></span>|<span data-ttu-id="fd946-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="fd946-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fd946-112">Opis</span><span class="sxs-lookup"><span data-stu-id="fd946-112">Description</span></span>  

 <span data-ttu-id="fd946-113">Wskazuje, że rekord śledzenia został obcięty.</span><span class="sxs-lookup"><span data-stu-id="fd946-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="fd946-114">Zmienne/adnotacje/dane użytkownika zostały usunięte.</span><span class="sxs-lookup"><span data-stu-id="fd946-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fd946-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="fd946-115">Message</span></span>  

 <span data-ttu-id="fd946-116">Obcięty rekord śledzenia %1 zapisany w sesji ETW z dostawcą %2.</span><span class="sxs-lookup"><span data-stu-id="fd946-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="fd946-117">Zmienne/adnotacje/dane użytkownika zostały usunięte</span><span class="sxs-lookup"><span data-stu-id="fd946-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="fd946-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="fd946-118">Details</span></span>  
  
|<span data-ttu-id="fd946-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="fd946-119">Data Item Name</span></span>|<span data-ttu-id="fd946-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="fd946-120">Data Item Type</span></span>|<span data-ttu-id="fd946-121">Opis</span><span class="sxs-lookup"><span data-stu-id="fd946-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fd946-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="fd946-122">RecordNumber</span></span>|<span data-ttu-id="fd946-123">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="fd946-123">xs:string</span></span>|<span data-ttu-id="fd946-124">Numer rekordu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="fd946-124">The tracking record number.</span></span>|  
|<span data-ttu-id="fd946-125">Identyfikatorem</span><span class="sxs-lookup"><span data-stu-id="fd946-125">ProviderId</span></span>|<span data-ttu-id="fd946-126">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="fd946-126">xs:string</span></span>|<span data-ttu-id="fd946-127">Identyfikator dostawcy ETW.</span><span class="sxs-lookup"><span data-stu-id="fd946-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="fd946-128">Wywołując</span><span class="sxs-lookup"><span data-stu-id="fd946-128">AppDomain</span></span>|<span data-ttu-id="fd946-129">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="fd946-129">xs:string</span></span>|<span data-ttu-id="fd946-130">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fd946-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
