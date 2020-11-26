---
title: Liczniki wydajności w punkcie końcowym
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: cdddd8be962df0b295eb394fcaba3756e8a1a50f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237966"
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="6f5f0-102">Liczniki wydajności w punkcie końcowym</span><span class="sxs-lookup"><span data-stu-id="6f5f0-102">Endpoint Performance Counters</span></span>

<span data-ttu-id="6f5f0-103">Liczniki wydajności punktów końcowych przechwytują dane, które ujawniają, w jaki sposób punkt końcowy akceptuje komunikaty.</span><span class="sxs-lookup"><span data-stu-id="6f5f0-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="6f5f0-104">Można je znaleźć w `ServiceModelEndpoint 4.0.0.0` obiekcie wydajności podczas wyświetlania z monitorem wydajności.</span><span class="sxs-lookup"><span data-stu-id="6f5f0-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="6f5f0-105">Wystąpienia są nazwane przy użyciu tego wzorca:</span><span class="sxs-lookup"><span data-stu-id="6f5f0-105">The instances are named using this pattern:</span></span>  
  
`(ServiceName).(ContractName)@(endpoint listener address)`  
  
 <span data-ttu-id="6f5f0-106">Dane są podobne do tych zebranych dla poszczególnych operacji, ale są agregowane w całym punkcie końcowym.</span><span class="sxs-lookup"><span data-stu-id="6f5f0-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="6f5f0-107">Istnieje limit długości nazwy wystąpienia licznika wydajności.</span><span class="sxs-lookup"><span data-stu-id="6f5f0-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="6f5f0-108">Jeśli nazwa wystąpienia licznika Windows Communication Foundation (WCF) przekracza maksymalną długość, WCF zastępuje część nazwy wystąpienia wartością skrótu.</span><span class="sxs-lookup"><span data-stu-id="6f5f0-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5f0-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6f5f0-109">See also</span></span>

- [<span data-ttu-id="6f5f0-110">Liczniki wydajności</span><span class="sxs-lookup"><span data-stu-id="6f5f0-110">Performance Counters</span></span>](index.md)
