---
title: Uwagi dotyczące zabezpieczeń rejestrowania komunikatów
ms.date: 03/30/2017
ms.assetid: 21f513f2-815b-47f3-85a6-03c008510038
ms.openlocfilehash: 8594329fb27aa1d77a2baffee2a7e37ea0d009c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283773"
---
# <a name="security-concerns-for-message-logging"></a>Uwagi dotyczące zabezpieczeń rejestrowania komunikatów

W tym temacie opisano, jak można chronić poufne dane przed ujawnieniem w dziennikach komunikatów, a także zdarzenia generowane przez funkcję rejestrowania komunikatów.  
  
## <a name="security-concerns"></a>Zagadnienia dotyczące zabezpieczeń  
  
### <a name="logging-sensitive-information"></a>Rejestrowanie poufnych informacji  

 Windows Communication Foundation (WCF) nie modyfikuje żadnych danych w nagłówkach i treści specyficznych dla aplikacji. Funkcja WCF nie śledzi również informacji osobistych w nagłówkach lub danych treści specyficznych dla aplikacji.  
  
 Po włączeniu rejestrowania komunikatów informacje osobiste w nagłówkach specyficznych dla aplikacji, takie jak ciąg zapytania; i informacje o treści, takie jak numer karty kredytowej, mogą stać się widoczne w dziennikach. Narzędzie wdrażania aplikacji jest odpowiedzialne za wymuszanie kontroli dostępu do plików konfiguracyjnych i dzienników. Jeśli nie chcesz, aby ten rodzaj informacji był widoczny, należy wyłączyć rejestrowanie lub przefiltrować część danych, jeśli chcesz udostępnić dzienniki.  
  
 Poniższe porady mogą pomóc zapobiec przypadkowemu ujawnieniu zawartości pliku dziennika:  
  
- Upewnij się, że pliki dziennika są chronione za pomocą list Access Control (ACL) zarówno w scenariuszach hosta sieci Web, jak i z dowolnego hosta.  
  
- Wybierz rozszerzenie pliku, którego nie można łatwo obsłużyć przy użyciu żądania sieci Web. Na przykład rozszerzenie pliku XML nie jest bezpiecznym wyborem. Listę rozszerzeń, które mogą być przekazywane, można znaleźć w podręczniku administratora usług Internet Information Services (IIS).  
  
- Określ ścieżkę bezwzględną dla lokalizacji pliku dziennika, która powinna znajdować się poza katalogiem publicznym wirtualnego katalogu głównego hosta sieci Web, aby uniemożliwić dostęp do niej przez stronę zewnętrzną przy użyciu przeglądarki sieci Web.  
  
 Domyślnie klucze i dane osobowe, takie jak nazwa użytkownika i hasło, nie są rejestrowane w śladach i zarejestrowanych komunikatach. Administrator komputera może jednak użyć `enableLoggingKnownPII` atrybutu w `machineSettings` elemencie Machine.config pliku, aby zezwolić aplikacjom działającym na maszynie na rejestrowanie znanych informacji osobistych. W poniższej konfiguracji pokazano, jak to zrobić:  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <machineSettings enableLoggingKnownPii="true"/>  
   </system.serviceModel>  
</configuration>
```  
  
 Narzędzie do wdrażania aplikacji może następnie użyć `logKnownPii` atrybutu w pliku App.config lub Web.config, aby umożliwić logowanie do użytku osobowego w następujący sposób:  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="true">  
        <listeners>  
                 <add name="messages"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
    </sources>  
</system.diagnostics>  
```  
  
 Tylko wtedy, gdy oba ustawienia są włączone do rejestrowania przez dane `true` osobowe. Kombinacja dwóch przełączników pozwala elastycznie rejestrować znane dane OSOBowe dla każdej aplikacji.  
  
> [!IMPORTANT]
> We [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] `logEntireMessage` `logKnownPii` flagach i należy również ustawić wartość `true` w pliku Web.config lub pliku App.config, aby włączyć rejestrowanie danych osobowych, jak pokazano w poniższym przykładzie `<system.serviceModel><messageLogging logEntireMessage="true" logKnownPii="true" …` .  
  
 Należy pamiętać, że w przypadku określenia co najmniej dwóch źródeł niestandardowych w pliku konfiguracyjnym odczytywane są tylko atrybuty pierwszego źródła. Pozostałe są ignorowane. Oznacza to, że w przypadku następujących App.config plik, dane OSOBowe nie są rejestrowane dla obu źródeł, mimo że rejestrowanie danych osobowych jest jawnie włączone dla drugiego źródła.  
  
