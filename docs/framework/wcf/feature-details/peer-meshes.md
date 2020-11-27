---
title: Siatki elementów równorzędnych
ms.date: 03/30/2017
ms.assetid: d93e312e-ac04-40f8-baea-5da1cacb546e
ms.openlocfilehash: 62feb237dd4a8a471175e32363887376f7d86212
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272101"
---
# <a name="peer-meshes"></a>Siatki elementów równorzędnych

*Siatka* jest nazwaną kolekcją (grafem połączonym) węzłów równorzędnych, które mogą komunikować się między sobą i są identyfikowane przy użyciu unikatowego identyfikatora siatki. Każdy węzeł jest połączony z wieloma innymi węzłami. W dobrze połączonej siatce istnieje ścieżka między dwoma węzłami, z względu na stosunkowo kilka przeskoków między węzłami w najbliższych krawędziach siatki, a siatka pozostanie połączona nawet w przypadku usunięcia niektórych węzłów lub połączeń. Aktywne węzły w sieci publikują informacje o punkcie końcowym przy użyciu odpowiadającego im identyfikatora siatki, dzięki czemu inne elementy równorzędne mogą je znaleźć.  
  
## <a name="characteristics-of-a-mesh-created-using-peer-channel"></a>Charakterystyki siatki utworzonej przy użyciu kanału równorzędnego  
  
#### <a name="uniquely-identified"></a>Identyfikowane jednoznacznie  
  
- Unikatowy identyfikator identyfikuje każdą siatkę. Nazwa siatki (lub Identyfikator siatki) jest w tym samym formacie co nazwa hosta systemu nazw domen (DNS). W związku z tym ten identyfikator sieci musi być unikatowy dla zamierzonego klienta aplikacji w zakresie używanego przez program rozpoznawania nazw. Nazwa pospolita, taka jak "MyFamilysPeers" lub "KevinsPokerTable", może być w łatwy sposób koliduje z innymi nazwami użytkowników i może zwracać zamierzone informacje o punkcie końcowym elementu równorzędnego, co może spowodować problemy z ochroną prywatności lub zwiększenie opóźnienia połączenia. Aby uniknąć tych problemów, można dodać unikatowy identyfikator jako przyrostk do pseudonimu dla siatki (na przykład "KevinsPokerTable90210").  
  
#### <a name="message-flooding"></a>Zalanie komunikatów  
  
- Siatka umożliwia propagowanie komunikatów z jednego lub większej liczby nadawców do wszystkich innych węzłów równorzędnych w tej samej sieci. Komunikaty zalewane przez węzły równorzędne używają nagłówków określonych w przestrzeni nazw w `http://schemas.microsoft.com/net/2006/05/peer` .  
  
#### <a name="optimized-connections"></a>Zoptymalizowane połączenia  
  
- Siatka kanału równorzędnego automatycznie dostosowuje się, gdy węzły przyłączają się i opuszczają, co zapewnia, że wszystkie węzły mają dobrą łączność z niewielkim prawdopodobieństwem tworzenia partycji (grup węzłów izolowanych od siebie). Połączenia w sieci są również dynamicznie optymalizowane na podstawie bieżących wzorców ruchu, dzięki czemu opóźnienie komunikatów od nadawcy do odbiorcy jest tak małe, jak to możliwe.  
  
#### <a name="popular-network-features-that-peer-channel-does-not-provide"></a>Popularne funkcje sieciowe, które nie zapewniają kanału równorzędnego  

 Ważne jest, aby wiedzieć o popularnych funkcjach sieciowych, które nie są obsługiwane przez kanał równorzędny. Te funkcje, które mogą być zbudowane w oparciu o kanał równorzędny, obejmują następujące elementy:  
  
- **Porządkowanie komunikatów:** Komunikaty pochodzące z jednego źródła mogą nie dotrzeć do wszystkich innych stron w tej samej kolejności lub w kolejności, w której wysłano źródło. Aplikacje, które wymagają komunikatów, są dostarczane w określonej kolejności, muszą ją skompilować do swoich aplikacji (na przykład przez dołączenie monotonicznieego identyfikatora z wszystkimi komunikatami).  
  
- **Niezawodna obsługa komunikatów:** Kanał równorzędny nie zawiera mechanizmu, aby zapewnić odbieranie komunikatów przez wszystkie elementy równorzędne. Aby zagwarantować dostarczanie komunikatów, należy napisać warstwę niezawodności na kanale równorzędnym.
