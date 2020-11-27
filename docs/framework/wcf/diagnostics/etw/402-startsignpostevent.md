---
title: 402 — StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
ms.openlocfilehash: ff32c900f4e357b7f1eca669a0ea60f80ea24b19
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258325"
---
# <a name="402---startsignpostevent"></a><span data-ttu-id="ab949-102">402 — StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="ab949-102">402 - StartSignpostEvent</span></span>

## <a name="properties"></a><span data-ttu-id="ab949-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ab949-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab949-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="ab949-104">ID</span></span>|<span data-ttu-id="ab949-105">402</span><span class="sxs-lookup"><span data-stu-id="ab949-105">402</span></span>|  
|<span data-ttu-id="ab949-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="ab949-106">Keywords</span></span>|<span data-ttu-id="ab949-107">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ab949-107">Troubleshooting</span></span>|  
|<span data-ttu-id="ab949-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="ab949-108">Level</span></span>|<span data-ttu-id="ab949-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="ab949-109">Information</span></span>|  
|<span data-ttu-id="ab949-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="ab949-110">Channel</span></span>|<span data-ttu-id="ab949-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="ab949-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ab949-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ab949-112">Description</span></span>  

 <span data-ttu-id="ab949-113">To zdarzenie oznacza początek działania end-to-end.</span><span class="sxs-lookup"><span data-stu-id="ab949-113">This event marks the beginning of an end-to-end activity.</span></span> <span data-ttu-id="ab949-114">Zawiera nazwę działania.</span><span class="sxs-lookup"><span data-stu-id="ab949-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ab949-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="ab949-115">Message</span></span>  

 <span data-ttu-id="ab949-116">Granica działania.</span><span class="sxs-lookup"><span data-stu-id="ab949-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ab949-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ab949-117">Details</span></span>  
  
|<span data-ttu-id="ab949-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="ab949-118">Data Item Name</span></span>|<span data-ttu-id="ab949-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="ab949-119">Data Item Type</span></span>|<span data-ttu-id="ab949-120">Opis</span><span class="sxs-lookup"><span data-stu-id="ab949-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ab949-121">Dane rozszerzone</span><span class="sxs-lookup"><span data-stu-id="ab949-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="ab949-122">Nazwa działania.</span><span class="sxs-lookup"><span data-stu-id="ab949-122">The name of the activity.</span></span>|  
|<span data-ttu-id="ab949-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="ab949-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ab949-124">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ab949-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
