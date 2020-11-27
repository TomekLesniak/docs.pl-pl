---
title: 'Usługa: Wywołania na sekundę'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 7e702d402909c4a85a2cb42c837e0813c4d9f841
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252884"
---
# <a name="service-calls-per-second"></a>Usługa: Wywołania na sekundę

Nazwa licznika: wywołania na sekundę.  
  
## <a name="description"></a>Opis  

 Liczba wywołań tej usługi w drugim.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F) gdzie licznik (N) reprezentuje liczbę operacji wykonanych w ciągu ostatniego interwału próbkowania, mianownik (D) reprezentuje liczbę taktów, które upłynęły podczas ostatniego interwału próbkowania, a F jest częstotliwością taktów.
