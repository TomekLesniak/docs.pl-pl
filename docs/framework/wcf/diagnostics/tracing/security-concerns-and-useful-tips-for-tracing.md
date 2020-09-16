---
title: Problemy dotyczące zabezpieczeń i przydatne porady na temat śledzenia
ms.date: 03/30/2017
ms.assetid: 88bc2880-ecb9-47cd-9816-39016a07076f
ms.openlocfilehash: 91a1b4bab3ac47f41821ad69228310c3993cf037
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555045"
---
# <a name="security-concerns-and-useful-tips-for-tracing"></a><span data-ttu-id="bce73-102">Problemy dotyczące zabezpieczeń i przydatne porady na temat śledzenia</span><span class="sxs-lookup"><span data-stu-id="bce73-102">Security Concerns and Useful Tips for Tracing</span></span>
<span data-ttu-id="bce73-103">W tym temacie opisano, jak można chronić poufne informacje przed ujawnieniem, a także przydatne porady dotyczące korzystania z programu WebHost.</span><span class="sxs-lookup"><span data-stu-id="bce73-103">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
## <a name="using-a-custom-trace-listener-with-webhost"></a><span data-ttu-id="bce73-104">Korzystanie z niestandardowego odbiornika śledzenia z elementem WebHost</span><span class="sxs-lookup"><span data-stu-id="bce73-104">Using a Custom Trace Listener with WebHost</span></span>  
 <span data-ttu-id="bce73-105">Jeśli piszesz własny odbiornik śledzenia, należy mieć świadomość, że ślady mogą zostać utracone w przypadku usługi hostowanej w sieci Web.</span><span class="sxs-lookup"><span data-stu-id="bce73-105">If you are writing your own trace listener, you should be aware of the possibility that traces might be lost in the case of a Web-hosted service.</span></span> <span data-ttu-id="bce73-106">Podczas odtwarzania programu WebHost zamykany jest proces na żywo, podczas gdy duplikat jest przełączany.</span><span class="sxs-lookup"><span data-stu-id="bce73-106">When WebHost recycles, it shuts down the live process while a duplicate takes over.</span></span> <span data-ttu-id="bce73-107">Jednak te dwa procesy muszą nadal mieć dostęp do tego samego zasobu przez jakiś czas, który jest zależny od typu odbiornika.</span><span class="sxs-lookup"><span data-stu-id="bce73-107">However, the two processes must still have access to the same resource for some time, which is dependent on the listener type.</span></span> <span data-ttu-id="bce73-108">W takim przypadku program `XmlWriterTraceListener` tworzy nowy plik śledzenia dla drugiego procesu; podczas gdy śledzenie zdarzeń systemu Windows zarządza wieloma procesami w ramach tej samej sesji i zapewnia dostęp do tego samego pliku.</span><span class="sxs-lookup"><span data-stu-id="bce73-108">In this case, , `XmlWriterTraceListener` creates a new trace file for the second process; while Windows event tracing manages multiple processes within the same session and gives access to the same file.</span></span> <span data-ttu-id="bce73-109">Jeśli własny odbiornik nie oferuje podobnych funkcji, ślady mogą zostać utracone, gdy plik zostanie zablokowany przez dwa procesy.</span><span class="sxs-lookup"><span data-stu-id="bce73-109">If your own listener does not provide similar functionalities, traces can be lost when the file is locked up by the two processes.</span></span>  
  
 <span data-ttu-id="bce73-110">Należy również pamiętać, że niestandardowy odbiornik śledzenia może wysyłać ślady i wiadomości w sieci, na przykład do zdalnej bazy danych.</span><span class="sxs-lookup"><span data-stu-id="bce73-110">You should also be aware that a custom trace listener can send traces and messages on the wire, for example, to a remote database.</span></span> <span data-ttu-id="bce73-111">Jako narzędzie do wdrażania aplikacji należy skonfigurować odbiorniki niestandardowe z odpowiednią kontrolą dostępu.</span><span class="sxs-lookup"><span data-stu-id="bce73-111">As an application deployer, you should configure custom listeners with appropriate access control.</span></span> <span data-ttu-id="bce73-112">Należy również zastosować kontrolę zabezpieczeń na wszystkich danych osobowych, które mogą być ujawnione w lokalizacji zdalnej.</span><span class="sxs-lookup"><span data-stu-id="bce73-112">You should also apply security control on any personal information that can be exposed at the remote location.</span></span>  
  
