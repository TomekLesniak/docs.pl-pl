---
title: Wystąpienia
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: f4bf639e626945c7e753ac352dfecc7a79541bfd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266080"
---
# <a name="instances"></a><span data-ttu-id="5de55-102">Wystąpienia</span><span class="sxs-lookup"><span data-stu-id="5de55-102">Instances</span></span>

<span data-ttu-id="5de55-103">Nazwa licznika: wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="5de55-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5de55-104">Opis</span><span class="sxs-lookup"><span data-stu-id="5de55-104">Description</span></span>  

 <span data-ttu-id="5de55-105">Liczba kontekstów wystąpień, które obecnie zawiera usługa.</span><span class="sxs-lookup"><span data-stu-id="5de55-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="5de55-106">W większości przypadków liczba kontekstów wystąpienia jest taka sama jak liczba wystąpień.</span><span class="sxs-lookup"><span data-stu-id="5de55-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="5de55-107">Jednak poniższe scenariusze są wyjątkiem od tej reguły.</span><span class="sxs-lookup"><span data-stu-id="5de55-107">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="5de55-108">Metoda usługi wywołuje <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> metodę jawnie.</span><span class="sxs-lookup"><span data-stu-id="5de55-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="5de55-109">A <xref:System.ServiceModel.ReleaseInstanceMode> jest stosowany do <xref:System.ServiceModel.OperationBehaviorAttribute> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="5de55-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de55-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5de55-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
