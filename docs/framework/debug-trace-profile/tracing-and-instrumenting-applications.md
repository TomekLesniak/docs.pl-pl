---
title: Śledzenie i instrumentacja aplikacji
description: Śledzenie i Instrumentacja aplikacji na platformie .NET. Funkcja śledzenia umożliwia monitorowanie wykonywania aplikacji w trakcie jej działania. Instrumentacja umożliwia mierzenie poziomu wydajności.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework]
- debugging [.NET Framework], instrumentation
- performance monitoring, instrumentation
- instrumentation, about instrumentation
- tracing [.NET Framework], about tracing
- performance monitoring, tracing code
- Trace class, instrumentation for .NET applications
ms.assetid: 773b6fc4-9013-4322-b728-5dec7a72e743
ms.openlocfilehash: 63fdf49ba688c0b3c4ee6653e1c2960c49f526ce
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257122"
---
# <a name="tracing-and-instrumenting-applications"></a>Śledzenie i instrumentacja aplikacji

Śledzenie służy do monitorowania wykonywania aplikacji w trakcie jej działania. Możesz dodać instrumentację śledzenia i debugowania do aplikacji .NET Framework podczas jej opracowywania i można używać jej zarówno podczas tworzenia aplikacji, jak i po jej wdrożeniu. Przy użyciu <xref:System.Diagnostics.Trace?displayProperty=nameWithType> <xref:System.Diagnostics.Debug?displayProperty=nameWithType> klas, i można <xref:System.Diagnostics.TraceSource?displayProperty=nameWithType> rejestrować informacje o błędach i wykonywaniu aplikacji w dziennikach, plikach tekstowych lub innych urządzeniach w celu późniejszej analizy.  
  
 Termin *Instrumentacja* odnosi się do zdolności do monitorowania lub mierzenia poziomu wydajności produktu oraz do diagnozowania błędów. W programowaniu oznacza to zdolność aplikacji do dołączenia:  
  
- **Śledzenie kodu** — otrzymywanie komunikatów informacyjnych dotyczących wykonywania aplikacji w czasie wykonywania.  
  
- **Debugowanie** — śledzenie i rozwiązywanie błędów programistycznych w aplikacji opracowywanej. Aby uzyskać więcej informacji, zobacz [debugowanie](/visualstudio/debugger/debugger-feature-tour).  
  
- **Liczniki wydajności** — składniki, które umożliwiają śledzenie wydajności aplikacji. Aby uzyskać więcej informacji, zobacz [liczniki wydajności](performance-counters.md).  
  
- **Dzienniki zdarzeń** — składniki umożliwiające otrzymywanie i śledzenie najważniejszych zdarzeń w trakcie wykonywania aplikacji. Aby uzyskać więcej informacji, zobacz <xref:System.Diagnostics.EventLog> Klasa.  
  
 Instrumentacja aplikacji przez umieszczenie instrukcji Trace w strategicznych lokalizacjach w kodzie jest szczególnie przydatne w przypadku aplikacji rozproszonych. Przy użyciu instrukcji śledzenia można przystąpić do Instrumentacji aplikacji, aby nie tylko wyświetlała informacje, gdy coś się nie powiedzie, ale również do monitorowania, jak dobrze działa aplikacja.  
  
 <xref:System.Diagnostics.TraceSource>Klasa udostępnia ulepszone funkcje śledzenia i może być używana zamiast metod statycznych <xref:System.Diagnostics.Trace> klas starszych i <xref:System.Diagnostics.Debug> śledzenia. Znane <xref:System.Diagnostics.Trace> i <xref:System.Diagnostics.Debug> klasy są nadal szeroko używane, ale <xref:System.Diagnostics.TraceSource> Klasa jest zalecana dla nowych poleceń śledzenia, takich jak <xref:System.Diagnostics.TraceSource.TraceEvent%2A> i <xref:System.Diagnostics.TraceSource.TraceData%2A> .  
  
 <xref:System.Diagnostics.Trace>Klasy i <xref:System.Diagnostics.Debug> są identyczne, z tą różnicą, że procedury i funkcje <xref:System.Diagnostics.Trace> klasy są kompilowane domyślnie do kompilacji wydań, ale te <xref:System.Diagnostics.Debug> klasy nie są.  
  
 <xref:System.Diagnostics.Trace>Klasy i <xref:System.Diagnostics.Debug> zapewniają środki do monitorowania i badania wydajności aplikacji podczas tworzenia lub po wdrożeniu. Na przykład można użyć <xref:System.Diagnostics.Trace> klasy do śledzenia określonych typów akcji w wdrożonej aplikacji (na przykład tworzenia nowych połączeń z bazą danych) i w związku z tym może monitorować wydajność aplikacji.  
  
