---
title: Scenariusze asynchroniczne z zastosowaniem protokołu HTTP lub TCP albo potoku nazwanego
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 00213c8d117f4319d7e29312dd0b9805d916231a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244148"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a>Scenariusze asynchroniczne z zastosowaniem protokołu HTTP lub TCP albo potoku nazwanego

W tym temacie opisano działania i transfery dla różnych scenariuszy żądań asynchronicznych/odpowiedzi z żądaniami wielowątkowymi przy użyciu protokołu HTTP, TCP lub potoku nazwanego.  
  
## <a name="asynchronous-requestreply-without-errors"></a>Asynchroniczne żądanie/odpowiedź bez błędów  

 W tej sekcji opisano działania i transfery scenariusza żądania/odpowiedzi asynchronicznej oraz klientów wielowątkowych.  
  
 Działanie obiektu wywołującego kończy się `beginCall` , gdy zwraca i `endCall` zwraca. Wywołanie zwrotne zwraca wartość wywołania zwrotnego.  
  
 Wywołane działanie kończy się `beginCall` , gdy zwraca, `endCall` zwraca lub gdy wywołanie zwrotne zwraca, jeśli zostało wywołane z tego działania.  
  
### <a name="asynchronous-client-without-callback"></a>Klient asynchroniczny bez wywołania zwrotnego  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a>Propagacja jest włączona po obu stronach, przy użyciu protokołu HTTP  

 ![Klient asynchroniczny bez wywołania zwrotnego, gdzie w obu stronach jest ustawiona wartość true.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)
  
 Jeśli `propagateActivity=true` ProcessMessage wskazuje aktywność ProcessAction do przekazania.  
  
 W przypadku scenariuszy opartych na protokole HTTP ReceiveBytes jest wywoływana w pierwszej wiadomości w celu wysłania i istnieje dla okresu istnienia żądania.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a>Propagacja jest wyłączona po obu stronach, przy użyciu protokołu HTTP  

 Jeśli `propagateActivity=false` po obu stronach ProcessMessage nie wskazuje, które działanie ProcessAction do przeniesienia. W związku z tym nowe tymczasowe działanie ProcessAction z nowym IDENTYFIKATORem jest wywoływana. Po dopasowaniu asynchronicznej odpowiedzi do żądania w kodzie ServiceModel, identyfikator działania można pobrać z kontekstu lokalnego. Rzeczywiste działanie ProcessAction można przenieść do tego identyfikatora.  
  
 ![Klient asynchroniczny bez wywołania zwrotnego, gdzie Propagacja jest ustawiona na wartość false po obu stronach.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  

 W przypadku scenariuszy opartych na protokole HTTP ReceiveBytes jest wywoływana w pierwszej wiadomości w celu wysłania i istnieje dla okresu istnienia żądania.  
  
 Działanie działania procesu jest tworzone na kliencie asynchronicznym, gdy `propagateActivity=false` obiekt wywołujący lub wywoływany, a komunikat odpowiedzi nie zawiera nagłówka akcji.  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a>Propagacja jest włączona po obu stronach, przy użyciu protokołu TCP lub potoku nazwanego  

 ![Klient asynchroniczny bez wywołania zwrotnego, gdzie Propagacja jest ustawiona na wartość true po obu stronach i nazwanym potoku/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 W przypadku Named-Pipe lub opartego na protokole TCP scenariusza ReceiveBytes jest wywoływana, gdy klient zostanie otwarty i istnieje dla okresu istnienia połączenia.  
  
 Podobnie jak w przypadku pierwszego obrazu, jeśli `propagateActivity=true` ProcessMessage wskazuje aktywność ProcessAction do przekazania.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a>Propagacja jest wyłączona po obu stronach, przy użyciu protokołu TCP lub potoku nazwanego  

 W przypadku Named-Pipe lub opartego na protokole TCP scenariusza ReceiveBytes jest wywoływana, gdy klient zostanie otwarty i istnieje dla okresu istnienia połączenia.  
  
 Podobnie jak w przypadku drugiego obrazu, jeśli `propagateActivity=false` po obu stronach ProcessMessage nie wskazuje, które działanie ProcessAction ma zostać przesłane. W związku z tym nowe tymczasowe działanie ProcessAction z nowym IDENTYFIKATORem jest wywoływana. Po dopasowaniu asynchronicznej odpowiedzi do żądania w kodzie ServiceModel, identyfikator działania można pobrać z kontekstu lokalnego. Rzeczywiste działanie ProcessAction można przenieść do tego identyfikatora.  
  
 ![Klient asynchroniczny bez wywołania zwrotnego, gdzie Propagacja jest ustawiona na false po obu stronach i nazwanym potoku/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  

### <a name="asynchronous-client-with-callback"></a>Klient asynchroniczny z wywołaniem zwrotnym  

 W tym scenariuszu dodano działania G i ", w przypadku wywołania zwrotnego i `endCall` i ich transfery w/out.  
  
 W tej sekcji pokazano tylko, jak używać protokołu HTTP z `propagateActivity` = `true` . Jednak dodatkowe działania i transfery mają zastosowanie również do innych przypadków (czyli `propagateActivity` = `false` przy użyciu protokołu TCP lub nazwanego potoka).  
  
 Wywołanie zwrotne tworzy nowe działanie (G), gdy klient wywołuje kod użytkownika w celu powiadomienia, że wyniki są gotowe. Kod użytkownika następnie wywołuje w `endCall` ramach wywołania zwrotnego (jak pokazano na rysunku 5) lub poza wywołaniem zwrotnym (rysunek 6). Ponieważ nie jest znane, z którego działania użytkownika `endCall` jest wywoływane, to działanie jest oznaczone etykietą `A’` . Istnieje możliwość, że wartość "może być taka sama jak lub inna od.  
  
 ![Pokazuje klienta asynchronicznego z wywołaniem zwrotnym, endCall w wywołaniu zwrotnym.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  

 ![Pokazuje klienta asynchronicznego z wywołaniem zwrotnym endCall poza wywołaniem zwrotnym.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  

### <a name="asynchronous-server-with-callback"></a>Serwer asynchroniczny z wywołaniem zwrotnym  

 ![Pokazuje serwer asynchroniczny z wywołaniem zwrotnym.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  

 Stos kanałów wywołuje klienta po odebraniu komunikatu: ślady dla tego przetwarzania są emitowane w samym działaniu ProcessRequest.  
  
## <a name="asynchronous-requestreply-with-errors"></a>Asynchroniczne żądanie/odpowiedź z błędami  

 Błędy komunikatów o błędach są odbierane podczas `endCall` . W przeciwnym razie działania i transfery są podobne do poprzednich scenariuszy.  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a>Asynchroniczne One-Way z błędami lub bez nich  

 Klient nie zwrócił odpowiedzi lub błędu.
