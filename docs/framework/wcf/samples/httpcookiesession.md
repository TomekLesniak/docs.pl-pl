---
title: HttpCookieSession
ms.date: 03/30/2017
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
ms.openlocfilehash: df29ae84537cdb7cea40abcdb848ffbb8bbd6b9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253820"
---
# <a name="httpcookiesession"></a><span data-ttu-id="a3535-102">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="a3535-102">HttpCookieSession</span></span>

<span data-ttu-id="a3535-103">Ten przykład pokazuje, jak utworzyć niestandardowy kanał protokołu, aby używać plików cookie protokołu HTTP do zarządzania sesją.</span><span class="sxs-lookup"><span data-stu-id="a3535-103">This sample demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span> <span data-ttu-id="a3535-104">Ten kanał umożliwia komunikację między usługami Windows Communication Foundation (WCF) i klientami ASMX lub między klientami programu WCF i usługami ASMX.</span><span class="sxs-lookup"><span data-stu-id="a3535-104">This channel enables communication between Windows Communication Foundation (WCF) services and ASMX clients or between WCF clients and ASMX services.</span></span>  
  
 <span data-ttu-id="a3535-105">Gdy klient wywołuje metodę sieci Web w usłudze sieci Web ASMX, która jest oparta na sesji, aparat ASP.NET wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a3535-105">When a client calls a Web method in an ASMX Web service that is session-based, the ASP.NET engine does the following:</span></span>  
  
- <span data-ttu-id="a3535-106">Generuje unikatowy identyfikator (identyfikator sesji).</span><span class="sxs-lookup"><span data-stu-id="a3535-106">Generates a unique ID (session ID).</span></span>  
  
- <span data-ttu-id="a3535-107">Generuje obiekt sesji i kojarzy go z unikatowym IDENTYFIKATORem.</span><span class="sxs-lookup"><span data-stu-id="a3535-107">Generates the session object and associates it with the unique ID.</span></span>  
  
- <span data-ttu-id="a3535-108">Dodaje unikatowy identyfikator do nagłówka odpowiedzi HTTP Set-Cookie i wysyła go do klienta.</span><span class="sxs-lookup"><span data-stu-id="a3535-108">Adds the unique ID to a Set-Cookie HTTP response header and sends it to the client.</span></span>  
  
- <span data-ttu-id="a3535-109">Identyfikuje klienta podczas kolejnych wywołań w oparciu o identyfikator sesji, który wysyła do niego.</span><span class="sxs-lookup"><span data-stu-id="a3535-109">Identifies the client on subsequent calls based on the session ID it sends to it.</span></span>  
  
 <span data-ttu-id="a3535-110">Klient dołącza ten identyfikator sesji do kolejnych żądań do serwera.</span><span class="sxs-lookup"><span data-stu-id="a3535-110">The client includes this session ID in its subsequent requests to the server.</span></span> <span data-ttu-id="a3535-111">Serwer używa identyfikatora sesji z klienta programu w celu załadowania odpowiedniego obiektu sesji dla bieżącego kontekstu HTTP.</span><span class="sxs-lookup"><span data-stu-id="a3535-111">The server uses the session ID from the client to load the appropriate session object for the current HTTP context.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a3535-112">Przykłady mogą być już zainstalowane na komputerze.</span><span class="sxs-lookup"><span data-stu-id="a3535-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a3535-113">Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).</span><span class="sxs-lookup"><span data-stu-id="a3535-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a3535-114">Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady.</span><span class="sxs-lookup"><span data-stu-id="a3535-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a3535-115">Ten przykład znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="a3535-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a><span data-ttu-id="a3535-116">Wzorzec wymiany komunikatów kanału HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="a3535-116">HttpCookieSession Channel Message Exchange Pattern</span></span>  

 <span data-ttu-id="a3535-117">Ten przykład umożliwia korzystanie z sesji dla scenariuszy w przeciwieństwie do ASMX.</span><span class="sxs-lookup"><span data-stu-id="a3535-117">This sample enables sessions for ASMX-like scenarios.</span></span> <span data-ttu-id="a3535-118">W dolnej części stosu kanału korzystamy z transportu HTTP, który obsługuje <xref:System.ServiceModel.Channels.IRequestChannel> i <xref:System.ServiceModel.Channels.IReplyChannel> .</span><span class="sxs-lookup"><span data-stu-id="a3535-118">At the bottom of our channel stack, we have the HTTP transport that supports <xref:System.ServiceModel.Channels.IRequestChannel> and <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span> <span data-ttu-id="a3535-119">Jest to zadanie kanału umożliwiające dostarczenie sesji do wyższych poziomów stosu kanału.</span><span class="sxs-lookup"><span data-stu-id="a3535-119">It is the job of the channel to provide sessions to the higher levels of the channel stack.</span></span> <span data-ttu-id="a3535-120">Przykład implementuje dwa kanały ( <xref:System.ServiceModel.Channels.IRequestSessionChannel> i), <xref:System.ServiceModel.Channels.IReplySessionChannel> które obsługują sesje.</span><span class="sxs-lookup"><span data-stu-id="a3535-120">The sample implements two channels, (<xref:System.ServiceModel.Channels.IRequestSessionChannel> and <xref:System.ServiceModel.Channels.IReplySessionChannel>) that support sessions.</span></span>  
  
