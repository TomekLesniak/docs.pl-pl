---
title: 'Punkt końcowy: Błędy sesji niezawodnej obsługi komunikatów na sekundę'
ms.date: 03/30/2017
ms.assetid: e9ae808a-7e1f-46b0-9560-d5a866be6d6e
ms.openlocfilehash: 118b6a68903f6550cb78f10ad953447e86f5cd3e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550231"
---
# <a name="endpoint-reliable-messaging-sessions-faulted-per-second"></a>Punkt końcowy: Błędy sesji niezawodnej obsługi komunikatów na sekundę
Nazwa licznika: Błędy sesji niezawodnej obsługi komunikatów na sekundę.  
  
## <a name="description"></a>Opis  
 Liczba sesji niezawodnej obsługi komunikatów, które są błędne w tym punkcie końcowym w drugim.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