## <a name="logging-sensitive-information"></a><span data-ttu-id="bce73-113">Rejestrowanie poufnych informacji</span><span class="sxs-lookup"><span data-stu-id="bce73-113">Logging Sensitive Information</span></span>  
 <span data-ttu-id="bce73-114">Ślady zawierają nagłówki wiadomości, gdy komunikat jest w zakresie.</span><span class="sxs-lookup"><span data-stu-id="bce73-114">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="bce73-115">Gdy śledzenie jest włączone, dane osobowe w nagłówkach specyficznych dla aplikacji, takie jak, ciąg zapytania; i informacje o treści, takie jak numer karty kredytowej, mogą stać się widoczne w dziennikach.</span><span class="sxs-lookup"><span data-stu-id="bce73-115">When tracing is enabled, personal information in application-specific headers, such as, a query string; and body information, such as, a credit card number, can become visible in the logs.</span></span> <span data-ttu-id="bce73-116">Narzędzie wdrażania aplikacji jest odpowiedzialne za wymuszanie kontroli dostępu do plików konfiguracji i śledzenia.</span><span class="sxs-lookup"><span data-stu-id="bce73-116">The application deployer is responsible for enforcing access control on the configuration and trace files.</span></span> <span data-ttu-id="bce73-117">Jeśli nie chcesz, aby ten rodzaj informacji był widoczny, należy wyłączyć śledzenie lub odfiltrować część danych, jeśli chcesz udostępnić dzienniki śledzenia.</span><span class="sxs-lookup"><span data-stu-id="bce73-117">If you do not want this kind of information to be visible, you should disable tracing, or filter out part of the data if you want to share the trace logs.</span></span>  
  
 <span data-ttu-id="bce73-118">Poniższe porady mogą pomóc zapobiec przypadkowemu ujawnieniu zawartości pliku śledzenia:</span><span class="sxs-lookup"><span data-stu-id="bce73-118">The following tips can help you to prevent the content of a trace file from being exposed unintentionally:</span></span>  
  
- <span data-ttu-id="bce73-119">Upewnij się, że pliki dziennika są chronione za pomocą list Access Control (ACL) zarówno w scenariuszach WebHost, jak i z dowolnego hosta.</span><span class="sxs-lookup"><span data-stu-id="bce73-119">Ensure that the log files are protected by Access Control Lists (ACL) both in WebHost and self-host scenarios.</span></span>  
  
- <span data-ttu-id="bce73-120">Wybierz rozszerzenie pliku, którego nie można łatwo obsłużyć przy użyciu żądania sieci Web.</span><span class="sxs-lookup"><span data-stu-id="bce73-120">Choose a file extension that cannot be easily served using a Web request.</span></span> <span data-ttu-id="bce73-121">Na przykład rozszerzenie pliku XML nie jest bezpiecznym wyborem.</span><span class="sxs-lookup"><span data-stu-id="bce73-121">For example, the .xml file extension is not a safe choice.</span></span> <span data-ttu-id="bce73-122">Aby wyświetlić listę rozszerzeń, które mogą być obsługiwane, można sprawdzić Przewodnik administrowania usługami IIS.</span><span class="sxs-lookup"><span data-stu-id="bce73-122">You can check the IIS administration guide to see a list of extensions that can be served.</span></span>  
  
