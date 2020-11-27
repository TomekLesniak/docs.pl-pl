---
title: Rozwiązywanie problemów z samouczkami wprowadzenie do Windows Communication Foundation
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 4d471372419996c5bc490c2d0fdd83927428a41e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281342"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Rozwiązywanie problemów z samouczkami wprowadzenie do Windows Communication Foundation

Ten artykuł zawiera rozwiązania najczęstszych problemów i błędów, które mogą wystąpić podczas wykonywania kroków opisanych w [samouczku: wprowadzenie do aplikacji Windows Communication Foundation](getting-started-tutorial.md).
  
## <a name="common-problems"></a>Typowe problemy

**Nie mogę znaleźć plików projektu na moim dysku twardym.**

 Program Visual Studio zapisuje pliki projektu *w \\ &lt; nazwie użytkownika C:\Users &gt; \source\repos*.  

**Nie mogę znaleźć pliku *App.config* wygenerowanego przez *Svcutil.exe*.**

 W programie Visual Studio okno **Dodaj istniejący element** domyślnie wyświetla tylko pliki z następującymi rozszerzeniami:

- *. cs*
- *.resx*
- *. Settings*
- *. xsd*
- *. WSDL*

Aby wyświetlić wszystkie typy plików, zaznacz **wszystkie pliki ( \* . \* )** na liście rozwijanej w prawym dolnym rogu okna **Dodaj istniejący element** .  
  
## <a name="common-errors"></a>Typowe błędy

### <a name="compile-the-service-application"></a>Kompiluj aplikację usługi

**Nie znaleziono błędu BC30420 "Sub Main" w elemencie "GettingStartedHost. Module1".**

Punkt wejścia jest nieprawidłowy dla aplikacji Visual Basic. Wprowadź następujące zmiany:

   1. W oknie **Eksplorator rozwiązań** wybierz folder **GettingStartedHost** , a następnie wybierz polecenie **Właściwości** z menu skrótów.
    a. W oknie **GettingStartedHost** w polu **obiekt uruchomieniowy** wybierz pozycję **Service. program** (lub punkt wejścia dla danej aplikacji) z listy.
    b. Z menu głównego wybierz pozycję **plik**  >  **Zapisz wszystko**.

### <a name="run-the-service-application"></a>Uruchom aplikację usługi

**Protokół HTTP nie może zarejestrować adresu URL "http: \/ /+: 8000/GettingStarted/CalculatorService". Proces nie ma uprawnień dostępu do tej przestrzeni nazw.**

 Aby uzyskać odpowiedni dostęp, uruchom proces hostujący usługę Windows Communication Foundation (WCF) z uprawnieniami administracyjnymi:

- Dla programu Visual Studio: Wybierz program Visual Studio w menu **Start** , a następnie wybierz polecenie **więcej**  >  **Uruchom jako administrator** z menu skrótów.
- Dla okna konsoli: wybierz pozycję **wiersz polecenia** w menu **Start** , a następnie w menu skrótów wybierz polecenie **więcej**  >  **Uruchom jako administrator** .
- W Eksploratorze Windows: zaznacz plik wykonywalny, a następnie wybierz opcję **Uruchom jako administrator** z menu skrótów.

### <a name="compile-the-client-application"></a>Kompilowanie aplikacji klienckiej

**"CalculatorClient" nie zawiera definicji "" i nie można \<method name> znaleźć metody rozszerzającej "" \<method name> akceptującej pierwszy argument typu "CalculatorClient" (czy nie brakuje dyrektywy using lub odwołania do zestawu?)**  

Tylko te metody, które można oznaczyć przy użyciu `ServiceOperationAttribute` atrybutu, są ujawniane publicznie. Jeśli pominięto `ServiceOperationAttribute` atrybut z metody w `ICalculator` interfejsie, podczas kompilacji pojawi się ten komunikat o błędzie.  

**Nie można znaleźć nazwy typu lub przestrzeni nazw "CalculatorClient" (czy nie brakuje dyrektywy using lub odwołania do zestawu?)**

 Ten błąd występuje, jeśli plik *generatedProxy.cs* (lub *generatedProxy. vb*) nie zostanie dodany do projektu klienta, gdy zostanie wygenerowany przy użyciu narzędzia *Svcutil.exe* .  

### <a name="run-the-client-application"></a>Uruchom aplikację kliencką

**Nieobsługiwany wyjątek: System. ServiceModel. EndpointNotFoundException: nie można nawiązać połączenia z elementem "http: \/ /localhost: 8000/GettingStarted/CalculatorService". Kod błędu TCP 10061: nie można nawiązać połączenia, ponieważ maszyna docelowa aktywnie odrzuciła ją.**

Ten błąd występuje, gdy aplikacja kliencka jest uruchamiana bez wcześniejszego uruchomienia usługi. Najpierw uruchom aplikację hosta, aby uruchomić usługę, a następnie uruchom aplikację kliencką.

### <a name="use-the-svcutilexe-tool"></a>Korzystanie z narzędzia Svcutil.exe

**Element "svcutil" nie został rozpoznany jako polecenie wewnętrzne lub zewnętrzne, program interoperacyjny lub plik wsadowy.**

 *Svcutil.exe* musi znajdować się w ścieżce systemowej. Najprostszym rozwiązaniem jest użycie wiersza polecenia programu Visual Studio. Z menu **Start** wybierz katalog **programu Visual Studio \<version>** , a następnie wybierz opcję **wiersz polecenia dla deweloperów dla programu \<version> vs**. Ten wiersz polecenia ustawia ścieżkę systemową do odpowiednich lokalizacji dla wszystkich narzędzi dostarczanych w ramach programu Visual Studio.  
  
### <a name="run-the-service-and-client-applications"></a>Uruchamianie usługi i aplikacji klienckich

**System. ServiceModel. Security. SecurityNegotiationException —: negocjowanie zabezpieczeń protokołu SOAP z "http: \/ /localhost: 8000/GettingStarted/CalculatorService" dla elementu docelowego "http: \/ /localhost: 8000/GettingStarted/CalculatorService" nie powiodło się**  

Ten błąd występuje na komputerze przyłączonym do domeny, który nie ma łączności sieciowej. Połącz komputer z siecią lub Wyłącz zabezpieczenia zarówno dla usługi, jak i dla klienta.

Aby wyłączyć zabezpieczenia:

- W przypadku usługi Zastąp kod, który tworzy `WSHttpBinding` następujący kod:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- W przypadku klienta w pliku konfiguracji zaktualizuj **\<security>** element pod **\<binding>** elementem w następujący sposób:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator">
      <security mode="None" />
    </binding
    ```  

## <a name="see-also"></a>Zobacz też  

 [Wprowadzenie do aplikacji WCF](getting-started-tutorial.md)  
 [Rozwiązywanie problemów z WCF — Szybki Start](wcf-troubleshooting-quickstart.md)  
 [Rozwiązywanie problemów z instalacją](troubleshooting-setup-issues.md)
