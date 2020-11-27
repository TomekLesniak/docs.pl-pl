---
title: Błędne sesje komunikacji niezawodnej na sekundę
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: 427ce2be4bd9fae6fd39922d79ee7427179dfd18
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276155"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Błędne sesje komunikacji niezawodnej na sekundę

Nazwa licznika: Błędy sesji niezawodnej obsługi komunikatów na sekundę.  
  
## <a name="description"></a>Opis  

 Liczba sesji niezawodnej obsługi komunikatów, które są błędne w tej usłudze w drugim.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
