---
title: 440 — StartSignpostEvent1
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 1e0278d665a961afab21445ab8490e3e5a94987c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293458"
---
# <a name="440---startsignpostevent1"></a><span data-ttu-id="eca52-102">440 — StartSignpostEvent1</span><span class="sxs-lookup"><span data-stu-id="eca52-102">440 - StartSignpostEvent1</span></span>

## <a name="properties"></a><span data-ttu-id="eca52-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="eca52-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eca52-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="eca52-104">ID</span></span>|<span data-ttu-id="eca52-105">440</span><span class="sxs-lookup"><span data-stu-id="eca52-105">440</span></span>|  
|<span data-ttu-id="eca52-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="eca52-106">Keywords</span></span>|<span data-ttu-id="eca52-107">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="eca52-107">Troubleshooting</span></span>|  
|<span data-ttu-id="eca52-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="eca52-108">Level</span></span>|<span data-ttu-id="eca52-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="eca52-109">Information</span></span>|  
|<span data-ttu-id="eca52-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="eca52-110">Channel</span></span>|<span data-ttu-id="eca52-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="eca52-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eca52-112">Opis</span><span class="sxs-lookup"><span data-stu-id="eca52-112">Description</span></span>  

 <span data-ttu-id="eca52-113">W obszarze śledzenie działań wskazuje, że komunikat spowodował Przekroczenie granicy działania w operacji wysyłania lub odbierania.</span><span class="sxs-lookup"><span data-stu-id="eca52-113">In activity tracing, indicates a message has started crossing an activity boundary in send or receive.</span></span>  
  
## <a name="message"></a><span data-ttu-id="eca52-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="eca52-114">Message</span></span>  

 <span data-ttu-id="eca52-115">Granica działania.</span><span class="sxs-lookup"><span data-stu-id="eca52-115">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="eca52-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="eca52-116">Details</span></span>  
  
|<span data-ttu-id="eca52-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="eca52-117">Data Item Name</span></span>|<span data-ttu-id="eca52-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="eca52-118">Data Item Type</span></span>|<span data-ttu-id="eca52-119">Opis</span><span class="sxs-lookup"><span data-stu-id="eca52-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="eca52-120">ExtendedData</span><span class="sxs-lookup"><span data-stu-id="eca52-120">ExtendedData</span></span>|`xs:string`|<span data-ttu-id="eca52-121">Nazwa działania.</span><span class="sxs-lookup"><span data-stu-id="eca52-121">The name of the activity.</span></span>|  
|<span data-ttu-id="eca52-122">Wywołując</span><span class="sxs-lookup"><span data-stu-id="eca52-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="eca52-123">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="eca52-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
