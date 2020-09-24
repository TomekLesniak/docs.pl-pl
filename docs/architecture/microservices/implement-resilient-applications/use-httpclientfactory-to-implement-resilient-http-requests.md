---
title: Używanie elementu IHttpClientFactory do implementowania odpornych na błędy żądań HTTP
description: Dowiedz się, jak używać usługi IHttpClientFactory, dostępnej od platformy .NET Core 2,1, do tworzenia `HttpClient` wystąpień, co ułatwia korzystanie z niej w aplikacjach.
ms.date: 08/31/2020
ms.openlocfilehash: ae093ef960b2540bf4916bf72ad3bec51fa33ebe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152575"
---
# <a name="use-ihttpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="7481d-103">Używanie elementu IHttpClientFactory do implementowania odpornych na błędy żądań HTTP</span><span class="sxs-lookup"><span data-stu-id="7481d-103">Use IHttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="7481d-104"><xref:System.Net.Http.IHttpClientFactory> jest umową zaimplementowaną przez `DefaultHttpClientFactory` , ceniona fabrykę, dostępną od platformy .NET Core 2,1, do tworzenia <xref:System.Net.Http.HttpClient> wystąpień, które mają być używane w aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="7481d-104"><xref:System.Net.Http.IHttpClientFactory> is a contract implemented by `DefaultHttpClientFactory`, an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="7481d-105">Problemy z oryginalną klasą HttpClient dostępną w programie .NET Core</span><span class="sxs-lookup"><span data-stu-id="7481d-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="7481d-106">Oryginalna i dobrze znana <xref:System.Net.Http.HttpClient> Klasa może być łatwo używana, ale w niektórych przypadkach nie jest ona prawidłowo używana przez wielu deweloperów.</span><span class="sxs-lookup"><span data-stu-id="7481d-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="7481d-107">Chociaż ta klasa implementuje `IDisposable` , deklaruje i tworzy wystąpienie w `using` instrukcji nie jest preferowana, ponieważ gdy `HttpClient` obiekt jest usuwany, podstawowe gniazdo nie jest natychmiast zwalniane, co może prowadzić do problemu z _wyczerpaniem gniazda_ .</span><span class="sxs-lookup"><span data-stu-id="7481d-107">Though this class implements `IDisposable`, declaring and instantiating it within a `using` statement is not preferred because when the `HttpClient` object gets disposed of, the underlying socket is not immediately released, which can lead to a _socket exhaustion_ problem.</span></span> <span data-ttu-id="7481d-108">Aby uzyskać więcej informacji o tym problemie, zapoznaj się z wpisem w blogu, [który jest używany HttpClient, i zastąp go destabilizacja oprogramowania](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span><span class="sxs-lookup"><span data-stu-id="7481d-108">For more information about this issue, see the blog post [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span></span>

<span data-ttu-id="7481d-109">W związku z tym, `HttpClient` jest przeznaczony do tworzenia wystąpień i ponownie używany przez cały czas życia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7481d-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="7481d-110">Wystąpienie `HttpClient` klasy dla każdego żądania spowoduje wyczerpanie liczby gniazd dostępnych w ramach dużych obciążeń.</span><span class="sxs-lookup"><span data-stu-id="7481d-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="7481d-111">Ten problem spowoduje `SocketException` błędy.</span><span class="sxs-lookup"><span data-stu-id="7481d-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="7481d-112">Możliwe podejścia do rozwiązania tego problemu są oparte na tworzeniu `HttpClient` obiektu jako singleton lub statyczny, jak wyjaśniono w tym [artykule firmy Microsoft w sprawie użycia HttpClient](../../../csharp/tutorials/console-webapiclient.md).</span><span class="sxs-lookup"><span data-stu-id="7481d-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span> <span data-ttu-id="7481d-113">Może to być dobre rozwiązanie dla krótkich aplikacji konsolowych lub podobnych, które działają kilka razy dziennie.</span><span class="sxs-lookup"><span data-stu-id="7481d-113">This can be a good solution for short-lived console apps or similar, that run a few times a day.</span></span>

