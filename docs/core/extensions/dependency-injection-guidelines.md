---
title: Wskazówki dotyczące wstrzykiwania zależności
description: Poznaj różne wskazówki dotyczące iniekcji zależności oraz najlepsze rozwiązania dotyczące tworzenia aplikacji .NET.
author: IEvangelist
ms.author: dapine
ms.date: 10/29/2020
ms.topic: guide
ms.openlocfilehash: 092fdc70bd5d6bae82c4c1da96db4d5ac08df452
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063168"
---
# <a name="dependency-injection-guidelines"></a><span data-ttu-id="f3066-103">Wskazówki dotyczące wstrzykiwania zależności</span><span class="sxs-lookup"><span data-stu-id="f3066-103">Dependency injection guidelines</span></span>

<span data-ttu-id="f3066-104">Ten artykuł zawiera ogólne wskazówki i najlepsze rozwiązania dotyczące implementowania iniekcji zależności w aplikacjach .NET.</span><span class="sxs-lookup"><span data-stu-id="f3066-104">This article provides general guidelines and best practices for implementing dependency injection in .NET applications.</span></span>

## <a name="design-services-for-dependency-injection"></a><span data-ttu-id="f3066-105">Projektowanie usług do iniekcji zależności</span><span class="sxs-lookup"><span data-stu-id="f3066-105">Design services for dependency injection</span></span>

<span data-ttu-id="f3066-106">Podczas projektowania usług pod kątem iniekcji zależności:</span><span class="sxs-lookup"><span data-stu-id="f3066-106">When designing services for dependency injection:</span></span>

- <span data-ttu-id="f3066-107">Unikaj stanowych, statycznych klas i elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="f3066-107">Avoid stateful, static classes and members.</span></span> <span data-ttu-id="f3066-108">Należy unikać tworzenia stanu globalnego przez projektowanie aplikacji do korzystania z usług pojedynczych.</span><span class="sxs-lookup"><span data-stu-id="f3066-108">Avoid creating global state by designing apps to use singleton services instead.</span></span>
- <span data-ttu-id="f3066-109">Unikaj bezpośredniego tworzenia wystąpień klas zależnych w ramach usług.</span><span class="sxs-lookup"><span data-stu-id="f3066-109">Avoid direct instantiation of dependent classes within services.</span></span> <span data-ttu-id="f3066-110">Bezpośrednie utworzenie wystąpienia Couples kod do konkretnej implementacji.</span><span class="sxs-lookup"><span data-stu-id="f3066-110">Direct instantiation couples the code to a particular implementation.</span></span>
- <span data-ttu-id="f3066-111">Zapewnianie niewielkich, dobrze przeprowadzonych i łatwych do przetestowania usług.</span><span class="sxs-lookup"><span data-stu-id="f3066-111">Make services small, well-factored, and easily tested.</span></span>

