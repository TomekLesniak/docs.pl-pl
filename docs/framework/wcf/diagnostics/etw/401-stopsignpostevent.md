---
title: 401— StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: e549a8aabd0a54022000515050cde19dc4f20dd3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294069"
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="dd077-102">401— StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="dd077-102">401- StopSignPostEvent</span></span>

## <a name="properties"></a><span data-ttu-id="dd077-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="dd077-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd077-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="dd077-104">ID</span></span>|<span data-ttu-id="dd077-105">401</span><span class="sxs-lookup"><span data-stu-id="dd077-105">401</span></span>|  
|<span data-ttu-id="dd077-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="dd077-106">Keywords</span></span>|<span data-ttu-id="dd077-107">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="dd077-107">Troubleshooting</span></span>|  
|<span data-ttu-id="dd077-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="dd077-108">Level</span></span>|<span data-ttu-id="dd077-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="dd077-109">Information</span></span>|  
|<span data-ttu-id="dd077-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="dd077-110">Channel</span></span>|<span data-ttu-id="dd077-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="dd077-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dd077-112">Opis</span><span class="sxs-lookup"><span data-stu-id="dd077-112">Description</span></span>  

 <span data-ttu-id="dd077-113">To zdarzenie oznacza zakończenie działania end-to-end.</span><span class="sxs-lookup"><span data-stu-id="dd077-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="dd077-114">Zawiera nazwę działania.</span><span class="sxs-lookup"><span data-stu-id="dd077-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dd077-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="dd077-115">Message</span></span>  

 <span data-ttu-id="dd077-116">Granica działania.</span><span class="sxs-lookup"><span data-stu-id="dd077-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dd077-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="dd077-117">Details</span></span>  
  
|<span data-ttu-id="dd077-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="dd077-118">Data Item Name</span></span>|<span data-ttu-id="dd077-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="dd077-119">Data Item Type</span></span>|<span data-ttu-id="dd077-120">Opis</span><span class="sxs-lookup"><span data-stu-id="dd077-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dd077-121">Dane rozszerzone</span><span class="sxs-lookup"><span data-stu-id="dd077-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="dd077-122">Nazwa działania.</span><span class="sxs-lookup"><span data-stu-id="dd077-122">The name of the activity.</span></span>|  
|<span data-ttu-id="dd077-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="dd077-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="dd077-124">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="dd077-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
