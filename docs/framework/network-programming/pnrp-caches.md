---
title: Pamięci podręczne PNRP
ms.date: 03/30/2017
ms.assetid: 270068d9-1b6b-4eb9-9e14-e02326bb88df
ms.openlocfilehash: 6f45b6d829867d830a9a10acf11e8456ba65d29e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263220"
---
# <a name="pnrp-caches"></a>Pamięci podręczne PNRP

Bufory protokołu PNRP (Peer Name Resolution Protocol) są lokalnymi kolekcjami algorithmically wybranych punktów końcowych elementu równorzędnego przechowywanych w elemencie równorzędnym.  
  
## <a name="pnrp-cache-initialization"></a>Inicjowanie pamięci podręcznej PNRP  

 W celu zainicjowania pamięci podręcznej PNRP lub kolekcji rekordów nazw równorzędnych podczas uruchamiania węzła równorzędnego węzeł może używać następujących metod:  
  
- Trwałe wpisy pamięci podręcznej, które były obecne podczas zamykania węzła, są ładowane z magazynu dysk twardy.  
  
- Jeśli aplikacja korzysta z infrastruktury współpracy P2P, informacje o współpracy są dostępne w Menedżerze kontaktów dla tego węzła.  
  
## <a name="scaling-peer-name-resolution-with-a-multi-level-cache"></a>Skalowanie rozpoznawania nazw elementów równorzędnych za pomocą pamięci podręcznej na wiele poziomów  

 Aby zachować niewielkie rozmiary pamięci podręcznej PNRP, węzły równorzędne używają pamięci podręcznej wielu poziomów, w której każdy poziom zawiera maksymalną liczbę wpisów. Każdy poziom w pamięci podręcznej reprezentuje jedną dziesiątą mniejszą część przestrzeni liczby identyfikatorów PNRP (2<sup>256</sup>). Najniższy poziom w pamięci podręcznej zawiera zarejestrowany lokalnie identyfikator PNRP oraz inne identyfikatory protokołu PNRP, które są numerycznie blisko siebie. Ponieważ poziom pamięci podręcznej jest wypełniony maksymalnie 20 wpisów, tworzony jest nowy niższy poziom. Maksymalna liczba poziomów w pamięci podręcznej znajduje się w kolejności LOG10 — (całkowita liczba identyfikatorów PNRP w chmurze). Na przykład w przypadku chmury globalnej z 100 000 000 identyfikatorami PNRP nie ma więcej niż 8 (100000000) poziomów w pamięci podręcznej i podobną liczbę przeskoków w celu rozpoznania identyfikatora PNRP podczas rozpoznawania nazw. Ten mechanizm umożliwia użycie rozproszonej tabeli skrótów, dla której można rozpoznać dowolny identyfikator PNRP, przekazując komunikaty żądania protokołu PNRP do najbliższego elementu równorzędnego do momentu znalezienia elementu równorzędnego z odpowiadającą CPA.  
  
 Aby upewnić się, że rozwiązanie może zostać ukończone, za każdym razem, gdy węzeł dodaje wpis do najniższego poziomu jego pamięci podręcznej, zapełni kopię wpisu do wszystkich węzłów znajdujących się na ostatnim poziomie pamięci podręcznej.  
  
 Wpisy pamięci podręcznej są odświeżane w czasie. Wpisy pamięci podręcznej, które są przestarzałe, są usuwane z pamięci podręcznej. Wynika to z tego, że rozproszonej tabeli skrótów identyfikatorów PNRP bazują na aktywnych punktach końcowych, w przeciwieństwie do serwera DNS, w którym rekordy adresów i protokół DNS nie zapewniają, że węzeł skojarzony z adresem jest aktywnie w sieci.  
  
## <a name="other-pnrp-caches"></a>Inne pamięci podręczne PNRP  

 Innym trwałym magazynem danych jest lokalna pamięć podręczna.  Oprócz innych obiektów wymaganych przez działanie protokołu PNRP mogą one obejmować rekordy skojarzone z chmurą lub sesją współpracy usługi PNRP, która jest bezpiecznie publikowana i synchronizowana między wszystkimi członkami chmury. Ten replikowany magazyn reprezentuje widok danych grupy, który powinien być taki sam dla wszystkich członków grupy. Technicznie te obiekty nie są rekordy na SE, ale raczej aplikacje, obecność i dane obiektów przeznaczone dla lokalnej pamięci podręcznej. Korzystanie z chmury PNRP gwarantuje, że obiekty są propagowane do wszystkich węzłów w sesji współpracy lub w chmurze PNRP.  Rejestruj replikację między elementami członkowskimi w chmurze przy użyciu protokołu SSL, aby zapewnić szyfrowanie i integralność danych.  
  
 Po dołączeniu elementu równorzędnego do chmury nie są automatycznie odbierane dane lokalnej pamięci podręcznej z hosta równorzędnego, do którego je dołączają; muszą subskrybować elementy równorzędne hosta, aby otrzymywać aktualizacje w aplikacji, obecności i danych obiektów. Po początkowej synchronizacji elementy równorzędne okresowo synchronizują swoje zreplikowane magazyny, aby upewnić się, że wszyscy członkowie grupy spójnie mają ten sam widok.  Sesja współpracy lub aplikacje w ramach sesji współpracy mogą również wykonywać tę samą funkcję.  
  
 Po rozpoczęciu sesji współpracy z chmurą aplikacje mogą rejestrować elementy równorzędne i rozpocząć publikowanie informacji przy użyciu zabezpieczeń zdefiniowanych przez zakres chmury. Po dołączeniu elementu równorzędnego do chmury mechanizmy zabezpieczeń dla chmury są stosowane do elementu równorzędnego, dając mu zakres, do którego należy wziąć udział.  Jego rekordy można następnie opublikować bezpiecznie w zakresie chmury. Należy zauważyć, że zakres chmury nie może być taki sam jak zakres aplikacji współpracy.  
  
 Elementy równorzędne mogą rejestrować interesy w odniesieniu do obiektów z innych elementów równorzędnych. Po zaktualizowaniu obiektu aplikacja do współpracy zostanie powiadomiona, a nowy obiekt zostanie przekazany do wszystkich subskrybentów aplikacji. Na przykład element równorzędny w aplikacji rozmowy grupowej może zarejestrować zainteresowanie otrzymywania informacji o aplikacji, co spowoduje wysłanie wszystkich rekordów rozmowy jako danych aplikacji.  Umożliwia to monitorowanie aktywności czatu w chmurze.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Net.PeerToPeer>