## <a name="service-channel"></a><span data-ttu-id="a3535-121">Kanał usługi</span><span class="sxs-lookup"><span data-stu-id="a3535-121">Service Channel</span></span>  

 <span data-ttu-id="a3535-122">Przykład zawiera kanał usługi w `HttpCookieReplySessionChannelListener` klasie.</span><span class="sxs-lookup"><span data-stu-id="a3535-122">The sample provides a service channel in the `HttpCookieReplySessionChannelListener` class.</span></span> <span data-ttu-id="a3535-123">Ta klasa implementuje <xref:System.ServiceModel.Channels.IChannelListener> interfejs i konwertuje <xref:System.ServiceModel.Channels.IReplyChannel> kanał z niższego poziomu w stosie kanału na <xref:System.ServiceModel.Channels.IReplySessionChannel> .</span><span class="sxs-lookup"><span data-stu-id="a3535-123">This class implements the <xref:System.ServiceModel.Channels.IChannelListener> interface and converts the <xref:System.ServiceModel.Channels.IReplyChannel> channel from lower in the channel stack to a <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="a3535-124">Ten proces można podzielić na następujące części:</span><span class="sxs-lookup"><span data-stu-id="a3535-124">This process can be divided into the following parts:</span></span>  
  
- <span data-ttu-id="a3535-125">Gdy odbiornik kanału zostanie otwarty, akceptuje wewnętrzny kanał od jego wewnętrznego odbiornika.</span><span class="sxs-lookup"><span data-stu-id="a3535-125">When the channel listener is opened, it accepts an inner channel from its inner listener.</span></span> <span data-ttu-id="a3535-126">Ponieważ odbiornik wewnętrzny jest odbiornikiem datagramów, a okres istnienia zaakceptowanego kanału jest odłączony od okresu istnienia odbiornika, możemy zamknąć odbiornik wewnętrzny i zawiesić się tylko w kanale wewnętrznym</span><span class="sxs-lookup"><span data-stu-id="a3535-126">Because the inner listener is a datagram listener and the lifetime of an accepted channel is decoupled from the lifetime of the listener, we can close the inner listener and only hold on to the inner channel</span></span>  
  
    ```csharp  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
- <span data-ttu-id="a3535-127">Po zakończeniu procesu otwierania należy skonfigurować pętlę komunikatów, aby odbierać komunikaty z kanału wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="a3535-127">When the open process completes, we set up a message loop to receive messages from the inner channel.</span></span>  
  
    ```csharp  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       this.completeReceiveCallback ??= new WaitCallback(CompleteReceiveCallback);
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
- <span data-ttu-id="a3535-128">Po nadejściu komunikatu kanał usługi bada identyfikator sesji i demultipleksery do odpowiedniego kanału sesji.</span><span class="sxs-lookup"><span data-stu-id="a3535-128">When a message arrives, the service channel examines the session identifier and de-multiplexes to the appropriate session channel.</span></span> <span data-ttu-id="a3535-129">Odbiornik kanału utrzymuje słownik, który mapuje identyfikatory sesji na wystąpienia kanału sesji.</span><span class="sxs-lookup"><span data-stu-id="a3535-129">The channel listener maintains a dictionary that maps the session identifiers to the session channel instances.</span></span>  
  
    ```csharp  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 <span data-ttu-id="a3535-130">`HttpCookieReplySessionChannel`Klasa implementuje <xref:System.ServiceModel.Channels.IReplySessionChannel> .</span><span class="sxs-lookup"><span data-stu-id="a3535-130">The `HttpCookieReplySessionChannel` class implements <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="a3535-131">Wyższe poziomy stosu kanału wywołują <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> metodę odczytu żądania dla tej sesji.</span><span class="sxs-lookup"><span data-stu-id="a3535-131">Higher levels of the channel stack call the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method to read requests for this session.</span></span> <span data-ttu-id="a3535-132">Każdy kanał sesji ma prywatną kolejkę komunikatów wypełnioną przez kanał usługi.</span><span class="sxs-lookup"><span data-stu-id="a3535-132">Each session channel has a private message queue that is populated by the service channel.</span></span>  
  
```csharp  
InputQueue<RequestContext> requestQueue;  
```  
  
 <span data-ttu-id="a3535-133">W przypadku gdy ktoś wywołuje <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> metodę i nie ma żadnych komunikatów w kolejce komunikatów, kanał czeka przez określony czas przed zamknięciem samego siebie.</span><span class="sxs-lookup"><span data-stu-id="a3535-133">In the case when someone calls the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method and there are no messages in the message queue, the channel waits for a specified amount of time before shutting itself down.</span></span> <span data-ttu-id="a3535-134">Spowoduje to wyczyszczenie kanałów sesji utworzonych dla klientów nie korzystających z programu WCF.</span><span class="sxs-lookup"><span data-stu-id="a3535-134">This cleans up the session channels created for non-WCF clients.</span></span>  
  
 <span data-ttu-id="a3535-135">Używamy `channelMapping` do śledzenia `ReplySessionChannels` i nie staramy się, aby nie zamykać ich, dopóki nie zostaną `innerChannel` zamknięte wszystkie zaakceptowane kanały.</span><span class="sxs-lookup"><span data-stu-id="a3535-135">We use the `channelMapping` to track the `ReplySessionChannels`, and we do not close our underlying `innerChannel` until all the accepted channels have been closed.</span></span> <span data-ttu-id="a3535-136">Ten sposób `HttpCookieReplySessionChannel` może występować poza okresem istnienia `HttpCookieReplySessionChannelListener` .</span><span class="sxs-lookup"><span data-stu-id="a3535-136">This way `HttpCookieReplySessionChannel` can exist beyond the lifetime of `HttpCookieReplySessionChannelListener`.</span></span> <span data-ttu-id="a3535-137">Nie trzeba również martwić się o odbiornik odbierający elementy bezużyteczne ze względu na to, że zaakceptowane kanały zachowują odwołanie do odbiornika za pomocą `OnClosed` wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="a3535-137">We also do not have to worry about the listener getting garbage collected underneath us because the accepted channels keep a reference to their listener through the `OnClosed` callback.</span></span>  
  
## <a name="client-channel"></a><span data-ttu-id="a3535-138">Kanał klienta</span><span class="sxs-lookup"><span data-stu-id="a3535-138">Client channel</span></span>  

 <span data-ttu-id="a3535-139">Odpowiedni kanał klienta znajduje się w `HttpCookieSessionChannelFactory` klasie.</span><span class="sxs-lookup"><span data-stu-id="a3535-139">The corresponding client channel is in the `HttpCookieSessionChannelFactory` class.</span></span> <span data-ttu-id="a3535-140">Podczas tworzenia kanału Fabryka kanałów otacza wewnętrzny kanał żądania przez `HttpCookieRequestSessionChannel` .</span><span class="sxs-lookup"><span data-stu-id="a3535-140">During channel creation, the channel factory wraps the inner request channel with an `HttpCookieRequestSessionChannel`.</span></span> <span data-ttu-id="a3535-141">`HttpCookieRequestSessionChannel`Klasa przekazuje wywołania do źródłowego kanału żądania.</span><span class="sxs-lookup"><span data-stu-id="a3535-141">The `HttpCookieRequestSessionChannel` class forwards the calls to the underlying request channel.</span></span> <span data-ttu-id="a3535-142">Gdy klient zamknie serwer proxy, program `HttpCookieRequestSessionChannel` wysyła do usługi komunikat informujący o tym, że kanał jest zamykany.</span><span class="sxs-lookup"><span data-stu-id="a3535-142">When the client closes the proxy, `HttpCookieRequestSessionChannel` sends a message to the service that indicates that the channel is being closed.</span></span> <span data-ttu-id="a3535-143">W rezultacie stos kanału usługi może bezpiecznie zamknąć używany kanał sesji.</span><span class="sxs-lookup"><span data-stu-id="a3535-143">Thus, the service channel stack can gracefully shutdown the session channel that is in use.</span></span>  
  
## <a name="binding-and-binding-element"></a><span data-ttu-id="a3535-144">Powiązanie i element powiązania</span><span class="sxs-lookup"><span data-stu-id="a3535-144">Binding and Binding Element</span></span>  

 <span data-ttu-id="a3535-145">Następnym krokiem po utworzeniu kanałów usługi i klienta jest zintegrowanie ich ze środowiskiem uruchomieniowym WCF.</span><span class="sxs-lookup"><span data-stu-id="a3535-145">After creating the service and client channels, the next step is to integrate them into the WCF runtime.</span></span> <span data-ttu-id="a3535-146">Kanały są dostępne dla usługi WCF poprzez powiązania i elementy powiązania.</span><span class="sxs-lookup"><span data-stu-id="a3535-146">Channels are exposed to WCF through bindings and binding elements.</span></span> <span data-ttu-id="a3535-147">Powiązanie składa się z jednego lub wielu elementów powiązania.</span><span class="sxs-lookup"><span data-stu-id="a3535-147">A binding consists of one or many binding elements.</span></span> <span data-ttu-id="a3535-148">Usługa WCF oferuje kilka powiązań zdefiniowanych przez system; na przykład BasicHttpBinding lub WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="a3535-148">WCF offers several system-defined bindings; for example, BasicHttpBinding or WSHttpBinding.</span></span> <span data-ttu-id="a3535-149">`HttpCookieSessionBindingElement`Klasa zawiera implementację elementu Binding.</span><span class="sxs-lookup"><span data-stu-id="a3535-149">The `HttpCookieSessionBindingElement` class contains the implementation for the binding element.</span></span> <span data-ttu-id="a3535-150">Zastępuje on odbiornik kanału i metody tworzenia fabryki kanałów, aby wykonać niezbędne odbiorniki kanału lub fabryki kanałów.</span><span class="sxs-lookup"><span data-stu-id="a3535-150">It overrides the channel listener and channel factory creation methods to do the necessary channel listener or channel factory instantiations.</span></span>  
  
 <span data-ttu-id="a3535-151">Przykład używa potwierdzeń zasad dla opisu usługi.</span><span class="sxs-lookup"><span data-stu-id="a3535-151">The sample uses policy assertions for the service description.</span></span> <span data-ttu-id="a3535-152">Dzięki temu przykładowi można opublikować wymagania dotyczące kanału dla innych klientów, którzy mogą korzystać z usługi.</span><span class="sxs-lookup"><span data-stu-id="a3535-152">This allows the sample to publish its channel requirements to other clients that can consume the service.</span></span> <span data-ttu-id="a3535-153">Na przykład ten element powiązania publikuje potwierdzenia zasad, aby umożliwić potencjalnym klientom znać, że obsługuje ona sesje.</span><span class="sxs-lookup"><span data-stu-id="a3535-153">For example, this binding element publishes policy assertions to let potential clients know that it supports sessions.</span></span> <span data-ttu-id="a3535-154">Ponieważ przykład włącza `ExchangeTerminateMessage` Właściwość w konfiguracji elementu powiązania, dodaje niezbędne potwierdzenia, aby pokazać, że usługa obsługuje dodatkową akcję wymiany komunikatów, aby zakończyć konwersację sesji.</span><span class="sxs-lookup"><span data-stu-id="a3535-154">Because the sample enables the `ExchangeTerminateMessage` property in the binding element configuration, it adds the necessary assertions to show that the service supports an extra message exchange action to terminate the session conversation.</span></span> <span data-ttu-id="a3535-155">Klienci mogą następnie użyć tej akcji.</span><span class="sxs-lookup"><span data-stu-id="a3535-155">Clients can then use this action.</span></span> <span data-ttu-id="a3535-156">Poniższy kod WSDL przedstawia potwierdzenia zasad utworzone przy użyciu `HttpCookieSessionBindingElement` .</span><span class="sxs-lookup"><span data-stu-id="a3535-156">The following WSDL code shows the policy assertions created from the `HttpCookieSessionBindingElement`.</span></span>  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="a3535-157">`HttpCookieSessionBinding`Klasa to powiązanie dostarczone z systemem, które używa wcześniej opisanego elementu Binding.</span><span class="sxs-lookup"><span data-stu-id="a3535-157">The `HttpCookieSessionBinding` class is a system-provided binding that uses the binding element described previously.</span></span>  
  
## <a name="adding-the-channel-to-the-configuration-system"></a><span data-ttu-id="a3535-158">Dodawanie kanału do systemu konfiguracji</span><span class="sxs-lookup"><span data-stu-id="a3535-158">Adding the Channel to the Configuration System</span></span>  

 <span data-ttu-id="a3535-159">Przykład zawiera dwie klasy, które uwidaczniają przykładowego kanału za pośrednictwem konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a3535-159">The sample provides two classes that expose the sample channel through configuration.</span></span> <span data-ttu-id="a3535-160">Pierwszy to a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> dla `HttpCookieSessionBindingElement` .</span><span class="sxs-lookup"><span data-stu-id="a3535-160">The first is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> for the `HttpCookieSessionBindingElement`.</span></span> <span data-ttu-id="a3535-161">Zbiorcza implementacja jest delegowana do elementu `HttpCookieSessionBindingConfigurationElement` , który pochodzi od <xref:System.ServiceModel.Configuration.StandardBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="a3535-161">The bulk of the implementation is delegated to the `HttpCookieSessionBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="a3535-162">`HttpCookieSessionBindingConfigurationElement`Ma właściwości, które odpowiadają właściwościom `HttpCookieSessionBindingElement` .</span><span class="sxs-lookup"><span data-stu-id="a3535-162">The `HttpCookieSessionBindingConfigurationElement` has properties that correspond to the properties on `HttpCookieSessionBindingElement`.</span></span>  
  
