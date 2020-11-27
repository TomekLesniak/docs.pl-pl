---
title: Wywołania zakończone niepowodzeniami na sekundę
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: d3eafc4b31f0e62093a972b7c9f2325a3648d21b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285463"
---
# <a name="calls-failed-per-second"></a>Wywołania zakończone niepowodzeniami na sekundę

Nazwa licznika: wywołania zakończone niepowodzeniem na sekundę  
  
## <a name="description"></a>Opis  

 Liczba wywołań z nieobsługiwanymi wyjątkami w tej operacji w drugim.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)  
  
 Licznik jest zwiększany za każdym razem, gdy w tej operacji występuje nieobsługiwany wyjątek.  
  
## <a name="see-also"></a>Zobacz też

- [Określanie i obsługa błędów w kontraktach i usługach](../../specifying-and-handling-faults-in-contracts-and-services.md)
