---
title: 'Instrukcje: Migrowanie zarządzanego kodu DCOM do WCF'
description: Migrowanie wywołań kodu zarządzanego Component Object Model (DCOM) między serwerami i klientami programu do Windows Communication Foundation (WCF).
ms.date: 03/30/2017
ms.assetid: 52961ffc-d1c7-4f83-832c-786444b951ba
ms.openlocfilehash: eb84b8071d8dec5d3e70a2f1903f84ee64c31b08
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274845"
---
# <a name="how-to-migrate-managed-code-dcom-to-wcf"></a>Instrukcje: Migrowanie zarządzanego kodu DCOM do WCF

Windows Communication Foundation (WCF) to zalecany i bezpieczny wybór dla rozproszonych Component Object Model (DCOM) dla wywołań kodu zarządzanego między serwerami i klientami w środowisku rozproszonym. W tym artykule przedstawiono sposób migrowania kodu z modelu DCOM do usługi WCF w następujących scenariuszach.  
  
- Usługa zdalna zwraca obiekt przez wartość do klienta  
  
- Klient wysyła obiekt według wartości do usługi zdalnej.  
  
- Usługa zdalna zwraca obiekt przez odwołanie do klienta  
  
 Ze względów bezpieczeństwa wysyłanie obiektu przez odwołanie z klienta do usługi nie jest dozwolone w programie WCF. Scenariusz, który wymaga konwersacji między klientem a serwerem można osiągnąć w programie WCF przy użyciu usługi dupleksowej.  Aby uzyskać więcej informacji na temat usług dupleksowych, zobacz [usługi dupleksowe](../wcf/feature-details/duplex-services.md).  
  
 Aby uzyskać więcej informacji na temat tworzenia usług i klientów programu WCF dla tych usług, zobacz [podstawowe programowanie WCF](../wcf/basic-wcf-programming.md), [projektowanie i implementowanie usług](../wcf/designing-and-implementing-services.md)oraz [Kompilowanie klientów](../wcf/building-clients.md).  
  
## <a name="dcom-example-code"></a>Przykładowy kod DCOM  

 W tych scenariuszach interfejsy DCOM, które są zilustrowane przy użyciu programu WCF, mają następującą strukturę:  
  
```csharp  
[ComVisible(true)]  
[Guid("AA9C4CDB-55EA-4413-90D2-843F1A49E6E6")]  
public interface IRemoteService  
{  
   Customer GetObjectByValue();  
   IRemoteObject GetObjectByReference();  
   void SendObjectByValue(Customer customer);  
}  
  
[ComVisible(true)]  
[Guid("A12C98DE-B6A1-463D-8C24-81E4BBC4351B")]  
public interface IRemoteObject  
{  
}  
  
public class Customer  
{  
}  
```  
  
## <a name="the-service-returns-an-object-by-value"></a>Usługa zwraca obiekt według wartości  

 W tym scenariuszu należy wykonać wywołanie do usługi i Metoda ta zwraca obiekt, który jest przesyłany przez wartość z serwera do klienta. Ten scenariusz reprezentuje następujące wywołanie COM:  
  
```csharp  
public interface IRemoteService  
{  
    Customer GetObjectByValue();  
}  
```  
  
 W tym scenariuszu klient otrzymuje deserializowaną kopię obiektu z usługi zdalnej. Klient może korzystać z tej kopii lokalnej bez wywołania zwrotnego do usługi.  Innymi słowy klient ma gwarancję, że usługa nie będzie uczestniczyć w żaden sposób w przypadku wywołania metod w kopii lokalnej. Program WCF zawsze zwraca obiekty z usługi według wartości, dlatego w poniższych krokach opisano tworzenie zwykłej usługi WCF.  
  
### <a name="step-1-define-the-wcf-service-interface"></a>Krok 1. Definiowanie interfejsu usługi WCF  

 Zdefiniuj publiczny interfejs dla usługi WCF i oznacz go <xref:System.ServiceModel.ServiceContractAttribute> atrybutem [].  Oznacz metody, które chcesz uwidocznić klientom z <xref:System.ServiceModel.OperationContractAttribute> atrybutem []. Poniższy przykład pokazuje, jak używać tych atrybutów do identyfikowania interfejsów po stronie serwera i metod interfejsu, które klient może wywoływać. Metoda użyta w tym scenariuszu jest pogrubienie.  
  
```csharp  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Web;
. . .  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]  
    void StoreCustomer(Customer customer);  
  
    [OperationContract]     Customer GetCustomer(string firstName, string lastName);
  
}  
```  
  