- <span data-ttu-id="bce73-123">Określ ścieżkę bezwzględną dla lokalizacji pliku dziennika, która powinna znajdować się poza katalogiem publicznym programu WebHost, aby uniemożliwić dostęp do niego przez zewnętrzną stronę przy użyciu przeglądarki sieci Web.</span><span class="sxs-lookup"><span data-stu-id="bce73-123">Specify an absolute path for the log file location, which should be outside of the WebHost vroot public directory to prevent it from being accessed by an external party using a Web browser.</span></span>  
  
 <span data-ttu-id="bce73-124">Domyślnie klucze i dane osobowe, takie jak nazwa użytkownika i hasło, nie są rejestrowane w śladach i zarejestrowanych komunikatach.</span><span class="sxs-lookup"><span data-stu-id="bce73-124">By default, keys and personally identifiable information (PII) such as username and password are not logged in traces and logged messages.</span></span> <span data-ttu-id="bce73-125">Administrator komputera może jednak użyć `enableLoggingKnownPII` atrybutu w `machineSettings` elemencie Machine.config pliku, aby zezwolić aplikacjom działającym na maszynie na rejestrowanie znanych danych osobowych (dane osobowe) w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="bce73-125">A machine administrator, however, can use the `enableLoggingKnownPII` attribute in the `machineSettings` element of the Machine.config file to permit applications running on the machine to log known personally identifiable information (PII) as follows:</span></span>  
  