## <a name="code-tracing-and-debugging"></a>Śledzenie i debugowanie kodu  

 Podczas programowania można użyć metod wyjściowych <xref:System.Diagnostics.Debug> klasy do wyświetlania komunikatów w oknie danych wyjściowych zintegrowanego środowiska programistycznego (IDE) programu Visual Studio. Przykład:  
  
```vb  
Trace.WriteLine("Hello World!")  
Debug.WriteLine("Hello World!")  
```  
  
```csharp  
System.Diagnostics.Trace.WriteLine("Hello World!");  
System.Diagnostics.Debug.WriteLine("Hello World!");  
```  
  
 W każdym z tych przykładów zostanie wyświetlony "Hello world!" w oknie dane wyjściowe, gdy aplikacja jest uruchamiana w debugerze.  
  
 Dzięki temu można debugować aplikacje i zoptymalizować ich wydajność na podstawie ich zachowania w środowisku testowym. Można debugować aplikację w kompilacji debugowania z <xref:System.Diagnostics.Debug> włączonym atrybutem warunkowym, tak aby wszystkie dane wyjściowe debugowania były odbierane. Gdy aplikacja jest gotowa do wydania, można skompilować kompilację wydania bez włączania <xref:System.Diagnostics.Debug> atrybutu warunkowego, dzięki czemu kompilator nie będzie zawierać kodu debugowania w końcowym pliku wykonywalnym. Aby uzyskać więcej informacji, zobacz [jak: kompilować warunkowo z śledzeniem i debugowaniem](how-to-compile-conditionally-with-trace-and-debug.md). Aby uzyskać więcej informacji na temat różnych konfiguracji kompilacji dla aplikacji, zobacz [Kompilowanie i kompilowanie](/visualstudio/ide/compiling-and-building-in-visual-studio).  
  
 Możesz również śledzić wykonywanie kodu w zainstalowanej aplikacji przy użyciu metod <xref:System.Diagnostics.Trace> klasy. Umieszczając [przełączniki śledzenia](trace-switches.md) w kodzie, można kontrolować, czy śledzenie ma się odbywać i jak obszerne. Umożliwia to monitorowanie stanu aplikacji w środowisku produkcyjnym. Jest to szczególnie ważne w przypadku aplikacji biznesowej, która używa wielu składników uruchomionych na wielu komputerach. Można kontrolować sposób używania przełączników po wdrożeniu za pomocą pliku konfiguracji. Aby uzyskać więcej informacji, zobacz [jak: Tworzenie, inicjowanie i konfigurowanie przełączników śledzenia](how-to-create-initialize-and-configure-trace-switches.md).  
  
 Podczas tworzenia aplikacji, dla której zamierzasz korzystać z śledzenia, zwykle w kodzie aplikacji są uwzględniane zarówno śledzenie, jak i debugowanie komunikatów. Gdy wszystko będzie gotowe do wdrożenia aplikacji, można skompilować kompilację wydania bez włączania atrybutu warunku **debugowania** . Można jednak włączyć atrybut **śledzenia** warunkowego, aby kompilator uwzględniał kod śledzenia w pliku wykonywalnym. Aby uzyskać więcej informacji, zobacz [jak: kompilować warunkowo z śledzeniem i debugowaniem](how-to-compile-conditionally-with-trace-and-debug.md).  
  