<span data-ttu-id="f3066-112">Jeśli klasa ma liczne wstrzykiwane zależności, może być znak, że Klasa ma zbyt wiele obowiązków i narusza [zasadę pojedynczej odpowiedzialności (SRP)](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#single-responsibility).</span><span class="sxs-lookup"><span data-stu-id="f3066-112">If a class has many injected dependencies, it might be a sign that the class has too many responsibilities and violates the [Single Responsibility Principle (SRP)](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#single-responsibility).</span></span> <span data-ttu-id="f3066-113">Próba refaktoryzacji klasy przez przeniesienie niektórych jej obowiązków do nowych klas.</span><span class="sxs-lookup"><span data-stu-id="f3066-113">Attempt to refactor the class by moving some of its responsibilities into new classes.</span></span>

### <a name="disposal-of-services"></a><span data-ttu-id="f3066-114">Usuwanie usług</span><span class="sxs-lookup"><span data-stu-id="f3066-114">Disposal of services</span></span>

<span data-ttu-id="f3066-115">Kontener jest odpowiedzialny za oczyszczanie typów, które tworzy, i <xref:System.IDisposable.Dispose%2A> wywołuje <xref:System.IDisposable> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="f3066-115">The container is responsible for cleanup of types it creates, and calls <xref:System.IDisposable.Dispose%2A> on <xref:System.IDisposable> instances.</span></span> <span data-ttu-id="f3066-116">Usługi rozpoznane przez kontener nigdy nie powinny zostać usunięte przez dewelopera.</span><span class="sxs-lookup"><span data-stu-id="f3066-116">Services resolved from the container should never be disposed by the developer.</span></span> <span data-ttu-id="f3066-117">Jeśli typ lub fabryka są zarejestrowane jako pojedyncze, kontener usuwa pojedyncze automatycznie.</span><span class="sxs-lookup"><span data-stu-id="f3066-117">If a type or factory is registered as a singleton, the container disposes the singleton automatically.</span></span>

<span data-ttu-id="f3066-118">W poniższym przykładzie usługi są tworzone przez kontener usługi i usuwane automatycznie:</span><span class="sxs-lookup"><span data-stu-id="f3066-118">In the following example, the services are created by the service container and disposed automatically:</span></span>

:::code language="csharp" source="snippets/configuration/console-di-disposable/TransientDisposable.cs":::

<span data-ttu-id="f3066-119">Wcześniejszy okres istnienia ma być przejściowy.</span><span class="sxs-lookup"><span data-stu-id="f3066-119">The preceding disposable is intended to have a transient lifetime.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-disposable/ScopedDisposable.cs":::

<span data-ttu-id="f3066-120">Wcześniejszy zakres jest przeznaczony do posiadania okresu istnienia w zakresie.</span><span class="sxs-lookup"><span data-stu-id="f3066-120">The preceding disposable is intended to have a scoped lifetime.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-disposable/SingletonDisposable.cs":::

<span data-ttu-id="f3066-121">Wcześniejszy okres istnienia jest przeznaczony do posiadania pojedynczej ważności.</span><span class="sxs-lookup"><span data-stu-id="f3066-121">The preceding disposable is intended to have a singleton lifetime.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-disposable/Program.cs" range="1-21,41-60" highlight="":::

<span data-ttu-id="f3066-122">Konsola debugowania wyświetla następujące przykładowe dane wyjściowe po uruchomieniu:</span><span class="sxs-lookup"><span data-stu-id="f3066-122">The debug console shows the following sample output after running:</span></span>

```console
Scope 1...
ScopedDisposable.Dispose()
TransientDisposable.Dispose()

Scope 2...
ScopedDisposable.Dispose()
TransientDisposable.Dispose()

info: Microsoft.Hosting.Lifetime[0]
      Application started.Press Ctrl+C to shut down.
info: Microsoft.Hosting.Lifetime[0]
     Hosting environment: Production
info: Microsoft.Hosting.Lifetime[0]
     Content root path: .\configuration\console-di-disposable\bin\Debug\net5.0
info: Microsoft.Hosting.Lifetime[0]
     Application is shutting down...
SingletonDisposable.Dispose()
```

### <a name="services-not-created-by-the-service-container"></a><span data-ttu-id="f3066-123">Usługi, które nie zostały utworzone przez kontener usługi</span><span class="sxs-lookup"><span data-stu-id="f3066-123">Services not created by the service container</span></span>

<span data-ttu-id="f3066-124">Spójrzmy na poniższy kod:</span><span class="sxs-lookup"><span data-stu-id="f3066-124">Consider the following code:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddSingleton(new ExampleService());

    // ...
}
```

<span data-ttu-id="f3066-125">Powyższy kod ma następujące działanie:</span><span class="sxs-lookup"><span data-stu-id="f3066-125">In the preceding code:</span></span>

- <span data-ttu-id="f3066-126">`ExampleService`Wystąpienie **nie** jest tworzone przez kontener usługi.</span><span class="sxs-lookup"><span data-stu-id="f3066-126">The `ExampleService` instance is **not** created by the service container.</span></span>
- <span data-ttu-id="f3066-127">Platforma **nie usuwa automatycznie** usług.</span><span class="sxs-lookup"><span data-stu-id="f3066-127">The framework does **not** dispose of the services automatically.</span></span>
- <span data-ttu-id="f3066-128">Deweloper jest odpowiedzialny za likwidację usług.</span><span class="sxs-lookup"><span data-stu-id="f3066-128">The developer is responsible for disposing the services.</span></span>

### <a name="idisposable-guidance-for-transient-and-shared-instances"></a><span data-ttu-id="f3066-129">Wskazówki interfejsu IDisposable dla wystąpień przejściowych i współużytkowanych</span><span class="sxs-lookup"><span data-stu-id="f3066-129">IDisposable guidance for Transient and shared instances</span></span>

#### <a name="transient-limited-lifetime"></a><span data-ttu-id="f3066-130">Przejściowy, ograniczony okres istnienia</span><span class="sxs-lookup"><span data-stu-id="f3066-130">Transient, limited lifetime</span></span>

<span data-ttu-id="f3066-131">**Scenariusz**</span><span class="sxs-lookup"><span data-stu-id="f3066-131">**Scenario**</span></span>

<span data-ttu-id="f3066-132">Aplikacja wymaga <xref:System.IDisposable> wystąpienia z przejściowym okresem istnienia dla jednego z następujących scenariuszy:</span><span class="sxs-lookup"><span data-stu-id="f3066-132">The app requires an <xref:System.IDisposable> instance with a transient lifetime for either of the following scenarios:</span></span>

- <span data-ttu-id="f3066-133">Wystąpienie jest rozwiązane w zakresie głównym (kontener główny).</span><span class="sxs-lookup"><span data-stu-id="f3066-133">The instance is resolved in the root scope (root container).</span></span>
- <span data-ttu-id="f3066-134">Wystąpienie powinno zostać usunięte przed zakończeniem zakresu.</span><span class="sxs-lookup"><span data-stu-id="f3066-134">The instance should be disposed before the scope ends.</span></span>

<span data-ttu-id="f3066-135">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="f3066-135">**Solution**</span></span>

<span data-ttu-id="f3066-136">Użyj wzorca fabryki, aby utworzyć wystąpienie poza zakresem nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="f3066-136">Use the factory pattern to create an instance outside of the parent scope.</span></span> <span data-ttu-id="f3066-137">W tej sytuacji aplikacja zwykle ma `Create` metodę, która wywołuje bezpośrednio Konstruktor typu końcowego.</span><span class="sxs-lookup"><span data-stu-id="f3066-137">In this situation, the app would generally have a `Create` method that calls the final type's constructor directly.</span></span> <span data-ttu-id="f3066-138">Jeśli typ końcowy ma inne zależności, fabryka może:</span><span class="sxs-lookup"><span data-stu-id="f3066-138">If the final type has other dependencies, the factory can:</span></span>

- <span data-ttu-id="f3066-139">Odbierz <xref:System.IServiceProvider> w konstruktorze.</span><span class="sxs-lookup"><span data-stu-id="f3066-139">Receive an <xref:System.IServiceProvider> in its constructor.</span></span>
- <span data-ttu-id="f3066-140">Użyj polecenia, <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities.CreateInstance%2A?displayProperty=nameWithType> Aby utworzyć wystąpienie wystąpienia poza kontenerem, przy użyciu kontenera dla jego zależności.</span><span class="sxs-lookup"><span data-stu-id="f3066-140">Use <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities.CreateInstance%2A?displayProperty=nameWithType> to instantiate the instance outside of the container, while using the container for its dependencies.</span></span>

#### <a name="shared-instance-limited-lifetime"></a><span data-ttu-id="f3066-141">Wystąpienie udostępnione, ograniczony okres istnienia</span><span class="sxs-lookup"><span data-stu-id="f3066-141">Shared instance, limited lifetime</span></span>

<span data-ttu-id="f3066-142">**Scenariusz**</span><span class="sxs-lookup"><span data-stu-id="f3066-142">**Scenario**</span></span>

<span data-ttu-id="f3066-143">Aplikacja wymaga <xref:System.IDisposable> wystąpienia udostępnionego w wielu usługach, ale <xref:System.IDisposable> wystąpienie powinno mieć ograniczony okres istnienia.</span><span class="sxs-lookup"><span data-stu-id="f3066-143">The app requires a shared <xref:System.IDisposable> instance across multiple services, but the <xref:System.IDisposable> instance should have a limited lifetime.</span></span>

<span data-ttu-id="f3066-144">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="f3066-144">**Solution**</span></span>

<span data-ttu-id="f3066-145">Zarejestruj wystąpienie z okresem istnienia w zakresie.</span><span class="sxs-lookup"><span data-stu-id="f3066-145">Register the instance with a scoped lifetime.</span></span> <span data-ttu-id="f3066-146">Użyj <xref:Microsoft.Extensions.DependencyInjection.IServiceScopeFactory.CreateScope%2A?displayProperty=nameWithType> , aby utworzyć nowy <xref:Microsoft.Extensions.DependencyInjection.IServiceScope> .</span><span class="sxs-lookup"><span data-stu-id="f3066-146">Use <xref:Microsoft.Extensions.DependencyInjection.IServiceScopeFactory.CreateScope%2A?displayProperty=nameWithType> to create a new <xref:Microsoft.Extensions.DependencyInjection.IServiceScope>.</span></span> <span data-ttu-id="f3066-147">Użyj zakresu, <xref:System.IServiceProvider> Aby uzyskać wymagane usługi.</span><span class="sxs-lookup"><span data-stu-id="f3066-147">Use the scope's <xref:System.IServiceProvider> to get required services.</span></span> <span data-ttu-id="f3066-148">Usuń zakres, gdy nie jest już wymagany.</span><span class="sxs-lookup"><span data-stu-id="f3066-148">Dispose the scope when it's no longer needed.</span></span>

#### <a name="general-idisposable-guidelines"></a><span data-ttu-id="f3066-149">Ogólne `IDisposable` wytyczne</span><span class="sxs-lookup"><span data-stu-id="f3066-149">General `IDisposable` guidelines</span></span>

- <span data-ttu-id="f3066-150">Nie rejestruj <xref:System.IDisposable> wystąpień z przejściowym okresem istnienia.</span><span class="sxs-lookup"><span data-stu-id="f3066-150">Don't register <xref:System.IDisposable> instances with a transient lifetime.</span></span> <span data-ttu-id="f3066-151">Zamiast tego użyj wzorca fabryki.</span><span class="sxs-lookup"><span data-stu-id="f3066-151">Use the factory pattern instead.</span></span>
- <span data-ttu-id="f3066-152">Nie należy rozwiązywać <xref:System.IDisposable> wystąpień z okresem przejściowym lub z określonym zakresem w zakresie głównym.</span><span class="sxs-lookup"><span data-stu-id="f3066-152">Don't resolve <xref:System.IDisposable> instances with a transient or scoped lifetime in the root scope.</span></span> <span data-ttu-id="f3066-153">Jedynym wyjątkiem jest to, że aplikacja tworzy/odtworzy i usuwa <xref:System.IServiceProvider> , ale nie jest idealnym wzorcem.</span><span class="sxs-lookup"><span data-stu-id="f3066-153">The only exception to this is if the app creates/recreates and disposes <xref:System.IServiceProvider>, but this isn't an ideal pattern.</span></span>
- <span data-ttu-id="f3066-154">Odebranie <xref:System.IDisposable> zależności za pośrednictwem programu di nie wymaga, aby odbiorca zaimplementował <xref:System.IDisposable> sam siebie.</span><span class="sxs-lookup"><span data-stu-id="f3066-154">Receiving an <xref:System.IDisposable> dependency via DI doesn't require that the receiver implement <xref:System.IDisposable> itself.</span></span> <span data-ttu-id="f3066-155">Odbiorca zależności nie <xref:System.IDisposable> powinien wywoływać <xref:System.IDisposable.Dispose%2A> tej zależności.</span><span class="sxs-lookup"><span data-stu-id="f3066-155">The receiver of the <xref:System.IDisposable> dependency shouldn't call <xref:System.IDisposable.Dispose%2A> on that dependency.</span></span>
- <span data-ttu-id="f3066-156">Używanie zakresów do kontrolowania okresów istnienia usług.</span><span class="sxs-lookup"><span data-stu-id="f3066-156">Use scopes to control the lifetimes of services.</span></span> <span data-ttu-id="f3066-157">Zakresy nie są hierarchiczne i nie ma żadnych specjalnych połączeń między zakresami.</span><span class="sxs-lookup"><span data-stu-id="f3066-157">Scopes aren't hierarchical, and there's no special connection among scopes.</span></span>

<span data-ttu-id="f3066-158">Aby uzyskać więcej informacji na temat oczyszczania zasobów, zobacz [Implementuj `Dispose` metodę](../../standard/garbage-collection/implementing-dispose.md)lub [Zaimplementuj `DisposeAsync` metodę](../../standard/garbage-collection/implementing-disposeasync.md).</span><span class="sxs-lookup"><span data-stu-id="f3066-158">For more information on resource cleanup, see [Implement a `Dispose` method](../../standard/garbage-collection/implementing-dispose.md), or [Implement a `DisposeAsync` method](../../standard/garbage-collection/implementing-disposeasync.md).</span></span> <span data-ttu-id="f3066-159">Dodatkowo Rozważ możliwość wypróbowania [usług przejściowych przechwyconych przez scenariusz kontenera](#disposable-transient-services-captured-by-container) w miarę odnoszących się do oczyszczania zasobów.</span><span class="sxs-lookup"><span data-stu-id="f3066-159">Additionally, consider the [Disposable transient services captured by container](#disposable-transient-services-captured-by-container) scenario as it relates to resource cleanup.</span></span>

## <a name="default-service-container-replacement"></a><span data-ttu-id="f3066-160">Zastępowanie kontenera usług domyślnych</span><span class="sxs-lookup"><span data-stu-id="f3066-160">Default service container replacement</span></span>

<span data-ttu-id="f3066-161">Wbudowany kontener usług został zaprojektowany z myślą o potrzebach platformy i większości aplikacji konsumenckich.</span><span class="sxs-lookup"><span data-stu-id="f3066-161">The built-in service container is designed to serve the needs of the framework and most consumer apps.</span></span> <span data-ttu-id="f3066-162">Zalecamy użycie wbudowanego kontenera, chyba że potrzebna jest określona funkcja, która nie jest obsługiwana przez program, na przykład:</span><span class="sxs-lookup"><span data-stu-id="f3066-162">We recommend using the built-in container unless you need a specific feature that it doesn't support, such as:</span></span>

- <span data-ttu-id="f3066-163">Iniekcja właściwości</span><span class="sxs-lookup"><span data-stu-id="f3066-163">Property injection</span></span>
- <span data-ttu-id="f3066-164">Iniekcja oparta na nazwie</span><span class="sxs-lookup"><span data-stu-id="f3066-164">Injection based on name</span></span>
- <span data-ttu-id="f3066-165">Kontenery podrzędne</span><span class="sxs-lookup"><span data-stu-id="f3066-165">Child containers</span></span>
- <span data-ttu-id="f3066-166">Niestandardowe zarządzanie okresem istnienia</span><span class="sxs-lookup"><span data-stu-id="f3066-166">Custom lifetime management</span></span>
- <span data-ttu-id="f3066-167">`Func<T>` Obsługa inicjowania z opóźnieniem</span><span class="sxs-lookup"><span data-stu-id="f3066-167">`Func<T>` support for lazy initialization</span></span>
- <span data-ttu-id="f3066-168">Rejestracja oparta na Konwencji</span><span class="sxs-lookup"><span data-stu-id="f3066-168">Convention-based registration</span></span>

<span data-ttu-id="f3066-169">Za pomocą aplikacji ASP.NET Core można używać następujących kontenerów innych firm:</span><span class="sxs-lookup"><span data-stu-id="f3066-169">The following third-party containers can be used with ASP.NET Core apps:</span></span>

- [<span data-ttu-id="f3066-170">Autofac</span><span class="sxs-lookup"><span data-stu-id="f3066-170">Autofac</span></span>](https://autofac.readthedocs.io/en/latest/integration/aspnetcore.html)
- [<span data-ttu-id="f3066-171">DryIoc</span><span class="sxs-lookup"><span data-stu-id="f3066-171">DryIoc</span></span>](https://www.nuget.org/packages/DryIoc.Microsoft.DependencyInjection)
- [<span data-ttu-id="f3066-172">Prolongaty</span><span class="sxs-lookup"><span data-stu-id="f3066-172">Grace</span></span>](https://www.nuget.org/packages/Grace.DependencyInjection.Extensions)
- [<span data-ttu-id="f3066-173">LightInject</span><span class="sxs-lookup"><span data-stu-id="f3066-173">LightInject</span></span>](https://github.com/seesharper/LightInject.Microsoft.DependencyInjection)
- [<span data-ttu-id="f3066-174">Lamar</span><span class="sxs-lookup"><span data-stu-id="f3066-174">Lamar</span></span>](https://jasperfx.github.io/lamar/)
- [<span data-ttu-id="f3066-175">Stashbox</span><span class="sxs-lookup"><span data-stu-id="f3066-175">Stashbox</span></span>](https://github.com/z4kn4fein/stashbox-extensions-dependencyinjection)
- [<span data-ttu-id="f3066-176">Unity</span><span class="sxs-lookup"><span data-stu-id="f3066-176">Unity</span></span>](https://www.nuget.org/packages/Unity.Microsoft.DependencyInjection)

## <a name="thread-safety"></a><span data-ttu-id="f3066-177">Bezpieczeństwo wątkowe</span><span class="sxs-lookup"><span data-stu-id="f3066-177">Thread safety</span></span>

<span data-ttu-id="f3066-178">Twórz bezpieczne dla wątków usługi pojedyncze.</span><span class="sxs-lookup"><span data-stu-id="f3066-178">Create thread-safe singleton services.</span></span> <span data-ttu-id="f3066-179">Jeśli usługa singleton ma zależność od przejściowej usługi, usługa przejściowa może również wymagać bezpieczeństwa wątków w zależności od tego, w jaki sposób jest używana przez pojedyncze.</span><span class="sxs-lookup"><span data-stu-id="f3066-179">If a singleton service has a dependency on a transient service, the transient service may also require thread safety depending on how it's used by the singleton.</span></span>

<span data-ttu-id="f3066-180">Metoda fabryki pojedynczej usługi, taka jak drugi argument funkcji [AddSingleton \<TService> (IServiceCollection, Func \<IServiceProvider,TService> )](xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A), nie musi być bezpieczna wątkowo.</span><span class="sxs-lookup"><span data-stu-id="f3066-180">The factory method of single service, such as the second argument to [AddSingleton\<TService>(IServiceCollection, Func\<IServiceProvider,TService>)](xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A), doesn't need to be thread-safe.</span></span> <span data-ttu-id="f3066-181">Podobnie jak w przypadku `static` konstruktora typu (), gwarantowane jest wywoływanie tylko raz przez pojedynczy wątek.</span><span class="sxs-lookup"><span data-stu-id="f3066-181">Like a type (`static`) constructor, it's guaranteed to be called only once by a single thread.</span></span>

## <a name="recommendations"></a><span data-ttu-id="f3066-182">Zalecenia</span><span class="sxs-lookup"><span data-stu-id="f3066-182">Recommendations</span></span>

- <span data-ttu-id="f3066-183">`async/await``Task`rozpoznawanie usług opartych na usłudze i nie jest obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="f3066-183">`async/await` and `Task` based service resolution isn't supported.</span></span> <span data-ttu-id="f3066-184">Ponieważ język C# nie obsługuje konstruktorów asynchronicznych, należy używać metod asynchronicznych po synchronicznym rozpoznaniu usługi.</span><span class="sxs-lookup"><span data-stu-id="f3066-184">Because C# doesn't support asynchronous constructors, use asynchronous methods after synchronously resolving the service.</span></span>
- <span data-ttu-id="f3066-185">Unikaj przechowywania danych i konfiguracji bezpośrednio w kontenerze usługi.</span><span class="sxs-lookup"><span data-stu-id="f3066-185">Avoid storing data and configuration directly in the service container.</span></span> <span data-ttu-id="f3066-186">Na przykład koszyk użytkownika nie powinien być zazwyczaj dodawany do kontenera usługi.</span><span class="sxs-lookup"><span data-stu-id="f3066-186">For example, a user's shopping cart shouldn't typically be added to the service container.</span></span> <span data-ttu-id="f3066-187">Konfiguracja powinna używać wzorca opcji.</span><span class="sxs-lookup"><span data-stu-id="f3066-187">Configuration should use the options pattern.</span></span> <span data-ttu-id="f3066-188">Podobnie należy unikać obiektów "posiadacz danych", które istnieją tylko w celu zezwalania na dostęp do innego obiektu.</span><span class="sxs-lookup"><span data-stu-id="f3066-188">Similarly, avoid "data holder" objects that only exist to allow access to another object.</span></span> <span data-ttu-id="f3066-189">Lepiej jest zażądać rzeczywistego elementu za pośrednictwem DI.</span><span class="sxs-lookup"><span data-stu-id="f3066-189">It's better to request the actual item via DI.</span></span>
- <span data-ttu-id="f3066-190">Unikaj statycznego dostępu do usług.</span><span class="sxs-lookup"><span data-stu-id="f3066-190">Avoid static access to services.</span></span> <span data-ttu-id="f3066-191">Na przykład Unikaj przechwytywania [IApplicationBuilder. ApplicationServices](xref:Microsoft.AspNetCore.Builder.IApplicationBuilder.ApplicationServices) jako statycznego pola lub właściwości do użycia w innym miejscu.</span><span class="sxs-lookup"><span data-stu-id="f3066-191">For example, avoid capturing [IApplicationBuilder.ApplicationServices](xref:Microsoft.AspNetCore.Builder.IApplicationBuilder.ApplicationServices) as a static field or property for use elsewhere.</span></span>
- <span data-ttu-id="f3066-192">Utrzymuj [szybkie](#async-di-factories-can-cause-deadlocks) i synchroniczne operacje.</span><span class="sxs-lookup"><span data-stu-id="f3066-192">Keep [DI factories](#async-di-factories-can-cause-deadlocks) fast and synchronous.</span></span>
- <span data-ttu-id="f3066-193">Unikaj używania [*wzorca lokalizatora usługi*](#scoped-service-as-singleton).</span><span class="sxs-lookup"><span data-stu-id="f3066-193">Avoid using the [*service locator pattern*](#scoped-service-as-singleton).</span></span> <span data-ttu-id="f3066-194">Na przykład nie wywołuj, <xref:System.IServiceProvider.GetService%2A> Aby uzyskać wystąpienie usługi, gdy będzie można użyć di zamiast.</span><span class="sxs-lookup"><span data-stu-id="f3066-194">For example, don't invoke <xref:System.IServiceProvider.GetService%2A> to obtain a service instance when you can use DI instead.</span></span>
- <span data-ttu-id="f3066-195">Inna odmiana lokalizatora usługi, aby uniknąć, wprowadza fabrykę, która rozwiązuje zależności w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="f3066-195">Another service locator variation to avoid is injecting a factory that resolves dependencies at runtime.</span></span> <span data-ttu-id="f3066-196">Obie te praktyki mieszają się [z niewersjami strategii kontroli](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#dependency-inversion) .</span><span class="sxs-lookup"><span data-stu-id="f3066-196">Both of these practices mix [Inversion of Control](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#dependency-inversion) strategies.</span></span>
- <span data-ttu-id="f3066-197">Należy unikać wywołań do <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> programu `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="f3066-197">Avoid calls to <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> in `ConfigureServices`.</span></span> <span data-ttu-id="f3066-198">Wywoływanie `BuildServiceProvider` zazwyczaj odbywa się, gdy deweloper chce rozwiązać usługę w programie `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="f3066-198">Calling `BuildServiceProvider` typically happens when the developer wants to resolve a service in `ConfigureServices`.</span></span>
- <span data-ttu-id="f3066-199">[Nierozporządzalne usługi przejściowe są przechwytywane](#disposable-transient-services-captured-by-container) przez kontener do usuwania.</span><span class="sxs-lookup"><span data-stu-id="f3066-199">[Disposable transient services are captured](#disposable-transient-services-captured-by-container) by the container for disposal.</span></span> <span data-ttu-id="f3066-200">Może to przeznaczyć przeciek pamięci, jeśli został rozwiązany z kontenera najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="f3066-200">This can turn into a memory leak if resolved from the top-level container.</span></span>
- <span data-ttu-id="f3066-201">Włącz weryfikację zakresu, aby upewnić się, że aplikacja nie ma pojedynczych, które przechwytują usługi o określonym zakresie.</span><span class="sxs-lookup"><span data-stu-id="f3066-201">Enable scope validation to make sure the app doesn't have singletons that capture scoped services.</span></span> <span data-ttu-id="f3066-202">Aby uzyskać więcej informacji, zobacz [Walidacja zakresu](dependency-injection.md#scope-validation).</span><span class="sxs-lookup"><span data-stu-id="f3066-202">For more information, see [Scope validation](dependency-injection.md#scope-validation).</span></span>

<span data-ttu-id="f3066-203">Podobnie jak w przypadku wszystkich zestawów zaleceń, mogą wystąpić sytuacje, w których ignorowanie zalecenia jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="f3066-203">Like all sets of recommendations, you may encounter situations where ignoring a recommendation is required.</span></span> <span data-ttu-id="f3066-204">Wyjątki są rzadkimi, głównie szczególnymi przypadkami w ramach samej struktury.</span><span class="sxs-lookup"><span data-stu-id="f3066-204">Exceptions are rare, mostly special cases within the framework itself.</span></span>

<span data-ttu-id="f3066-205">DI jest *alternatywą* dla wzorców dostępu do obiektów static/Global.</span><span class="sxs-lookup"><span data-stu-id="f3066-205">DI is an *alternative* to static/global object access patterns.</span></span> <span data-ttu-id="f3066-206">Możesz nie być w stanie korzystać z zalet programu DI w przypadku jego mieszania z dostępem do obiektów statycznych.</span><span class="sxs-lookup"><span data-stu-id="f3066-206">You may not be able to realize the benefits of DI if you mix it with static object access.</span></span>

## <a name="example-anti-patterns"></a><span data-ttu-id="f3066-207">Przykładowe antywzorce</span><span class="sxs-lookup"><span data-stu-id="f3066-207">Example anti-patterns</span></span>

<span data-ttu-id="f3066-208">Oprócz wytycznych opisanych w tym artykule, istnieje kilka antywzorców, *których **należy** unikać* .</span><span class="sxs-lookup"><span data-stu-id="f3066-208">In addition to the guidelines in this article, there are several anti-patterns *you **should** avoid* .</span></span> <span data-ttu-id="f3066-209">Niektóre z tych antywzorców zapoznają się z tworzeniem środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="f3066-209">Some of these anti-patterns are learnings from developing the runtimes themselves.</span></span>

> [!WARNING]
> <span data-ttu-id="f3066-210">Są to przykładowe *wzorce,* *nie Kopiuj kodu, nie używaj* tych wzorców i unikaj tych wzorców we wszystkich kosztach.</span><span class="sxs-lookup"><span data-stu-id="f3066-210">These are example anti-patterns, *do not* copy the code, *do not* use these patterns, and avoid these patterns at all costs.</span></span>

### <a name="disposable-transient-services-captured-by-container"></a><span data-ttu-id="f3066-211">Jednorazowe usługi przejściowe przechwycone przez kontener</span><span class="sxs-lookup"><span data-stu-id="f3066-211">Disposable transient services captured by container</span></span>

<span data-ttu-id="f3066-212">Po zarejestrowaniu usług *przejściowych* , które implementują <xref:System.IDisposable> , domyślnie do tych odwołań są przechowywane kontenery di, a nie <xref:System.IDisposable.Dispose> ich do momentu zatrzymania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f3066-212">When you register *Transient* services that implement <xref:System.IDisposable>, by default the DI container will hold onto these references, and not <xref:System.IDisposable.Dispose> of them until the application stops.</span></span> <span data-ttu-id="f3066-213">Przyczyną może być przeciek pamięci, jeśli został on rozwiązany z poziomu kontenera.</span><span class="sxs-lookup"><span data-stu-id="f3066-213">This can turn into a memory leak if resolved from the level container.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="18-30":::

<span data-ttu-id="f3066-214">W poprzednim wzorcu `ExampleDisposable` są tworzone wystąpienia 1 000 obiektów i są one odblokowane.</span><span class="sxs-lookup"><span data-stu-id="f3066-214">In the preceding anti-pattern, 1,000 `ExampleDisposable` objects are instantiated and rooted.</span></span> <span data-ttu-id="f3066-215">Nie zostaną usunięte, dopóki `serviceProvider` wystąpienie nie zostanie usunięte.</span><span class="sxs-lookup"><span data-stu-id="f3066-215">They will not be disposed of until the `serviceProvider` instance is disposed.</span></span>

<span data-ttu-id="f3066-216">Aby uzyskać więcej informacji na temat debugowania przecieków pamięci, zobacz [debugowanie przecieku pamięci w programie .NET](../diagnostics/debug-memory-leak.md).</span><span class="sxs-lookup"><span data-stu-id="f3066-216">For more information on debugging memory leaks, see [Debug a memory leak in .NET](../diagnostics/debug-memory-leak.md).</span></span>

### <a name="async-di-factories-can-cause-deadlocks"></a><span data-ttu-id="f3066-217">Asynchroniczne operacje DI mogą spowodować zakleszczenie</span><span class="sxs-lookup"><span data-stu-id="f3066-217">Async DI factories can cause deadlocks</span></span>

<span data-ttu-id="f3066-218">Termin "DI Factors" oznacza metody przeciążenia, które istnieją podczas wywoływania `Add{LIFETIME}` .</span><span class="sxs-lookup"><span data-stu-id="f3066-218">The term "DI factories" refers to the overload methods that exist when calling `Add{LIFETIME}`.</span></span> <span data-ttu-id="f3066-219">Istnieją przeciążenia akceptujące `Func<IServiceProvider, T>` miejsce `T` , gdzie jest rejestrowana usługa, a parametr ma nazwę `implementationFactory` .</span><span class="sxs-lookup"><span data-stu-id="f3066-219">There are overloads accepting a `Func<IServiceProvider, T>` where `T` is the service being registered, and the parameter is named `implementationFactory`.</span></span> <span data-ttu-id="f3066-220">`implementationFactory`Można podać jako wyrażenie lambda, funkcję lokalną lub metodę.</span><span class="sxs-lookup"><span data-stu-id="f3066-220">The `implementationFactory` can be provided as a lambda expression, local function, or method.</span></span> <span data-ttu-id="f3066-221">Jeśli fabryka jest asynchroniczna i używasz <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> , spowoduje to zakleszczenie.</span><span class="sxs-lookup"><span data-stu-id="f3066-221">If the factory is asynchronous, and you use <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>, this will cause a deadlock.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="32-45" highlight="4-8":::

<span data-ttu-id="f3066-222">W poprzednim kodzie, `implementationFactory` otrzymuje wyrażenie lambda, gdzie treść wywołuje <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> `Task<Bar>` metodę zwracającą.</span><span class="sxs-lookup"><span data-stu-id="f3066-222">In the preceding code, the `implementationFactory` is given a lambda expression where the body calls <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> on a `Task<Bar>` returning method.</span></span> <span data-ttu-id="f3066-223">***Powoduje to zakleszczenie*** .</span><span class="sxs-lookup"><span data-stu-id="f3066-223">This ***causes a deadlock*** .</span></span> <span data-ttu-id="f3066-224">`GetBarAsync`Metoda po prostu emuluje asynchroniczne operacje pracy z <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> , a następnie wywołuje <xref:Microsoft.Extensions.DependencyInjection.ServiceProviderServiceExtensions.GetRequiredService%60%601(System.IServiceProvider)> .</span><span class="sxs-lookup"><span data-stu-id="f3066-224">The `GetBarAsync` method simply emulates an asynchronous work operation with <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>, and then calls <xref:Microsoft.Extensions.DependencyInjection.ServiceProviderServiceExtensions.GetRequiredService%60%601(System.IServiceProvider)>.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="47-53":::

<span data-ttu-id="f3066-225">Aby uzyskać więcej informacji na temat wskazówek asynchronicznych, zobacz [programowanie asynchroniczne: ważne informacje i porady](../../csharp/async.md#important-info-and-advice).</span><span class="sxs-lookup"><span data-stu-id="f3066-225">For more information on asynchronous guidance, see [Asynchronous programming: Important info and advice](../../csharp/async.md#important-info-and-advice).</span></span> <span data-ttu-id="f3066-226">Aby uzyskać więcej informacji na temat zakleszczenia debugowania, zobacz [debugowanie zakleszczenia w programie .NET](../diagnostics/debug-deadlock.md).</span><span class="sxs-lookup"><span data-stu-id="f3066-226">For more information debugging deadlocks, see [Debug a deadlock in .NET](../diagnostics/debug-deadlock.md).</span></span>

<span data-ttu-id="f3066-227">W przypadku korzystania z tego oprogramowania antywzorca i wystąpienia zakleszczenia można wyświetlić dwa wątki oczekujące w oknie stosów równoległych programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f3066-227">When you're running this anti-pattern and the deadlock occurs, you can view the two threads waiting from Visual Studio's Parallel Stacks window.</span></span> <span data-ttu-id="f3066-228">Aby uzyskać więcej informacji, zobacz [Wyświetlanie wątków i zadań w oknie stosów równoległych](/visualstudio/debugger/using-the-parallel-stacks-window).</span><span class="sxs-lookup"><span data-stu-id="f3066-228">For more information, see [View threads and tasks in the Parallel Stacks window](/visualstudio/debugger/using-the-parallel-stacks-window).</span></span>

### <a name="captive-dependency"></a><span data-ttu-id="f3066-229">Zależność podrzędna</span><span class="sxs-lookup"><span data-stu-id="f3066-229">Captive dependency</span></span>

<span data-ttu-id="f3066-230">Termin ["zależność podrzędna"](https://blog.ploeh.dk/2014/06/02/captive-dependency) został zastosowany przez [oznaczenie Seeman](https://blog.ploeh.dk/about)i odnosi się do nieprawdziwej konfiguracji okresów istnienia usługi, w przypadku których usługa o dłuższym czasie utrzymuje nieprzerwaną usługę.</span><span class="sxs-lookup"><span data-stu-id="f3066-230">The term ["captive dependency"](https://blog.ploeh.dk/2014/06/02/captive-dependency) was coined by [Mark Seeman](https://blog.ploeh.dk/about), and refers to the misconfiguration of service lifetimes, where a longer-lived service holds a shorter-lived service captive.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="55-65":::

<span data-ttu-id="f3066-231">W powyższym kodzie `Foo` jest zarejestrowany jako pojedynczy i `Bar` ma zakres, który na powierzchni jest prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="f3066-231">In the preceding code, `Foo` is registered as a singleton and `Bar` is scoped - which on the surface seems valid.</span></span> <span data-ttu-id="f3066-232">Należy jednak wziąć pod uwagę implementację programu `Foo` .</span><span class="sxs-lookup"><span data-stu-id="f3066-232">However, consider the implementation of `Foo`.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Foo.cs" highlight="5":::

<span data-ttu-id="f3066-233">`Foo`Obiekt wymaga `Bar` obiektu, a ponieważ `Foo` jest elementem pojedynczym i `Bar` ma zakres-nieprawidłową konfigurację.</span><span class="sxs-lookup"><span data-stu-id="f3066-233">The `Foo` object requires a `Bar` object, and since `Foo` is a singleton, and `Bar` is scoped - this is a misconfiguration.</span></span> <span data-ttu-id="f3066-234">W takim przypadku `Foo` można utworzyć wystąpienie tylko raz, a jego `Bar` okres istnienia będzie dłuższy niż przewidziany okres istnienia w zakresie `Bar` .</span><span class="sxs-lookup"><span data-stu-id="f3066-234">As is, `Foo` would only be instantiated once, and it would hold onto `Bar` for its lifetime, which is longer than the intended scoped lifetime of `Bar`.</span></span> <span data-ttu-id="f3066-235">Należy rozważyć sprawdzenie poprawności zakresów, przekazanie `validateScopes: true` do <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Boolean)> .</span><span class="sxs-lookup"><span data-stu-id="f3066-235">You should consider validating scopes, by passing `validateScopes: true` to the <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Boolean)>.</span></span> <span data-ttu-id="f3066-236">Podczas sprawdzania poprawności zakresów uzyskasz <xref:System.InvalidOperationException> komunikat podobny do "nie można korzystać z usługi w zakresie" z pojedynczego elementu "foo".</span><span class="sxs-lookup"><span data-stu-id="f3066-236">When you validate the scopes, you'd get an <xref:System.InvalidOperationException> with a message similar to "Cannot consume scoped service 'Bar' from singleton 'Foo'.".</span></span>

<span data-ttu-id="f3066-237">Aby uzyskać więcej informacji, zobacz [Walidacja zakresu](dependency-injection.md#scope-validation).</span><span class="sxs-lookup"><span data-stu-id="f3066-237">For more information, see [Scope validation](dependency-injection.md#scope-validation).</span></span>

### <a name="scoped-service-as-singleton"></a><span data-ttu-id="f3066-238">Usługa objęta zakresem jako pojedyncza</span><span class="sxs-lookup"><span data-stu-id="f3066-238">Scoped service as singleton</span></span>

<span data-ttu-id="f3066-239">W przypadku korzystania z usług objętych zakresem, jeśli nie tworzysz zakresu lub w istniejącym zakresie — usługa zostanie poprzednia.</span><span class="sxs-lookup"><span data-stu-id="f3066-239">When using scoped services, if you're not creating a scope or within an existing scope - the service becomes a singleton.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="68-82" highlight="13-14":::

<span data-ttu-id="f3066-240">W powyższym kodzie `Bar` jest pobierany w <xref:Microsoft.Extensions.DependencyInjection.IServiceScope> , który jest prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="f3066-240">In the preceding code, `Bar` is retrieved within an <xref:Microsoft.Extensions.DependencyInjection.IServiceScope>, which is correct.</span></span> <span data-ttu-id="f3066-241">Antywzorzec to pobieranie `Bar` poza zakresem, a zmienna nosi nazwę, `avoid` Aby pokazać, które przykładowe pobieranie jest nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="f3066-241">The anti-pattern is the retrieval of `Bar` outside of the scope, and the variable is named `avoid` to show which example retrieval is incorrect.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3066-242">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f3066-242">See also</span></span>

- [<span data-ttu-id="f3066-243">Iniekcja zależności w programie .NET</span><span class="sxs-lookup"><span data-stu-id="f3066-243">Dependency injection in .NET</span></span>](dependency-injection.md)
- [<span data-ttu-id="f3066-244">Samouczek: używanie iniekcji zależności w programie .NET</span><span class="sxs-lookup"><span data-stu-id="f3066-244">Tutorial: Use dependency injection in .NET</span></span>](dependency-injection-usage.md)
