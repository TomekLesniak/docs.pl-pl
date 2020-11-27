---
title: 'Najlepsze rozwiązania: Elementy pośredniczące'
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: 57be78681147dfc5bc37701a76c1347040f5da1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277897"
---
# <a name="best-practices-intermediaries"></a>Najlepsze rozwiązania: Elementy pośredniczące

Należy zachować ostrożność w celu prawidłowego obsługi błędów podczas wywoływania pośredników, aby upewnić się, że kanały po stronie usługi na pośrednim są poprawnie zamknięte.  
  
 Rozważmy następujący scenariusz: Klient wysyła wywołanie do pośrednika, które następnie wywołuje usługę zaplecza.  Usługa zaplecza nie definiuje kontraktu błędów, więc wszelkie błędy zgłoszone przez tę usługę będą traktowane jako błąd nieokreślony.  Usługa zaplecza zgłasza, że funkcja <xref:System.ApplicationException> WCF prawidłowo przerywa kanał po stronie usługi. <xref:System.ApplicationException>Następnie powierzchnie, <xref:System.ServiceModel.FaultException> które są zgłaszane do pośrednika. Pośrednika zgłasza <xref:System.ApplicationException> . Funkcja WCF interpretuje ją jako błąd nieokreślony z pośrednich i przekazuje je do klienta. Po otrzymaniu błędu zarówno pośrednika, jak i błąd klienta ich kanałów po stronie klienta. Kanał po stronie usług pośrednika pozostanie otwarty, ponieważ platforma WCF nie wie, że błąd jest krytyczny.  
  
 Najlepszym rozwiązaniem w tym scenariuszu jest wykrycie, czy błąd pochodzący z usługi jest krytyczny, a jeśli tak, pośrednik powinien spowodować błąd swojego kanału po stronie usługi, jak pokazano w poniższym fragmencie kodu.  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- [Obsługa błędów programu WCF](wcf-error-handling.md)
- [Określanie i obsługa błędów w kontraktach i usługach](specifying-and-handling-faults-in-contracts-and-services.md)
