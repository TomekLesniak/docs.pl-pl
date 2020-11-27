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
# <a name="instances"></a>Wystąpienia

Nazwa licznika: wystąpienia.  
  
## <a name="description"></a>Opis  

 Liczba kontekstów wystąpień, które obecnie zawiera usługa.  
  
 W większości przypadków liczba kontekstów wystąpienia jest taka sama jak liczba wystąpień. Jednak poniższe scenariusze są wyjątkiem od tej reguły.  
  
- Metoda usługi wywołuje <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> metodę jawnie.  
  
- A <xref:System.ServiceModel.ReleaseInstanceMode> jest stosowany do <xref:System.ServiceModel.OperationBehaviorAttribute> wystąpienia.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.OperationBehaviorAttribute>
