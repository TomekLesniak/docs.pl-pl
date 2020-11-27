---
title: Niezawodny bezpieczny profil
ms.date: 03/30/2017
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
ms.openlocfilehash: 0647b8eaec39b990c139d970b5af1159fb18f8e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267237"
---
# <a name="reliable-secure-profile"></a>Niezawodny bezpieczny profil

Ten przykład pokazuje, jak utworzyć funkcję WCF i [niezawodny profil bezpieczny (RSP)](http://www.ws-i.org/Profiles/ReliableSecureProfile-1.0.html). W tym przykładzie przedstawiono implementację kanału [tworzenia połączenia](http://docs.oasis-open.org/ws-rx/wsmc/200702/wsmc-1.0-spec-cs-01.pdf) , który może być połączony z niezawodnej obsługi komunikatów i opcjonalnie bezpiecznym kanałem do tworzenia niezawodnego bezpiecznego powiązania na podstawie specyfikacji RSP.  
  
> [!IMPORTANT]
> Przykłady mogą być już zainstalowane na komputerze. Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady. Ten przykład znajduje się w następującym katalogu.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a>Dyskusja  

 Ten przykład pokazuje niezawodny asynchronicznie dwukierunkowy scenariusz wymiany komunikatów. Usługa ma umowę dupleksową, a klient implementuje kontrakt wywołania dupleksowego. Klient inicjuje żądanie do usługi, dla którego oczekiwano odpowiedzi na osobnym połączeniu. Komunikat o żądaniu jest przesyłany niezawodnie. Klient nie chce otwierać punktu końcowego nasłuchiwania na końcu. W związku z tym sonduje usługę za pomocą żądań "Utwórz połączenie", aby usługa mogła wysłać odpowiedź z powrotem do kanału z tyłu tego żądania "Utwórz połączenie". Ten przykład pokazuje, jak zapewnić bezpieczną niezawodną komunikację dwukierunkową za pośrednictwem protokołu HTTP bez obsługi przez klienta punktu końcowego nasłuchiwania (i tworzenia wyjątku zapory).  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, skompilować i uruchomić przykład  
  
1. Otwórz rozwiązanie **ReliableSecureProfile** .  
  
2. Kliknij prawym przyciskiem myszy projekt **usługi** w **Eksplorator rozwiązań**, wybierz polecenie **Debuguj**, **Uruchom nowe wystąpienie** z menu kontekstowego. Spowoduje to uruchomienie hosta usługi.  
  
3. Kliknij prawym przyciskiem myszy projekt **klienta** w **Eksplorator rozwiązań**, wybierz polecenie **Debuguj**, **Uruchom nowe wystąpienie** z menu kontekstowego. Spowoduje to uruchomienie klienta.  
  
4. Wpisz dowolny ciąg w wierszu polecenia w oknie konsoli klienta i kliknij przycisk ENTER. Spowoduje to wysłanie ciągu wejściowego do usługi, która oblicza skrót tego ciągu.  
  
5. Wyświetl wyniki dla systemu Windows klienta, gdy usługa wywoła ponownie operację kontraktu wywołania zwrotnego dupleksu, aby wyświetlić wynik w oknie konsoli klienta. Istnieje zamierzone opóźnienie usługi w celu symulowania długotrwałej operacji przetwarzania danych.  
  
6. Monitorowanie ruchu HTTP (przez dowolne narzędzia do monitorowania sieci online, takie jak Monitor sieci, programu Fiddler i tak dalej), pokazuje, że jest ustanowiona sekwencja komunikacji między klientem a usługą zgodnie z niezawodnym bezpiecznym profilem oraz jak klient sonduje usługę przy użyciu żądań "Utwórz połączenie". Gdy usługa jest gotowa do wysłania przetworzonej odpowiedzi, używa kanału z tyłu ostatniego żądania "Utwórz połączenie", aby wysłać wyniki.  
  
7. Naciśnij klawisz ENTER w oknie konsoli usługi, aby zamknąć usługę. Naciśnij klawisz ENTER w oknie konsoli klienta, aby zamknąć klienta programu.
