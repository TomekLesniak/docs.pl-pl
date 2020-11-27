---
title: 3557 — TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 4a4979047481687ef0d5c9d5891dec8f2826beed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263662"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="3bf19-102">3557 — TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="3bf19-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>

## <a name="properties"></a><span data-ttu-id="3bf19-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="3bf19-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3bf19-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="3bf19-104">ID</span></span>|<span data-ttu-id="3bf19-105">3557</span><span class="sxs-lookup"><span data-stu-id="3bf19-105">3557</span></span>|  
|<span data-ttu-id="3bf19-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="3bf19-106">Keywords</span></span>|<span data-ttu-id="3bf19-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="3bf19-107">WFServices</span></span>|  
|<span data-ttu-id="3bf19-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="3bf19-108">Level</span></span>|<span data-ttu-id="3bf19-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="3bf19-109">Information</span></span>|  
|<span data-ttu-id="3bf19-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="3bf19-110">Channel</span></span>|<span data-ttu-id="3bf19-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="3bf19-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3bf19-112">Opis</span><span class="sxs-lookup"><span data-stu-id="3bf19-112">Description</span></span>  

 <span data-ttu-id="3bf19-113">Wskazuje, że wywołanie metody EndCommit na CommittableTransaction zgłosiło wyjątek TransactionException.</span><span class="sxs-lookup"><span data-stu-id="3bf19-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3bf19-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="3bf19-114">Message</span></span>  

 <span data-ttu-id="3bf19-115">Wywołanie metody metody EndCommit na CommittableTransaction o identyfikatorze "%1" spowodowało wyjęcie operacji TransactionException z następującym komunikatem: "%2".</span><span class="sxs-lookup"><span data-stu-id="3bf19-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3bf19-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3bf19-116">Details</span></span>  
  
|<span data-ttu-id="3bf19-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="3bf19-117">Data Item Name</span></span>|<span data-ttu-id="3bf19-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="3bf19-118">Data Item Type</span></span>|<span data-ttu-id="3bf19-119">Opis</span><span class="sxs-lookup"><span data-stu-id="3bf19-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3bf19-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="3bf19-120">TransactionId</span></span>|<span data-ttu-id="3bf19-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3bf19-121">xs:string</span></span>|<span data-ttu-id="3bf19-122">Identyfikator CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="3bf19-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="3bf19-123">Wyjątek</span><span class="sxs-lookup"><span data-stu-id="3bf19-123">Exception</span></span>|<span data-ttu-id="3bf19-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3bf19-124">xs:string</span></span>|<span data-ttu-id="3bf19-125">Szczegóły wyjątku dla wyjątku</span><span class="sxs-lookup"><span data-stu-id="3bf19-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="3bf19-126">Wywołując</span><span class="sxs-lookup"><span data-stu-id="3bf19-126">AppDomain</span></span>|<span data-ttu-id="3bf19-127">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="3bf19-127">xs:string</span></span>|<span data-ttu-id="3bf19-128">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3bf19-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