```xml  
<configuration>  
   <system.ServiceModel>  
      <machineSettings enableLoggingKnownPii="Boolean"/>  
   </system.ServiceModel>  
</configuration>
```  
  
 <span data-ttu-id="bce73-126">Narzędzie do wdrażania aplikacji może następnie użyć `logKnownPii` atrybutu w pliku App.config lub Web.config, aby umożliwić logowanie do użytku osobowego w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="bce73-126">An application deployer can then use the `logKnownPii` attribute in either the App.config or Web.config file to enable PII logging as follows:</span></span>  
  
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
  
 <span data-ttu-id="bce73-127">Tylko wtedy, gdy oba ustawienia są włączone do rejestrowania przez dane `true` osobowe.</span><span class="sxs-lookup"><span data-stu-id="bce73-127">Only when both settings are `true` is PII logging enabled.</span></span> <span data-ttu-id="bce73-128">Kombinacja dwóch przełączników pozwala elastycznie rejestrować znane dane OSOBowe dla każdej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bce73-128">The combination of two switches allows the flexibility to log known PII for each application.</span></span>  
  
 <span data-ttu-id="bce73-129">Należy pamiętać, że w przypadku określenia co najmniej dwóch źródeł niestandardowych w pliku konfiguracyjnym odczytywane są tylko atrybuty pierwszego źródła.</span><span class="sxs-lookup"><span data-stu-id="bce73-129">You should be aware that if you specify two or more custom sources in a configuration file, only the attributes of the first source are read.</span></span> <span data-ttu-id="bce73-130">Pozostałe są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="bce73-130">The others are ignored.</span></span> <span data-ttu-id="bce73-131">Oznacza to, że w przypadku następujących App.config plik, dane OSOBowe nie są rejestrowane dla obu źródeł, mimo że rejestrowanie danych osobowych jest jawnie włączone dla drugiego źródła.</span><span class="sxs-lookup"><span data-stu-id="bce73-131">This means that, for the following App.config, file, PII is not logged for both sources even though PII logging is explicitly enabled for the second source.</span></span>  
  
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
            <add name="xml" />  
         </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="bce73-132">Jeśli `<machineSettings enableLoggingKnownPii="Boolean"/>` element istnieje poza plikiem Machine.config, system zgłasza <xref:System.Configuration.ConfigurationErrorsException> .</span><span class="sxs-lookup"><span data-stu-id="bce73-132">If the `<machineSettings enableLoggingKnownPii="Boolean"/>` element exists outside the Machine.config file, the system throws a <xref:System.Configuration.ConfigurationErrorsException>.</span></span>  
  
 <span data-ttu-id="bce73-133">Zmiany są skuteczne tylko wtedy, gdy aplikacja jest uruchamiana lub uruchamiana ponownie.</span><span class="sxs-lookup"><span data-stu-id="bce73-133">The changes are effective only when the application starts or restarts.</span></span> <span data-ttu-id="bce73-134">Zdarzenie jest rejestrowane przy uruchamianiu, gdy oba atrybuty są ustawione na `true` .</span><span class="sxs-lookup"><span data-stu-id="bce73-134">An event is logged at startup when both attributes are set to `true`.</span></span> <span data-ttu-id="bce73-135">Zdarzenie jest rejestrowane również wtedy, gdy `logKnownPii` jest ustawione na, `true` ale `enableLoggingKnownPii` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="bce73-135">An event is also logged if `logKnownPii` is set to `true` but `enableLoggingKnownPii` is `false`.</span></span>  
  
 <span data-ttu-id="bce73-136">Aby uzyskać więcej informacji na temat rejestrowania danych osobowych, zobacz przykład [blokady zabezpieczeń danych osobowych](../../samples/pii-security-lockdown.md) .</span><span class="sxs-lookup"><span data-stu-id="bce73-136">For more information on PII logging, see [PII Security Lockdown](../../samples/pii-security-lockdown.md) sample.</span></span>  
  
 <span data-ttu-id="bce73-137">W przypadku korzystania z tych dwóch przełączników administrator komputera i narzędzie wdrażania aplikacji powinny mieć wyjątkową ostrożność.</span><span class="sxs-lookup"><span data-stu-id="bce73-137">The machine administrator and application deployer should exercise extreme caution when using these two switches.</span></span> <span data-ttu-id="bce73-138">W przypadku włączenia rejestrowania przez dane OSOBowe są rejestrowane klucze zabezpieczeń i dane OSOBowe.</span><span class="sxs-lookup"><span data-stu-id="bce73-138">If PII logging is enabled, security keys and PII are logged.</span></span> <span data-ttu-id="bce73-139">Jeśli jest wyłączona, poufne i specyficzne dla aplikacji dane są nadal rejestrowane w nagłówkach i treściach komunikatów.</span><span class="sxs-lookup"><span data-stu-id="bce73-139">If it is disabled, sensitive and application-specific data is still logged in message headers and bodies.</span></span> <span data-ttu-id="bce73-140">Aby uzyskać bardziej szczegółowe omówienie ochrony prywatności i ochrony danych osobowych przed ujawnieniem, zobacz [prywatność użytkowników](/previous-versions/dotnet/articles/aa480490(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="bce73-140">For a more thorough discussion on privacy and protecting PII from being exposed, see [User Privacy](/previous-versions/dotnet/articles/aa480490(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="bce73-141">Ponadto adres IP nadawcy wiadomości jest rejestrowany raz dla połączenia dla transportów zorientowanych na połączenia, a raz na komunikat wysyłany w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="bce73-141">In addition, the IP address of the message sender is logged once per connection for connection-oriented transports, and once per message sent otherwise.</span></span> <span data-ttu-id="bce73-142">Jest to wykonywane bez zgody nadawcy.</span><span class="sxs-lookup"><span data-stu-id="bce73-142">This is done without the consent of the sender.</span></span> <span data-ttu-id="bce73-143">Jednak rejestrowanie odbywa się tylko na poziomach śledzenia informacji lub szczegółowości, które nie są domyślnymi lub zalecanymi poziomami śledzenia w środowisku produkcyjnym, z wyjątkiem debugowania na żywo.</span><span class="sxs-lookup"><span data-stu-id="bce73-143">However, this logging only occurs at the Information or Verbose tracing levels, which are not the default or recommended tracing levels in production, except for live debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce73-144">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="bce73-144">See also</span></span>

- [<span data-ttu-id="bce73-145">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="bce73-145">Tracing</span></span>](index.md)
