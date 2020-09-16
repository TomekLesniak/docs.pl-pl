---
title: 'Usługa: Wywołania zwracające błędy na sekundę'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: 211240d5bef7fe31a36f636313b48a2b9e15b239
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556014"
---
# <a name="service-calls-faulted-per-second"></a>Usługa: Wywołania zwracające błędy na sekundę
Nazwa licznika: wywołania z błędami na sekundę.  
  
## <a name="description"></a>Opis  
 Liczba wywołań, które zwróciły błędy do tej usługi w drugim.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.  
  
 (N 1-N 0)/((D 1-D 0)/F)  
  
 W aplikacjach Windows Communication Foundation (WCF) metody usługi komunikują przetwarzanie informacji o błędach przy użyciu komunikatów błędów protokołu SOAP. Błędy protokołu SOAP to typy komunikatów, które są zawarte w metadanych dla operacji usługi, dlatego należy utworzyć kontrakt błędów, którego klienci mogą używać do bardziej niezawodnego lub interaktywnego wykonania. Ponieważ błędy protokołu SOAP są wyrażane dla klientów w formularzu XML, są one wysoce interoperacyjne.  
  
## <a name="see-also"></a>Zobacz także

- [Określanie i obsługa błędów w kontraktach i usługach](../../specifying-and-handling-faults-in-contracts-and-services.md)
