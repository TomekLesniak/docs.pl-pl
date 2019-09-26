---
title: Implementowanie magistrali zdarzeń z oprogramowaniem RabbitMQ na potrzeby środowisk testowych lub deweloperskich
description: Architektura mikrousług platformy .NET dla aplikacji platformy .NET w kontenerze | Użyj RabbitMQ, aby zaimplementować obsługę komunikatów usługi Event Bus dla zdarzeń integracji dla środowisk programistycznych lub testowych.
ms.date: 10/02/2018
ms.openlocfilehash: af02208bb9e680403a04377ccb740a8b15be29bc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/30/2019
ms.locfileid: "70296563"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="baf12-103">Implementowanie magistrali zdarzeń z oprogramowaniem RabbitMQ na potrzeby środowisk testowych lub deweloperskich</span><span class="sxs-lookup"><span data-stu-id="baf12-103">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="baf12-104">Należy zacząć od tego, że jeśli utworzysz niestandardową magistralę zdarzeń w oparciu o RabbitMQ uruchomione w kontenerze, jako aplikację eShopOnContainers, powinna ona być używana tylko w środowiskach deweloperskich i testowych.</span><span class="sxs-lookup"><span data-stu-id="baf12-104">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="baf12-105">Nie należy używać go w środowisku produkcyjnym, chyba że tworzysz go jako część usługi Service Bus gotowej do produkcji.</span><span class="sxs-lookup"><span data-stu-id="baf12-105">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="baf12-106">W przypadku prostej niestandardowej magistrali zdarzeń może brakować wielu funkcji krytycznych gotowych do produkcji dostępnych w komercyjnej usłudze Service Bus.</span><span class="sxs-lookup"><span data-stu-id="baf12-106">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="baf12-107">Jedna z implementacji niestandardowej usługi Event Bus w eShopOnContainers jest zasadniczo biblioteką korzystającą z interfejsu API RabbitMQ (istnieje inna implementacja oparta na Azure Service Bus).</span><span class="sxs-lookup"><span data-stu-id="baf12-107">One of the event bus custom implementation in eShopOnContainers is basically a library using the RabbitMQ API (There’s another implementation based on Azure Service Bus).</span></span>

<span data-ttu-id="baf12-108">Implementacja magistrali zdarzeń z RabbitMQ umożliwia mikrousługom subskrybowanie zdarzeń, publikowanie zdarzeń i odbieranie zdarzeń, jak pokazano na rysunku 6-21.</span><span class="sxs-lookup"><span data-stu-id="baf12-108">The event bus implementation with RabbitMQ lets microservices subscribe to events, publish events, and receive events, as shown in Figure 6-21.</span></span>

![RabbitMQ działa jako pośrednik między wydawcą komunikatów i subskrybentami, aby obsłużyć dystrybucję.](./media/image22.png)

<span data-ttu-id="baf12-110">**Rysunek 6-21.**</span><span class="sxs-lookup"><span data-stu-id="baf12-110">**Figure 6-21.**</span></span> <span data-ttu-id="baf12-111">RabbitMQ implementacja magistrali zdarzeń</span><span class="sxs-lookup"><span data-stu-id="baf12-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="baf12-112">W kodzie Klasa EventBusRabbitMQ implementuje ogólny interfejs IEventBus.</span><span class="sxs-lookup"><span data-stu-id="baf12-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="baf12-113">Jest to oparte na iniekcji zależności, co pozwala na zamianę z tej wersji deweloperskiej/testowej na wersję produkcyjną.</span><span class="sxs-lookup"><span data-stu-id="baf12-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
}
```

<span data-ttu-id="baf12-114">RabbitMQ implementacja przykładowej magistrali zdarzeń do tworzenia/testowania to kod standardowy.</span><span class="sxs-lookup"><span data-stu-id="baf12-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="baf12-115">Musi obsługiwać połączenie z serwerem RabbitMQ i dostarczać kod do publikowania zdarzenia komunikatu w kolejkach.</span><span class="sxs-lookup"><span data-stu-id="baf12-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="baf12-116">Należy również zaimplementować słownik kolekcji programów obsługi zdarzeń integracji dla każdego typu zdarzenia; te typy zdarzeń mogą mieć różne wystąpienia i różne subskrypcje dla mikrousług odbiornika, jak pokazano na rysunku 6-21.</span><span class="sxs-lookup"><span data-stu-id="baf12-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 6-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="baf12-117">Implementowanie prostej metody publikacji z RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="baf12-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="baf12-118">Poniższy kod jest ***uproszczoną*** wersją implementacji usługi Event Bus dla RabbitMQ, aby zaprezentować cały scenariusz.</span><span class="sxs-lookup"><span data-stu-id="baf12-118">The following code is a ***simplified*** version of an event bus implementation for RabbitMQ, to showcase the whole scenario.</span></span> <span data-ttu-id="baf12-119">W ten sposób nie obsługujesz połączenia w ten sposób.</span><span class="sxs-lookup"><span data-stu-id="baf12-119">You don't really handle the connection this way.</span></span> <span data-ttu-id="baf12-120">Aby wyświetlić pełną implementację, zobacz rzeczywisty kod w repozytorium [dotnet-Architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) .</span><span class="sxs-lookup"><span data-stu-id="baf12-120">To see the full implementation, see the actual code in the [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) repository.</span></span> 

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Publish(IntegrationEvent @event)
    {
        var eventName = @event.GetType().Name;
        var factory = new ConnectionFactory() { HostName = _connectionString };
        using (var connection = factory.CreateConnection())
        using (var channel = connection.CreateModel())
        {
            channel.ExchangeDeclare(exchange: _brokerName,
                type: "direct");
            string message = JsonConvert.SerializeObject(@event);
            var body = Encoding.UTF8.GetBytes(message);
            channel.BasicPublish(exchange: _brokerName,
                routingKey: eventName,
                basicProperties: null,
                body: body);
       }
    }
}
```

