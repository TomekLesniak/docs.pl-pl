---
title: Porzucone komunikaty komunikacji niezawodnej na sekundę
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 1e6db155f21fb2443394bc3a65235d4e9539dab3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276181"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a>Porzucone komunikaty komunikacji niezawodnej na sekundę

Nazwa licznika: porzucone sesje niezawodnej obsługi komunikatów na sekundę.  
  
## <a name="description"></a>Opis  

 Całkowita liczba komunikatów komunikacji niezawodnej, które zostały usunięte w tej usłudze w drugim.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