### <a name="phases-of-code-tracing"></a>Etapy śledzenia kodu  

 Istnieją trzy fazy śledzenia kodu:  
  
1. **Instrumentacja** — Dodawanie kodu śledzenia do aplikacji.  
  
2. **Śledzenie** — kod śledzenia zapisuje informacje w określonym miejscu docelowym.  
  
3. **Analiza** — informacje o śledzeniu są oceniane, aby identyfikować i zrozumieć problemy w aplikacji.  
  
 Podczas tworzenia wszystkie metody debugowania i śledzenia danych wyjściowych zapisują informacje w oknie danych wyjściowych w programie Visual Studio domyślnie. W wdrożonej aplikacji metody zapisują informacje o śledzeniu do określonych celów. Aby uzyskać więcej informacji na temat określania docelowego wyjścia do śledzenia lub debugowania, zobacz [detektory śledzenia](trace-listeners.md).  
  
 Poniżej znajduje się ogólny widok najważniejszych kroków zwykle związanych z użyciem śledzenia do analizowania i rozwiązywania potencjalnych problemów w wdrożonych aplikacjach. Aby uzyskać więcej informacji na temat sposobu wykonywania tych kroków, zobacz odpowiedni link.  
  
##### <a name="to-use-tracing-in-an-application"></a>Aby użyć śledzenia w aplikacji  
  
1. Rozważ, które dane wyjściowe śledzenia mają być odbierane po wdrożeniu aplikacji.  
  
2. Utwórz zestaw przełączników. Aby uzyskać więcej informacji, zobacz [How to: Configure Trace switchs](how-to-create-initialize-and-configure-trace-switches.md).  
  
3. Dodaj instrukcje śledzenia do kodu aplikacji.  
  
4. Określ, gdzie mają być wyświetlane dane wyjściowe śledzenia i Dodaj odpowiednie detektory. Aby uzyskać więcej informacji, zobacz [Tworzenie i Inicjowanie odbiorników śledzenia](how-to-create-and-initialize-trace-listeners.md).  
  
5. Przetestuj i Debuguj aplikację oraz kod śledzenia, który zawiera.  
  
6. Skompiluj aplikację do kodu wykonywalnego za pomocą jednej z następujących procedur:  
  
    - Użyj menu **kompilacja** wraz z stroną **debugowanie** okna dialogowego **strony właściwości** w **Eksplorator rozwiązań**. Użyj tego podczas kompilowania w programie Visual Studio.  
  
         \- oraz  
  
    - Zastosuj dyrektywy kompilatora **Trace** i **Debug** dla metody wiersza polecenia kompilowania. Aby uzyskać więcej informacji, zobacz [warunek kompilowania z użyciem śledzenia i debugowania](how-to-compile-conditionally-with-trace-and-debug.md). Użyj tego podczas kompilowania z wiersza polecenia.  
  
7. Jeśli w czasie wykonywania wystąpi problem, Włącz odpowiedni przełącznik śledzenia. Aby uzyskać więcej informacji, zobacz [Konfigurowanie przełączników śledzenia](how-to-create-initialize-and-configure-trace-switches.md).  
  
     Kod śledzenia zapisuje komunikaty śledzenia do określonego celu, na przykład ekran, plik tekstowy lub dziennik zdarzeń. Typ odbiornika, który został uwzględniony w <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> kolekcji, określa element docelowy.  
  
8. Analizowanie komunikatów śledzenia w celu zidentyfikowania i zrozumienia problemu w aplikacji.  
  