### <a name="step-2-define-the-data-contract"></a>Krok 2. Definiowanie kontraktu danych  

 Następnie należy utworzyć kontrakt danych dla usługi, która będzie opisywać, w jaki sposób dane będą wymieniane między usługą i jej klientami.  Klasy opisane w kontrakcie danych powinny być oznaczone <xref:System.Runtime.Serialization.DataContractAttribute> atrybutem []. Poszczególne właściwości lub pola, które mają być widoczne zarówno dla klienta, jak i serwera, powinny być oznaczone <xref:System.Runtime.Serialization.DataMemberAttribute> atrybutem []. Jeśli chcesz, aby typy pochodne od klasy w kontrakcie danych były dozwolone, należy je zidentyfikować przy użyciu <xref:System.Runtime.Serialization.KnownTypeAttribute> atrybutu []. Funkcja WCF będzie serializować lub deserializować typy w interfejsie usługi i typach identyfikowanych jako znane typy. Jeśli spróbujesz użyć typu, który nie jest typem znanym, wystąpi wyjątek.  
  
 Aby uzyskać więcej informacji na temat umów dotyczących danych, zobacz [Kontrakty danych](../wcf/samples/data-contracts.md).  
  
```csharp  
[DataContract]  
[KnownType(typeof(PremiumCustomer))]  
public class Customer  
{  
    [DataMember]  
    public string Firstname;  
    [DataMember]  
    public string Lastname;  
    [DataMember]  
    public Address DefaultDeliveryAddress;  
    [DataMember]  
    public Address DefaultBillingAddress;  
}  
 [DataContract]  
public class PremiumCustomer : Customer  
{  
    [DataMember]  
    public int AccountID;  
}  
  
 [DataContract]  
public class Address  
{  
    [DataMember]  
    public string Street;  
    [DataMember]  
    public string Zipcode;  
    [DataMember]  
    public string City;  
    [DataMember]  
    public string State;  
    [DataMember]  
    public string Country;  
}  
```  
  
### <a name="step-3-implement-the-wcf-service"></a>Krok 3. Implementowanie usługi WCF  

 Następnie należy zaimplementować klasę usługi WCF implementującą interfejs zdefiniowany w poprzednim kroku.  
  
```csharp  
public class CustomerService: ICustomerManager
{  
    public void StoreCustomer(Customer customer)  
    {  
        // write to a database  
    }  
    public Customer GetCustomer(string firstName, string lastName)  
    {  
        // read from a database  
    }  
}  
```  
  
### <a name="step-4-configure-the-service-and-the-client"></a>Krok 4. Konfigurowanie usługi i klienta  

 Aby uruchomić usługę WCF, należy zadeklarować punkt końcowy, który uwidacznia ten interfejs usługi w określonym adresie URL przy użyciu określonego powiązania WCF. Powiązanie określa informacje o transportach, kodowaniu i protokole dla klientów i serwera do komunikacji. Zazwyczaj można dodawać powiązania do pliku konfiguracji projektu usługi (web.config). Poniżej przedstawiono wpis powiązania dla przykładowej usługi:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Server.CustomerService">  
        <endpoint address="http://localhost:8083/CustomerManager"
                  binding="basicHttpBinding"  
                  contract="Shared.ICustomerManager" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 Następnie należy skonfigurować klienta tak, aby pasował do informacji o powiązaniu określonych przez usługę. Aby to zrobić, Dodaj następujący plik do pliku konfiguracji aplikacji klienta (app.config).  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="customermanager"
                address="http://localhost:8083/CustomerManager"
                binding="basicHttpBinding"
                contract="Shared.ICustomerManager"/>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="step-5-run-the-service"></a>Krok 5. uruchomienie usługi  

 Na koniec możesz go hostować w aplikacji konsolowej, dodając następujące wiersze do aplikacji usługi i uruchamiając aplikację. Aby uzyskać więcej informacji na temat innych sposobów hostowania aplikacji usługi WCF, [usług hostingowych](../wcf/hosting-services.md).  
  
```csharp  
ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
customerServiceHost.Open();  
```  
  
### <a name="step-6-call-the-service-from-the-client"></a>Krok 6. Wywoływanie usługi z klienta  

 Aby wywołać usługę od klienta, należy utworzyć fabrykę kanałów dla usługi i zażądać kanału, co umożliwi bezpośrednie wywoływanie `GetCustomer` metody bezpośrednio od klienta. Kanał implementuje interfejs usługi i obsługuje podstawową logikę żądania/odpowiedzi.  Wartością zwracaną z tego wywołania metody jest deserializowana kopia odpowiedzi usługi.  
  
