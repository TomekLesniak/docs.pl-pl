---
title: 3503 — DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: e1e64824ee9a95757ed7c00aa17fa80898219401
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270331"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="05e90-102">3503 — DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="05e90-102">3503 - DuplicateCorrelationQuery</span></span>

## <a name="properties"></a><span data-ttu-id="05e90-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="05e90-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05e90-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="05e90-104">ID</span></span>|<span data-ttu-id="05e90-105">3503</span><span class="sxs-lookup"><span data-stu-id="05e90-105">3503</span></span>|  
|<span data-ttu-id="05e90-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="05e90-106">Keywords</span></span>|<span data-ttu-id="05e90-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="05e90-107">WFServices</span></span>|  
|<span data-ttu-id="05e90-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="05e90-108">Level</span></span>|<span data-ttu-id="05e90-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="05e90-109">Warning</span></span>|  
|<span data-ttu-id="05e90-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="05e90-110">Channel</span></span>|<span data-ttu-id="05e90-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="05e90-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="05e90-112">Opis</span><span class="sxs-lookup"><span data-stu-id="05e90-112">Description</span></span>  

 <span data-ttu-id="05e90-113">Wskazuje, że znaleziono zduplikowany CorrelationQuery.</span><span class="sxs-lookup"><span data-stu-id="05e90-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="05e90-114">Zduplikowane zapytanie nie zostanie użyte podczas obliczania korelacji.</span><span class="sxs-lookup"><span data-stu-id="05e90-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="05e90-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="05e90-115">Message</span></span>  

 <span data-ttu-id="05e90-116">Znaleziono zduplikowany CorrelationQuery z WHERE = ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="05e90-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="05e90-117">To zduplikowane zapytanie nie zostanie użyte podczas obliczania korelacji.</span><span class="sxs-lookup"><span data-stu-id="05e90-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="05e90-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="05e90-118">Details</span></span>  
  
|<span data-ttu-id="05e90-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="05e90-119">Data Item Name</span></span>|<span data-ttu-id="05e90-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="05e90-120">Data Item Type</span></span>|<span data-ttu-id="05e90-121">Opis</span><span class="sxs-lookup"><span data-stu-id="05e90-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="05e90-122">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="05e90-122">Where</span></span>|<span data-ttu-id="05e90-123">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="05e90-123">xs:string</span></span>|<span data-ttu-id="05e90-124">Część WHERE zapytania korelacji.</span><span class="sxs-lookup"><span data-stu-id="05e90-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="05e90-125">Wywołując</span><span class="sxs-lookup"><span data-stu-id="05e90-125">AppDomain</span></span>|<span data-ttu-id="05e90-126">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="05e90-126">xs:string</span></span>|<span data-ttu-id="05e90-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="05e90-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
