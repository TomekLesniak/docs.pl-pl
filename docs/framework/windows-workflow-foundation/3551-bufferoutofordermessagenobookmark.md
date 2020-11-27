---
title: 3551 — BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 5e6a5f9d21435fee8309bd222443407e50ec2cee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263610"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="930d1-102">3551 — BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="930d1-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>

## <a name="properties"></a><span data-ttu-id="930d1-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="930d1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="930d1-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="930d1-104">ID</span></span>|<span data-ttu-id="930d1-105">3551</span><span class="sxs-lookup"><span data-stu-id="930d1-105">3551</span></span>|  
|<span data-ttu-id="930d1-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="930d1-106">Keywords</span></span>|<span data-ttu-id="930d1-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="930d1-107">WFServices</span></span>|  
|<span data-ttu-id="930d1-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="930d1-108">Level</span></span>|<span data-ttu-id="930d1-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="930d1-109">Information</span></span>|  
|<span data-ttu-id="930d1-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="930d1-110">Channel</span></span>|<span data-ttu-id="930d1-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="930d1-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="930d1-112">Opis</span><span class="sxs-lookup"><span data-stu-id="930d1-112">Description</span></span>  

 <span data-ttu-id="930d1-113">Wskazuje, że wznowienie zakładki zakończyło się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="930d1-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="930d1-114">Buforowana operacja odbierania zostanie ponowiona, gdy wystąpienie usługi będzie gotowe do przetworzenia tej konkretnej operacji.</span><span class="sxs-lookup"><span data-stu-id="930d1-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="930d1-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="930d1-115">Message</span></span>  

 <span data-ttu-id="930d1-116">W tej chwili nie można wykonać operacji "%2" w wystąpieniu usługi "%1".</span><span class="sxs-lookup"><span data-stu-id="930d1-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="930d1-117">Kolejna próba zostanie podjęta, gdy wystąpienie usługi będzie gotowe do przetworzenia tej konkretnej operacji.</span><span class="sxs-lookup"><span data-stu-id="930d1-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="930d1-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="930d1-118">Details</span></span>  
  
|<span data-ttu-id="930d1-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="930d1-119">Data Item Name</span></span>|<span data-ttu-id="930d1-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="930d1-120">Data Item Type</span></span>|<span data-ttu-id="930d1-121">Opis</span><span class="sxs-lookup"><span data-stu-id="930d1-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="930d1-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="930d1-122">OperationName</span></span>|<span data-ttu-id="930d1-123">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="930d1-123">xs:string</span></span>|<span data-ttu-id="930d1-124">Nazwa operacji.</span><span class="sxs-lookup"><span data-stu-id="930d1-124">The name of the operation.</span></span>|  
|<span data-ttu-id="930d1-125">Właściwość ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="930d1-125">ServiceInstanceId</span></span>|<span data-ttu-id="930d1-126">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="930d1-126">xs:string</span></span>|<span data-ttu-id="930d1-127">Identyfikator wystąpienia usługi.</span><span class="sxs-lookup"><span data-stu-id="930d1-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="930d1-128">Wywołując</span><span class="sxs-lookup"><span data-stu-id="930d1-128">AppDomain</span></span>|<span data-ttu-id="930d1-129">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="930d1-129">xs:string</span></span>|<span data-ttu-id="930d1-130">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="930d1-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
