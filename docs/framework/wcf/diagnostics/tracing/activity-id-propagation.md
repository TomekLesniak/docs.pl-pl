---
title: Propagacja identyfikatora działania
ms.date: 03/30/2017
ms.assetid: cd1c1ae5-cc8a-4f51-90c9-f7b476bcfe70
ms.openlocfilehash: 0f0478b16bf2ca0975ae0290a8855756ecfc383e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236107"
---
# <a name="activity-id-propagation"></a>Propagacja identyfikatora działania

Propagacja jest wykonywana, gdy włączone jest śledzenie aktywności ServiceModel (Propagacja elementu ServiceModel) lub wyłączone (Propagacja działań użytkownika do użytkownika).  
  
## <a name="servicemodel-activity-tracing-is-enabled"></a>Śledzenie działań ServiceModel jest włączone  

 Jeśli ServiceModel ActivityTracing jest włączony, Propagacja odbywa się między działaniami ProcessAction.  
  
### <a name="server"></a>Serwer  

 Gdy `propagateActivity` atrybut jest ustawiony na `true` zarówno na kliencie, jak i na serwerze, identyfikator `ProcessAction` działania na serwerze jest IDENTYCZNy z identyfikatorem w `ActivityId` nagłówku propagowanych komunikatów.  
  
 Gdy `ActivityId` w komunikacie nie występuje nagłówek (czyli `propagateActivity` = `false` na kliencie) lub `propagateActivity` = `false` na serwerze, serwer generuje nowy identyfikator działania.  
  
### <a name="client"></a>Klient  

 Jeśli klient jest synchronicznie pojedynczym wątkiem, klient nie uwzględnia żadnych ustawień `propagateActivity` na kliencie lub serwerze. Zamiast tego odpowiedź jest obsługiwana w działaniu żądania. Jeśli klient jest asynchroniczny lub synchronicznie wielowątkowy, `propagateActivity` = `true` na kliencie i istnieje nagłówek identyfikatora działania w komunikacie wysyłanym przez serwer, klient Pobiera identyfikator działania z komunikatu i przesyła do działania procesu działania, które zawiera identyfikator propagowanej aktywności. W przeciwnym razie klient przesyła z działania Process Message do nowego działania akcji procesu. Ten dodatkowy transfer do nowego działania akcji procesu jest wykonywany w celu zapewnienia spójności. W ramach tego działania klient Pobiera identyfikator aktywności działania BeginCall z lokalnego kontekstu wątku, gdy wątek zostanie przydzielony do przetwarzania komunikatów odpowiedzi. Następnie przenosi do działania początkowej akcji proces.  
  
 Jeśli klient jest w trybie dupleksu, klient działa jako serwer podczas odbioru wiadomości.  
  
### <a name="propagation-in-fault-messages"></a>Propagacja w komunikatach o błędach  

 Nie ma różnicy w obsłudze komunikatów prawidłowych i błędów. Jeśli `propagateActivity` = `true` identyfikator działania dodany do nagłówka komunikatu o błędzie protokołu SOAP jest identyczny z działaniem otoczenia.  
  
## <a name="servicemodel-activity-tracing-is-disabled"></a>Śledzenie działań ServiceModel jest wyłączone  

 Jeśli ServiceModel ActivityTracing jest wyłączony, Propagacja odbywa się między działaniami kodu użytkownika bezpośrednio bez przechodzenia przez działania programu ServiceModel. Identyfikator działania zdefiniowany przez użytkownika jest również propagowany za pomocą nagłówka identyfikatora działania wiadomości.  
  
 Jeśli `propagateActivity` = `true` i `ActivityTracing` = `off` dla odbiornika śledzenia ServiceModel (bez względu na to, czy funkcja śledzenia jest włączona na modelu ServiceModel), na kliencie lub serwerze:  
  
- W przypadku żądania operacji lub wysyłania odpowiedzi, identyfikator działania w protokole TLS jest propagowany z kodu użytkownika do momentu, gdy wiadomość zostanie utworzona. Nagłówek identyfikatora działania jest również wstawiany do komunikatu przed jego wysłaniem.  
  
- W przypadku odebrania żądania lub odebrania odpowiedzi identyfikator działania jest pobierany z nagłówka wiadomości zaraz po utworzeniu odebranego obiektu wiadomości. Identyfikator działania w protokole TLS jest propagowany zaraz po osiągnięciu przez niego komunikatu z zakresu, dopóki nie zostanie osiągnięty kod użytkownika.  
  
 Te akcje gwarantują, że ślady użytkownika będą wyświetlane w tym samym działaniu, gdy Propagacja jest włączona. Nie ma jednak gwarancji na ślady ServiceModel. Ślady ServiceModel występują w działaniu kodu użytkownika tylko wtedy, gdy przetwarzanie tych śladów jest wykonywane w tym samym wątku, w którym ustawiono działanie kod użytkownika.  
  
 Ogólnie rzecz biorąc, ślady elementu ServiceModel można zaobserwować w następujących miejscach:  
  
- Jeśli śledzenie ServiceModel jest wyłączone, wszystkie emitowane ślady pojawiają się w działaniach użytkownika. Jeśli Propagacja jest włączona zarówno na serwerze, jak i na kliencie, te ślady będą znajdować się w tym samym działaniu.  
  
- Jeśli śledzenie ServiceModel jest włączone, ale ActivityTracing jest wyłączone, ślady użytkownika są wyświetlane w tym samym działaniu, jeśli Propagacja jest włączona na obu końcach. Ślady ServiceModel pojawiają się w domyślnym działaniu 0000, chyba że występują w tym samym wątku co przetwarzanie kodu użytkownika, w którym działanie jest początkowo ustawione.  
  
- Jeśli włączone są zarówno śledzenie ServiceModel, jak i ActivityTracing, ślady użytkownika są wyświetlane w działaniach zdefiniowanych przez użytkownika, a ślady ServiceModel są wyświetlane w działaniach zdefiniowanych przez program ServiceModel. Propagacja odbywa się na poziomie elementu ServiceModel.