```csharp  
ChannelFactory<ICustomerManager> factory =
     new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager service = factory.CreateChannel();  
Customer customer = service.GetCustomer("Mary", "Smith");  
```  
  
## <a name="the-client-sends-a-by-value-object-to-the-server"></a>Klient wysyła do serwera obiekt przez wartość  

 W tym scenariuszu klient wysyła do serwera obiekt, według wartości. Oznacza to, że serwer otrzyma deserializowaną kopię obiektu.  Serwer może wywoływać metody w tej kopii i zagwarantować, że nie ma wywołania zwrotnego w kodzie klienta. Jak wspomniano wcześniej, normalne wymiany danych WCF są według wartości.  Gwarantuje to, że wywoływanie metod na jednym z tych obiektów jest wykonywane tylko lokalnie — nie wywoła kodu na kliencie.  
  
 Ten scenariusz reprezentuje następujące wywołanie metody COM:  
  
```csharp  
public interface IRemoteService  
{  
    void SendObjectByValue(Customer customer);  
}  
```  
  
 Ten scenariusz używa tego samego interfejsu usługi i kontraktu danych, jak pokazano w pierwszym przykładzie. Ponadto klient i usługa zostaną skonfigurowane w taki sam sposób. W tym przykładzie tworzony jest kanał służący do wysyłania obiektu i uruchamiania w ten sam sposób. Jednak w tym przykładzie utworzysz klienta, który wywoła usługę, przekazując obiekt według wartości. Metoda usługi, która będzie wywoływana przez klienta w kontrakcie usługi, jest pogrubienie:  
  
```csharp  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]     void StoreCustomer(Customer customer);  
  
    [OperationContract]  
    Customer GetCustomer(string firstName, string lastName);  
}  
```  
  
### <a name="add-code-to-the-client-that-sends-a-by-value-object"></a>Dodawanie kodu do klienta wysyłającego obiekt przez wartość  

 Poniższy kod pokazuje, jak klient tworzy nowy obiekt klienta według wartości, tworzy kanał do komunikowania się z `ICustomerManager` usługą i wysyła do niego obiekt klienta.  
  
 Obiekt klienta zostanie Zserializowany i wysłany do usługi, w którym zostanie odszeregowany przez usługę w nowej kopii tego obiektu.  Wszystkie metody wywołania usługi na tym obiekcie będą wykonywane tylko lokalnie na serwerze. Należy pamiętać, że ten kod ilustruje wysyłanie typu pochodnego ( `PremiumCustomer` ).  Kontrakt usługi oczekuje `Customer` obiektu, ale kontrakt danych usługi używa <xref:System.Runtime.Serialization.KnownTypeAttribute> atrybutu [], aby wskazać, że `PremiumCustomer` jest również dozwolone.  Funkcja WCF nie będzie podejmować próby serializacji lub deserializacji dowolnego innego typu za pośrednictwem tego interfejsu usługi.  
  
```csharp  
PremiumCustomer customer = new PremiumCustomer();  
customer.Firstname = "John";  
customer.Lastname = "Doe";  
customer.DefaultBillingAddress = new Address();  
customer.DefaultBillingAddress.Street = "One Microsoft Way";  
customer.DefaultDeliveryAddress = customer.DefaultBillingAddress;  
customer.AccountID = 42;  
  
ChannelFactory<ICustomerManager> factory =  
   new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager customerManager = factory.CreateChannel();  
customerManager.StoreCustomer(customer);  
```  
  
