---
title: Śledzenie działania w ramach zabezpieczeń komunikatów
ms.date: 03/30/2017
ms.assetid: 68862534-3b2e-4270-b097-8121b12a2c97
ms.openlocfilehash: 4ab34e3a3ef8487a747c9f9dac71a22006ea515a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265014"
---
# <a name="activity-tracing-in-message-security"></a>Śledzenie działania w ramach zabezpieczeń komunikatów

W tym temacie opisano śledzenie działań na potrzeby przetwarzania zabezpieczeń, które odbywa się w następujących trzech fazach.  
  
- Negocjowanie/SCT Exchange. Może się to zdarzyć w przypadku późniejszego transportu (za pomocą wymiany danych binarnych) lub warstwy wiadomości (za pomocą wymiany komunikatów protokołu SOAP).  
  
- Szyfrowanie/odszyfrowywanie komunikatu z weryfikacją podpisu i uwierzytelnianiem. Ślady są wyświetlane w działaniu otoczenia, zazwyczaj "Akcja procesu".  
  
- Autoryzacja i weryfikacja. Może się to zdarzyć lokalnie lub podczas komunikacji między punktami końcowymi.  
  
## <a name="negotiationsct-exchange"></a>Negocjowanie/wymiana z SCT  

 W fazie wymiany negocjacji/SCT są tworzone dwa typy działań na kliencie: "Skonfiguruj bezpieczną sesję" i "Zamknij bezpieczną sesję". "Skonfiguruj bezpieczną sesję" obejmuje ślady dla wymiany komunikatów RST/RSTR/SCT, natomiast polecenie "Zamknij bezpieczną sesję" obejmuje ślady dla wiadomości Anuluj.  
  
 Na serwerze każde żądanie/odpowiedź dla RST/RSTR/SCT pojawia się w jego własnej aktywności. Jeśli `propagateActivity` = `true` zarówno serwer, jak i klient, działania na serwerze mają ten sam identyfikator i pojawiają się razem w oknie "bezpieczna sesja" podczas wyświetlania za pomocą przeglądarki śledzenia usługi.  
  
 Ten model śledzenia aktywności jest prawidłowy dla uwierzytelniania nazwy użytkownika/hasła, uwierzytelniania certyfikatów i uwierzytelniania NTLM.  
  
 W poniższej tabeli wymieniono działania i ślady dotyczące negocjacji oraz wymiany SCT.  
  
||Czas, w którym odbywa się negocjowanie/nawiązywanie wymiany z SCT|Działania|Ślady|  
|-|-------------------------------------------------|----------------|------------|  
|Bezpieczny transport<br /><br /> (HTTPS, SSL)|Po odebraniu pierwszego komunikatu.|Ślady są emitowane w działaniu otoczenia.|— Ślady programu Exchange<br />-Nawiązano bezpieczny kanał<br />— Otrzymane wpisy tajne są udostępniane.|  
|Warstwa komunikatów zabezpieczonych<br /><br /> (WSHTTP)|Po odebraniu pierwszego komunikatu.|Na kliencie:<br /><br /> -"Skonfiguruj bezpieczną sesję" z "akcją procesu" dla tego pierwszego komunikatu dla każdego żądania/odpowiedzi dla RST/RSTR/SCT.<br />-"Zamknij bezpieczną sesję" dla elementu CANCEL Exchange wychodzącego z działania "Zamknij serwer proxy". To działanie może wystąpić z innego otoczenia, w zależności od tego, kiedy jest zamykana bezpieczna sesja.<br /><br /> Na serwerze programu:<br /><br /> -Jedno działanie "Akcja procesowa" dla każdego żądania/odpowiedzi dla RST/SCT/Anuluj na serwerze. W przypadku `propagateActivity` = `true` , gdy działania RST/RSTR/SCT są scalane z usługą "Skonfiguruj sesję zabezpieczeń", a przycisk Anuluj zostanie scalony z działaniem "Zamknij" z klienta.<br /><br /> Dla opcji "Skonfiguruj bezpieczną sesję" Istnieją dwa etapy:<br /><br /> 1. negocjowanie uwierzytelniania. Jest to opcjonalne, jeśli klient ma już odpowiednie poświadczenia. Tę fazę można wykonać za poorednictwem bezpiecznego transportu lub wymian komunikatów. W tym drugim przypadku mogą wystąpić 1 lub 2 RSTR. W przypadku tych wymian ślady są emitowane w nowych działaniach żądania/odpowiedzi zgodnie z założeniami.<br />2. Ustanawianie bezpiecznej sesji (SCT), w której występuje jeden z nich. Ma to takie same działania otoczenia jak opisane wcześniej.|— Ślady programu Exchange<br />-Nawiązano bezpieczny kanał<br />— Otrzymane wpisy tajne są udostępniane.|  
  
> [!NOTE]
> W trybie zabezpieczeń mieszanym uwierzytelnianie negocjacji odbywa się w wymianach binarnych, ale w wymianie komunikatów jest to polecenie SCT. W trybie czysty transport negocjacje odbywają się tylko w transporcie bez dodatkowych działań.  
  
## <a name="message-encryption-and-decryption"></a>Szyfrowanie i odszyfrowywanie komunikatów  

 Poniższa tabela zawiera listę działań i śladów związanych z szyfrowaniem/odszyfrowywaniem komunikatów oraz uwierzytelnianiem sygnatury.  
  
||Bezpieczny transport<br /><br /> (HTTPS, SSL) i bezpieczna warstwa komunikatów<br /><br /> (WSHTTP)|  
|-|---------------------------------------------------------------------------------|  
|Czas, w którym następuje szyfrowanie i odszyfrowywanie wiadomości, a także uwierzytelnianie podpisu|Po odebraniu komunikatu|  
|Działania|Ślady są emitowane w działaniu ProcessAction na kliencie i serwerze.|  
|Ślady|-sendSecurityHeader (nadawca):<br />-Podpisz wiadomość<br />-Szyfruj dane żądania<br />-receiveSecurityHeader (odbiornik):<br />-Weryfikuj podpis<br />-Odszyfruj dane odpowiedzi<br />-Uwierzytelnianie|  
  
> [!NOTE]
> W trybie czystego transportu szyfrowanie lub odszyfrowywanie komunikatów odbywa się tylko w transporcie bez dodatkowych działań.  
  
## <a name="authorization-and-verification"></a>Autoryzacja i weryfikacja  

 Poniższa tabela zawiera listę działań i śladów na potrzeby autoryzacji.  
  
||Czas trwania autoryzacji|Działania|Ślady|  
|-|-------------------------------------|----------------|------------|  
|Lokalna (domyślnie)|Po odszyfrowaniu komunikatu na serwerze|Ślady są emitowane w działaniu ProcessAction na serwerze.|Użytkownik autoryzowany.|  
|Zdalne|Po odszyfrowaniu komunikatu na serwerze|Ślady są emitowane w nowym działaniu wywoływanym przez działanie ProcessAction.|Użytkownik autoryzowany.|
