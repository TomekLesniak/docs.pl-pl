---
title: 3550 — BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 61605d666911cce277bcebbb0a2f803e9a5dcfeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261309"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="3d55c-102">3550 — BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="3d55c-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>

## <a name="properties"></a><span data-ttu-id="3d55c-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="3d55c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3d55c-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="3d55c-104">ID</span></span>|<span data-ttu-id="3d55c-105">3550</span><span class="sxs-lookup"><span data-stu-id="3d55c-105">3550</span></span>|  
|<span data-ttu-id="3d55c-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="3d55c-106">Keywords</span></span>|<span data-ttu-id="3d55c-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="3d55c-107">WFServices</span></span>|  
|<span data-ttu-id="3d55c-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="3d55c-108">Level</span></span>|<span data-ttu-id="3d55c-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="3d55c-109">Information</span></span>|  
|<span data-ttu-id="3d55c-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="3d55c-110">Channel</span></span>|<span data-ttu-id="3d55c-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="3d55c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3d55c-112">Opis</span><span class="sxs-lookup"><span data-stu-id="3d55c-112">Description</span></span>  

 <span data-ttu-id="3d55c-113">Wskazuje, że zbuforowane odbieranie nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="3d55c-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="3d55c-114">Operacja zostanie podjęta ponownie, gdy wystąpienie usługi będzie gotowe do przetworzenia tej konkretnej operacji.</span><span class="sxs-lookup"><span data-stu-id="3d55c-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3d55c-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="3d55c-115">Message</span></span>  

 <span data-ttu-id="3d55c-116">Nie można teraz wykonać operacji "%1".</span><span class="sxs-lookup"><span data-stu-id="3d55c-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="3d55c-117">Kolejna próba zostanie podjęta, gdy wystąpienie usługi będzie gotowe do przetworzenia tej konkretnej operacji.</span><span class="sxs-lookup"><span data-stu-id="3d55c-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3d55c-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3d55c-118">Details</span></span>  
  
|<span data-ttu-id="3d55c-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="3d55c-119">Data Item Name</span></span>|<span data-ttu-id="3d55c-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="3d55c-120">Data Item Type</span></span>|<span data-ttu-id="3d55c-121">Opis</span><span class="sxs-lookup"><span data-stu-id="3d55c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3d55c-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="3d55c-122">OperationName</span></span>|<span data-ttu-id="3d55c-123">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3d55c-123">xs:string</span></span>|<span data-ttu-id="3d55c-124">Nazwa operacji.</span><span class="sxs-lookup"><span data-stu-id="3d55c-124">The name of the operation.</span></span>|  
|<span data-ttu-id="3d55c-125">Wywołując</span><span class="sxs-lookup"><span data-stu-id="3d55c-125">AppDomain</span></span>|<span data-ttu-id="3d55c-126">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3d55c-126">xs:string</span></span>|<span data-ttu-id="3d55c-127">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3d55c-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