## <a name="the-service-returns-an-object-by-reference"></a>Usługa zwraca obiekt przez odwołanie  

 W tym scenariuszu aplikacja kliencka wysyła wywołanie do usługi zdalnej, a metoda zwraca obiekt, który jest przesyłany przez odwołanie z usługi do klienta.  
  
 Jak wspomniano wcześniej, usługi WCF zawsze zwracają obiekt według wartości.  Można jednak osiągnąć podobny wynik przy użyciu <xref:System.ServiceModel.EndpointAddress10> klasy.  <xref:System.ServiceModel.EndpointAddress10>Jest obiektem możliwym do serializacji przez wartość, który może być używany przez klienta w celu uzyskania na serwerze sesji na podstawie obiektu referencyjnego.  
  
 Zachowanie obiektu przez odwołanie w programie WCF przedstawionym w tym scenariuszu różni się od modelu DCOM.  W modelu DCOM serwer może bezpośrednio zwrócić do klienta obiekt przez odwołanie, a klient może wywołać metody tego obiektu, które są wykonywane na serwerze.  W programie WCF jednak zwracany obiekt jest zawsze przez wartość.  Klient musi wykonać ten obiekt przez wartość, reprezentowany przez i za jego <xref:System.ServiceModel.EndpointAddress10> pomocą, aby utworzyć własny obiekt sesji.  Metoda kliencka wywołuje na serwerze. Innymi słowy, ten obiekt odwołujący się do programu WCF to normalna usługa WCF, która jest skonfigurowana do sesji.  
  
 W programie WCF sesja jest sposobem skorelowania wielu wiadomości przesyłanych między dwoma punktami końcowymi.  Oznacza to, że gdy klient uzyska połączenie z tą usługą, zostanie ustanowiona sesja między klientem a serwerem.  Klient będzie używać jednego unikatowego wystąpienia obiektu po stronie serwera dla wszystkich jego interakcji w ramach jednej sesji. Umowy WCF dotyczące sesji są podobne do wzorców żądań i odpowiedzi sieciowych zorientowanych na połączenia.  
  
 Ten scenariusz jest reprezentowany przez poniższą metodę DCOM.  
  
```csharp  
public interface IRemoteService  
{  
    IRemoteObject GetObjectByReference();  
}  
```  
  
### <a name="step-1-define-the-sessionful-wcf-service-interface-and-implementation"></a>Krok 1. Definiowanie sesji interfejsu i implementacji usługi WCF  

 Najpierw Zdefiniuj interfejs usługi WCF, który zawiera obiekt session.  
  
 W tym kodzie obiekt sesji jest oznaczony `ServiceContract` atrybutem, który identyfikuje go jako zwykły interfejs usługi WCF.  Ponadto <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> Właściwość jest ustawiona na wartość wskazującą, że będzie ona sesją usługi.  
  
```csharp  
[ServiceContract(SessionMode = SessionMode.Allowed)]  
public interface ISessionBoundObject  
{  
    [OperationContract]  
    string GetCurrentValue();  
  
    [OperationContract]  
    void SetCurrentValue(string value);  
}  
```  
  
 Poniższy kod przedstawia implementację usługi.  
  
 Usługa jest oznaczona atrybutem [ServiceBehavior], a jej Właściwość InstanceContextmode ma wartość InstanceContextmode. PerSessions, aby wskazać, że dla każdej sesji należy utworzyć unikatowe wystąpienie tego typu.  
  
```csharp  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
    public class MySessionBoundObject : ISessionBoundObject  
    {  
        private string _value;  
  
        public string GetCurrentValue()  
        {  
            return _value;  
        }  
  
        public void SetCurrentValue(string val)  
        {  
            _value = val;  
        }  
  
    }  
```  
  
### <a name="step-2-define-the-wcf-factory-service-for-the-sessionful-object"></a>Krok 2. Definiowanie usługi fabryki WCF dla obiektu sesji  

 Usługa, która tworzy obiekt sesji, musi być zdefiniowana i zaimplementowana. Poniższy kod pokazuje, jak to zrobić. Ten kod tworzy kolejną usługę WCF, która zwraca <xref:System.ServiceModel.EndpointAddress10> obiekt.  Jest to możliwy do serializacji formularz punktu końcowego, którego można użyć do utworzenia obiektu z pełnymi sesjami.  
  
```csharp  
[ServiceContract]  
    public interface ISessionBoundFactory  
    {  
        [OperationContract]  
        EndpointAddress10 GetInstanceAddress();  
    }  
```  
  
 Poniżej przedstawiono implementację tej usługi. Ta implementacja obsługuje pojedyncze fabryki kanałów do tworzenia obiektów sesji.  Gdy `GetInstanceAddress` jest wywoływana, tworzy kanał i tworzy <xref:System.ServiceModel.EndpointAddress10> obiekt, który wskazuje na adres zdalny skojarzony z tym kanałem.   <xref:System.ServiceModel.EndpointAddress10> jest typem danych, który może być zwracany do klienta przez wartość.
  
```csharp  
public class SessionBoundFactory : ISessionBoundFactory  
    {  
        public static ChannelFactory<ISessionBoundObject> _factory =
            new ChannelFactory<ISessionBoundObject>("sessionbound");  
  
        public SessionBoundFactory()  
        {  
        }  
  
        public EndpointAddress10 GetInstanceAddress()  
        {  
            IClientChannel channel = (IClientChannel)_factory.CreateChannel();  
            return EndpointAddress10.FromEndpointAddress(channel.RemoteAddress);  
        }  
    }  
```  
  
