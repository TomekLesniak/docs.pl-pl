---
title: 403 — SuspendSignpostEvent
ms.date: 03/30/2017
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
ms.openlocfilehash: 66251141cdf66c18ad0c1334f6f3e6c0629b4b33
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241060"
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="7dce6-102">403 — SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="7dce6-102">403 - SuspendSignpostEvent</span></span>

## <a name="properties"></a><span data-ttu-id="7dce6-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="7dce6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7dce6-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="7dce6-104">ID</span></span>|<span data-ttu-id="7dce6-105">403</span><span class="sxs-lookup"><span data-stu-id="7dce6-105">403</span></span>|  
|<span data-ttu-id="7dce6-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="7dce6-106">Keywords</span></span>|<span data-ttu-id="7dce6-107">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="7dce6-107">Troubleshooting</span></span>|  
|<span data-ttu-id="7dce6-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="7dce6-108">Level</span></span>|<span data-ttu-id="7dce6-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="7dce6-109">Information</span></span>|  
|<span data-ttu-id="7dce6-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="7dce6-110">Channel</span></span>|<span data-ttu-id="7dce6-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="7dce6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7dce6-112">Opis</span><span class="sxs-lookup"><span data-stu-id="7dce6-112">Description</span></span>  

 <span data-ttu-id="7dce6-113">To zdarzenie oznacza zawieszenie działania end-to-end.</span><span class="sxs-lookup"><span data-stu-id="7dce6-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="7dce6-114">Zawiera nazwę działania.</span><span class="sxs-lookup"><span data-stu-id="7dce6-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7dce6-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="7dce6-115">Message</span></span>  

 <span data-ttu-id="7dce6-116">Granica działania.</span><span class="sxs-lookup"><span data-stu-id="7dce6-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7dce6-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="7dce6-117">Details</span></span>  
  
|<span data-ttu-id="7dce6-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="7dce6-118">Data Item Name</span></span>|<span data-ttu-id="7dce6-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="7dce6-119">Data Item Type</span></span>|<span data-ttu-id="7dce6-120">Opis</span><span class="sxs-lookup"><span data-stu-id="7dce6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7dce6-121">Dane rozszerzone</span><span class="sxs-lookup"><span data-stu-id="7dce6-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="7dce6-122">Nazwa działania.</span><span class="sxs-lookup"><span data-stu-id="7dce6-122">The name of the activity.</span></span>|  
|<span data-ttu-id="7dce6-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="7dce6-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7dce6-124">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7dce6-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