### <a name="binding-element-extension-section"></a><span data-ttu-id="a3535-163">Sekcja rozszerzenia elementu powiązania</span><span class="sxs-lookup"><span data-stu-id="a3535-163">Binding Element Extension Section</span></span>  

 <span data-ttu-id="a3535-164">Sekcja `HttpCookieSessionBindingElementSection` jest <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> udostępniana `HttpCookieSessionBindingElement` systemowi konfiguracyjnemu.</span><span class="sxs-lookup"><span data-stu-id="a3535-164">The section `HttpCookieSessionBindingElementSection` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `HttpCookieSessionBindingElement` to the configuration system.</span></span> <span data-ttu-id="a3535-165">Za pomocą kilku zastąpień Nazwa sekcji konfiguracji, typ elementu powiązania oraz sposób tworzenia elementu powiązania są zdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="a3535-165">With a few overrides the configuration section name, the type of the binding element and how to create the binding element are defined.</span></span> <span data-ttu-id="a3535-166">Następnie możemy zarejestrować sekcję rozszerzenia w pliku konfiguracji w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="a3535-166">We can then register the extension section in a configuration file as follows:</span></span>  
  
```xml  
<configuration>
    <system.serviceModel>
      <extensions>
        <bindingElementExtensions>
          <add name="httpCookieSession"
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,
                    HttpCookieSessionExtension, Version=1.0.0.0,
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>
    </system.serviceModel>
</configuration>  
```  
  
