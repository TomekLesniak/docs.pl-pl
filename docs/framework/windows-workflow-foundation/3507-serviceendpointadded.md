---
title: 3507 — ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: 903071e7b1f89dc3489b8d3ac05427d699a33a7e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240761"
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="ff916-102">3507 — ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="ff916-102">3507 - ServiceEndpointAdded</span></span>

## <a name="properties"></a><span data-ttu-id="ff916-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ff916-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff916-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="ff916-104">ID</span></span>|<span data-ttu-id="ff916-105">3507</span><span class="sxs-lookup"><span data-stu-id="ff916-105">3507</span></span>|  
|<span data-ttu-id="ff916-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="ff916-106">Keywords</span></span>|<span data-ttu-id="ff916-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="ff916-107">WFServices</span></span>|  
|<span data-ttu-id="ff916-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="ff916-108">Level</span></span>|<span data-ttu-id="ff916-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="ff916-109">Information</span></span>|  
|<span data-ttu-id="ff916-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="ff916-110">Channel</span></span>|<span data-ttu-id="ff916-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="ff916-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ff916-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ff916-112">Description</span></span>  

 <span data-ttu-id="ff916-113">Wskazuje, że punkt końcowy usługi został dodany.</span><span class="sxs-lookup"><span data-stu-id="ff916-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ff916-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="ff916-114">Message</span></span>  

 <span data-ttu-id="ff916-115">Dodano punkt końcowy usługi dla adresu "%1", powiązania "%2" i kontraktu "%3".</span><span class="sxs-lookup"><span data-stu-id="ff916-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ff916-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ff916-116">Details</span></span>  
  
|<span data-ttu-id="ff916-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="ff916-117">Data Item Name</span></span>|<span data-ttu-id="ff916-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="ff916-118">Data Item Type</span></span>|<span data-ttu-id="ff916-119">Opis</span><span class="sxs-lookup"><span data-stu-id="ff916-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ff916-120">Adres</span><span class="sxs-lookup"><span data-stu-id="ff916-120">Address</span></span>|<span data-ttu-id="ff916-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ff916-121">xs:string</span></span>|<span data-ttu-id="ff916-122">Adres punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="ff916-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="ff916-123">Wiązanie</span><span class="sxs-lookup"><span data-stu-id="ff916-123">Binding</span></span>|<span data-ttu-id="ff916-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ff916-124">xs:string</span></span>|<span data-ttu-id="ff916-125">Powiązanie punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="ff916-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="ff916-126">Kontrakt</span><span class="sxs-lookup"><span data-stu-id="ff916-126">Contract</span></span>|<span data-ttu-id="ff916-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ff916-127">xs:string</span></span>|<span data-ttu-id="ff916-128">Kontrakt punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="ff916-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="ff916-129">Wywołując</span><span class="sxs-lookup"><span data-stu-id="ff916-129">AppDomain</span></span>|<span data-ttu-id="ff916-130">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="ff916-130">xs:string</span></span>|<span data-ttu-id="ff916-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ff916-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
