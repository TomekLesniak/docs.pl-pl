---
title: Implementowanie zadań w tle w mikrousługach za pomocą IHostedService i klasy BackgroundService
description: Architektura mikrousług platformy .NET dla aplikacji platformy .NET w kontenerze | Zapoznaj się z nowymi opcjami umożliwiającymi korzystanie z IHostedService i BackgroundService w celu zaimplementowania zadań w tle w mikrousługach .NET Core.
ms.date: 08/14/2020
ms.openlocfilehash: 279f9e0093deafab51e63d72dce233c8e9466a55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173357"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a>Implementowanie zadań w tle w mikrousługach za pomocą IHostedService i klasy BackgroundService

Zadania w tle i zaplanowane zadania to coś, czego można użyć w dowolnej aplikacji, niezależnie od tego, czy jest on zgodny ze wzorcem architektury mikrousług. Różnica w przypadku korzystania z architektury mikrousług polega na tym, że zadanie w tle można zaimplementować w oddzielnym procesie/kontenerze do obsługi, aby można było skalować je w dół i w górę w zależności od potrzeb.

Z ogólnego punktu widzenia w programie .NET Core wywołano te typy zadań *hostowanych usług*, ponieważ są one usługami/logiką hostowaną w ramach hosta/aplikacji/mikrousługi. Należy zauważyć, że w tym przypadku usługa hostowana po prostu oznacza klasę z logiką zadań w tle.

Począwszy od platformy .NET Core 2,0, struktura zawiera nowy interfejs o nazwie <xref:Microsoft.Extensions.Hosting.IHostedService> pomagającej łatwo zaimplementować usługi hostowane. Podstawowy pomysł polega na tym, że można zarejestrować wiele zadań w tle (usługi hostowane), które są uruchamiane w tle, podczas gdy host lub host sieci Web jest uruchomiony, jak pokazano na obrazie 6-26.

![Diagram przedstawiający porównanie ASP.NET Core IWebHost i .NET Core IHost.](./media/background-tasks-with-ihostedservice/ihosted-service-webhost-vs-host.png)

**Rysunek 6-26**. Używanie IHostedService w elemencie WebHost a Host

ASP.NET Core 1. x i 2. x obsługa `IWebHost` procesów w tle w aplikacjach sieci Web. Program .NET Core 2,1 i jego nowsze wersje obsługują `IHost` procesy w tle, w których są proste aplikacje konsolowe. Zwróć uwagę na różnice między `WebHost` i `Host` .

`WebHost`(Klasa bazowa implementująca `IWebHost` ) w ASP.NET Core 2,0 to artefakt infrastruktury używany do udostępniania funkcji serwera HTTP dla procesu, na przykład podczas wdrażania aplikacji sieci Web MVC lub usługi Web API. Zapewnia ona wszystkie nowe dobro infrastruktury w ASP.NET Core, co pozwala na korzystanie z iniekcji zależności, wstawianie middlewares w potoku żądań i podobne. `WebHost`Używa tych bardzo samo `IHostedServices` dla zadań w tle.

A `Host` (Implementacja klasy bazowej `IHost` ) została wprowadzona w programie .net Core 2,1. `Host`W zasadzie usługa a pozwala korzystać z podobnej infrastruktury niż to, z jakim korzystasz `WebHost` (iniekcja zależności, usługi hostowane itp.), ale w tym przypadku wystarczy, że chcesz mieć prosty i jaśniejszy proces jako host, bez żadnych informacji związanych z funkcjami MVC, Web API lub http Server.

W związku z tym można wybrać i utworzyć wyspecjalizowany proces hosta z `IHost` obsługą usług hostowanych, a nic innego, na przykład tylko na potrzeby hostowania `IHostedServices` , lub można również zwiększyć istniejące ASP.NET Core `WebHost` , takie jak istniejący ASP.NET Core Web API lub aplikacja MVC.

Każde podejście ma wady i zalety w zależności od potrzeb firmy i skalowalności. Dolna linia jest zasadniczo taka, że jeśli zadania w tle nie mają niczego do wykonania przy użyciu protokołu HTTP ( `IWebHost` ), należy użyć `IHost` .

## <a name="registering-hosted-services-in-your-webhost-or-host"></a>Rejestrowanie usług hostowanych w usłudze WebHost lub hoście

Przejdźmy do dalszych etapów `IHostedService` interfejsu, ponieważ jego użycie jest dość podobne w `WebHost` lub w `Host` .

Sygnalizujący to jeden przykład artefaktu korzystającego z usług hostowanych, ale można go również użyć do znacznie prostszego działania, takiego jak:

- Zadanie w tle sondowanie bazy danych szukającej zmian.
- Zaplanowane zadanie aktualizuje nieco pamięci podręcznej.
- Implementacja QueueBackgroundWorkItem, która umożliwia wykonywanie zadania w wątku w tle.
- Przetwarzanie komunikatów z kolejki komunikatów w tle aplikacji sieci Web podczas udostępniania wspólnych usług, takich jak `ILogger` .
- Zadanie w tle zostało uruchomione przy użyciu `Task.Run()` .