## <a name="trace-instrumentation-and-distributed-applications"></a>Instrumentacja śledzenia i aplikacje rozproszone  

 Podczas tworzenia aplikacji rozproszonej może być trudne przetestowanie aplikacji w sposób, w jaki zostanie ona użyta. Kilka zespołów programistycznych ma możliwość testowania wszystkich możliwych kombinacji systemów operacyjnych lub przeglądarek sieci Web (w tym wszystkich zlokalizowanych opcji języka) lub do symulowania dużej liczby użytkowników, którzy mają dostęp do aplikacji w tym samym czasie. W tych okolicznościach nie można sprawdzić, w jaki sposób aplikacja rozproszona będzie reagować na duże woluminy, różne konfiguracje i unikatowe zachowania użytkowników końcowych. Ponadto wiele części aplikacji rozproszonej nie ma interfejsu użytkownika, z którym można korzystać bezpośrednio lub wyświetlać działania tych części.  
  
 Można jednak wyrównać to przez umożliwienie aplikacjom rozproszonym opisywanie pewnych zdarzeń związanych z administratorami systemu, szczególnie niewłaściwymi, przez *instrumentację* aplikacji — czyli przez umieszczenie instrukcji śledzenia w strategicznych lokalizacjach w kodzie. Wtedy, gdy coś nieoczekiwanego występuje w czasie wykonywania (na przykład nadmiernie długi czas odpowiedzi), można określić przyczynę najprawdopodobniej.  
  
 Za pomocą instrukcji śledzenia można uniknąć trudnego zadania sprawdzającego oryginalny kod źródłowy, modyfikacji, ponownej kompilacji i próby wygenerowania błędu czasu wykonywania w środowisku debugowania. Należy pamiętać, że można Instrumentacja aplikacji nie tylko w celu wyświetlenia błędów, ale również do monitorowania wydajności.  
  
## <a name="strategic-placement-of-trace-statements"></a>Strategiczne rozmieszczenie instrukcji Trace  

 Należy zachować szczególną ostrożność podczas umieszczania instrukcji śledzenia do użycia w czasie wykonywania. Należy wziąć pod uwagę, jakie informacje o śledzeniu mogą być potrzebne we wdrożonej aplikacji, tak aby wszystkie możliwe scenariusze śledzenia były odpowiednio omówione. Ze względu na to, że aplikacje korzystające ze śledzenia różnią się od siebie, jednak nie ma ogólnych wytycznych dotyczących strategicznego rozmieszczenia śledzenia. Aby uzyskać więcej informacji na temat umieszczania instrukcji śledzenia, zobacz [How to: Dodawanie instrukcji Trace do kodu aplikacji](how-to-add-trace-statements-to-application-code.md).  
  
## <a name="output-from-tracing"></a>Dane wyjściowe ze śledzenia  

 Dane wyjściowe śledzenia są zbierane przez obiekty nazywane *odbiornikami*. Odbiornik jest obiektem, który odbiera dane wyjściowe śledzenia i zapisuje je na urządzeniu wyjściowym (zazwyczaj okno, dziennik lub plik tekstowy). Gdy odbiornik śledzenia jest tworzony, jest zazwyczaj dodawany do <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> kolekcji, co pozwala odbiornikowi odbierać wszystkie dane wyjściowe śledzenia.  
  
 Informacje o śledzeniu są zawsze zapisywane co najmniej do domyślnego <xref:System.Diagnostics.Trace> docelowego wyjścia, a <xref:System.Diagnostics.DefaultTraceListener> . Jeśli z jakiegoś powodu usunięto <xref:System.Diagnostics.DefaultTraceListener> bez dodawania innych odbiorników do <xref:System.Diagnostics.Trace.Listeners%2A> kolekcji, nie otrzymasz żadnych komunikatów śledzenia. Aby uzyskać więcej informacji, zobacz [detektory śledzenia](trace-listeners.md).  
  
 Sześć <xref:System.Diagnostics.Debug> członków i <xref:System.Diagnostics.Trace> metod, które zapisują informacje o śledzeniu, są wymienione w poniższej tabeli.  
  
