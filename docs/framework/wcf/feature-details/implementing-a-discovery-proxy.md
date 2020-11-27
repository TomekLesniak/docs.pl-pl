---
title: Implementowanie serwera proxy odnajdywania
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: ae003c89bb0f14623c5d31a1596533d821380336
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268303"
---
# <a name="implementing-a-discovery-proxy"></a>Implementowanie serwera proxy odnajdywania

W tej sekcji opisano kroki wymagane do zaimplementowania serwera proxy odnajdywania. Serwer proxy odnajdywania jest usługą autonomiczną, która zawiera repozytorium usług. Klienci mogą wysyłać zapytania do serwera proxy odnajdywania, aby znaleźć usługi wykrywalne, których dotyczy serwer proxy. Sposób wypełniania serwera proxy za pomocą usług jest do realizatora. Na przykład serwer proxy odnajdywania może połączyć się z istniejącym repozytorium usługi i przetworzyć te informacje, administrator może użyć interfejsu API zarządzania, aby dodać odnajdywane usługi do serwera proxy, lub serwer proxy odnajdywania może korzystać z funkcji anonsowania do aktualizowania wewnętrznej pamięci podręcznej.  
  
 Implementacja programu WCF zawiera klasy podstawowe, które umożliwiają łatwe tworzenie serwera proxy. Możesz użyć tych interfejsów API, aby skompilować serwer proxy odnajdywania na podstawie istniejącego repozytorium.  
  
 Serwer proxy odnajdywania wdrożony w tym miejscu jest podobny do wszystkich innych usług WCF, w tym, że można również odnajdywać serwer proxy odnajdywania i klienci lokalizują jego punkty końcowe.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Instrukcje: wdrażanie serwera proxy odnajdywania](how-to-implement-a-discovery-proxy.md)  
 Opisuje sposób implementacji serwera proxy odnajdywania.  
  
 [Instrukcje: implementowanie odnajdywanej usługi rejestrowanej za pomocą serwera proxy odnajdywania](discoverable-service-that-registers-with-the-discovery-proxy.md)  
 Zawiera opis sposobu implementacji odnajdywanej usługi WCF, która jest rejestrowana przy użyciu serwera proxy odnajdywania.  
  
 [Instrukcje: wdrażanie aplikacji klienta znajdującej usługę przy użyciu serwera proxy odnajdywania](client-app-discovery-proxy-to-find-a-service.md)  
 Opisuje sposób implementacji aplikacji klienckiej WCF, która używa serwera proxy odnajdywania do wyszukiwania usługi.  
  
 [Instrukcje: testowanie serwera proxy odnajdywania](how-to-test-the-discovery-proxy.md)  
 Opisuje, jak przetestować kod zapisany w poprzednich trzech tematach.  
  
## <a name="see-also"></a>Zobacz też

- [Odnajdywanie w programie WCF](wcf-discovery.md)
- [Instrukcje: programowe dodawanie możliwości odnajdywania do usługi i klienta WCF](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
