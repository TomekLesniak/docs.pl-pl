---
title: Iniekcja zależności w programie .NET
description: Dowiedz się, w jaki sposób platforma .NET implementuje iniekcję zależności i jak z niej korzystać.
author: IEvangelist
ms.author: dapine
ms.date: 09/23/2020
ms.topic: overview
ms.openlocfilehash: 2aaa24e54dad7b765781bf7c790890a57a77af14
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608353"
---
# <a name="dependency-injection-in-net"></a>Iniekcja zależności w programie .NET

Platforma .NET obsługuje wzorzec projektowania oprogramowania dla iniekcji zależności, który jest techniką do osiągnięcia [nieużywanej kontroli (IOC)](../../architecture/modern-web-apps-azure/architectural-principles.md#dependency-inversion) między klasami i ich zależnościami. Wstrzykiwanie zależności w programie .NET to [pierwszy obywatel klasy](https://en.wikipedia.org/wiki/First-class_citizen), a także konfiguracji, rejestrowania i wzorca opcji.

*Zależność* jest obiektem, od którego zależy inny obiekt. Zapoznaj się `MessageWriter` z następującą klasą z `Write` metodą, od której zależą inne klasy:

```csharp
public class MessageWriter
{
    public void Write(string message)
    {
        Console.WriteLine($"MessageWriter.Write(message: \"{message}\")");
    }
}
```

Klasa może utworzyć wystąpienie `MessageWriter` klasy, aby użyć jej `Write` metody. W poniższym przykładzie `MessageWriter` Klasa jest zależna od `Worker` klasy:

```csharp
public class Worker : BackgroundService
{
    private readonly MessageWriter _messageWriter = new MessageWriter();

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            _messageWriter.Write($"Worker running at: {DateTimeOffset.Now}");
            await Task.Delay(1000, stoppingToken);
        }
    }
}
```

Klasa tworzy i bezpośrednio zależy od `MessageWriter` klasy. Stałe kodowane, takie jak w poprzednim przykładzie, są problematyczne i należy je unikać z następujących powodów:

- Aby zastąpić `MessageWriter` inną implementacją, `MessageService` należy zmodyfikować klasę.
- Jeśli `MessageWriter` ma zależności, muszą one być również konfigurowane przez `MessageService` klasę. W dużym projekcie z wieloma klasami, w zależności od tego `MessageWriter` , kod konfiguracji jest rozmieszczany w całej aplikacji.
- Ta implementacja jest trudna do testowania jednostkowego. Aplikacja powinna używać klasy imitacji lub zastępczej `MessageWriter` , która nie jest możliwa w przypadku tego podejścia.

Iniekcja zależności eliminuje te problemy w następujący sposób:

- Użycie interfejsu lub klasy bazowej do abstrakcyjnej implementacji zależności.
- Rejestracja zależności w kontenerze usługi. Platforma .NET udostępnia wbudowany kontener usług <xref:System.IServiceProvider> . Usługi są zwykle rejestrowane w momencie uruchomienia aplikacji i dołączane do <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection> . Po dodaniu wszystkich usług należy użyć <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> programu, aby utworzyć kontener usługi.
- *Iniekcja* usługi do konstruktora klasy, w której jest używana. Struktura przejmuje odpowiedzialność za utworzenie wystąpienia zależności i jego likwidację, gdy nie jest już potrzebny.

Na przykład `IMessageWriter` Interfejs definiuje `Write` metodę:

:::code language="csharp" source="snippets/configuration/dependency-injection/IMessageWriter.cs":::

Ten interfejs jest implementowany przez konkretny typ `MessageWriter` :

:::code language="csharp" source="snippets/configuration/dependency-injection/MessageWriter.cs":::

Przykładowy kod rejestruje `IMessageWriter` usługę w konkretnym typie `MessageWriter` . <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A>Metoda rejestruje usługę z okresem istnienia w określonym zakresie, okresem istnienia pojedynczego żądania. [Okresy istnienia usługi](#service-lifetimes) zostały opisane w dalszej części tego tematu.

:::code language="csharp" source="snippets/configuration/dependency-injection/Program.cs" highlight="16":::

W przykładowej aplikacji `IMessageWriter` jest wymagana usługa, która jest używana do wywołania `Write` metody:

:::code language="csharp" source="snippets/configuration/dependency-injection/Worker.cs":::

Przy użyciu wzorca DI, usługa procesu roboczego:

- Nie używa konkretnego typu `MessageWriter` , tylko `IMessageWriter` interfejsu, który implementuje go. Dzięki temu można łatwo zmienić implementację używaną przez kontroler bez modyfikowania kontrolera.
- Nie tworzy wystąpienia `MessageWriter` , jest tworzone przez element di kontener.

Implementację `IMessageWriter` interfejsu można ulepszyć za pomocą wbudowanego interfejsu API rejestrowania:

:::code language="csharp" source="snippets/configuration/dependency-injection/LoggingMessageWriter.cs":::

Zaktualizowana `ConfigureServices` Metoda rejestruje nową `IMessageWriter` implementację:

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureServices((_, services) =>
            services.AddHostedService<Worker>()
                    .AddScoped<IMessageWriter, LoggingMessageWriter>());
```

`LoggingMessageWriter` zależy od <xref:Microsoft.Extensions.Logging.ILogger%601> , który z nich żąda w konstruktorze. `ILogger<TCategoryName>` to [Usługa udostępniona przez platformę](#framework-provided-services).

Użycie iniekcji zależności w łańcuchu nie jest nietypowe. Każda żądana zależność z kolei żąda własnych zależności. Kontener rozwiązuje zależności w grafie i zwraca w pełni rozwiązane usługi. Zestaw zbiorczy zależności, które muszą zostać rozwiązane, jest zwykle nazywany *drzewem zależności*, *wykresem zależności*lub *wykresem obiektów*.

Kontener jest rozpoznawany `ILogger<TCategoryName>` przez wykorzystanie [(rodzajowe) otwartych typów](/dotnet/csharp/language-reference/language-specification/types#open-and-closed-types), eliminując konieczność zarejestrowania każdego [(rodzajowego) konstruowanego typu](/dotnet/csharp/language-reference/language-specification/types#constructed-types).

W terminologii wtrysku zależności, usługa:

- Jest zazwyczaj obiektem, który udostępnia usługę innym obiektom, takim jak `IMessageWriter` Usługa.
- Nie jest powiązany z usługą sieci Web, chociaż usługa może korzystać z usługi sieci Web.

Struktura zapewnia niezawodny system rejestrowania. `IMessageWriter`Implementacje opisane w powyższych przykładach zostały opracowane w celu zademonstrowania podstawowych di, a nie do zaimplementowania rejestrowania. Większość aplikacji nie musi być w trakcie pisania rejestratorów. Poniższy kod ilustruje użycie domyślnego rejestrowania, które wymaga zarejestrowania tylko `Worker` `ConfigureServices` jako usługi hostowanej <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A> :

```csharp
public class Worker : BackgroundService
{
    private readonly ILogger<Worker> _logger;

    public Worker(ILogger<Worker> logger) =>
        _logger = logger;

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogInformation("Worker running at: {time}", DateTimeOffset.Now);
            await Task.Delay(1000, stoppingToken);
        }
    }
}
```

Korzystając z powyższego kodu, nie ma potrzeby aktualizowania `ConfigureServices` , ponieważ rejestrowanie jest dostarczane przez strukturę.

## <a name="register-groups-of-services-with-extension-methods"></a>Rejestrowanie grup usług przy użyciu metod rozszerzających

Rozszerzenia Microsoft używają Konwencji do rejestracji grupy powiązanych usług. Konwencja polega na użyciu pojedynczej `Add{GROUP_NAME}` metody rozszerzenia w celu zarejestrowania wszystkich usług wymaganych przez funkcję platformy. Na przykład <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> Metoda rozszerzenia rejestruje wszystkie usługi wymagane do korzystania z opcji.

## <a name="framework-provided-services"></a>Usługi udostępniane przez platformę

`ConfigureServices`Metoda rejestruje usługi, z których korzysta aplikacja, w tym funkcje platformy. Początkowo `IServiceCollection` dostarczone z `ConfigureServices` usługami zdefiniowanymi przez platformę, w zależności od [konfiguracji hosta](generic-host.md#host-configuration). W przypadku aplikacji opartych na szablonach platformy .NET struktura rejestruje setki usług.

W poniższej tabeli przedstawiono niewielki przykład następujących usług zarejestrowanych w ramach platformy:

| Typ usługi                                                                       | Okres istnienia  |
|------------------------------------------------------------------------------------|-----------|
| <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime>                       | Pojedynczego |
| <xref:Microsoft.Extensions.Logging.ILogger%601?displayProperty=fullName>           | Pojedynczego |
| <xref:Microsoft.Extensions.Logging.ILoggerFactory?displayProperty=fullName>        | Pojedynczego |
| <xref:Microsoft.Extensions.ObjectPool.ObjectPoolProvider?displayProperty=fullName> | Pojedynczego |
| <xref:Microsoft.Extensions.Options.IConfigureOptions%601?displayProperty=fullName> | Administracyjnej |
| <xref:Microsoft.Extensions.Options.IOptions%601?displayProperty=fullName>          | Pojedynczego |
| <xref:System.Diagnostics.DiagnosticListener?displayProperty=fullName>              | Pojedynczego |
| <xref:System.Diagnostics.DiagnosticSource?displayProperty=fullName>                | Pojedynczego |

## <a name="service-lifetimes"></a>Okresy istnienia usługi

Usługi mogą być zarejestrowane przy użyciu jednego z następujących okresów istnienia:

- Administracyjnej
- Zakresie
- Pojedynczego

W poniższych sekcjach opisano wszystkie poprzednie okresy istnienia. Wybierz odpowiedni okres istnienia dla każdej zarejestrowanej usługi.

### <a name="transient"></a>Administracyjnej

Przejściowe usługi okresu istnienia są tworzone za każdym razem, gdy zażądają one kontenera usług. Ten okres istnienia działa najlepiej w przypadku lekkich i bezstanowych usług. Zarejestruj usługi przejściowe w usłudze <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddTransient%2A> .

W przypadku aplikacji, które przetwarzają żądania, usługi przejściowe są usuwane na końcu żądania.

### <a name="scoped"></a>Zakresie

W przypadku aplikacji sieci Web okres istnienia w zakresie wskazuje, że usługi są tworzone raz dla każdego żądania klienta (połączenie). Zarejestruj usługi z zakresem w usłudze <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A> .

W przypadku aplikacji, które przetwarzają żądania, usługi o określonym zakresie są usuwane na końcu żądania.

W przypadku korzystania z Entity Framework Core <xref:Microsoft.Extensions.DependencyInjection.EntityFrameworkServiceCollectionExtensions.AddDbContext%2A> Metoda rozszerzenia rejestruje `DbContext` typy z okresem istnienia w zakresie domyślnie.

> [!NOTE]
> ***Nie*** należy rozwiązywać usługi z zakresem z pojedynczej. Może to spowodować, że usługa będzie mieć nieprawidłowy stan podczas przetwarzania kolejnych żądań. Warto:
>
> - Rozwiązanie pojedynczej usługi z usługi w zakresie lub przejściowej.
> - Rozwiąż usługę objętą zakresem z innej usługi w zakresie lub przejściowej.

Domyślnie w środowisku programistycznym rozpoznawanie usługi z innej usługi o dłuższym okresie istnienia zgłasza wyjątek. Aby uzyskać więcej informacji, zobacz [Walidacja zakresu](#scope-validation).

### <a name="singleton"></a>Pojedynczego

Są tworzone pojedyncze usługi okresu istnienia:

- Podczas pierwszego żądania.
- Przez dewelopera, gdy udostępnia wystąpienie implementacji bezpośrednio do kontenera. Takie podejście jest rzadko niezbędne.

Każde kolejne żądanie implementacji usługi z kontenera iniekcji zależności używa tego samego wystąpienia. Jeśli aplikacja wymaga pojedynczych zachowań, zezwól kontenerowi usługi na zarządzanie okresem istnienia usługi. Nie Wdrażaj wzorca projektu singleton i podawanie kodu do usuwania pojedynczych elementów. Usługi nigdy nie powinny być usuwane przez kod, który rozwiązał usługę z kontenera. Jeśli typ lub fabryka są zarejestrowane jako pojedyncze, kontener usuwa pojedyncze automatycznie.

Zarejestruj usługi pojedyncze przy użyciu programu <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A> . Usługi pojedyncze muszą być bezpieczne dla wątków i często używane w usługach bezstanowych.

W przypadku aplikacji, które przetwarzają żądania, pojedyncze usługi są usuwane, gdy <xref:Microsoft.Extensions.DependencyInjection.ServiceProvider> zostanie usunięty podczas zamykania aplikacji. Ponieważ pamięć nie jest wydawana do momentu wyłączenia aplikacji, należy rozważyć użycie pamięci w ramach pojedynczej usługi.

> [!WARNING]
> ***Nie*** należy rozwiązywać usługi z zakresem z pojedynczej. Może to spowodować, że usługa będzie mieć nieprawidłowy stan podczas przetwarzania kolejnych żądań. Rozwiązaniem jest rozwiązanie pojedynczej usługi z poziomu usługi w zakresie lub przejściowej.

## <a name="service-registration-methods"></a>Metody rejestracji usług

Struktura zawiera metody rozszerzenia rejestracji usług, które są przydatne w określonych scenariuszach:

| Metoda | Automatyczny<br>object<br>myśl | Wiele<br>implementacje | Przekaż argumenty |
|--|:-:|:-:|:-:|
| `Add{LIFETIME}<{SERVICE}, {IMPLEMENTATION}>()`<br><br>Przykład:<br><br>`services.AddSingleton<IMyDep, MyDep>();` | Tak | Tak | Nie |
| `Add{LIFETIME}<{SERVICE}>(sp => new {IMPLEMENTATION})`<br><br>Przykłady:<br><br>`services.AddSingleton<IMyDep>(sp => new MyDep());`<br>`services.AddSingleton<IMyDep>(sp => new MyDep(99));` | Tak | Tak | Tak |
| `Add{LIFETIME}<{IMPLEMENTATION}>()`<br><br>Przykład:<br><br>`services.AddSingleton<MyDep>();` | Tak | Nie | Nie |
| `AddSingleton<{SERVICE}>(new {IMPLEMENTATION})`<br><br>Przykłady:<br><br>`services.AddSingleton<IMyDep>(new MyDep());`<br>`services.AddSingleton<IMyDep>(new MyDep(99));` | Nie | Tak | Tak |
| `AddSingleton(new {IMPLEMENTATION})`<br><br>Przykłady:<br><br>`services.AddSingleton(new MyDep());`<br>`services.AddSingleton(new MyDep(99));` | Nie | Nie | Tak |

Aby uzyskać więcej informacji na temat usuwania typów, zobacz sekcję [dotyczącą usuwania usług](dependency-injection-guidelines.md#disposal-of-services) .

Struktura zawiera również `TryAdd{LIFETIME}` metody rozszerzające, które rejestrują usługę tylko wtedy, gdy nie zarejestrowano jeszcze implementacji.

W poniższym przykładzie wywołanie `AddSingleton` rejestruje się `MessageWriter` jako implementacja dla `IMessageWriter` . Wywołanie nie `TryAddSingleton` działa, ponieważ `IMessageWriter` ma już zarejestrowaną implementację:

```csharp
services.AddSingleton<IMessageWriter, MessageWriter>();
services.TryAddSingleton<IMessageWriter, DifferentMessageWriter>();
```

`TryAddSingleton`Nie ma żadnego efektu, ponieważ został już dodany i próba "try" zakończy się niepowodzeniem.

Aby uzyskać więcej informacji, zobacz:

- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAdd%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddTransient%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddScoped%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddSingleton%2A>

Metody [TryAddEnumerable (servicedescriptor)](xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddEnumerable%2A) rejestrują usługę tylko wtedy, gdy nie istnieje jeszcze implementacja tego *samego typu*. Wiele usług jest rozpoznawanych za pośrednictwem `IEnumerable<{SERVICE}>` . Podczas rejestrowania usług Dodaj wystąpienie, jeśli jeden z tych samych typów nie został jeszcze dodany. Autorzy biblioteki używają `TryAddEnumerable` , aby uniknąć rejestrowania wielu kopii implementacji w kontenerze.

W poniższym przykładzie pierwsze wywołanie `TryAddEnumerable` rejestracji `MessageWriter` jako implementacji dla `IMessageWriter1` . Drugie wywołanie rejestru `MessageWriter` dla `IMessageWriter2` . Trzecie wywołanie nie działa `IMessageWriter1` , ponieważ ma już zarejestrowana implementacja `MessageWriter` :

```csharp
public interface IMessageWriter1 { }
public interface IMessageWriter2 { }

