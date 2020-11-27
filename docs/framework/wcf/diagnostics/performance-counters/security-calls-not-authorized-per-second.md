---
title: Nieautoryzowane wywołania zabezpieczeń na sekundę
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 1e1e58946783c2eb376ae6ba50c3595c037a1e00
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276116"
---
# <a name="security-calls-not-authorized-per-second"></a>Nieautoryzowane wywołania zabezpieczeń na sekundę

Nazwa licznika: wywołania zabezpieczeń nie są autoryzowane na sekundę.  
  
## <a name="description"></a>Opis  

 Liczba wywołań, których autoryzacja zakończyła się niepowodzeniem w ramach tej operacji w drugim.  
  
 Licznik jest zwiększany, gdy <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> Metoda zwraca `false` . Wskazuje on, że komunikat przychodzący jest prawidłowym użytkownikiem i chroniony prawidłowo, ale użytkownik nie ma uprawnień do wykonywania określonych zadań.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