```xml  
<system.diagnostics>  
   <sources>  
      <source name="System.ServiceModel.MessageLogging"  
              logKnownPii="false">  
              <listeners>  
                 <add name="messages"  
                      type="System.Diagnostics.XmlWriterTraceListener"  
                      initializeData="c:\logs\messages.svclog" />  
              </listeners>  
            </source>  
      <source name="System.ServiceModel"
              logKnownPii="true">  
              <listeners>  
                 <add name="traces"  
                      type="System.Diagnostics.XmlWriterTraceListener"  
                      initializeData="c:\logs\traces.svclog" />  
              </listeners>  
      </source>  
   </sources>  
</system.diagnostics>  
```  
  
 Jeśli `<machineSettings enableLoggingKnownPii="Boolean"/>` element istnieje poza plikiem Machine.config, system zgłasza <xref:System.Configuration.ConfigurationErrorsException> .  
  
 Zmiany są skuteczne tylko wtedy, gdy aplikacja jest uruchamiana lub uruchamiana ponownie. Zdarzenie jest rejestrowane przy uruchamianiu, gdy oba atrybuty są ustawione na `true` . Zdarzenie jest rejestrowane również wtedy, gdy `logKnownPii` jest ustawione na, `true` ale `enableLoggingKnownPii` jest `false` .  
  
 W przypadku korzystania z tych dwóch przełączników administrator komputera i narzędzie wdrażania aplikacji powinny mieć wyjątkową ostrożność. W przypadku włączenia rejestrowania przez dane OSOBowe są rejestrowane klucze zabezpieczeń i dane OSOBowe. Jeśli jest wyłączona, poufne i specyficzne dla aplikacji dane są nadal rejestrowane w nagłówkach i treściach komunikatów. Bardziej szczegółowe omówienie ochrony prywatności i ochrony danych osobowych przed ujawnieniem można znaleźć w temacie [prywatność użytkowników](/previous-versions/dotnet/articles/aa480490(v=msdn.10)).  
  
> [!CAUTION]
> Dane OSOBowe nie są ukryte w źle sformułowanych wiadomościach. Takie komunikaty są rejestrowane bez żadnych modyfikacji. Opisane wcześniej atrybuty nie mają wpływu na to.  
  
### <a name="custom-trace-listener"></a>Odbiornik śledzenia niestandardowego  

 Dodawanie niestandardowego odbiornika śledzenia do źródła śledzenia rejestrowania komunikatów jest uprawnieniem, które powinno być ograniczone do administratora. Jest to spowodowane tym, że złośliwe niestandardowe odbiorniki można skonfigurować do zdalnego wysyłania wiadomości, co prowadzi do ujawnienia poufnych informacji. Ponadto, jeśli skonfigurujesz odbiornik niestandardowy do wysyłania komunikatów do sieci, takich jak, do zdalnej bazy danych, należy wymusić odpowiednią kontrolę dostępu do dzienników komunikatów na komputerze zdalnym.  
  
## <a name="events-triggered-by-message-logging"></a>Zdarzenia wyzwalane przez rejestrowanie komunikatów  

 Poniżej wymieniono wszystkie zdarzenia emitowane przez funkcję rejestrowania komunikatów.  
  
- Logowanie do wiadomości: to zdarzenie jest emitowane, gdy rejestrowanie komunikatów jest włączone w konfiguracji lub za pomocą usługi WMI. Zawartość zdarzenia to "rejestrowanie komunikatów zostało włączone. Poufne informacje mogą być rejestrowane w postaci zwykłego tekstu, nawet jeśli zostały zaszyfrowane w sieci, na przykład treści wiadomości ".  
  
- Wylogowanie komunikatu: to zdarzenie jest emitowane, gdy rejestrowanie komunikatów jest wyłączone za pomocą usługi WMI. Zawartość zdarzenia to "rejestrowanie komunikatów zostało wyłączone".  
  
- Rejestruj znane dane OSOBowe na: to zdarzenie jest emitowane po włączeniu rejestrowania znanego elementu dane OSOBowe. Dzieje się tak `enableLoggingKnownPii` , gdy atrybut w `machineSettings` elemencie Machine.config jest ustawiony na `true` , a `logKnownPii` atrybut `source` elementu w pliku App.config lub Web.config jest ustawiony na `true` .  
  
- Znane dane OSOBowe nie są dozwolone. to zdarzenie jest emitowane podczas rejestrowania znanego elementu dane OSOBowe jest niedozwolone. Dzieje się tak `logKnownPii` , gdy atrybut `source` elementu w pliku App.config lub Web.config jest ustawiony na `true` , ale `enableLoggingKnownPii` atrybut w `machineSettings` elemencie pliku Machine.config jest ustawiony na `false` . Wyjątek nie jest zgłaszany.  
  
 Te zdarzenia można wyświetlać w narzędziu Podgląd zdarzeń, które są dostarczane z systemem Windows. Aby uzyskać więcej informacji na ten temat, zobacz [Rejestrowanie zdarzeń](./event-logging/index.md).  
  
## <a name="see-also"></a>Zobacz też

- [Rejestrowanie komunikatów](message-logging.md)
- [Problemy dotyczące zabezpieczeń i przydatne porady na temat śledzenia](./tracing/security-concerns-and-useful-tips-for-tracing.md)