<span data-ttu-id="baf12-121">[Rzeczywisty kod](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) metody Publish w aplikacji eShopOnContainers jest ulepszony za pomocą zasad [Polly](https://github.com/App-vNext/Polly) retry, które ponawiają próbę wykonania zadania przez określoną liczbę razy, gdy kontener RabbitMQ nie jest gotowy.</span><span class="sxs-lookup"><span data-stu-id="baf12-121">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="baf12-122">Taka sytuacja może wystąpić, gdy platforma Docker rozpocznie tworzenie kontenerów; na przykład kontener RabbitMQ może zaczynać się wolniej niż inne kontenery.</span><span class="sxs-lookup"><span data-stu-id="baf12-122">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="baf12-123">Jak wspomniano wcześniej, istnieje wiele możliwych konfiguracji w RabbitMQ, więc ten kod powinien być używany tylko w środowiskach deweloperskich i testowych.</span><span class="sxs-lookup"><span data-stu-id="baf12-123">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="baf12-124">Implementowanie kodu subskrypcji za pomocą interfejsu API RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="baf12-124">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="baf12-125">Podobnie jak w przypadku kodu publikacji Poniższy kod jest uproszczeniem części implementacji usługi Event Bus dla RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="baf12-125">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="baf12-126">Zwykle nie trzeba go zmieniać, chyba że jest to ulepszane.</span><span class="sxs-lookup"><span data-stu-id="baf12-126">Again, you usually do not need to change it unless you are improving it.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>
    {
        var eventName = _subsManager.GetEventKey<T>();
        
        var containsKey = _subsManager.HasSubscriptionsForEvent(eventName);
        if (!containsKey)
        {
            if (!_persistentConnection.IsConnected)
            {
                _persistentConnection.TryConnect();
            }

            using (var channel = _persistentConnection.CreateModel())
            {
                channel.QueueBind(queue: _queueName,
                                    exchange: BROKER_NAME,
                                    routingKey: eventName);
            }
        }

        _subsManager.AddSubscription<T, TH>();
    }
}
```

<span data-ttu-id="baf12-127">Każdy typ zdarzenia ma powiązany kanał, aby uzyskać zdarzenia z RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="baf12-127">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="baf12-128">W razie konieczności można mieć dowolną liczbę programów obsługi zdarzeń dla kanału i typu zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="baf12-128">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="baf12-129">Metoda Subskrybuj akceptuje obiekt IIntegrationEventHandler, który przypomina metodę wywołania zwrotnego w bieżącej mikrousłudze oraz powiązany obiekt IntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="baf12-129">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="baf12-130">Następnie kod dodaje ten program obsługi zdarzeń do listy programów obsługi zdarzeń, które każdy typ zdarzenia integracji może mieć dla mikrousługi klienta.</span><span class="sxs-lookup"><span data-stu-id="baf12-130">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="baf12-131">Jeśli kod klienta nie został jeszcze objęty subskrypcją zdarzenia, kod tworzy kanał dla typu zdarzenia, dzięki czemu może odbierać zdarzenia w stylu push z RabbitMQ, gdy to zdarzenie jest publikowane z poziomu innej usługi.</span><span class="sxs-lookup"><span data-stu-id="baf12-131">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="baf12-132">[Poprzedni](integration-event-based-microservice-communications.md)Następny
>[](subscribe-events.md)</span><span class="sxs-lookup"><span data-stu-id="baf12-132">[Previous](integration-event-based-microservice-communications.md)
[Next](subscribe-events.md)</span></span>