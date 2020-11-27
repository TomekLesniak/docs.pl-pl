---
title: 1037 — RuntimeTransactionComplete
ms.date: 03/30/2017
ms.assetid: 2c8c31e0-42a9-4f46-865b-2da9ab16a0ba
ms.openlocfilehash: ad05151a1497ea4b31e0fe33fe2983c1f145f224
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294251"
---
# <a name="1037---runtimetransactioncomplete"></a><span data-ttu-id="b479c-102">1037 — RuntimeTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="b479c-102">1037 - RuntimeTransactionComplete</span></span>

## <a name="properties"></a><span data-ttu-id="b479c-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="b479c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b479c-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="b479c-104">ID</span></span>|<span data-ttu-id="b479c-105">1037</span><span class="sxs-lookup"><span data-stu-id="b479c-105">1037</span></span>|  
|<span data-ttu-id="b479c-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="b479c-106">Keywords</span></span>|<span data-ttu-id="b479c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b479c-107">WFRuntime</span></span>|  
|<span data-ttu-id="b479c-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="b479c-108">Level</span></span>|<span data-ttu-id="b479c-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="b479c-109">Verbose</span></span>|  
|<span data-ttu-id="b479c-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="b479c-110">Channel</span></span>|<span data-ttu-id="b479c-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="b479c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b479c-112">Opis</span><span class="sxs-lookup"><span data-stu-id="b479c-112">Description</span></span>  

 <span data-ttu-id="b479c-113">Wskazuje, że transakcja czasu wykonywania została ukończona.</span><span class="sxs-lookup"><span data-stu-id="b479c-113">Indicates the runtime transaction has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b479c-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="b479c-114">Message</span></span>  

 <span data-ttu-id="b479c-115">Transakcja środowiska uruchomieniowego została zakończona ze stanem "%1".</span><span class="sxs-lookup"><span data-stu-id="b479c-115">The runtime transaction has completed with the state '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b479c-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="b479c-116">Details</span></span>  
  
|<span data-ttu-id="b479c-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="b479c-117">Data Item Name</span></span>|<span data-ttu-id="b479c-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="b479c-118">Data Item Type</span></span>|<span data-ttu-id="b479c-119">Opis</span><span class="sxs-lookup"><span data-stu-id="b479c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b479c-120">Stan</span><span class="sxs-lookup"><span data-stu-id="b479c-120">State</span></span>|<span data-ttu-id="b479c-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="b479c-121">xs:string</span></span>|<span data-ttu-id="b479c-122">Stan transakcji.</span><span class="sxs-lookup"><span data-stu-id="b479c-122">The state of the transaction.</span></span>|  
|<span data-ttu-id="b479c-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="b479c-123">AppDomain</span></span>|<span data-ttu-id="b479c-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="b479c-124">xs:string</span></span>|<span data-ttu-id="b479c-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b479c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
