---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: 180a06efc94acba40806e1f5d661553127549596
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248490"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="ac029-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="ac029-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>

<span data-ttu-id="ac029-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="ac029-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="ac029-104">Opis</span><span class="sxs-lookup"><span data-stu-id="ac029-104">Description</span></span>  

 <span data-ttu-id="ac029-105">System osiągnął limit ustawiony dla ograniczenia ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="ac029-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="ac029-106">Wartość dławienia można zmienić, modyfikując właściwość ManualFlowControlLimit na serwerze ServiceHost lub InstanceContext, zgodnie z wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="ac029-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="ac029-107">Ślad jest emitowany, gdy limit ręcznego sterowania przepływem został początkowo zmniejszony do wartości 0.</span><span class="sxs-lookup"><span data-stu-id="ac029-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="ac029-108">Kolejne zmiany w wartości 0 nie są śledzone.</span><span class="sxs-lookup"><span data-stu-id="ac029-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="ac029-109">Limit sterowania przepływem dla kontekstu wystąpienia jest śledzony jednokrotnie dla każdego kontekstu.</span><span class="sxs-lookup"><span data-stu-id="ac029-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac029-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ac029-110">See also</span></span>

- [<span data-ttu-id="ac029-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="ac029-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="ac029-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="ac029-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ac029-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="ac029-113">Administration and Diagnostics</span></span>](../index.md)
