---
title: 4209 — TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: 9aa8cdffebb0cdf8b1e8225a394edf78ecf032b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238681"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="8902c-102">4209 — TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="8902c-102">4209 - TimeoutOpeningSqlConnection</span></span>

## <a name="properties"></a><span data-ttu-id="8902c-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="8902c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8902c-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="8902c-104">ID</span></span>|<span data-ttu-id="8902c-105">4209</span><span class="sxs-lookup"><span data-stu-id="8902c-105">4209</span></span>|  
|<span data-ttu-id="8902c-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="8902c-106">Keywords</span></span>|<span data-ttu-id="8902c-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="8902c-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="8902c-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="8902c-108">Level</span></span>|<span data-ttu-id="8902c-109">Błąd</span><span class="sxs-lookup"><span data-stu-id="8902c-109">Error</span></span>|  
|<span data-ttu-id="8902c-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="8902c-110">Channel</span></span>|<span data-ttu-id="8902c-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="8902c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8902c-112">Opis</span><span class="sxs-lookup"><span data-stu-id="8902c-112">Description</span></span>  

 <span data-ttu-id="8902c-113">Wskazuje, że podczas próby otwarcia połączenia SQL został przekroczony limit czasu.</span><span class="sxs-lookup"><span data-stu-id="8902c-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8902c-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="8902c-114">Message</span></span>  

 <span data-ttu-id="8902c-115">Przekroczono limit czasu podczas próby otwarcia połączenia SQL.</span><span class="sxs-lookup"><span data-stu-id="8902c-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="8902c-116">Operacja nie została ukończona w wyznaczonym limicie czasu wynoszącym %1.</span><span class="sxs-lookup"><span data-stu-id="8902c-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="8902c-117">Czas przydzielony na tę operację mógł być częścią dłuższego limitu czasu.</span><span class="sxs-lookup"><span data-stu-id="8902c-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8902c-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="8902c-118">Details</span></span>  
  
|<span data-ttu-id="8902c-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="8902c-119">Data Item Name</span></span>|<span data-ttu-id="8902c-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="8902c-120">Data Item Type</span></span>|<span data-ttu-id="8902c-121">Opis</span><span class="sxs-lookup"><span data-stu-id="8902c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8902c-122">Limit czasu</span><span class="sxs-lookup"><span data-stu-id="8902c-122">Timeout</span></span>|<span data-ttu-id="8902c-123">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="8902c-123">xs:string</span></span>|<span data-ttu-id="8902c-124">Wartość limitu czasu dla otwierania połączenia SQL.</span><span class="sxs-lookup"><span data-stu-id="8902c-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="8902c-125">Wywołując</span><span class="sxs-lookup"><span data-stu-id="8902c-125">AppDomain</span></span>|<span data-ttu-id="8902c-126">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="8902c-126">xs:string</span></span>|<span data-ttu-id="8902c-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8902c-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
