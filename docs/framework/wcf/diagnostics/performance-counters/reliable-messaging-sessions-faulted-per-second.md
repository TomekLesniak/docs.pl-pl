---
title: Błędne sesje komunikacji niezawodnej na sekundę
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: 2d32f4224f3692cd4fc4f99a58bf54f49811e8ec
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542929"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Błędne sesje komunikacji niezawodnej na sekundę
Nazwa licznika: Błędy sesji niezawodnej obsługi komunikatów na sekundę.  
  
## <a name="description"></a>Opis  
 Liczba sesji niezawodnej obsługi komunikatów, które są błędne w tej usłudze w drugim.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
