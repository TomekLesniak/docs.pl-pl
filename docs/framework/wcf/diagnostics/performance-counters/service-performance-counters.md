---
title: Liczniki wydajności usługi
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: f3e3a798bf04f24aaea03b5d70762d52b67a82f0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252832"
---
# <a name="service-performance-counters"></a><span data-ttu-id="3463d-102">Liczniki wydajności usługi</span><span class="sxs-lookup"><span data-stu-id="3463d-102">Service Performance Counters</span></span>

<span data-ttu-id="3463d-103">Liczniki wydajności usługi mierzą zachowanie usługi jako całość i mogą służyć do diagnozowania wydajności całej usługi.</span><span class="sxs-lookup"><span data-stu-id="3463d-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="3463d-104">Mogą one znajdować się w `ServiceModelService 4.0.0.0` obiekcie wydajności podczas wyświetlania z monitorem wydajności (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="3463d-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="3463d-105">Wystąpienia są nazwane przy użyciu następującego wzorca:</span><span class="sxs-lookup"><span data-stu-id="3463d-105">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> <span data-ttu-id="3463d-106">Istnieje limit długości nazwy wystąpienia licznika wydajności.</span><span class="sxs-lookup"><span data-stu-id="3463d-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="3463d-107">Jeśli nazwa wystąpienia licznika Windows Communication Foundation (WCF) przekracza maksymalną długość, WCF zastępuje część nazwy wystąpienia wartością skrótu.</span><span class="sxs-lookup"><span data-stu-id="3463d-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3463d-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3463d-108">See also</span></span>

- [<span data-ttu-id="3463d-109">Liczniki wydajności</span><span class="sxs-lookup"><span data-stu-id="3463d-109">Performance Counters</span></span>](index.md)
