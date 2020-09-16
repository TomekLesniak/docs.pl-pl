---
title: 'Punkt końcowy: Przekazane transakcje na sekundę'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 9391651eaaca130ef47ddee9daa95b1f8c116892
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553795"
---
# <a name="endpoint-transactions-flowed-per-second"></a>Punkt końcowy: Przekazane transakcje na sekundę
Nazwa licznika: przepływające na sekundę transakcje.  
  
## <a name="description"></a>Opis  
 Liczba transakcji przepływających do operacji w tym punkcie końcowym w drugim. Ten licznik jest zwiększany za każdym razem, gdy w komunikacie wysyłanym do punktu końcowego jest obecny identyfikator transakcji.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
