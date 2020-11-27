---
title: 2577 — TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: 33c68984e88eaa5e3028899a7c3066c94a65e8eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271242"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="c3dd0-102">2577 — TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="c3dd0-102">2577 - TryCatchExceptionDuringCancelation</span></span>

## <a name="properties"></a><span data-ttu-id="c3dd0-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="c3dd0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3dd0-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="c3dd0-104">ID</span></span>|<span data-ttu-id="c3dd0-105">2577</span><span class="sxs-lookup"><span data-stu-id="c3dd0-105">2577</span></span>|  
|<span data-ttu-id="c3dd0-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="c3dd0-106">Keywords</span></span>|<span data-ttu-id="c3dd0-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="c3dd0-107">WFActivities</span></span>|  
|<span data-ttu-id="c3dd0-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="c3dd0-108">Level</span></span>|<span data-ttu-id="c3dd0-109">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="c3dd0-109">Warning</span></span>|  
|<span data-ttu-id="c3dd0-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="c3dd0-110">Channel</span></span>|<span data-ttu-id="c3dd0-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="c3dd0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c3dd0-112">Opis</span><span class="sxs-lookup"><span data-stu-id="c3dd0-112">Description</span></span>  

 <span data-ttu-id="c3dd0-113">Wskazuje, że działanie podrzędne działania TryCatch zgłosiło wyjątek podczas anulowania.</span><span class="sxs-lookup"><span data-stu-id="c3dd0-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c3dd0-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="c3dd0-114">Message</span></span>  

 <span data-ttu-id="c3dd0-115">Działanie podrzędne działania TryCatch "%1" zgłosiło wyjątek podczas anulowania.</span><span class="sxs-lookup"><span data-stu-id="c3dd0-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c3dd0-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="c3dd0-116">Details</span></span>  
  
|<span data-ttu-id="c3dd0-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="c3dd0-117">Data Item Name</span></span>|<span data-ttu-id="c3dd0-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="c3dd0-118">Data Item Type</span></span>|<span data-ttu-id="c3dd0-119">Opis</span><span class="sxs-lookup"><span data-stu-id="c3dd0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c3dd0-120">Nazwa wyświetlana</span><span class="sxs-lookup"><span data-stu-id="c3dd0-120">DisplayName</span></span>|<span data-ttu-id="c3dd0-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c3dd0-121">xs:string</span></span>|<span data-ttu-id="c3dd0-122">Nazwa wyświetlana działania.</span><span class="sxs-lookup"><span data-stu-id="c3dd0-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="c3dd0-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="c3dd0-123">AppDomain</span></span>|<span data-ttu-id="c3dd0-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="c3dd0-124">xs:string</span></span>|<span data-ttu-id="c3dd0-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c3dd0-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
