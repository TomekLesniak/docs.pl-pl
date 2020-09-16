---
title: 'Usługa: przepływające transakcje na sekundę'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 2ed9f6711c998bbd3f1130b9a91d8ac850821a07
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559327"
---
# <a name="service-transactions-flowed-per-second"></a>Usługa: przepływające transakcje na sekundę
Nazwa licznika: przepływające na sekundę transakcje.  
  
## <a name="description"></a>Opis  
 Liczba transakcji przepływających do operacji w tej usłudze w drugim.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
