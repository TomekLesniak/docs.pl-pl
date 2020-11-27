---
title: 4210 — SqlExceptionCaught
ms.date: 03/30/2017
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
ms.openlocfilehash: 1dab44e3fb97d74a2146f5bf992225222bc93d50
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280380"
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="b1ba7-102">4210 — SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="b1ba7-102">4210 - SqlExceptionCaught</span></span>

## <a name="properties"></a><span data-ttu-id="b1ba7-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="b1ba7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1ba7-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="b1ba7-104">ID</span></span>|<span data-ttu-id="b1ba7-105">4210</span><span class="sxs-lookup"><span data-stu-id="b1ba7-105">4210</span></span>|  
|<span data-ttu-id="b1ba7-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="b1ba7-106">Keywords</span></span>|<span data-ttu-id="b1ba7-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="b1ba7-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="b1ba7-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="b1ba7-108">Level</span></span>|<span data-ttu-id="b1ba7-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="b1ba7-109">Warning</span></span>|  
|<span data-ttu-id="b1ba7-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="b1ba7-110">Channel</span></span>|<span data-ttu-id="b1ba7-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="b1ba7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b1ba7-112">Opis</span><span class="sxs-lookup"><span data-stu-id="b1ba7-112">Description</span></span>  

 <span data-ttu-id="b1ba7-113">Wskazuje, że wyjątek SQL został przechwycony.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-113">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b1ba7-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="b1ba7-114">Message</span></span>  

 <span data-ttu-id="b1ba7-115">Przechwycono wyjątek SQL o numerze %1 (komunikat %2).</span><span class="sxs-lookup"><span data-stu-id="b1ba7-115">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b1ba7-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="b1ba7-116">Details</span></span>  
  
|<span data-ttu-id="b1ba7-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="b1ba7-117">Data Item Name</span></span>|<span data-ttu-id="b1ba7-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="b1ba7-118">Data Item Type</span></span>|<span data-ttu-id="b1ba7-119">Opis</span><span class="sxs-lookup"><span data-stu-id="b1ba7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b1ba7-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="b1ba7-120">ErrorNumber</span></span>|<span data-ttu-id="b1ba7-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="b1ba7-121">xs:string</span></span>|<span data-ttu-id="b1ba7-122">Numer błędu SQL.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-122">The SQL error number.</span></span>|  
|<span data-ttu-id="b1ba7-123">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="b1ba7-123">ExceptionMessage</span></span>|<span data-ttu-id="b1ba7-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="b1ba7-124">xs:string</span></span>|<span data-ttu-id="b1ba7-125">Komunikat z wyjątku SQL.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-125">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="b1ba7-126">Wywołując</span><span class="sxs-lookup"><span data-stu-id="b1ba7-126">AppDomain</span></span>|<span data-ttu-id="b1ba7-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="b1ba7-127">xs:string</span></span>|<span data-ttu-id="b1ba7-128">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
