---
title: Zatwierdzone operacje transakcyjne na sekundę
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: deb29820aab09adad8825a299145772892117948
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250011"
---
# <a name="transacted-operations-committed-per-second"></a>Zatwierdzone operacje transakcyjne na sekundę

Nazwa licznika: zatwierdzone Operacje transakcyjne na sekundę.  
  
## <a name="description"></a>Opis  

 Liczba operacji transakcyjnych, które zostały zatwierdzone w tej usłudze w drugim.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)