Można zasadniczo odciążyć dowolne z tych akcji do zadania w tle, które implementuje `IHostedService` .

Sposób dodawania jednego lub wielu `IHostedServices` do `WebHost` lub `Host` jest przez zarejestrowanie go za pomocą <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A>   metody rozszerzającej w ASP.NET Core `WebHost` (lub w `Host` środowisku .NET Core 2,1 lub nowszym). Zasadniczo należy zarejestrować usługi hostowane w znanej `ConfigureServices()` metodzie `Startup` klasy, jak w poniższym kodzie z typowego elementu webhost ASP.NET.

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //Other DI registrations;

    // Register Hosted Services
    services.AddHostedService<GracePeriodManagerService>();
    services.AddHostedService<MyHostedServiceB>();
    services.AddHostedService<MyHostedServiceC>();
    //...
}
```

W tym kodzie `GracePeriodManagerService` usługa hostowana jest realnym kodem z mikrousługi eShopOnContainers w firmie, a pozostałe dwa są tylko dwoma dodatkowymi przykładami.

`IHostedService`Wykonywanie zadania w tle jest koordynowane z okresem istnienia aplikacji (hosta lub mikrousługi). Zadania są rejestrowane, gdy aplikacja zostanie uruchomiona i masz możliwość wykonywania pewnych działań lub czyszczenia danych podczas zamykania aplikacji.

Bez korzystania z programu `IHostedService` można zawsze uruchomić wątek w tle, aby uruchomić dowolne zadanie. Różnica jest precyzyjna w czasie zamykania aplikacji, gdy ten wątek zostanie po prostu zamknięty, bez możliwości uruchamiania łagodnych akcji oczyszczania.

## <a name="the-ihostedservice-interface"></a>Interfejs IHostedService

Po zarejestrowaniu `IHostedService` platforma .NET Core będzie wywoływała `StartAsync()` metody i, `StopAsync()` `IHostedService` podczas uruchamiania i zatrzymywania aplikacji. Aby uzyskać więcej informacji, zobacz [IHostedService Interface](/aspnet/core/fundamentals/host/hosted-services?tabs=visual-studio&view=aspnetcore-3.1#ihostedservice-interface)

Jak można wyobrazić, można utworzyć wiele implementacji IHostedService i zarejestrować je w `ConfigureService()` metodzie w kontenerze di, jak pokazano wcześniej. Wszystkie te usługi hostowane zostaną uruchomione i zatrzymane wraz z aplikacją/mikrousługą.

Jako programista użytkownik jest odpowiedzialny za obsługę zatrzymania działania usług, gdy `StopAsync()` Metoda jest wyzwalana przez hosta.

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a>Implementowanie IHostedService z niestandardową klasą usługi hostowanej pochodną z klasy podstawowej BackgroundService

Można utworzyć niestandardową klasę usług hostowanych od podstaw i zaimplementować ją `IHostedService` , tak jak należy to zrobić w przypadku korzystania z platformy .NET Core 2,0.

Jednak ponieważ większość zadań w tle będzie miała podobne potrzeby w odniesieniu do zarządzania tokenami anulowania i innych typowych operacji, istnieje wygodna abstrakcyjna klasa bazowa, z której pochodzi `BackgroundService` (dostępna od platformy .NET Core 2,1).

Ta klasa udostępnia główną służbę wymaganą do skonfigurowania zadania w tle.

Następny kod jest abstrakcyjną klasą bazową BackgroundService zaimplementowaną w środowisku .NET Core.

```csharp
// Copyright (c) .NET Foundation. Licensed under the Apache License, Version 2.0.
/// <summary>
/// Base class for implementing a long running <see cref="IHostedService"/>.
/// </summary>
public abstract class BackgroundService : IHostedService, IDisposable
{
    private Task _executingTask;
    private readonly CancellationTokenSource _stoppingCts =
                                                   new CancellationTokenSource();

    protected abstract Task ExecuteAsync(CancellationToken stoppingToken);

    public virtual Task StartAsync(CancellationToken cancellationToken)
    {
        // Store the task we're executing
        _executingTask = ExecuteAsync(_stoppingCts.Token);

        // If the task is completed then return it,
        // this will bubble cancellation and failure to the caller
        if (_executingTask.IsCompleted)
        {
            return _executingTask;
        }

        // Otherwise it's running
        return Task.CompletedTask;
    }

    public virtual async Task StopAsync(CancellationToken cancellationToken)
    {
        // Stop called without start
        if (_executingTask == null)
        {
            return;
        }

        try
        {
            // Signal cancellation to the executing method
            _stoppingCts.Cancel();
        }
        finally
        {
            // Wait until the task completes or the stop token triggers
            await Task.WhenAny(_executingTask, Task.Delay(Timeout.Infinite,
                                                          cancellationToken));
        }

    }

