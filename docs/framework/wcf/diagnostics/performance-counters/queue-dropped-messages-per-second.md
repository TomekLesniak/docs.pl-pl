---
title: Zakolejkowane komunikaty porzucone na sekundę
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: 81ba15965676ba7ffe5ca2aaac5e1d0e94e27962
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266041"
---
# <a name="queue-dropped-messages-per-second"></a>Zakolejkowane komunikaty porzucone na sekundę

Nazwa licznika: liczba porzuconych komunikatów w kolejce na sekundę.  
  
## <a name="description"></a>Opis  

 Liczba komunikatów porzuconych przez transport w kolejce w tej usłudze w drugim.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
