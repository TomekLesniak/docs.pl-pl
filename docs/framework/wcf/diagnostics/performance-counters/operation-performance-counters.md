---
title: Liczniki wydajności operacji
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: 01f3ed7b2722f7ff4bdbb50e352920bdc277330f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295235"
---
# <a name="operation-performance-counters"></a>Liczniki wydajności operacji

Liczniki wydajności operacji są dostępne w `ServiceModelOperation 4.0.0.0` obiekcie wydajności podczas wyświetlania z monitorem wydajności (Perfmon.exe). Każda operacja ma pojedyncze wystąpienie. Oznacza to, że jeśli dany kontrakt zawiera 10 operacji, do tego kontraktu są skojarzone 10 wystąpień liczników operacji. Wystąpienia obiektów są nazwane przy użyciu następującego wzorca:  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 Ten licznik umożliwia pomiar sposobu użycia wywołania oraz sposobu wykonywania operacji.  
  
> [!CAUTION]
> Istnieje limit długości nazwy wystąpienia licznika wydajności. Jeśli nazwa wystąpienia licznika Windows Communication Foundation (WCF) przekracza maksymalną długość, WCF zastępuje część nazwy wystąpienia wartością skrótu.  
  
## <a name="see-also"></a>Zobacz też

- [Liczniki wydajności](index.md)