    public virtual void Dispose()
    {
        _stoppingCts.Cancel();
    }
}
```

Podczas wyprowadzania z poprzedniej abstrakcyjnej klasy podstawowej, dzięki tej dziedziczonej implementacji, wystarczy zaimplementować `ExecuteAsync()` metodę we własnej niestandardowej klasie usługi hostowanej, tak jak w poniższym uproszczonym kodzie z eShopOnContainers, który sonduje bazę danych i publikuje zdarzenia integracji w usłudze Event Bus w razie potrzeby.

```csharp
public class GracePeriodManagerService : BackgroundService
{
    private readonly ILogger<GracePeriodManagerService> _logger;
    private readonly OrderingBackgroundSettings _settings;

    private readonly IEventBus _eventBus;

    public GracePeriodManagerService(IOptions<OrderingBackgroundSettings> settings,
                                     IEventBus eventBus,
                                     ILogger<GracePeriodManagerService> logger)
    {
        // Constructor's parameters validations...
    }

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        _logger.LogDebug($"GracePeriodManagerService is starting.");

        stoppingToken.Register(() =>
            _logger.LogDebug($" GracePeriod background task is stopping."));

        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogDebug($"GracePeriod task doing background work.");

            // This eShopOnContainers method is querying a database table
            // and publishing events into the Event Bus (RabbitMQ / ServiceBus)
            CheckConfirmedGracePeriodOrders();

            await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
        }

        _logger.LogDebug($"GracePeriod background task is stopping.");
    }

    .../...
}
```

W tym konkretnym przypadku eShopOnContainers jest wykonywana metoda aplikacji, która jest kwerendą tabeli bazy danych szukającą zamówień o określonym stanie i w przypadku stosowania zmian, publikuje zdarzenia integracji za pośrednictwem magistrali zdarzeń (poniżej można używać RabbitMQ lub Azure Service Bus).

Oczywiście możesz zamiast tego uruchomić dowolne inne zadanie w tle.

Domyślnie token anulowania jest ustawiany z limitem czasu równym 5 sekund, ale można zmienić tę wartość podczas kompilowania `WebHost` przy użyciu `UseShutdownTimeout` rozszerzenia `IWebHostBuilder` . Oznacza to, że nasza usługa powinna zostać anulowana w ciągu 5 sekund, w przeciwnym razie będzie bardziej nieoczekiwanie zabity.

Poniższy kod zmieni ten czas na 10 sekund.

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a>Diagram klas podsumowania

Na poniższej ilustracji przedstawiono wizualne podsumowanie klas i interfejsów, które są wykorzystywane podczas implementowania IHostedServices.

![Diagram przedstawiający, że IWebHost i IHost mogą obsługiwać wiele usług.](./media/background-tasks-with-ihostedservice/class-diagram-custom-ihostedservice.png)

**Rysunek 6-27**. Diagram klas przedstawiający wiele klas i interfejsów związanych z IHostedService

Diagram klas: IWebHost i IHost mogą obsługiwać wiele usług, które dziedziczą z BackgroundService, który implementuje IHostedService.

### <a name="deployment-considerations-and-takeaways"></a>Zagadnienia dotyczące wdrażania i wnioski

Należy pamiętać, że sposób wdrażania ASP.NET Core `WebHost` lub .NET Core `Host` może mieć wpływ na ostateczne rozwiązanie. Na przykład w przypadku wdrożenia `WebHost` na serwerze IIS lub w regularnych Azure App Service można wyłączyć hosta z powodu odtwarzania puli aplikacji. Ale w przypadku wdrażania hosta jako kontenera do programu Orchestrator, takiego jak Kubernetes, można kontrolować zagwarantowaną liczbę wystąpień na żywo hosta. Ponadto można rozważyć inne podejścia w chmurze szczególnie dla tych scenariuszy, takie jak Azure Functions. Na koniec w przypadku konieczności uruchomienia usługi przez cały czas i wdrożenia na serwerze z systemem Windows można użyć usługi systemu Windows.

Jednak nawet w przypadku `WebHost` wdrożenia w puli aplikacji istnieją scenariusze, takie jak ponowne wypełnianie lub opróżnianie pamięci podręcznej w pamięci aplikacji, które nadal mogą być stosowane.

`IHostedService`Interfejs zapewnia wygodny sposób uruchamiania zadań w tle w ASP.NET Core aplikacji sieci Web (w programie .net core 2,0 i nowszych wersjach) lub w dowolnym procesie/hoście (począwszy od platformy .net core 2,1 z `IHost` ). Jej główną zaletą jest możliwość bezpiecznego anulowania usuwania kodu zadań w tle, gdy sam host jest zamykany.

## <a name="additional-resources"></a>Zasoby dodatkowe

- **Tworzenie zaplanowanego zadania w ASP.NET Core/standardowa 2,0** \
  <https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html>

- **Implementacja IHostedService w ASP.NET Core 2,0** \
  <https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice>

- **Przykład GenericHost za pomocą ASP.NET Core 2,1** \
  <https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample>

> [!div class="step-by-step"]
> [Poprzedni](test-aspnet-core-services-web-apps.md) 
>  [Dalej](implement-api-gateways-with-ocelot.md)