public class MessageWriter : IMessageWriter1, IMessageWriter2
{
}

services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter1, MessageWriter>());
services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter2, MessageWriter>());
services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter1, MessageWriter>());
```

Rejestracja usługi jest zazwyczaj kolejnością niezależną, z wyjątkiem rejestracji wielu implementacji tego samego typu.

`IServiceCollection` jest kolekcją <xref:Microsoft.Extensions.DependencyInjection.ServiceDescriptor> obiektów. Poniższy przykład pokazuje, jak zarejestrować usługę przez utworzenie i dodanie `ServiceDescriptor` :

```csharp
string secretKey = Configuration["SecretKey"];
var descriptor = new ServiceDescriptor(
    typeof(IMessageWriter),
    _ => new DefaultMessageWriter(secretKey),
    ServiceLifetime.Transient);

services.Add(descriptor);
```

`Add{LIFETIME}`Metody wbudowane wykorzystują takie samo podejście. Na przykład zobacz [kod źródłowy addscope](https://github.com/dotnet/extensions/blob/v3.1.8/src/DependencyInjection/DI.Abstractions/src/ServiceCollectionServiceExtensions.cs#L216-L237).

### <a name="constructor-injection-behavior"></a>Zachowanie iniekcji konstruktora

Usługi można rozwiązać przy użyciu:

- <xref:System.IServiceProvider>
- <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities>:
  - Tworzy obiekty, które nie są zarejestrowane w kontenerze.
  - Używany z niektórymi funkcjami środowiska.

Konstruktory mogą akceptować argumenty, które nie są dostarczane przez iniekcję zależności, ale argumenty muszą przypisywać wartości domyślne.

Gdy usługi są rozwiązane przez `IServiceProvider` lub `ActivatorUtilities` , iniekcja konstruktora wymaga konstruktora *publicznego* .

Gdy usługi są rozwiązane przez `ActivatorUtilities` , iniekcja konstruktora wymaga, aby istnieje tylko jeden odpowiedni Konstruktor. Przeciążenia konstruktora są obsługiwane, ale może istnieć tylko jedno Przeciążenie, którego argumenty mogą być spełnione przez iniekcję zależności.

## <a name="scope-validation"></a>Weryfikacja zakresu

Gdy aplikacja jest uruchamiana w `Development` środowisku i wywołuje [CreateDefaultBuilder](generic-host.md#default-builder-settings) , aby skompilować hosta, domyślny dostawca usług sprawdza, czy:

- Usługi w zakresie nie są rozpoznawane przez dostawcę usług głównych.
- Usługi w zakresie nie są wstawiane do pojedynczych.

Dostawca usług głównych jest tworzony, gdy <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> jest wywoływany. Okres istnienia dostawcy usług głównych odpowiada okresowi istnienia aplikacji, gdy dostawca rozpoczyna pracę z aplikacją i jest usuwany po zamknięciu aplikacji.

Usługi o określonym zakresie są usuwane przez kontener, który go utworzył. Jeśli w kontenerze głównym zostanie utworzona usługa o określonym zakresie, okres istnienia usługi zostanie skutecznie podwyższony do pojedynczej, ponieważ jest usuwany tylko przez kontener główny po zamknięciu aplikacji. Sprawdzanie poprawności zakresów usług przechwytuje te sytuacje, gdy `BuildServiceProvider` jest wywoływana.

## <a name="see-also"></a>Zobacz także

- [Używanie iniekcji zależności w programie .NET](dependency-injection-usage.md)
- [Wskazówki dotyczące wstrzykiwania zależności](dependency-injection-guidelines.md)
- [Wzorce konferencji NDC na potrzeby tworzenia aplikacji](https://www.youtube.com/watch?v=x-C-CNBVTaY)
- [Zasada jawnych zależności](../../architecture/modern-web-apps-azure/architectural-principles.md#explicit-dependencies)
- [Niewersja kontenerów sterowania i wzorzec iniekcji zależności (Martin Fowlera)](https://www.martinfowler.com/articles/injection.html)
- W repozytorium [GitHub.com/dotnet/Extensions](https://github.com/dotnet/extensions/issues) należy utworzyć di usterki
