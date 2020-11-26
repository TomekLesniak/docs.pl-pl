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
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a>System.ServiceModel.ManualFlowThrottleLimitReached

System.ServiceModel.ManualFlowThrottleLimitReached  
  
## <a name="description"></a>Opis  

 System osiągnął limit ustawiony dla ograniczenia ManualFlowControlLimit. Wartość dławienia można zmienić, modyfikując właściwość ManualFlowControlLimit na serwerze ServiceHost lub InstanceContext, zgodnie z wymaganiami.  
  
 Ślad jest emitowany, gdy limit ręcznego sterowania przepływem został początkowo zmniejszony do wartości 0. Kolejne zmiany w wartości 0 nie są śledzone. Limit sterowania przepływem dla kontekstu wystąpienia jest śledzony jednokrotnie dla każdego kontekstu.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
