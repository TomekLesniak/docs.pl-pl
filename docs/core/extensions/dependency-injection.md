---
title: Iniekcja zależności w programie .NET
description: Dowiedz się, w jaki sposób platforma .NET implementuje iniekcję zależności i jak z niej korzystać.
author: IEvangelist
ms.author: dapine
ms.date: 10/28/2020
ms.topic: overview
ms.openlocfilehash: 3692b9e779d450f07d47599417349bb57f72ac36
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687575"
---
# <a name="dependency-injection-in-net"></a><span data-ttu-id="e2666-103">Iniekcja zależności w programie .NET</span><span class="sxs-lookup"><span data-stu-id="e2666-103">Dependency injection in .NET</span></span>

<span data-ttu-id="e2666-104">Platforma .NET obsługuje wzorzec projektowania oprogramowania dla iniekcji zależności, który jest techniką do osiągnięcia [nieużywanej kontroli (IOC)](../../architecture/modern-web-apps-azure/architectural-principles.md#dependency-inversion) między klasami i ich zależnościami.</span><span class="sxs-lookup"><span data-stu-id="e2666-104">.NET supports the dependency injection (DI) software design pattern, which is a technique for achieving [Inversion of Control (IoC)](../../architecture/modern-web-apps-azure/architectural-principles.md#dependency-inversion) between classes and their dependencies.</span></span> <span data-ttu-id="e2666-105">Wstrzykiwanie zależności w programie .NET to [pierwszy obywatel klasy](https://en.wikipedia.org/wiki/First-class_citizen), a także konfiguracji, rejestrowania i wzorca opcji.</span><span class="sxs-lookup"><span data-stu-id="e2666-105">Dependency injection in .NET is a [first-class citizen](https://en.wikipedia.org/wiki/First-class_citizen), along with configuration, logging, and the options pattern.</span></span>

<span data-ttu-id="e2666-106">*Zależność* jest obiektem, od którego zależy inny obiekt.</span><span class="sxs-lookup"><span data-stu-id="e2666-106">A *dependency* is an object that another object depends on.</span></span> <span data-ttu-id="e2666-107">Zapoznaj się `MessageWriter` z następującą klasą z `Write` metodą, od której zależą inne klasy:</span><span class="sxs-lookup"><span data-stu-id="e2666-107">Examine the following `MessageWriter` class with a `Write` method that other classes depend on:</span></span>

```csharp
public class MessageWriter
{
    public void Write(string message)
    {
        Console.WriteLine($"MessageWriter.Write(message: \"{message}\")");
    }
}
```

<span data-ttu-id="e2666-108">Klasa może utworzyć wystąpienie `MessageWriter` klasy, aby użyć jej `Write` metody.</span><span class="sxs-lookup"><span data-stu-id="e2666-108">A class can create an instance of the `MessageWriter` class to make use of its `Write` method.</span></span> <span data-ttu-id="e2666-109">W poniższym przykładzie `MessageWriter` Klasa jest zależna od `Worker` klasy:</span><span class="sxs-lookup"><span data-stu-id="e2666-109">In the following example, the `MessageWriter` class is a dependency of the `Worker` class:</span></span>

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

<span data-ttu-id="e2666-110">Klasa tworzy i bezpośrednio zależy od `MessageWriter` klasy.</span><span class="sxs-lookup"><span data-stu-id="e2666-110">The class creates and directly depends on the `MessageWriter` class.</span></span> <span data-ttu-id="e2666-111">Stałe kodowane, takie jak w poprzednim przykładzie, są problematyczne i należy je unikać z następujących powodów:</span><span class="sxs-lookup"><span data-stu-id="e2666-111">Hard-coded dependencies, such as in the previous example, are problematic and should be avoided for the following reasons:</span></span>

- <span data-ttu-id="e2666-112">Aby zastąpić `MessageWriter` inną implementacją, `Worker` należy zmodyfikować klasę.</span><span class="sxs-lookup"><span data-stu-id="e2666-112">To replace `MessageWriter` with a different implementation, the `Worker` class must be modified.</span></span>
- <span data-ttu-id="e2666-113">Jeśli `MessageWriter` ma zależności, muszą one być również konfigurowane przez `Worker` klasę.</span><span class="sxs-lookup"><span data-stu-id="e2666-113">If `MessageWriter` has dependencies, they must also be configured by the `Worker` class.</span></span> <span data-ttu-id="e2666-114">W dużym projekcie z wieloma klasami, w zależności od tego `MessageWriter` , kod konfiguracji jest rozmieszczany w całej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e2666-114">In a large project with multiple classes depending on `MessageWriter`, the configuration code becomes scattered across the app.</span></span>
- <span data-ttu-id="e2666-115">Ta implementacja jest trudna do testowania jednostkowego.</span><span class="sxs-lookup"><span data-stu-id="e2666-115">This implementation is difficult to unit test.</span></span> <span data-ttu-id="e2666-116">Aplikacja powinna używać klasy imitacji lub zastępczej `MessageWriter` , która nie jest możliwa w przypadku tego podejścia.</span><span class="sxs-lookup"><span data-stu-id="e2666-116">The app should use a mock or stub `MessageWriter` class, which isn't possible with this approach.</span></span>

<span data-ttu-id="e2666-117">Iniekcja zależności eliminuje te problemy w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="e2666-117">Dependency injection addresses these problems through:</span></span>

- <span data-ttu-id="e2666-118">Użycie interfejsu lub klasy bazowej do abstrakcyjnej implementacji zależności.</span><span class="sxs-lookup"><span data-stu-id="e2666-118">The use of an interface or base class to abstract the dependency implementation.</span></span>
- <span data-ttu-id="e2666-119">Rejestracja zależności w kontenerze usługi.</span><span class="sxs-lookup"><span data-stu-id="e2666-119">Registration of the dependency in a service container.</span></span> <span data-ttu-id="e2666-120">Platforma .NET udostępnia wbudowany kontener usług <xref:System.IServiceProvider> .</span><span class="sxs-lookup"><span data-stu-id="e2666-120">.NET provides a built-in service container, <xref:System.IServiceProvider>.</span></span> <span data-ttu-id="e2666-121">Usługi są zwykle rejestrowane w momencie uruchomienia aplikacji i dołączane do <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection> .</span><span class="sxs-lookup"><span data-stu-id="e2666-121">Services are typically registered at the app's start-up, and appended to an <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="e2666-122">Po dodaniu wszystkich usług należy użyć <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> programu, aby utworzyć kontener usługi.</span><span class="sxs-lookup"><span data-stu-id="e2666-122">Once all services are added, you use <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> to create the service container.</span></span>
- <span data-ttu-id="e2666-123">*Iniekcja* usługi do konstruktora klasy, w której jest używana.</span><span class="sxs-lookup"><span data-stu-id="e2666-123">*Injection* of the service into the constructor of the class where it's used.</span></span> <span data-ttu-id="e2666-124">Struktura przejmuje odpowiedzialność za utworzenie wystąpienia zależności i jego likwidację, gdy nie jest już potrzebny.</span><span class="sxs-lookup"><span data-stu-id="e2666-124">The framework takes on the responsibility of creating an instance of the dependency and disposing of it when it's no longer needed.</span></span>

<span data-ttu-id="e2666-125">Na przykład `IMessageWriter` Interfejs definiuje `Write` metodę:</span><span class="sxs-lookup"><span data-stu-id="e2666-125">As an example, the `IMessageWriter` interface defines the `Write` method:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/IMessageWriter.cs":::

<span data-ttu-id="e2666-126">Ten interfejs jest implementowany przez konkretny typ `MessageWriter` :</span><span class="sxs-lookup"><span data-stu-id="e2666-126">This interface is implemented by a concrete type, `MessageWriter`:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/MessageWriter.cs":::

<span data-ttu-id="e2666-127">Przykładowy kod rejestruje `IMessageWriter` usługę w konkretnym typie `MessageWriter` .</span><span class="sxs-lookup"><span data-stu-id="e2666-127">The sample code registers the `IMessageWriter` service with the concrete type `MessageWriter`.</span></span> <span data-ttu-id="e2666-128"><xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A>Metoda rejestruje usługę z okresem istnienia w określonym zakresie, okresem istnienia pojedynczego żądania.</span><span class="sxs-lookup"><span data-stu-id="e2666-128">The <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A> method registers the service with a scoped lifetime, the lifetime of a single request.</span></span> <span data-ttu-id="e2666-129">[Okresy istnienia usługi](#service-lifetimes) zostały opisane w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="e2666-129">[Service lifetimes](#service-lifetimes) are described later in this topic.</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/Program.cs" highlight="16":::

<span data-ttu-id="e2666-130">W przykładowej aplikacji `IMessageWriter` jest wymagana usługa, która jest używana do wywołania `Write` metody:</span><span class="sxs-lookup"><span data-stu-id="e2666-130">In the sample app, the `IMessageWriter` service is requested and used to call the `Write` method:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/Worker.cs":::

<span data-ttu-id="e2666-131">Przy użyciu wzorca DI, usługa procesu roboczego:</span><span class="sxs-lookup"><span data-stu-id="e2666-131">By using the DI pattern, the worker service:</span></span>

- <span data-ttu-id="e2666-132">Nie używa konkretnego typu `MessageWriter` , tylko `IMessageWriter` interfejsu, który implementuje go.</span><span class="sxs-lookup"><span data-stu-id="e2666-132">Doesn't use the concrete type `MessageWriter`, only the `IMessageWriter` interface that implements it.</span></span> <span data-ttu-id="e2666-133">Dzięki temu można łatwo zmienić implementację używaną przez kontroler bez modyfikowania kontrolera.</span><span class="sxs-lookup"><span data-stu-id="e2666-133">That makes it easy to change the implementation that the controller uses without modifying the controller.</span></span>
- <span data-ttu-id="e2666-134">Nie tworzy wystąpienia `MessageWriter` , jest tworzone przez element di kontener.</span><span class="sxs-lookup"><span data-stu-id="e2666-134">Doesn't create an instance of `MessageWriter`, it's created by the DI container.</span></span>

<span data-ttu-id="e2666-135">Implementację `IMessageWriter` interfejsu można ulepszyć za pomocą wbudowanego interfejsu API rejestrowania:</span><span class="sxs-lookup"><span data-stu-id="e2666-135">The implementation of the `IMessageWriter` interface can be improved by using the built-in logging API:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/LoggingMessageWriter.cs":::

<span data-ttu-id="e2666-136">Zaktualizowana `ConfigureServices` Metoda rejestruje nową `IMessageWriter` implementację:</span><span class="sxs-lookup"><span data-stu-id="e2666-136">The updated `ConfigureServices` method registers the new `IMessageWriter` implementation:</span></span>

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureServices((_, services) =>
            services.AddHostedService<Worker>()
                    .AddScoped<IMessageWriter, LoggingMessageWriter>());
```

<span data-ttu-id="e2666-137">`LoggingMessageWriter` zależy od <xref:Microsoft.Extensions.Logging.ILogger%601> , który z nich żąda w konstruktorze.</span><span class="sxs-lookup"><span data-stu-id="e2666-137">`LoggingMessageWriter` depends on <xref:Microsoft.Extensions.Logging.ILogger%601>, which it requests in the constructor.</span></span> <span data-ttu-id="e2666-138">`ILogger<TCategoryName>` to [Usługa udostępniona przez platformę](#framework-provided-services).</span><span class="sxs-lookup"><span data-stu-id="e2666-138">`ILogger<TCategoryName>` is a [framework-provided service](#framework-provided-services).</span></span>

<span data-ttu-id="e2666-139">Użycie iniekcji zależności w łańcuchu nie jest nietypowe.</span><span class="sxs-lookup"><span data-stu-id="e2666-139">It's not unusual to use dependency injection in a chained fashion.</span></span> <span data-ttu-id="e2666-140">Każda żądana zależność z kolei żąda własnych zależności.</span><span class="sxs-lookup"><span data-stu-id="e2666-140">Each requested dependency in turn requests its own dependencies.</span></span> <span data-ttu-id="e2666-141">Kontener rozwiązuje zależności w grafie i zwraca w pełni rozwiązane usługi.</span><span class="sxs-lookup"><span data-stu-id="e2666-141">The container resolves the dependencies in the graph and returns the fully resolved service.</span></span> <span data-ttu-id="e2666-142">Zestaw zbiorczy zależności, które muszą zostać rozwiązane, jest zwykle nazywany *drzewem zależności*, *wykresem zależności* lub *wykresem obiektów*.</span><span class="sxs-lookup"><span data-stu-id="e2666-142">The collective set of dependencies that must be resolved is typically referred to as a *dependency tree*, *dependency graph*, or *object graph*.</span></span>

<span data-ttu-id="e2666-143">Kontener jest rozpoznawany `ILogger<TCategoryName>` przez wykorzystanie [(rodzajowe) otwartych typów](/dotnet/csharp/language-reference/language-specification/types#open-and-closed-types), eliminując konieczność zarejestrowania każdego [(rodzajowego) konstruowanego typu](/dotnet/csharp/language-reference/language-specification/types#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="e2666-143">The container resolves `ILogger<TCategoryName>` by taking advantage of [(generic) open types](/dotnet/csharp/language-reference/language-specification/types#open-and-closed-types), eliminating the need to register every [(generic) constructed type](/dotnet/csharp/language-reference/language-specification/types#constructed-types).</span></span>

<span data-ttu-id="e2666-144">W terminologii wtrysku zależności, usługa:</span><span class="sxs-lookup"><span data-stu-id="e2666-144">In dependency injection terminology, a service:</span></span>

- <span data-ttu-id="e2666-145">Jest zazwyczaj obiektem, który udostępnia usługę innym obiektom, takim jak `IMessageWriter` Usługa.</span><span class="sxs-lookup"><span data-stu-id="e2666-145">Is typically an object that provides a service to other objects, such as the `IMessageWriter` service.</span></span>
- <span data-ttu-id="e2666-146">Nie jest powiązany z usługą sieci Web, chociaż usługa może korzystać z usługi sieci Web.</span><span class="sxs-lookup"><span data-stu-id="e2666-146">Is not related to a web service, although the service may use a web service.</span></span>

<span data-ttu-id="e2666-147">Struktura zapewnia niezawodny system rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="e2666-147">The framework provides a robust logging system.</span></span> <span data-ttu-id="e2666-148">`IMessageWriter`Implementacje opisane w powyższych przykładach zostały opracowane w celu zademonstrowania podstawowych di, a nie do zaimplementowania rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="e2666-148">The `IMessageWriter` implementations shown in the preceding examples were written to demonstrate basic DI, not to implement logging.</span></span> <span data-ttu-id="e2666-149">Większość aplikacji nie musi być w trakcie pisania rejestratorów.</span><span class="sxs-lookup"><span data-stu-id="e2666-149">Most apps shouldn't need to write loggers.</span></span> <span data-ttu-id="e2666-150">Poniższy kod ilustruje użycie domyślnego rejestrowania, które wymaga zarejestrowania tylko `Worker` `ConfigureServices` jako usługi hostowanej <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A> :</span><span class="sxs-lookup"><span data-stu-id="e2666-150">The following code demonstrates using the default logging, which only requires the `Worker` to be registered in `ConfigureServices` as a hosted service <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A>:</span></span>

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

<span data-ttu-id="e2666-151">Korzystając z powyższego kodu, nie ma potrzeby aktualizowania `ConfigureServices` , ponieważ rejestrowanie jest dostarczane przez strukturę.</span><span class="sxs-lookup"><span data-stu-id="e2666-151">Using the preceding code, there is no need to update `ConfigureServices`, because logging is provided by the framework.</span></span>

## <a name="register-groups-of-services-with-extension-methods"></a><span data-ttu-id="e2666-152">Rejestrowanie grup usług przy użyciu metod rozszerzających</span><span class="sxs-lookup"><span data-stu-id="e2666-152">Register groups of services with extension methods</span></span>

<span data-ttu-id="e2666-153">Rozszerzenia Microsoft używają Konwencji do rejestracji grupy powiązanych usług.</span><span class="sxs-lookup"><span data-stu-id="e2666-153">Microsoft Extensions uses a convention for registering a group of related services.</span></span> <span data-ttu-id="e2666-154">Konwencja polega na użyciu pojedynczej `Add{GROUP_NAME}` metody rozszerzenia w celu zarejestrowania wszystkich usług wymaganych przez funkcję platformy.</span><span class="sxs-lookup"><span data-stu-id="e2666-154">The convention is to use a single `Add{GROUP_NAME}` extension method to register all of the services required by a framework feature.</span></span> <span data-ttu-id="e2666-155">Na przykład <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> Metoda rozszerzenia rejestruje wszystkie usługi wymagane do korzystania z opcji.</span><span class="sxs-lookup"><span data-stu-id="e2666-155">For example, the <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> extension method registers all of the services required for using options.</span></span>

## <a name="framework-provided-services"></a><span data-ttu-id="e2666-156">Usługi udostępniane przez platformę</span><span class="sxs-lookup"><span data-stu-id="e2666-156">Framework-provided services</span></span>

<span data-ttu-id="e2666-157">`ConfigureServices`Metoda rejestruje usługi, z których korzysta aplikacja, w tym funkcje platformy.</span><span class="sxs-lookup"><span data-stu-id="e2666-157">The `ConfigureServices` method registers services that the app uses, including platform features.</span></span> <span data-ttu-id="e2666-158">Początkowo `IServiceCollection` dostarczone z `ConfigureServices` usługami zdefiniowanymi przez platformę, w zależności od [konfiguracji hosta](generic-host.md#host-configuration).</span><span class="sxs-lookup"><span data-stu-id="e2666-158">Initially, the `IServiceCollection` provided to `ConfigureServices` has services defined by the framework depending on [how the host was configured](generic-host.md#host-configuration).</span></span> <span data-ttu-id="e2666-159">W przypadku aplikacji opartych na szablonach platformy .NET struktura rejestruje setki usług.</span><span class="sxs-lookup"><span data-stu-id="e2666-159">For apps based on the .NET templates, the framework registers hundreds of services.</span></span>

<span data-ttu-id="e2666-160">W poniższej tabeli przedstawiono niewielki przykład następujących usług zarejestrowanych w ramach platformy:</span><span class="sxs-lookup"><span data-stu-id="e2666-160">The following table lists a small sample of these framework-registered services:</span></span>

| <span data-ttu-id="e2666-161">Typ usługi</span><span class="sxs-lookup"><span data-stu-id="e2666-161">Service Type</span></span>                                                                       | <span data-ttu-id="e2666-162">Okres istnienia</span><span class="sxs-lookup"><span data-stu-id="e2666-162">Lifetime</span></span>  |
|------------------------------------------------------------------------------------|-----------|
| <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime>                       | <span data-ttu-id="e2666-163">Pojedynczego</span><span class="sxs-lookup"><span data-stu-id="e2666-163">Singleton</span></span> |
| <xref:Microsoft.Extensions.Logging.ILogger%601?displayProperty=fullName>           | <span data-ttu-id="e2666-164">Pojedynczego</span><span class="sxs-lookup"><span data-stu-id="e2666-164">Singleton</span></span> |
| <xref:Microsoft.Extensions.Logging.ILoggerFactory?displayProperty=fullName>        | <span data-ttu-id="e2666-165">Pojedynczego</span><span class="sxs-lookup"><span data-stu-id="e2666-165">Singleton</span></span> |
| <xref:Microsoft.Extensions.ObjectPool.ObjectPoolProvider?displayProperty=fullName> | <span data-ttu-id="e2666-166">Pojedynczego</span><span class="sxs-lookup"><span data-stu-id="e2666-166">Singleton</span></span> |
| <xref:Microsoft.Extensions.Options.IConfigureOptions%601?displayProperty=fullName> | <span data-ttu-id="e2666-167">Administracyjnej</span><span class="sxs-lookup"><span data-stu-id="e2666-167">Transient</span></span> |
| <xref:Microsoft.Extensions.Options.IOptions%601?displayProperty=fullName>          | <span data-ttu-id="e2666-168">Pojedynczego</span><span class="sxs-lookup"><span data-stu-id="e2666-168">Singleton</span></span> |
| <xref:System.Diagnostics.DiagnosticListener?displayProperty=fullName>              | <span data-ttu-id="e2666-169">Pojedynczego</span><span class="sxs-lookup"><span data-stu-id="e2666-169">Singleton</span></span> |
| <xref:System.Diagnostics.DiagnosticSource?displayProperty=fullName>                | <span data-ttu-id="e2666-170">Pojedynczego</span><span class="sxs-lookup"><span data-stu-id="e2666-170">Singleton</span></span> |

## <a name="service-lifetimes"></a><span data-ttu-id="e2666-171">Okresy istnienia usługi</span><span class="sxs-lookup"><span data-stu-id="e2666-171">Service lifetimes</span></span>

<span data-ttu-id="e2666-172">Usługi mogą być zarejestrowane przy użyciu jednego z następujących okresów istnienia:</span><span class="sxs-lookup"><span data-stu-id="e2666-172">Services can be registered with one of the following lifetimes:</span></span>

- <span data-ttu-id="e2666-173">Administracyjnej</span><span class="sxs-lookup"><span data-stu-id="e2666-173">Transient</span></span>
- <span data-ttu-id="e2666-174">Zakresie</span><span class="sxs-lookup"><span data-stu-id="e2666-174">Scoped</span></span>
- <span data-ttu-id="e2666-175">Pojedynczego</span><span class="sxs-lookup"><span data-stu-id="e2666-175">Singleton</span></span>

<span data-ttu-id="e2666-176">W poniższych sekcjach opisano wszystkie poprzednie okresy istnienia.</span><span class="sxs-lookup"><span data-stu-id="e2666-176">The following sections describe each of the preceding lifetimes.</span></span> <span data-ttu-id="e2666-177">Wybierz odpowiedni okres istnienia dla każdej zarejestrowanej usługi.</span><span class="sxs-lookup"><span data-stu-id="e2666-177">Choose an appropriate lifetime for each registered service.</span></span>

### <a name="transient"></a><span data-ttu-id="e2666-178">Administracyjnej</span><span class="sxs-lookup"><span data-stu-id="e2666-178">Transient</span></span>

<span data-ttu-id="e2666-179">Przejściowe usługi okresu istnienia są tworzone za każdym razem, gdy zażądają one kontenera usług.</span><span class="sxs-lookup"><span data-stu-id="e2666-179">Transient lifetime services are created each time they're requested from the service container.</span></span> <span data-ttu-id="e2666-180">Ten okres istnienia działa najlepiej w przypadku lekkich i bezstanowych usług.</span><span class="sxs-lookup"><span data-stu-id="e2666-180">This lifetime works best for lightweight, stateless services.</span></span> <span data-ttu-id="e2666-181">Zarejestruj usługi przejściowe w usłudze <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddTransient%2A> .</span><span class="sxs-lookup"><span data-stu-id="e2666-181">Register transient services with <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddTransient%2A>.</span></span>

<span data-ttu-id="e2666-182">W przypadku aplikacji, które przetwarzają żądania, usługi przejściowe są usuwane na końcu żądania.</span><span class="sxs-lookup"><span data-stu-id="e2666-182">In apps that process requests, transient services are disposed at the end of the request.</span></span>

### <a name="scoped"></a><span data-ttu-id="e2666-183">Zakresie</span><span class="sxs-lookup"><span data-stu-id="e2666-183">Scoped</span></span>

<span data-ttu-id="e2666-184">W przypadku aplikacji sieci Web okres istnienia w zakresie wskazuje, że usługi są tworzone raz dla każdego żądania klienta (połączenie).</span><span class="sxs-lookup"><span data-stu-id="e2666-184">For web applications a scoped lifetime indicates that services are created once per client request (connection).</span></span> <span data-ttu-id="e2666-185">Zarejestruj usługi z zakresem w usłudze <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A> .</span><span class="sxs-lookup"><span data-stu-id="e2666-185">Register scoped services with <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A>.</span></span>

<span data-ttu-id="e2666-186">W przypadku aplikacji, które przetwarzają żądania, usługi o określonym zakresie są usuwane na końcu żądania.</span><span class="sxs-lookup"><span data-stu-id="e2666-186">In apps that process requests, scoped services are disposed at the end of the request.</span></span>

<span data-ttu-id="e2666-187">W przypadku korzystania z Entity Framework Core <xref:Microsoft.Extensions.DependencyInjection.EntityFrameworkServiceCollectionExtensions.AddDbContext%2A> Metoda rozszerzenia rejestruje `DbContext` typy z okresem istnienia w zakresie domyślnie.</span><span class="sxs-lookup"><span data-stu-id="e2666-187">When using Entity Framework Core, the <xref:Microsoft.Extensions.DependencyInjection.EntityFrameworkServiceCollectionExtensions.AddDbContext%2A> extension method registers `DbContext` types with a scoped lifetime by default.</span></span>

> [!NOTE]
> <span data-ttu-id="e2666-188">**Nie należy** wyłączać usługi o określonym zakresie z pojedynczej i należy zachować ostrożność bez pośredniego, na przykład za pośrednictwem usługi przejściowej.</span><span class="sxs-lookup"><span data-stu-id="e2666-188">Do \***not** _ resolve a scoped service from a singleton and be careful not to do so indirectly, for example, through a transient service.</span></span> <span data-ttu-id="e2666-189">Może to spowodować, że usługa będzie mieć nieprawidłowy stan podczas przetwarzania kolejnych żądań.</span><span class="sxs-lookup"><span data-stu-id="e2666-189">It may cause the service to have incorrect state when processing subsequent requests.</span></span> <span data-ttu-id="e2666-190">Warto:</span><span class="sxs-lookup"><span data-stu-id="e2666-190">It's fine to:</span></span>
>
> - <span data-ttu-id="e2666-191">Rozwiązanie pojedynczej usługi z usługi w zakresie lub przejściowej.</span><span class="sxs-lookup"><span data-stu-id="e2666-191">Resolve a singleton service from a scoped or transient service.</span></span>
> - <span data-ttu-id="e2666-192">Rozwiąż usługę objętą zakresem z innej usługi w zakresie lub przejściowej.</span><span class="sxs-lookup"><span data-stu-id="e2666-192">Resolve a scoped service from another scoped or transient service.</span></span>

<span data-ttu-id="e2666-193">Domyślnie w środowisku programistycznym rozpoznawanie usługi z innej usługi o dłuższym okresie istnienia zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="e2666-193">By default, in the development environment, resolving a service from another service with a longer lifetime throws an exception.</span></span> <span data-ttu-id="e2666-194">Aby uzyskać więcej informacji, zobacz [Walidacja zakresu](#scope-validation).</span><span class="sxs-lookup"><span data-stu-id="e2666-194">For more information, see [Scope validation](#scope-validation).</span></span>

### <a name="singleton"></a><span data-ttu-id="e2666-195">Pojedynczego</span><span class="sxs-lookup"><span data-stu-id="e2666-195">Singleton</span></span>

<span data-ttu-id="e2666-196">Są tworzone pojedyncze usługi okresu istnienia:</span><span class="sxs-lookup"><span data-stu-id="e2666-196">Singleton lifetime services are created either:</span></span>

- <span data-ttu-id="e2666-197">Podczas pierwszego żądania.</span><span class="sxs-lookup"><span data-stu-id="e2666-197">The first time they're requested.</span></span>
- <span data-ttu-id="e2666-198">Przez dewelopera, gdy udostępnia wystąpienie implementacji bezpośrednio do kontenera.</span><span class="sxs-lookup"><span data-stu-id="e2666-198">By the developer, when providing an implementation instance directly to the container.</span></span> <span data-ttu-id="e2666-199">Takie podejście jest rzadko niezbędne.</span><span class="sxs-lookup"><span data-stu-id="e2666-199">This approach is rarely needed.</span></span>

<span data-ttu-id="e2666-200">Każde kolejne żądanie implementacji usługi z kontenera iniekcji zależności używa tego samego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="e2666-200">Every subsequent request of the service implementation from the dependency injection container uses the same instance.</span></span> <span data-ttu-id="e2666-201">Jeśli aplikacja wymaga pojedynczych zachowań, zezwól kontenerowi usługi na zarządzanie okresem istnienia usługi.</span><span class="sxs-lookup"><span data-stu-id="e2666-201">If the app requires singleton behavior, allow the service container to manage the service's lifetime.</span></span> <span data-ttu-id="e2666-202">Nie Wdrażaj wzorca projektu singleton i podawanie kodu do usuwania pojedynczych elementów.</span><span class="sxs-lookup"><span data-stu-id="e2666-202">Don't implement the singleton design pattern and provide code to dispose of the singleton.</span></span> <span data-ttu-id="e2666-203">Usługi nigdy nie powinny być usuwane przez kod, który rozwiązał usługę z kontenera.</span><span class="sxs-lookup"><span data-stu-id="e2666-203">Services should never be disposed by code that resolved the service from the container.</span></span> <span data-ttu-id="e2666-204">Jeśli typ lub fabryka są zarejestrowane jako pojedyncze, kontener usuwa pojedyncze automatycznie.</span><span class="sxs-lookup"><span data-stu-id="e2666-204">If a type or factory is registered as a singleton, the container disposes the singleton automatically.</span></span>

<span data-ttu-id="e2666-205">Zarejestruj usługi pojedyncze przy użyciu programu <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A> .</span><span class="sxs-lookup"><span data-stu-id="e2666-205">Register singleton services with <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A>.</span></span> <span data-ttu-id="e2666-206">Usługi pojedyncze muszą być bezpieczne dla wątków i często używane w usługach bezstanowych.</span><span class="sxs-lookup"><span data-stu-id="e2666-206">Singleton services must be thread safe and are often used in stateless services.</span></span>

<span data-ttu-id="e2666-207">W przypadku aplikacji, które przetwarzają żądania, pojedyncze usługi są usuwane, gdy <xref:Microsoft.Extensions.DependencyInjection.ServiceProvider> zostanie usunięty podczas zamykania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e2666-207">In apps that process requests, singleton services are disposed when the <xref:Microsoft.Extensions.DependencyInjection.ServiceProvider> is disposed on application shutdown.</span></span> <span data-ttu-id="e2666-208">Ponieważ pamięć nie jest wydawana do momentu wyłączenia aplikacji, należy rozważyć użycie pamięci w ramach pojedynczej usługi.</span><span class="sxs-lookup"><span data-stu-id="e2666-208">Because memory is not released until the app is shut down, consider memory use with a singleton service.</span></span>

> [!WARNING]
> <span data-ttu-id="e2666-209">_*_Nie_*_ należy rozwiązywać usługi z zakresem z pojedynczej.</span><span class="sxs-lookup"><span data-stu-id="e2666-209">Do _*_not_*_ resolve a scoped service from a singleton.</span></span> <span data-ttu-id="e2666-210">Może to spowodować, że usługa będzie mieć nieprawidłowy stan podczas przetwarzania kolejnych żądań.</span><span class="sxs-lookup"><span data-stu-id="e2666-210">It may cause the service to have incorrect state when processing subsequent requests.</span></span> <span data-ttu-id="e2666-211">Rozwiązaniem jest rozwiązanie pojedynczej usługi z poziomu usługi w zakresie lub przejściowej.</span><span class="sxs-lookup"><span data-stu-id="e2666-211">It's fine to resolve a singleton service from a scoped or transient service.</span></span>

## <a name="service-registration-methods"></a><span data-ttu-id="e2666-212">Metody rejestracji usług</span><span class="sxs-lookup"><span data-stu-id="e2666-212">Service registration methods</span></span>

<span data-ttu-id="e2666-213">Struktura zawiera metody rozszerzenia rejestracji usług, które są przydatne w określonych scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="e2666-213">The framework provides service registration extension methods that are useful in specific scenarios:</span></span>

| <span data-ttu-id="e2666-214">Metoda</span><span class="sxs-lookup"><span data-stu-id="e2666-214">Method</span></span> | <span data-ttu-id="e2666-215">Automatyczny</span><span class="sxs-lookup"><span data-stu-id="e2666-215">Automatic</span></span><br><span data-ttu-id="e2666-216">object</span><span class="sxs-lookup"><span data-stu-id="e2666-216">object</span></span><br><span data-ttu-id="e2666-217">myśl</span><span class="sxs-lookup"><span data-stu-id="e2666-217">disposal</span></span> | <span data-ttu-id="e2666-218">Wiele</span><span class="sxs-lookup"><span data-stu-id="e2666-218">Multiple</span></span><br><span data-ttu-id="e2666-219">implementacje</span><span class="sxs-lookup"><span data-stu-id="e2666-219">implementations</span></span> | <span data-ttu-id="e2666-220">Przekaż argumenty</span><span class="sxs-lookup"><span data-stu-id="e2666-220">Pass args</span></span> |
|--|:-:|:-:|:-:|
| `Add{LIFETIME}<{SERVICE}, {IMPLEMENTATION}>()`<br><br><span data-ttu-id="e2666-221">Przykład:</span><span class="sxs-lookup"><span data-stu-id="e2666-221">Example:</span></span><br><br>`services.AddSingleton<IMyDep, MyDep>();` | <span data-ttu-id="e2666-222">Tak</span><span class="sxs-lookup"><span data-stu-id="e2666-222">Yes</span></span> | <span data-ttu-id="e2666-223">Tak</span><span class="sxs-lookup"><span data-stu-id="e2666-223">Yes</span></span> | <span data-ttu-id="e2666-224">Nie</span><span class="sxs-lookup"><span data-stu-id="e2666-224">No</span></span> |
| `Add{LIFETIME}<{SERVICE}>(sp => new {IMPLEMENTATION})`<br><br><span data-ttu-id="e2666-225">Przykłady:</span><span class="sxs-lookup"><span data-stu-id="e2666-225">Examples:</span></span><br><br>`services.AddSingleton<IMyDep>(sp => new MyDep());`<br>`services.AddSingleton<IMyDep>(sp => new MyDep(99));` | <span data-ttu-id="e2666-226">Tak</span><span class="sxs-lookup"><span data-stu-id="e2666-226">Yes</span></span> | <span data-ttu-id="e2666-227">Tak</span><span class="sxs-lookup"><span data-stu-id="e2666-227">Yes</span></span> | <span data-ttu-id="e2666-228">Tak</span><span class="sxs-lookup"><span data-stu-id="e2666-228">Yes</span></span> |
| `Add{LIFETIME}<{IMPLEMENTATION}>()`<br><br><span data-ttu-id="e2666-229">Przykład:</span><span class="sxs-lookup"><span data-stu-id="e2666-229">Example:</span></span><br><br>`services.AddSingleton<MyDep>();` | <span data-ttu-id="e2666-230">Tak</span><span class="sxs-lookup"><span data-stu-id="e2666-230">Yes</span></span> | <span data-ttu-id="e2666-231">Nie</span><span class="sxs-lookup"><span data-stu-id="e2666-231">No</span></span> | <span data-ttu-id="e2666-232">Nie</span><span class="sxs-lookup"><span data-stu-id="e2666-232">No</span></span> |
| `AddSingleton<{SERVICE}>(new {IMPLEMENTATION})`<br><br><span data-ttu-id="e2666-233">Przykłady:</span><span class="sxs-lookup"><span data-stu-id="e2666-233">Examples:</span></span><br><br>`services.AddSingleton<IMyDep>(new MyDep());`<br>`services.AddSingleton<IMyDep>(new MyDep(99));` | <span data-ttu-id="e2666-234">Nie</span><span class="sxs-lookup"><span data-stu-id="e2666-234">No</span></span> | <span data-ttu-id="e2666-235">Tak</span><span class="sxs-lookup"><span data-stu-id="e2666-235">Yes</span></span> | <span data-ttu-id="e2666-236">Tak</span><span class="sxs-lookup"><span data-stu-id="e2666-236">Yes</span></span> |
| `AddSingleton(new {IMPLEMENTATION})`<br><br><span data-ttu-id="e2666-237">Przykłady:</span><span class="sxs-lookup"><span data-stu-id="e2666-237">Examples:</span></span><br><br>`services.AddSingleton(new MyDep());`<br>`services.AddSingleton(new MyDep(99));` | <span data-ttu-id="e2666-238">Nie</span><span class="sxs-lookup"><span data-stu-id="e2666-238">No</span></span> | <span data-ttu-id="e2666-239">Nie</span><span class="sxs-lookup"><span data-stu-id="e2666-239">No</span></span> | <span data-ttu-id="e2666-240">Tak</span><span class="sxs-lookup"><span data-stu-id="e2666-240">Yes</span></span> |

<span data-ttu-id="e2666-241">Aby uzyskać więcej informacji na temat usuwania typów, zobacz sekcję [dotyczącą usuwania usług](dependency-injection-guidelines.md#disposal-of-services) .</span><span class="sxs-lookup"><span data-stu-id="e2666-241">For more information on type disposal, see the [Disposal of services](dependency-injection-guidelines.md#disposal-of-services) section.</span></span>

<span data-ttu-id="e2666-242">Zarejestrowanie usługi z użyciem tylko typu implementacji jest równoznaczne z zarejestrowaniem tej usługi z tą samą implementacją i typem usługi.</span><span class="sxs-lookup"><span data-stu-id="e2666-242">Registering a service with only an implementation type is equivalent to registering that service with the same implementation and service type.</span></span> <span data-ttu-id="e2666-243">Dlatego nie można zarejestrować wielu implementacji usługi przy użyciu metod, które nie pobierają jawnego typu usługi.</span><span class="sxs-lookup"><span data-stu-id="e2666-243">This is why multiple implementations of a service cannot be registered using the methods that don't take an explicit service type.</span></span> <span data-ttu-id="e2666-244">Metody te mogą rejestrować wiele _instances \* usługi, ale wszystkie będą miały ten sam typ *implementacji* .</span><span class="sxs-lookup"><span data-stu-id="e2666-244">These methods can register multiple _instances\* of a service, but they will all have the same *implementation* type.</span></span>

<span data-ttu-id="e2666-245">Wszystkie powyższe metody rejestracji usług mogą służyć do rejestrowania wielu wystąpień usług tego samego typu usługi.</span><span class="sxs-lookup"><span data-stu-id="e2666-245">Any of the above service registration methods can be used to register multiple service instances of the same service type.</span></span> <span data-ttu-id="e2666-246">W poniższym przykładzie `AddSingleton` jest wywoływana dwukrotnie `IMessageWriter` jako typ usługi.</span><span class="sxs-lookup"><span data-stu-id="e2666-246">In the following example, `AddSingleton` is called twice with `IMessageWriter` as the service type.</span></span> <span data-ttu-id="e2666-247">Drugie wywołanie `AddSingleton` przesłania poprzednią, gdy zostanie rozpoznane jako `IMessageWriter` i dodaje do poprzedniego, gdy wiele usług jest rozpoznawanych za pośrednictwem `IEnumerable<IMessageWriter>` .</span><span class="sxs-lookup"><span data-stu-id="e2666-247">The second call to `AddSingleton` overrides the previous one when resolved as `IMessageWriter` and adds to the previous one when multiple services are resolved via `IEnumerable<IMessageWriter>`.</span></span> <span data-ttu-id="e2666-248">Usługi są wyświetlane w kolejności, w jakiej zostały zarejestrowane po rozwiązaniu przez `IEnumerable<{SERVICE}>` .</span><span class="sxs-lookup"><span data-stu-id="e2666-248">Services appear in the order they were registered when resolved via `IEnumerable<{SERVICE}>`.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-ienumerable/Program.cs" highlight="19-24":::

<span data-ttu-id="e2666-249">Poprzedni przykładowy kod źródłowy rejestruje dwie implementacje programu `IMessageWriter` .</span><span class="sxs-lookup"><span data-stu-id="e2666-249">The preceding sample source code registers two implementations of the `IMessageWriter`.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-ienumerable/ExampleService.cs" highlight="9-18":::

<span data-ttu-id="e2666-250">`ExampleService`Definiuje dwa parametry konstruktora; pojedyncze `IMessageWriter` i `IEnumerable<IMessageWriter>` .</span><span class="sxs-lookup"><span data-stu-id="e2666-250">The `ExampleService` defines two constructor parameters; a single `IMessageWriter`, and an `IEnumerable<IMessageWriter>`.</span></span> <span data-ttu-id="e2666-251">Pojedynczy `IMessageWriter` to ostatni implementacji, który został zarejestrowany, podczas gdy `IEnumerable<IMessageWriter>` reprezentuje wszystkie zarejestrowane implementacje.</span><span class="sxs-lookup"><span data-stu-id="e2666-251">The single `IMessageWriter` is the last implemenation to have been registered, whereas the `IEnumerable<IMessageWriter>` represents all registered implementations.</span></span>

<span data-ttu-id="e2666-252">Struktura zawiera również `TryAdd{LIFETIME}` metody rozszerzające, które rejestrują usługę tylko wtedy, gdy nie zarejestrowano jeszcze implementacji.</span><span class="sxs-lookup"><span data-stu-id="e2666-252">The framework also provides `TryAdd{LIFETIME}` extension methods, which register the service only if there isn't already an implementation registered.</span></span>

<span data-ttu-id="e2666-253">W poniższym przykładzie wywołanie `AddSingleton` rejestruje się `ConsoleMessageWriter` jako implementacja dla `IMessageWriter` .</span><span class="sxs-lookup"><span data-stu-id="e2666-253">In the following example, the call to `AddSingleton` registers `ConsoleMessageWriter` as an implementation for `IMessageWriter`.</span></span> <span data-ttu-id="e2666-254">Wywołanie nie `TryAddSingleton` działa, ponieważ `IMessageWriter` ma już zarejestrowaną implementację:</span><span class="sxs-lookup"><span data-stu-id="e2666-254">The call to `TryAddSingleton` has no effect because `IMessageWriter` already has a registered implementation:</span></span>

```csharp
services.AddSingleton<IMessageWriter, ConsoleMessageWriter>();
services.TryAddSingleton<IMessageWriter, LoggingMessageWriter>();
```

<span data-ttu-id="e2666-255">`TryAddSingleton`Nie ma żadnego efektu, ponieważ został już dodany i próba "try" zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="e2666-255">The `TryAddSingleton` has no effect, as it was already added and the "try" will fail.</span></span> <span data-ttu-id="e2666-256">Mogą to być `ExampleService` następujące:</span><span class="sxs-lookup"><span data-stu-id="e2666-256">The `ExampleService` would assert the following:</span></span>

```csharp
public class ExampleService
{
    public ExampleService(
        IMessageWriter messageWriter,
        IEnumerable<IMessageWriter> messageWriters)
    {
        Trace.Assert(messageWriter is ConsoleMessageWriter);
        Trace.Assert(messageWriters.Single() is ConsoleMessageWriter);
    }
}
```

<span data-ttu-id="e2666-257">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="e2666-257">For more information, see:</span></span>

- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAdd%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddTransient%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddScoped%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddSingleton%2A>

<span data-ttu-id="e2666-258">Metody [TryAddEnumerable (servicedescriptor)](xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddEnumerable%2A) rejestrują usługę tylko wtedy, gdy nie istnieje jeszcze implementacja tego *samego typu*.</span><span class="sxs-lookup"><span data-stu-id="e2666-258">The [TryAddEnumerable(ServiceDescriptor)](xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddEnumerable%2A) methods register the service only if there isn't already an implementation *of the same type*.</span></span> <span data-ttu-id="e2666-259">Wiele usług jest rozpoznawanych za pośrednictwem `IEnumerable<{SERVICE}>` .</span><span class="sxs-lookup"><span data-stu-id="e2666-259">Multiple services are resolved via `IEnumerable<{SERVICE}>`.</span></span> <span data-ttu-id="e2666-260">Podczas rejestrowania usług Dodaj wystąpienie, jeśli jeden z tych samych typów nie został jeszcze dodany.</span><span class="sxs-lookup"><span data-stu-id="e2666-260">When registering services, add an instance if one of the same types hasn't already been added.</span></span> <span data-ttu-id="e2666-261">Autorzy biblioteki używają `TryAddEnumerable` , aby uniknąć rejestrowania wielu kopii implementacji w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="e2666-261">Library authors use `TryAddEnumerable` to avoid registering multiple copies of an implementation in the container.</span></span>

<span data-ttu-id="e2666-262">W poniższym przykładzie pierwsze wywołanie `TryAddEnumerable` rejestracji `MessageWriter` jako implementacji dla `IMessageWriter1` .</span><span class="sxs-lookup"><span data-stu-id="e2666-262">In the following example, the first call to `TryAddEnumerable` registers `MessageWriter` as an implementation for `IMessageWriter1`.</span></span> <span data-ttu-id="e2666-263">Drugie wywołanie rejestru `MessageWriter` dla `IMessageWriter2` .</span><span class="sxs-lookup"><span data-stu-id="e2666-263">The second call registers `MessageWriter` for `IMessageWriter2`.</span></span> <span data-ttu-id="e2666-264">Trzecie wywołanie nie działa `IMessageWriter1` , ponieważ ma już zarejestrowana implementacja `MessageWriter` :</span><span class="sxs-lookup"><span data-stu-id="e2666-264">The third call has no effect because `IMessageWriter1` already has a registered implementation of `MessageWriter`:</span></span>

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

<span data-ttu-id="e2666-265">Rejestracja usługi jest zazwyczaj kolejnością niezależną, z wyjątkiem rejestracji wielu implementacji tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="e2666-265">Service registration is generally order independent except when registering multiple implementations of the same type.</span></span>

<span data-ttu-id="e2666-266">`IServiceCollection` jest kolekcją <xref:Microsoft.Extensions.DependencyInjection.ServiceDescriptor> obiektów.</span><span class="sxs-lookup"><span data-stu-id="e2666-266">`IServiceCollection` is a collection of <xref:Microsoft.Extensions.DependencyInjection.ServiceDescriptor> objects.</span></span> <span data-ttu-id="e2666-267">Poniższy przykład pokazuje, jak zarejestrować usługę przez utworzenie i dodanie `ServiceDescriptor` :</span><span class="sxs-lookup"><span data-stu-id="e2666-267">The following example shows how to register a service by creating and adding a `ServiceDescriptor`:</span></span>

```csharp
string secretKey = Configuration["SecretKey"];
var descriptor = new ServiceDescriptor(
    typeof(IMessageWriter),
    _ => new DefaultMessageWriter(secretKey),
    ServiceLifetime.Transient);

services.Add(descriptor);
```

<span data-ttu-id="e2666-268">`Add{LIFETIME}`Metody wbudowane wykorzystują takie samo podejście.</span><span class="sxs-lookup"><span data-stu-id="e2666-268">The built-in `Add{LIFETIME}` methods use the same approach.</span></span> <span data-ttu-id="e2666-269">Na przykład zobacz [kod źródłowy addscope](https://github.com/dotnet/extensions/blob/v3.1.8/src/DependencyInjection/DI.Abstractions/src/ServiceCollectionServiceExtensions.cs#L216-L237).</span><span class="sxs-lookup"><span data-stu-id="e2666-269">For example, see the [AddScoped source code](https://github.com/dotnet/extensions/blob/v3.1.8/src/DependencyInjection/DI.Abstractions/src/ServiceCollectionServiceExtensions.cs#L216-L237).</span></span>

### <a name="constructor-injection-behavior"></a><span data-ttu-id="e2666-270">Zachowanie iniekcji konstruktora</span><span class="sxs-lookup"><span data-stu-id="e2666-270">Constructor injection behavior</span></span>

<span data-ttu-id="e2666-271">Usługi można rozwiązać przy użyciu:</span><span class="sxs-lookup"><span data-stu-id="e2666-271">Services can be resolved by using:</span></span>

- <xref:System.IServiceProvider>
- <span data-ttu-id="e2666-272"><xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities>:</span><span class="sxs-lookup"><span data-stu-id="e2666-272"><xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities>:</span></span>
  - <span data-ttu-id="e2666-273">Tworzy obiekty, które nie są zarejestrowane w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="e2666-273">Creates objects that aren't registered in the container.</span></span>
  - <span data-ttu-id="e2666-274">Używany z niektórymi funkcjami środowiska.</span><span class="sxs-lookup"><span data-stu-id="e2666-274">Used with some framework features.</span></span>

<span data-ttu-id="e2666-275">Konstruktory mogą akceptować argumenty, które nie są dostarczane przez iniekcję zależności, ale argumenty muszą przypisywać wartości domyślne.</span><span class="sxs-lookup"><span data-stu-id="e2666-275">Constructors can accept arguments that aren't provided by dependency injection, but the arguments must assign default values.</span></span>

<span data-ttu-id="e2666-276">Gdy usługi są rozwiązane przez `IServiceProvider` lub `ActivatorUtilities` , iniekcja konstruktora wymaga konstruktora *publicznego* .</span><span class="sxs-lookup"><span data-stu-id="e2666-276">When services are resolved by `IServiceProvider` or `ActivatorUtilities`, constructor injection requires a *public* constructor.</span></span>

<span data-ttu-id="e2666-277">Gdy usługi są rozwiązane przez `ActivatorUtilities` , iniekcja konstruktora wymaga, aby istnieje tylko jeden odpowiedni Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="e2666-277">When services are resolved by `ActivatorUtilities`, constructor injection requires that only one applicable constructor exists.</span></span> <span data-ttu-id="e2666-278">Przeciążenia konstruktora są obsługiwane, ale może istnieć tylko jedno Przeciążenie, którego argumenty mogą być spełnione przez iniekcję zależności.</span><span class="sxs-lookup"><span data-stu-id="e2666-278">Constructor overloads are supported, but only one overload can exist whose arguments can all be fulfilled by dependency injection.</span></span>

## <a name="scope-validation"></a><span data-ttu-id="e2666-279">Weryfikacja zakresu</span><span class="sxs-lookup"><span data-stu-id="e2666-279">Scope validation</span></span>

<span data-ttu-id="e2666-280">Gdy aplikacja jest uruchamiana w `Development` środowisku i wywołuje [CreateDefaultBuilder](generic-host.md#default-builder-settings) , aby skompilować hosta, domyślny dostawca usług sprawdza, czy:</span><span class="sxs-lookup"><span data-stu-id="e2666-280">When the app runs in the `Development` environment and calls [CreateDefaultBuilder](generic-host.md#default-builder-settings) to build the host, the default service provider performs checks to verify that:</span></span>

- <span data-ttu-id="e2666-281">Usługi w zakresie nie są rozpoznawane przez dostawcę usług głównych.</span><span class="sxs-lookup"><span data-stu-id="e2666-281">Scoped services aren't resolved from the root service provider.</span></span>
- <span data-ttu-id="e2666-282">Usługi w zakresie nie są wstawiane do pojedynczych.</span><span class="sxs-lookup"><span data-stu-id="e2666-282">Scoped services aren't injected into singletons.</span></span>

<span data-ttu-id="e2666-283">Dostawca usług głównych jest tworzony, gdy <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> jest wywoływany.</span><span class="sxs-lookup"><span data-stu-id="e2666-283">The root service provider is created when <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> is called.</span></span> <span data-ttu-id="e2666-284">Okres istnienia dostawcy usług głównych odpowiada okresowi istnienia aplikacji, gdy dostawca rozpoczyna pracę z aplikacją i jest usuwany po zamknięciu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e2666-284">The root service provider's lifetime corresponds to the app's lifetime when the provider starts with the app and is disposed when the app shuts down.</span></span>

<span data-ttu-id="e2666-285">Usługi o określonym zakresie są usuwane przez kontener, który go utworzył.</span><span class="sxs-lookup"><span data-stu-id="e2666-285">Scoped services are disposed by the container that created them.</span></span> <span data-ttu-id="e2666-286">Jeśli w kontenerze głównym zostanie utworzona usługa o określonym zakresie, okres istnienia usługi zostanie skutecznie podwyższony do pojedynczej, ponieważ jest usuwany tylko przez kontener główny po zamknięciu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e2666-286">If a scoped service is created in the root container, the service's lifetime is effectively promoted to singleton because it's only disposed by the root container when the app shuts down.</span></span> <span data-ttu-id="e2666-287">Sprawdzanie poprawności zakresów usług przechwytuje te sytuacje, gdy `BuildServiceProvider` jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="e2666-287">Validating service scopes catches these situations when `BuildServiceProvider` is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2666-288">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e2666-288">See also</span></span>

- [<span data-ttu-id="e2666-289">Używanie iniekcji zależności w programie .NET</span><span class="sxs-lookup"><span data-stu-id="e2666-289">Use dependency injection in .NET</span></span>](dependency-injection-usage.md)
- [<span data-ttu-id="e2666-290">Wskazówki dotyczące wstrzykiwania zależności</span><span class="sxs-lookup"><span data-stu-id="e2666-290">Dependency injection guidelines</span></span>](dependency-injection-guidelines.md)
- [<span data-ttu-id="e2666-291">Wstrzykiwanie zależności w ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e2666-291">Dependency injection in ASP.NET Core</span></span>](/aspnet/core/fundamentals/dependency-injection)
- [<span data-ttu-id="e2666-292">Wzorce konferencji NDC na potrzeby tworzenia aplikacji</span><span class="sxs-lookup"><span data-stu-id="e2666-292">NDC Conference Patterns for DI app development</span></span>](https://www.youtube.com/watch?v=x-C-CNBVTaY)
- [<span data-ttu-id="e2666-293">Zasada jawnych zależności</span><span class="sxs-lookup"><span data-stu-id="e2666-293">Explicit dependencies principle</span></span>](../../architecture/modern-web-apps-azure/architectural-principles.md#explicit-dependencies)
- [<span data-ttu-id="e2666-294">Niewersja kontenerów sterowania i wzorzec iniekcji zależności (Martin Fowlera)</span><span class="sxs-lookup"><span data-stu-id="e2666-294">Inversion of control containers and the dependency injection pattern (Martin Fowler)</span></span>](https://www.martinfowler.com/articles/injection.html)
- <span data-ttu-id="e2666-295">W repozytorium [GitHub.com/dotnet/Extensions](https://github.com/dotnet/extensions/issues) należy utworzyć di usterki</span><span class="sxs-lookup"><span data-stu-id="e2666-295">DI bugs should be created in the [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) repo</span></span>