## <a name="test-code"></a><span data-ttu-id="a3535-167">Kod testu</span><span class="sxs-lookup"><span data-stu-id="a3535-167">Test Code</span></span>  

 <span data-ttu-id="a3535-168">Kod testowy służący do korzystania z tego przykładowego transportu jest dostępny w katalogach klienta i usług.</span><span class="sxs-lookup"><span data-stu-id="a3535-168">Test code for using this sample transport is available in the Client and Service directories.</span></span> <span data-ttu-id="a3535-169">Składa się z dwóch testów — jeden test używa powiązania z `allowCookies` ustawionym `true` na klienta.</span><span class="sxs-lookup"><span data-stu-id="a3535-169">It consists of two tests—one test uses a binding with `allowCookies` set to `true` on the client.</span></span> <span data-ttu-id="a3535-170">Drugi test umożliwia jawne zamknięcie (przy użyciu wymiany komunikatów zakończenia) dla powiązania.</span><span class="sxs-lookup"><span data-stu-id="a3535-170">The second test enables explicit shutdown (using the terminate message exchange) on the binding.</span></span>  
  
 <span data-ttu-id="a3535-171">Po uruchomieniu przykładu powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="a3535-171">When you run the sample, you should see the following output:</span></span>  
  
```console  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a3535-172">Aby skonfigurować, skompilować i uruchomić przykład</span><span class="sxs-lookup"><span data-stu-id="a3535-172">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a3535-173">Zainstaluj ASP.NET 4,0 przy użyciu następującego polecenia.</span><span class="sxs-lookup"><span data-stu-id="a3535-173">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="a3535-174">Upewnij się, że została wykonana [Procedura konfiguracji jednorazowej dla przykładów Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3535-174">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="a3535-175">Aby skompilować rozwiązanie, postępuj zgodnie z instrukcjami w temacie [Tworzenie przykładów Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3535-175">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="a3535-176">Aby uruchomić przykład w konfiguracji na jednym lub wielu komputerach, postępuj zgodnie z instrukcjami w temacie [Uruchamianie przykładów Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3535-176">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
