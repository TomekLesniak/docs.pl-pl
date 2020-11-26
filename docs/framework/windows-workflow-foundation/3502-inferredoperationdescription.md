---
title: 3502 — InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 05278067e3f86612ee4aafbe7d5eb66dc934cb85
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242113"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="514dc-102">3502 — InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="514dc-102">3502 - InferredOperationDescription</span></span>

## <a name="properties"></a><span data-ttu-id="514dc-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="514dc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="514dc-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="514dc-104">ID</span></span>|<span data-ttu-id="514dc-105">3502</span><span class="sxs-lookup"><span data-stu-id="514dc-105">3502</span></span>|  
|<span data-ttu-id="514dc-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="514dc-106">Keywords</span></span>|<span data-ttu-id="514dc-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="514dc-107">WFServices</span></span>|  
|<span data-ttu-id="514dc-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="514dc-108">Level</span></span>|<span data-ttu-id="514dc-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="514dc-109">Information</span></span>|  
|<span data-ttu-id="514dc-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="514dc-110">Channel</span></span>|<span data-ttu-id="514dc-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="514dc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="514dc-112">Opis</span><span class="sxs-lookup"><span data-stu-id="514dc-112">Description</span></span>  

 <span data-ttu-id="514dc-113">Wskazuje, że obiekt OperationDescription został wywnioskowany z obiektu WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="514dc-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="514dc-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="514dc-114">Message</span></span>  

 <span data-ttu-id="514dc-115">Obiekt OperationDescription o nazwie "%1" w kontrakcie "%2" został wywnioskowany z obiektu WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="514dc-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="514dc-116">IsOneWay = %3.</span><span class="sxs-lookup"><span data-stu-id="514dc-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="514dc-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="514dc-117">Details</span></span>  
  
|<span data-ttu-id="514dc-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="514dc-118">Data Item Name</span></span>|<span data-ttu-id="514dc-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="514dc-119">Data Item Type</span></span>|<span data-ttu-id="514dc-120">Opis</span><span class="sxs-lookup"><span data-stu-id="514dc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="514dc-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="514dc-121">OperationName</span></span>|<span data-ttu-id="514dc-122">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="514dc-122">xs:string</span></span>|<span data-ttu-id="514dc-123">Nazwa operacji.</span><span class="sxs-lookup"><span data-stu-id="514dc-123">The name of the operation.</span></span>|  
|<span data-ttu-id="514dc-124">Nr kontraktu</span><span class="sxs-lookup"><span data-stu-id="514dc-124">ContractName</span></span>|<span data-ttu-id="514dc-125">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="514dc-125">xs:string</span></span>|<span data-ttu-id="514dc-126">Nazwa kontraktu.</span><span class="sxs-lookup"><span data-stu-id="514dc-126">The name of the contract.</span></span>|  
|<span data-ttu-id="514dc-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="514dc-127">IsOneWay</span></span>|<span data-ttu-id="514dc-128">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="514dc-128">xs:string</span></span>|<span data-ttu-id="514dc-129">Prawda lub FAŁSZ wskazujący, czy kontrakt jest jednokierunkowe.</span><span class="sxs-lookup"><span data-stu-id="514dc-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="514dc-130">Wywołując</span><span class="sxs-lookup"><span data-stu-id="514dc-130">AppDomain</span></span>|<span data-ttu-id="514dc-131">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="514dc-131">xs:string</span></span>|<span data-ttu-id="514dc-132">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="514dc-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
