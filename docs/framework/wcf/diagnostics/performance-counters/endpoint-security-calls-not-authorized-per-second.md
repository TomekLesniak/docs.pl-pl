---
title: 'Punkt końcowy: wywołania zabezpieczeń bez autoryzacji na sekundę'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: 5b289d7e026b481576bd7de186364773a57c17bc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256524"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a>Punkt końcowy: wywołania zabezpieczeń bez autoryzacji na sekundę

Nazwa licznika: wywołania zabezpieczeń nie są autoryzowane na sekundę.  
  
## <a name="description"></a>Opis  

 Liczba komunikatów przychodzących w drugim, które są prawidłowymi użytkownikami i są chronione prawidłowo, ale użytkownik nie ma uprawnień do wykonywania określonych zadań.  
  
 Licznik jest zwiększany, gdy <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> Metoda zwraca `false` .  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
