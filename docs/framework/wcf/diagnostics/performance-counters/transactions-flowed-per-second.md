---
title: Przepływ transakcji na sekundę
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: d55856a5d820df2c668863a2a3e853995a113143
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552209"
---
# <a name="transactions-flowed-per-second"></a>Przepływ transakcji na sekundę
Nazwa licznika: przepływające transakcje na sekundę  
  
## <a name="description"></a>Opis  
 Liczba transakcji przepływających do tej operacji w drugim. Ten licznik jest zwiększany za każdym razem, gdy w komunikacie wysyłanym do operacji jest obecny identyfikator transakcji.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