<span data-ttu-id="7481d-114">Innym problemem, z którym deweloperzy pracują usługi, jest użycie udostępnionego wystąpienia programu `HttpClient` w długotrwałych procesach.</span><span class="sxs-lookup"><span data-stu-id="7481d-114">Another issue that developers run into is when using a shared instance of `HttpClient` in long-running processes.</span></span> <span data-ttu-id="7481d-115">W sytuacji, gdy HttpClient jest tworzona jako obiekt pojedynczy lub statyczny, nie może obsłużyć zmian DNS zgodnie z opisem w tym [zagadnieniu](https://github.com/dotnet/runtime/issues/18348) dotyczącego repozytorium dotnet/Runtime.</span><span class="sxs-lookup"><span data-stu-id="7481d-115">In a situation where the HttpClient is instantiated as a singleton or a static object, it fails to handle the DNS changes as described in this [issue](https://github.com/dotnet/runtime/issues/18348) of the dotnet/runtime GitHub repository.</span></span>

<span data-ttu-id="7481d-116">Problem nie `HttpClient` dotyczy jednak na SE, ale z [domyślnym konstruktorem dla HttpClient](/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), ponieważ tworzy nowe konkretne wystąpienie <xref:System.Net.Http.HttpMessageHandler> , które jest takie, które ma problemy z *WYCZERPANIEM gniazd* i zmiany systemu DNS wymienione powyżej.</span><span class="sxs-lookup"><span data-stu-id="7481d-116">However, the issue isn't really with `HttpClient` per se, but with the [default constructor for HttpClient](/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), because it creates a new concrete instance of <xref:System.Net.Http.HttpMessageHandler>, which is the one that has *sockets exhaustion* and DNS changes issues mentioned above.</span></span>

<span data-ttu-id="7481d-117">Aby rozwiązać problemy wymienione powyżej i umożliwić `HttpClient` Zarządzanie wystąpieniami, w programie .NET Core 2,1 wprowadzono <xref:System.Net.Http.IHttpClientFactory> interfejs, którego można użyć do konfigurowania i tworzenia `HttpClient` wystąpień w aplikacji za pomocą iniekcji zależności (di).</span><span class="sxs-lookup"><span data-stu-id="7481d-117">To address the issues mentioned above and to make `HttpClient` instances manageable, .NET Core 2.1 introduced the <xref:System.Net.Http.IHttpClientFactory> interface which can be used to configure and create `HttpClient` instances in an app through Dependency Injection (DI).</span></span> <span data-ttu-id="7481d-118">Udostępnia również rozszerzenia dla oprogramowania pośredniczącego opartego na Polly, które umożliwiają delegowanie programów obsługi w HttpClient.</span><span class="sxs-lookup"><span data-stu-id="7481d-118">It also provides extensions for Polly-based middleware to take advantage of delegating handlers in HttpClient.</span></span>

<span data-ttu-id="7481d-119">[Polly](http://www.thepollyproject.org/) jest biblioteką obsługi błędów przejściowych, która ułatwia deweloperom Dodawanie odporności do aplikacji przy użyciu wstępnie zdefiniowanych zasad w sposób bezpieczny dla bezpieczeństwa i bezpiecznego wątkowo.</span><span class="sxs-lookup"><span data-stu-id="7481d-119">[Polly](http://www.thepollyproject.org/) is a transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="benefits-of-using-ihttpclientfactory"></a><span data-ttu-id="7481d-120">Zalety korzystania z usługi IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="7481d-120">Benefits of using IHttpClientFactory</span></span>

<span data-ttu-id="7481d-121">Bieżąca implementacja <xref:System.Net.Http.IHttpClientFactory> , która również implementuje <xref:System.Net.Http.IHttpMessageHandlerFactory> program, oferuje następujące korzyści:</span><span class="sxs-lookup"><span data-stu-id="7481d-121">The current implementation of <xref:System.Net.Http.IHttpClientFactory>, that also implements <xref:System.Net.Http.IHttpMessageHandlerFactory>, offers the following benefits:</span></span>

- <span data-ttu-id="7481d-122">Zapewnia centralną lokalizację do nazywania i konfigurowania `HttpClient` obiektów logicznych.</span><span class="sxs-lookup"><span data-stu-id="7481d-122">Provides a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="7481d-123">Można na przykład skonfigurować klienta (agenta usługi), który jest wstępnie skonfigurowany w celu uzyskania dostępu do konkretnej mikrousługi.</span><span class="sxs-lookup"><span data-stu-id="7481d-123">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="7481d-124">Codify koncepcję wychodzącego oprogramowania pośredniczącego przez delegowanie programów obsługi w programie `HttpClient` i implementację oprogramowania pośredniczącego opartego na Polly, aby wykorzystać zasady dotyczące odporności Polly.</span><span class="sxs-lookup"><span data-stu-id="7481d-124">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly's policies for resiliency.</span></span>
- <span data-ttu-id="7481d-125">`HttpClient` ma już koncepcję delegowania programów obsługi, które mogą być połączone ze sobą w przypadku wychodzących żądań HTTP.</span><span class="sxs-lookup"><span data-stu-id="7481d-125">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="7481d-126">Klientów HTTP można zarejestrować do fabryki i można użyć procedury obsługi Polly, aby użyć zasad Polly do ponawiania, CircuitBreakers itd.</span><span class="sxs-lookup"><span data-stu-id="7481d-126">You can register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="7481d-127">Zarządzaj okresem istnienia, <xref:System.Net.Http.HttpMessageHandler> Aby uniknąć wspomnianych problemów i problemów, które mogą wystąpić podczas samodzielnego zarządzania `HttpClient` okresami istnienia.</span><span class="sxs-lookup"><span data-stu-id="7481d-127">Manage the lifetime of <xref:System.Net.Http.HttpMessageHandler> to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

> [!TIP]
> <span data-ttu-id="7481d-128">`HttpClient`Wystąpienia wstrzykiwane przez di mogą zostać bezpiecznie usunięte, ponieważ skojarzona z nim `HttpMessageHandler` zarządza fabryka.</span><span class="sxs-lookup"><span data-stu-id="7481d-128">The `HttpClient` instances injected by DI, can be disposed of safely, because the associated `HttpMessageHandler` is managed by the factory.</span></span> <span data-ttu-id="7481d-129">W rzeczywistości wystąpienia wstrzykiwane `HttpClient` są *objęte zakresem* od di perspektywy.</span><span class="sxs-lookup"><span data-stu-id="7481d-129">As a matter of fact, injected `HttpClient` instances are *Scoped* from a DI perspective.</span></span>

> [!NOTE]
> <span data-ttu-id="7481d-130">Implementacja programu `IHttpClientFactory` ( `DefaultHttpClientFactory` ) jest ściśle związana z implementacją di w `Microsoft.Extensions.DependencyInjection` pakiecie NuGet.</span><span class="sxs-lookup"><span data-stu-id="7481d-130">The implementation of `IHttpClientFactory` (`DefaultHttpClientFactory`) is tightly tied to the DI implementation in the `Microsoft.Extensions.DependencyInjection` NuGet package.</span></span> <span data-ttu-id="7481d-131">Aby uzyskać więcej informacji na temat używania innych kontenerów, zobacz tę [dyskusję](https://github.com/dotnet/extensions/issues/1345)w witrynie GitHub.</span><span class="sxs-lookup"><span data-stu-id="7481d-131">For more information about using other DI containers, see this [GitHub discussion](https://github.com/dotnet/extensions/issues/1345).</span></span>

## <a name="multiple-ways-to-use-ihttpclientfactory"></a><span data-ttu-id="7481d-132">Wiele sposobów używania IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="7481d-132">Multiple ways to use IHttpClientFactory</span></span>

<span data-ttu-id="7481d-133">Istnieje kilka sposobów, których można używać `IHttpClientFactory` w aplikacji:</span><span class="sxs-lookup"><span data-stu-id="7481d-133">There are several ways that you can use `IHttpClientFactory` in your application:</span></span>

- <span data-ttu-id="7481d-134">Podstawowy sposób użycia</span><span class="sxs-lookup"><span data-stu-id="7481d-134">Basic usage</span></span>
- <span data-ttu-id="7481d-135">Użyj nazwanych klientów</span><span class="sxs-lookup"><span data-stu-id="7481d-135">Use Named Clients</span></span>
- <span data-ttu-id="7481d-136">Używaj wpisanych klientów</span><span class="sxs-lookup"><span data-stu-id="7481d-136">Use Typed Clients</span></span>
- <span data-ttu-id="7481d-137">Korzystanie z wygenerowanych klientów</span><span class="sxs-lookup"><span data-stu-id="7481d-137">Use Generated Clients</span></span>

<span data-ttu-id="7481d-138">Ze względu na zwięzłości te wskazówki przedstawiają najbardziej strukturalny sposób użycia `IHttpClientFactory` , który jest używany jako klienci z określonym typem (wzorzec agenta usługi).</span><span class="sxs-lookup"><span data-stu-id="7481d-138">For the sake of brevity, this guidance shows the most structured way to use `IHttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="7481d-139">Wszystkie opcje są jednak udokumentowane i są obecnie wymienione w tym [artykule `IHttpClientFactory` dotyczące użycia](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span><span class="sxs-lookup"><span data-stu-id="7481d-139">However, all options are documented and are currently listed in this [article covering the `IHttpClientFactory` usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-ihttpclientfactory"></a><span data-ttu-id="7481d-140">Jak używać klientów z określonym programem IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="7481d-140">How to use Typed Clients with IHttpClientFactory</span></span>

<span data-ttu-id="7481d-141">Co to jest "klient z określonym typem"?</span><span class="sxs-lookup"><span data-stu-id="7481d-141">So, what's a "Typed Client"?</span></span> <span data-ttu-id="7481d-142">Jest to tylko `HttpClient` wstępnie skonfigurowane do określonego użytku.</span><span class="sxs-lookup"><span data-stu-id="7481d-142">It's just an `HttpClient` that's pre-configured for some specific use.</span></span> <span data-ttu-id="7481d-143">Ta konfiguracja może obejmować określone wartości, takie jak serwer podstawowy, nagłówki HTTP lub limity czasu.</span><span class="sxs-lookup"><span data-stu-id="7481d-143">This configuration can include specific values such as the base server, HTTP headers or time outs.</span></span>

<span data-ttu-id="7481d-144">Na poniższym diagramie pokazano, w jaki sposób typy klientów są używane w programie `IHttpClientFactory` :</span><span class="sxs-lookup"><span data-stu-id="7481d-144">The following diagram shows how Typed Clients are used with `IHttpClientFactory`:</span></span>

![Diagram przedstawiający sposób używania z IHttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

<span data-ttu-id="7481d-146">**Rysunek 8-4**.</span><span class="sxs-lookup"><span data-stu-id="7481d-146">**Figure 8-4**.</span></span> <span data-ttu-id="7481d-147">Używanie `IHttpClientFactory` z typami klas klienta.</span><span class="sxs-lookup"><span data-stu-id="7481d-147">Using `IHttpClientFactory` with Typed Client classes.</span></span>

<span data-ttu-id="7481d-148">Na powyższym obrazie `ClientService` (używanym przez kontroler lub kod klienta) jest używana `HttpClient` wartość utworzona przez zarejestrowany `IHttpClientFactory` .</span><span class="sxs-lookup"><span data-stu-id="7481d-148">In the above image, a `ClientService` (used by a controller or client code) uses an `HttpClient` created by the registered `IHttpClientFactory`.</span></span> <span data-ttu-id="7481d-149">Ta fabryka przypisuje `HttpMessageHandler` z puli do programu `HttpClient` .</span><span class="sxs-lookup"><span data-stu-id="7481d-149">This factory assigns an `HttpMessageHandler` from a pool to the `HttpClient`.</span></span> <span data-ttu-id="7481d-150">`HttpClient`Konfigurację można skonfigurować przy użyciu zasad Polly podczas rejestrowania `IHttpClientFactory` w kontenerze di z metodą rozszerzenia <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A> .</span><span class="sxs-lookup"><span data-stu-id="7481d-150">The `HttpClient` can be configured with Polly's policies when registering the `IHttpClientFactory` in the DI container with the extension method <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A>.</span></span>

<span data-ttu-id="7481d-151">Aby skonfigurować powyższą strukturę, Dodaj do <xref:System.Net.Http.IHttpClientFactory> aplikacji, instalując `Microsoft.Extensions.Http` pakiet NuGet, który zawiera <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A> metodę rozszerzenia dla <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection> .</span><span class="sxs-lookup"><span data-stu-id="7481d-151">To configure the above structure, add <xref:System.Net.Http.IHttpClientFactory> in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A> extension method for <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="7481d-152">Ta metoda rozszerzenia rejestruje klasę wewnętrzną, `DefaultHttpClientFactory` która ma być używana jako Klasa pojedyncza dla interfejsu `IHttpClientFactory` .</span><span class="sxs-lookup"><span data-stu-id="7481d-152">This extension method registers the internal `DefaultHttpClientFactory` class to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="7481d-153">Definiuje konfigurację przejściową dla <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder> .</span><span class="sxs-lookup"><span data-stu-id="7481d-153">It defines a transient configuration for the <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>.</span></span> <span data-ttu-id="7481d-154">Ta procedura obsługi komunikatów ( <xref:System.Net.Http.HttpMessageHandler> obiekt) pobierana z puli jest używana przez `HttpClient` zwracaną z fabryki.</span><span class="sxs-lookup"><span data-stu-id="7481d-154">This message handler (<xref:System.Net.Http.HttpMessageHandler> object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="7481d-155">W następnym kodzie można zobaczyć, jak `AddHttpClient()` można użyć do rejestrowania klientów typu (agentów usług), których należy użyć `HttpClient` .</span><span class="sxs-lookup"><span data-stu-id="7481d-155">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="7481d-156">Zarejestrowanie usług klienta, jak pokazano w poprzednim kodzie, tworzy `DefaultClientFactory` standard `HttpClient` dla każdej usługi.</span><span class="sxs-lookup"><span data-stu-id="7481d-156">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="7481d-157">Można również dodać konfigurację specyficzną dla wystąpienia w ramach rejestracji do programu, na przykład skonfigurować adres podstawowy i dodać zasady odporności, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="7481d-157">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="7481d-158">Tylko w przypadku przykładu można zobaczyć jedną z powyższych zasad w następnym kodzie:</span><span class="sxs-lookup"><span data-stu-id="7481d-158">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="7481d-159">Więcej informacji o używaniu programu Polly można znaleźć w [następnym artykule](implement-http-call-retries-exponential-backoff-polly.md).</span><span class="sxs-lookup"><span data-stu-id="7481d-159">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="7481d-160">HttpClient okresy istnienia</span><span class="sxs-lookup"><span data-stu-id="7481d-160">HttpClient lifetimes</span></span>

<span data-ttu-id="7481d-161">Za każdym razem, gdy otrzymujesz `HttpClient` obiekt z `IHttpClientFactory` , zostanie zwrócone nowe wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="7481d-161">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="7481d-162">Ale każdy z nich `HttpClient` używa `HttpMessageHandler` puli i ponownie używanej przez program `IHttpClientFactory` w celu zmniejszenia zużycia zasobów, o ile `HttpMessageHandler` okres istnienia nie wygasł.</span><span class="sxs-lookup"><span data-stu-id="7481d-162">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="7481d-163">Buforowanie programów obsługi jest pożądane, ponieważ każdy program obsługi zazwyczaj zarządza własnymi połączeniami HTTP; Utworzenie większej liczby programów obsługi niż to konieczne może skutkować opóźnieniami połączeń.</span><span class="sxs-lookup"><span data-stu-id="7481d-163">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="7481d-164">Niektóre programy obsługi powodują również, że połączenia są otwarte w nieskończoność, co może uniemożliwić obsłużenie zmian DNS przez program obsługi.</span><span class="sxs-lookup"><span data-stu-id="7481d-164">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="7481d-165">W `HttpMessageHandler` obiektach w puli jest używany okres istnienia, który to czas, przez który `HttpMessageHandler` wystąpienie w puli może być ponownie używane.</span><span class="sxs-lookup"><span data-stu-id="7481d-165">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="7481d-166">Wartość domyślna to dwie minuty, ale można ją przesłonić dla poszczególnych klientów.</span><span class="sxs-lookup"><span data-stu-id="7481d-166">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="7481d-167">Aby przesłonić ten element, wywołaj to, `SetHandlerLifetime()` <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> który jest zwracany podczas tworzenia klienta, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="7481d-167">To override it, call `SetHandlerLifetime()` on the <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="7481d-168">Każdy klient z określonym typem może mieć własną skonfigurowaną wartość okresu istnienia programu obsługi.</span><span class="sxs-lookup"><span data-stu-id="7481d-168">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="7481d-169">Ustaw okres istnienia w `InfiniteTimeSpan` celu wyłączenia procedury obsługi.</span><span class="sxs-lookup"><span data-stu-id="7481d-169">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="7481d-170">Zaimplementuj wpisane klasy klienta korzystające z wstrzykniętych i skonfigurowanych HttpClient</span><span class="sxs-lookup"><span data-stu-id="7481d-170">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="7481d-171">W poprzednim kroku należy określić zdefiniowane klasy klienta, takie jak klasy w przykładowym kodzie, takie jak "BasketService", "CatalogService", "OrderingService" itp. — typ klienta jest klasą akceptującą `HttpClient` obiekt (wstrzykiwaną za pośrednictwem jego konstruktora) i używa go do wywołania pewnej zdalnej usługi http.</span><span class="sxs-lookup"><span data-stu-id="7481d-171">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like 'BasketService', 'CatalogService', 'OrderingService', etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="7481d-172">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="7481d-172">For example:</span></span>

```csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;
    private readonly string _remoteServiceBaseUrl;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient;
    }

    public async Task<Catalog> GetCatalogItems(int page, int take,
                                               int? brand, int? type)
    {
        var uri = API.Catalog.GetAllCatalogItems(_remoteServiceBaseUrl,
                                                 page, take, brand, type);

        var responseString = await _httpClient.GetStringAsync(uri);

        var catalog = JsonConvert.DeserializeObject<Catalog>(responseString);
        return catalog;
    }
}
```

<span data-ttu-id="7481d-173">Określony klient ( `CatalogService` w tym przykładzie) jest uaktywniany przez di (iniekcja zależności), co oznacza, że może akceptować wszystkie zarejestrowane usługi w swoim konstruktorze, oprócz `HttpClient` .</span><span class="sxs-lookup"><span data-stu-id="7481d-173">The Typed Client (`CatalogService` in the example) is activated by DI (Dependency Injection), that means it can accept any registered service in its constructor, in addition to `HttpClient`.</span></span>

<span data-ttu-id="7481d-174">Klient z określonym typem jest efektywnie obiektem przejściowym, co oznacza, że nowe wystąpienie jest tworzone za każdym razem, gdy jest to wymaganie.</span><span class="sxs-lookup"><span data-stu-id="7481d-174">A Typed Client is effectively a transient object, that means a new instance is created each time one is needed.</span></span> <span data-ttu-id="7481d-175">Nowe wystąpienie jest odbierane za `HttpClient` każdym razem, gdy jest konstruowany.</span><span class="sxs-lookup"><span data-stu-id="7481d-175">It receives a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="7481d-176">Jednak `HttpMessageHandler` obiekty w puli są obiektami, które są ponownie używane przez wiele `HttpClient` wystąpień.</span><span class="sxs-lookup"><span data-stu-id="7481d-176">However, the `HttpMessageHandler` objects in the pool are the objects that are reused by multiple `HttpClient` instances.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="7481d-177">Korzystanie z wpisanych klas klienta</span><span class="sxs-lookup"><span data-stu-id="7481d-177">Use your Typed Client classes</span></span>

<span data-ttu-id="7481d-178">Na koniec po zaimplementowaniu klas wpisanych można je zarejestrować i skonfigurować przy użyciu `AddHttpClient()` .</span><span class="sxs-lookup"><span data-stu-id="7481d-178">Finally, once you have your typed classes implemented, you can have them registered and configured with `AddHttpClient()`.</span></span> <span data-ttu-id="7481d-179">Można ich używać wszędzie tam, gdzie usługi są wstrzykiwane przez DI.</span><span class="sxs-lookup"><span data-stu-id="7481d-179">After that you can use them wherever have services injected by DI.</span></span> <span data-ttu-id="7481d-180">Na przykład w kodzie lub kontrolerze strony Razor w aplikacji sieci Web MVC, jak w poniższym kodzie z eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="7481d-180">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC.Controllers
{
    public class CatalogController : Controller
    {
        private ICatalogService _catalogSvc;

        public CatalogController(ICatalogService catalogSvc) =>
                                                           _catalogSvc = catalogSvc;

        public async Task<IActionResult> Index(int? BrandFilterApplied,
                                               int? TypesFilterApplied,
                                               int? page,
                                               [FromQuery]string errorMsg)
        {
            var itemsPage = 10;
            var catalog = await _catalogSvc.GetCatalogItems(page ?? 0,
                                                            itemsPage,
                                                            BrandFilterApplied,
                                                            TypesFilterApplied);
            //… Additional code
        }

        }
}
```

<span data-ttu-id="7481d-181">Do tego momentu Powyższy fragment kodu pokazuje przykład wykonywania zwykłych żądań HTTP.</span><span class="sxs-lookup"><span data-stu-id="7481d-181">Up to this point, the above code snippet has only shown the example of performing regular HTTP requests.</span></span> <span data-ttu-id="7481d-182">Ale "Magic" znajduje się w następujących sekcjach, w których pokazano, jak wszystkie żądania HTTP wykonywane przez `HttpClient` program, mogą mieć odporne na błędy zasady, takie jak ponowne próby przy użyciu wykładniczej wycofywania, wyłączników, funkcji zabezpieczeń przy użyciu tokenów uwierzytelniania, a nawet innych funkcji niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="7481d-182">But the 'magic' comes in the following sections where it shows how all the HTTP requests made by `HttpClient`, can have resilient policies such as retries with exponential backoff, circuit breakers, security features using auth tokens, or even any other custom feature.</span></span> <span data-ttu-id="7481d-183">Wszystkie te czynności można wykonać tylko przez dodanie zasad i delegowanie programów obsługi do zarejestrowanych klientów z określonym typem.</span><span class="sxs-lookup"><span data-stu-id="7481d-183">And all of these can be done just by adding policies and delegating handlers to your registered Typed Clients.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7481d-184">Zasoby dodatkowe</span><span class="sxs-lookup"><span data-stu-id="7481d-184">Additional resources</span></span>

- <span data-ttu-id="7481d-185">**Używanie HttpClientFactory w programie .NET Core**</span><span class="sxs-lookup"><span data-stu-id="7481d-185">**Using HttpClientFactory in .NET Core**</span></span>  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="7481d-186">**Kod źródłowy HttpClientFactory w `dotnet/extensions` repozytorium GitHub**</span><span class="sxs-lookup"><span data-stu-id="7481d-186">**HttpClientFactory source code in the `dotnet/extensions` GitHub repository**</span></span>  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="7481d-187">**Polly (odporność platformy .NET i Biblioteka obsługi błędów przejściowych)**</span><span class="sxs-lookup"><span data-stu-id="7481d-187">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <http://www.thepollyproject.org/>
  
- <span data-ttu-id="7481d-188">**Korzystanie z IHttpClientFactory bez iniekcji zależności (problem z usługą GitHub)**</span><span class="sxs-lookup"><span data-stu-id="7481d-188">**Using IHttpClientFactory without dependency injection (GitHub issue)**</span></span>  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
><span data-ttu-id="7481d-189">[Poprzedni](implement-resilient-entity-framework-core-sql-connections.md) 
> [Dalej](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="7481d-189">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