### <a name="step-3-configure-and-start-the-wcf-services"></a>Krok 3. Konfigurowanie i uruchamianie usług WCF  

 Aby hostować te usługi, należy wprowadzić następujące dodatki do pliku konfiguracji serwera (web.config).  
  
1. Dodaj `<client>` sekcję opisującą punkt końcowy dla obiektu sesji.  W tym scenariuszu serwer działa również jako klient i musi być skonfigurowany, aby go włączyć.  
  
2. W `<services>` sekcji Zadeklaruj punkty końcowe usługi dla obiektu fabryki i sesji.  Dzięki temu Klient może komunikować się z punktami końcowymi usługi, uzyskać <xref:System.ServiceModel.EndpointAddress10> i utworzyć kanał sesji.  
  
 Poniżej przedstawiono przykładowy plik konfiguracji z następującymi ustawieniami:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="sessionbound"  
                address="net.tcp://localhost:8081/SessionBoundObject"  
                binding="netTcpBinding"  
                contract="Shared.ISessionBoundObject"/>  
    </client>  
  
    <services>  
      <service name="Server.MySessionBoundObject">  
        <endpoint address="net.tcp://localhost:8081/SessionBoundObject"  
                  binding="netTcpBinding"
                  contract="Shared.ISessionBoundObject" />  
      </service>  
      <service name="Server.SessionBoundFactory">  
        <endpoint address="net.tcp://localhost:8081/SessionBoundFactory"  
                  binding="netTcpBinding"
                  contract="Shared.ISessionBoundFactory" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 Dodaj następujące wiersze do aplikacji konsolowej, do samodzielnego hostowania usługi i uruchom aplikację.  
  
```csharp  
ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
factoryHost.Open();  
  
ServiceHost sessionBoundServiceHost = new ServiceHost(  
typeof(MySessionBoundObject));  
sessionBoundServiceHost.Open();  
```  
  
### <a name="step-4-configure-the-client-and-call-the-service"></a>Krok 4. Konfigurowanie klienta i wywoływanie usługi  

 Skonfiguruj klienta programu do komunikacji z usługami WCF, wprowadzając następujące wpisy w pliku konfiguracyjnym aplikacji projektu (app.config).  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="sessionbound"
                address="net.tcp://localhost:8081/SessionBoundObject"
                binding="netTcpBinding"
                contract="Shared.ISessionBoundObject"/>  
      <endpoint name="factory"
                address="net.tcp://localhost:8081/SessionBoundFactory"
                binding="netTcpBinding"
                contract="Shared.ISessionBoundFactory"/>  
    </client>
  </system.serviceModel>  
</configuration>  
```  
  
 Aby wywołać usługę, Dodaj kod do klienta, aby wykonać następujące czynności:  
  
1. Utwórz kanał do `ISessionBoundFactory` usługi.  
  
2. Użyj kanału, aby wywołać usługę w celu `ISessionBoundFactory` uzyskania <xref:System.ServiceModel.EndpointAddress10> obiektu.  
  
3. Użyj, <xref:System.ServiceModel.EndpointAddress10> Aby utworzyć kanał, aby uzyskać obiekt sesji.  
  
4. Wywołaj `SetCurrentValue` metody i, `GetCurrentValue` Aby zademonstrować, pozostaje to samo wystąpienie obiektu w wielu wywołaniach.  
  
```csharp  
ChannelFactory<ISessionBoundFactory> factory =  
        new ChannelFactory<ISessionBoundFactory>("factory");  
  
ISessionBoundFactory sessionBoundFactory = factory.CreateChannel();  
  
EndpointAddress10 address = sessionBoundFactory.GetInstanceAddress();  
  
ChannelFactory<ISessionBoundObject> sessionBoundObjectFactory =  
    new ChannelFactory<ISessionBoundObject>(  
        new NetTcpBinding(),  
        address.ToEndpointAddress());  
  
ISessionBoundObject sessionBoundObject =  
        sessionBoundObjectFactory.CreateChannel();  
  
sessionBoundObject.SetCurrentValue("Hello");  
if (sessionBoundObject.GetCurrentValue() == "Hello")  
{  
    Console.WriteLine("Session-full instance management works as expected");  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- [Podstawy programowania przy użyciu programu WCF](../wcf/basic-wcf-programming.md)
- [Projektowanie i implementowanie usług](../wcf/designing-and-implementing-services.md)
- [Kompilowanie klientów](../wcf/building-clients.md)
- [Usługi dwukierunkowe](../wcf/feature-details/duplex-services.md)
