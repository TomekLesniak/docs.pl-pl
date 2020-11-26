---
title: 4802 — DiscoveryClientProtocolExceptionSuppressed
ms.date: 03/30/2017
ms.assetid: 568212f7-1060-4f5c-a7a0-1352c7cc743b
ms.openlocfilehash: e840c5d2e28a5240570a11e8edffe963d54b1e2c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242620"
---
# <a name="4802---discoveryclientprotocolexceptionsuppressed"></a><span data-ttu-id="f0a7b-102">4802 — DiscoveryClientProtocolExceptionSuppressed</span><span class="sxs-lookup"><span data-stu-id="f0a7b-102">4802 - DiscoveryClientProtocolExceptionSuppressed</span></span>

## <a name="properties"></a><span data-ttu-id="f0a7b-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="f0a7b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0a7b-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="f0a7b-104">ID</span></span>|<span data-ttu-id="f0a7b-105">4802</span><span class="sxs-lookup"><span data-stu-id="f0a7b-105">4802</span></span>|  
|<span data-ttu-id="f0a7b-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="f0a7b-106">Keywords</span></span>|<span data-ttu-id="f0a7b-107">Odnajdywanie</span><span class="sxs-lookup"><span data-stu-id="f0a7b-107">Discovery</span></span>|  
|<span data-ttu-id="f0a7b-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="f0a7b-108">Level</span></span>|<span data-ttu-id="f0a7b-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="f0a7b-109">Information</span></span>|  
|<span data-ttu-id="f0a7b-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="f0a7b-110">Channel</span></span>|<span data-ttu-id="f0a7b-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="f0a7b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f0a7b-112">Opis</span><span class="sxs-lookup"><span data-stu-id="f0a7b-112">Description</span></span>  

 <span data-ttu-id="f0a7b-113">To zdarzenie jest emitowane, gdy wyjątek protokołu został pominięty podczas zamykania obiekt DiscoveryClient.</span><span class="sxs-lookup"><span data-stu-id="f0a7b-113">This event is emitted when the a ProtocolException was suppressed while closing the DiscoveryClient.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f0a7b-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="f0a7b-114">Message</span></span>  

 <span data-ttu-id="f0a7b-115">Element ProtocolException został pominięty podczas zamykania obiekt DiscoveryClient.</span><span class="sxs-lookup"><span data-stu-id="f0a7b-115">A ProtocolException was suppressed while closing the DiscoveryClient.</span></span> <span data-ttu-id="f0a7b-116">Może to być spowodowane tym, że DiscoveryService nadal próbuje wysłać odpowiedź do obiekt DiscoveryClient.</span><span class="sxs-lookup"><span data-stu-id="f0a7b-116">This could be because a DiscoveryService is still trying to send response to the DiscoveryClient.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f0a7b-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f0a7b-117">Details</span></span>