|Metoda|Dane wyjściowe|  
|------------|------------|  
|`Assert`|Określony tekst; lub, jeśli nie jest określony, stos wywołań. Dane wyjściowe są zapisywane tylko wtedy, gdy warunek określony jako argument w `Assert` instrukcji ma **wartość false**.|  
|`Fail`|Określony tekst; lub, jeśli nie jest określony, stos wywołań.|  
|`Write`|Określony tekst.|  
|`WriteIf`|Określony tekst, jeśli warunek określony jako argument w `WriteIf` instrukcji jest spełniony.|  
|`WriteLine`|Określony tekst i znak powrotu karetki.|  
|`WriteLineIf`|Określony tekst i znak powrotu karetki, jeśli warunek określony jako argument w `WriteLineIf` instrukcji jest spełniony.|  
  
 Wszystkie odbiorniki w <xref:System.Diagnostics.Trace.Listeners%2A> kolekcji otrzymują komunikaty opisane w powyższej tabeli, ale wykonane akcje mogą się różnić w zależności od tego, jakiego rodzaju odbiornik odbiera komunikat. Na przykład okno <xref:System.Diagnostics.DefaultTraceListener> dialogowe wyświetla potwierdzenie, gdy otrzymuje `Fail` powiadomienie lub nie powiodło się `Assert` , ale <xref:System.Diagnostics.TextWriterTraceListener> po prostu zapisuje dane wyjściowe do strumienia.  
  
 Możesz tworzyć niestandardowe wyniki, implementując własny odbiornik. Niestandardowy odbiornik śledzenia może na przykład wyświetlić komunikaty w oknie komunikatu lub połączyć się z bazą danych w celu dodania komunikatów do tabeli. Wszystkie odbiorniki niestandardowe powinny obsługiwać sześć metod wymienionych powyżej. Aby uzyskać więcej informacji na temat tworzenia detektorów zdefiniowanych przez dewelopera, zobacz sekcję <xref:System.Diagnostics.TraceListener> w temacie .NET Framework Reference.  
  
 `Write`Metody i `WriteLine` zawsze zapisują określony tekst. `Assert`, `WriteIf` i `WriteLineIf` wymagają argumentu logicznego, który kontroluje, czy piszą określony tekst; napisze określony tekst tylko wtedy, gdy wyrażenie ma **wartość true** (dla `WriteIf` i `WriteLineIf` ) lub **false** (dla `Assert` ). `Fail`Metoda zawsze zapisuje określony tekst. Aby uzyskać więcej informacji, zobacz [jak: dodać instrukcje śledzenia do kodu aplikacji](how-to-add-trace-statements-to-application-code.md) i odwołania .NET Framework.  
  
## <a name="security-concerns"></a>Zagadnienia dotyczące zabezpieczeń  

 Jeśli nie wyłączysz śledzenia i debugowania przed wdrożeniem aplikacji ASP.NET, aplikacja może ujawnić informacje o sobie, które mogą zostać wykorzystane przez złośliwy program. Aby uzyskać więcej informacji, zobacz [jak: kompilowanie warunkowo z użyciem śledzenia i debugowania](how-to-compile-conditionally-with-trace-and-debug.md), [kompilowania i kompilowania](/visualstudio/ide/compiling-and-building-in-visual-studio)oraz [instrukcje: Tworzenie, inicjowanie i konfigurowanie przełączników śledzenia](how-to-create-initialize-and-configure-trace-switches.md). Debugowanie można również skonfigurować za poorednictwem Internet Information Services (IIS).  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- [Kontrakty kodu](code-contracts.md)
- [Typy projektów C#, F# i Visual Basic](/visualstudio/debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types)
- [Instrukcje: Dodawanie instrukcji śledzenia do kodu aplikacji](how-to-add-trace-statements-to-application-code.md)
- [Instrukcje: Kompilowanie warunkowe ze śledzeniem i debugowaniem](how-to-compile-conditionally-with-trace-and-debug.md)
- [Instrukcje: Tworzenie, inicjowanie i konfigurowanie przełączników śledzenia](how-to-create-initialize-and-configure-trace-switches.md)
- [Instrukcje: Tworzenie i inicjowanie źródeł śledzenia](how-to-create-and-initialize-trace-sources.md)
- [Instrukcje: Użycie TraceSource i filtrów z obiektami nasłuchującymi śledzenia](how-to-use-tracesource-and-filters-with-trace-listeners.md)
- [Obiekty nasłuchujące śledzenia](trace-listeners.md)
- [Przełączniki śledzenia](trace-switches.md)
