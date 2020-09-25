---
title: Wskazówki dotyczące iniekcji zależności
description: Poznaj różne wskazówki dotyczące iniekcji zależności oraz najlepsze rozwiązania dotyczące tworzenia aplikacji .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/23/2020
ms.topic: guide
ms.openlocfilehash: a8d52642b9217c7340db69494624d8ab85ea6c92
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247912"
---
# <a name="dependency-injection-guidelines"></a><span data-ttu-id="56808-103">Wskazówki dotyczące iniekcji zależności</span><span class="sxs-lookup"><span data-stu-id="56808-103">Dependency injection guidelines</span></span>

<span data-ttu-id="56808-104">Ten artykuł zawiera ogólne wskazówki i najlepsze rozwiązania dotyczące implementowania iniekcji zależności w aplikacjach .NET.</span><span class="sxs-lookup"><span data-stu-id="56808-104">This article provides general guidelines and best practices for implementing dependency injection in .NET applications.</span></span>

## <a name="design-services-for-dependency-injection"></a><span data-ttu-id="56808-105">Projektowanie usług do iniekcji zależności</span><span class="sxs-lookup"><span data-stu-id="56808-105">Design services for dependency injection</span></span>

<span data-ttu-id="56808-106">Podczas projektowania usług pod kątem iniekcji zależności:</span><span class="sxs-lookup"><span data-stu-id="56808-106">When designing services for dependency injection:</span></span>

- <span data-ttu-id="56808-107">Unikaj stanowych, statycznych klas i elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="56808-107">Avoid stateful, static classes and members.</span></span> <span data-ttu-id="56808-108">Należy unikać tworzenia stanu globalnego przez projektowanie aplikacji do korzystania z usług pojedynczych.</span><span class="sxs-lookup"><span data-stu-id="56808-108">Avoid creating global state by designing apps to use singleton services instead.</span></span>
- <span data-ttu-id="56808-109">Unikaj bezpośredniego tworzenia wystąpień klas zależnych w ramach usług.</span><span class="sxs-lookup"><span data-stu-id="56808-109">Avoid direct instantiation of dependent classes within services.</span></span> <span data-ttu-id="56808-110">Bezpośrednie utworzenie wystąpienia Couples kod do konkretnej implementacji.</span><span class="sxs-lookup"><span data-stu-id="56808-110">Direct instantiation couples the code to a particular implementation.</span></span>
- <span data-ttu-id="56808-111">Zapewnianie niewielkich, dobrze przeprowadzonych i łatwych do przetestowania usług.</span><span class="sxs-lookup"><span data-stu-id="56808-111">Make services small, well-factored, and easily tested.</span></span>

<span data-ttu-id="56808-112">Jeśli klasa ma liczne wstrzykiwane zależności, może być znak, że Klasa ma zbyt wiele obowiązków i narusza [zasadę pojedynczej odpowiedzialności (SRP)](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#single-responsibility).</span><span class="sxs-lookup"><span data-stu-id="56808-112">If a class has many injected dependencies, it might be a sign that the class has too many responsibilities and violates the [Single Responsibility Principle (SRP)](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#single-responsibility).</span></span> <span data-ttu-id="56808-113">Próba refaktoryzacji klasy przez przeniesienie niektórych jej obowiązków do nowych klas.</span><span class="sxs-lookup"><span data-stu-id="56808-113">Attempt to refactor the class by moving some of its responsibilities into new classes.</span></span>

### <a name="disposal-of-services"></a><span data-ttu-id="56808-114">Usuwanie usług</span><span class="sxs-lookup"><span data-stu-id="56808-114">Disposal of services</span></span>

<span data-ttu-id="56808-115">Kontener jest odpowiedzialny za oczyszczanie typów, które tworzy, i <xref:System.IDisposable.Dispose%2A> wywołuje <xref:System.IDisposable> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="56808-115">The container is responsible for cleanup of types it creates, and calls <xref:System.IDisposable.Dispose%2A> on <xref:System.IDisposable> instances.</span></span> <span data-ttu-id="56808-116">Usługi rozpoznane przez kontener nigdy nie powinny zostać usunięte przez dewelopera.</span><span class="sxs-lookup"><span data-stu-id="56808-116">Services resolved from the container should never be disposed by the developer.</span></span> <span data-ttu-id="56808-117">Jeśli typ lub fabryka są zarejestrowane jako pojedyncze, kontener usuwa pojedyncze automatycznie.</span><span class="sxs-lookup"><span data-stu-id="56808-117">If a type or factory is registered as a singleton, the container disposes the singleton automatically.</span></span>

<span data-ttu-id="56808-118">W poniższym przykładzie usługi są tworzone przez kontener usługi i usuwane automatycznie:</span><span class="sxs-lookup"><span data-stu-id="56808-118">In the following example, the services are created by the service container and disposed automatically:</span></span>

:::code language="csharp" source="snippets/configuration/console-di-disposable/TransientDisposable.cs":::

:::code language="csharp" source="snippets/configuration/console-di-disposable/ScopedDisposable.cs":::

:::code language="csharp" source="snippets/configuration/console-di-disposable/SingletonDisposable.cs":::

:::code language="csharp" source="snippets/configuration/console-di-disposable/Program.cs" range="1-21,41-60":::

<span data-ttu-id="56808-119">Konsola debugowania wyświetla następujące przykładowe dane wyjściowe po uruchomieniu:</span><span class="sxs-lookup"><span data-stu-id="56808-119">The debug console shows the following sample output after running:</span></span>

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

### <a name="services-not-created-by-the-service-container"></a><span data-ttu-id="56808-120">Usługi, które nie zostały utworzone przez kontener usługi</span><span class="sxs-lookup"><span data-stu-id="56808-120">Services not created by the service container</span></span>

<span data-ttu-id="56808-121">Spójrzmy na poniższy kod:</span><span class="sxs-lookup"><span data-stu-id="56808-121">Consider the following code:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddSingleton(new ExampleService());

    // ...
}
```

<span data-ttu-id="56808-122">Powyższy kod ma następujące działanie:</span><span class="sxs-lookup"><span data-stu-id="56808-122">In the preceding code:</span></span>

- <span data-ttu-id="56808-123">`ExampleService`Wystąpienie **nie** jest tworzone przez kontener usługi.</span><span class="sxs-lookup"><span data-stu-id="56808-123">The `ExampleService` instance is **not** created by the service container.</span></span>
- <span data-ttu-id="56808-124">Platforma **nie usuwa automatycznie** usług.</span><span class="sxs-lookup"><span data-stu-id="56808-124">The framework does **not** dispose of the services automatically.</span></span>
- <span data-ttu-id="56808-125">Deweloper jest odpowiedzialny za likwidację usług.</span><span class="sxs-lookup"><span data-stu-id="56808-125">The developer is responsible for disposing the services.</span></span>

### <a name="idisposable-guidance-for-transient-and-shared-instances"></a><span data-ttu-id="56808-126">Wskazówki interfejsu IDisposable dla wystąpień przejściowych i współużytkowanych</span><span class="sxs-lookup"><span data-stu-id="56808-126">IDisposable guidance for Transient and shared instances</span></span>

#### <a name="transient-limited-lifetime"></a><span data-ttu-id="56808-127">Przejściowy, ograniczony okres istnienia</span><span class="sxs-lookup"><span data-stu-id="56808-127">Transient, limited lifetime</span></span>

<span data-ttu-id="56808-128">**Scenariusz**</span><span class="sxs-lookup"><span data-stu-id="56808-128">**Scenario**</span></span>

<span data-ttu-id="56808-129">Aplikacja wymaga <xref:System.IDisposable> wystąpienia z przejściowym okresem istnienia dla jednego z następujących scenariuszy:</span><span class="sxs-lookup"><span data-stu-id="56808-129">The app requires an <xref:System.IDisposable> instance with a transient lifetime for either of the following scenarios:</span></span>

- <span data-ttu-id="56808-130">Wystąpienie jest rozwiązane w zakresie głównym (kontener główny).</span><span class="sxs-lookup"><span data-stu-id="56808-130">The instance is resolved in the root scope (root container).</span></span>
- <span data-ttu-id="56808-131">Wystąpienie powinno zostać usunięte przed zakończeniem zakresu.</span><span class="sxs-lookup"><span data-stu-id="56808-131">The instance should be disposed before the scope ends.</span></span>

<span data-ttu-id="56808-132">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="56808-132">**Solution**</span></span>

<span data-ttu-id="56808-133">Użyj wzorca fabryki, aby utworzyć wystąpienie poza zakresem nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="56808-133">Use the factory pattern to create an instance outside of the parent scope.</span></span> <span data-ttu-id="56808-134">W tej sytuacji aplikacja zwykle ma `Create` metodę, która wywołuje bezpośrednio Konstruktor typu końcowego.</span><span class="sxs-lookup"><span data-stu-id="56808-134">In this situation, the app would generally have a `Create` method that calls the final type's constructor directly.</span></span> <span data-ttu-id="56808-135">Jeśli typ końcowy ma inne zależności, fabryka może:</span><span class="sxs-lookup"><span data-stu-id="56808-135">If the final type has other dependencies, the factory can:</span></span>

- <span data-ttu-id="56808-136">Odbierz <xref:System.IServiceProvider> w konstruktorze.</span><span class="sxs-lookup"><span data-stu-id="56808-136">Receive an <xref:System.IServiceProvider> in its constructor.</span></span>
- <span data-ttu-id="56808-137">Użyj polecenia, <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities.CreateInstance%2A?displayProperty=nameWithType> Aby utworzyć wystąpienie wystąpienia poza kontenerem, przy użyciu kontenera dla jego zależności.</span><span class="sxs-lookup"><span data-stu-id="56808-137">Use <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities.CreateInstance%2A?displayProperty=nameWithType> to instantiate the instance outside of the container, while using the container for its dependencies.</span></span>

#### <a name="shared-instance-limited-lifetime"></a><span data-ttu-id="56808-138">Wystąpienie udostępnione, ograniczony okres istnienia</span><span class="sxs-lookup"><span data-stu-id="56808-138">Shared instance, limited lifetime</span></span>

<span data-ttu-id="56808-139">**Scenariusz**</span><span class="sxs-lookup"><span data-stu-id="56808-139">**Scenario**</span></span>

<span data-ttu-id="56808-140">Aplikacja wymaga <xref:System.IDisposable> wystąpienia udostępnionego w wielu usługach, ale <xref:System.IDisposable> wystąpienie powinno mieć ograniczony okres istnienia.</span><span class="sxs-lookup"><span data-stu-id="56808-140">The app requires a shared <xref:System.IDisposable> instance across multiple services, but the <xref:System.IDisposable> instance should have a limited lifetime.</span></span>

<span data-ttu-id="56808-141">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="56808-141">**Solution**</span></span>

<span data-ttu-id="56808-142">Zarejestruj wystąpienie z okresem istnienia w zakresie.</span><span class="sxs-lookup"><span data-stu-id="56808-142">Register the instance with a scoped lifetime.</span></span> <span data-ttu-id="56808-143">Użyj <xref:Microsoft.Extensions.DependencyInjection.IServiceScopeFactory.CreateScope%2A?displayProperty=nameWithType> , aby utworzyć nowy <xref:Microsoft.Extensions.DependencyInjection.IServiceScope> .</span><span class="sxs-lookup"><span data-stu-id="56808-143">Use <xref:Microsoft.Extensions.DependencyInjection.IServiceScopeFactory.CreateScope%2A?displayProperty=nameWithType> to create a new <xref:Microsoft.Extensions.DependencyInjection.IServiceScope>.</span></span> <span data-ttu-id="56808-144">Użyj zakresu, <xref:System.IServiceProvider> Aby uzyskać wymagane usługi.</span><span class="sxs-lookup"><span data-stu-id="56808-144">Use the scope's <xref:System.IServiceProvider> to get required services.</span></span> <span data-ttu-id="56808-145">Usuń zakres, gdy nie jest już wymagany.</span><span class="sxs-lookup"><span data-stu-id="56808-145">Dispose the scope when it's no longer needed.</span></span>

#### <a name="general-idisposable-guidelines"></a><span data-ttu-id="56808-146">Ogólne `IDisposable` wytyczne</span><span class="sxs-lookup"><span data-stu-id="56808-146">General `IDisposable` guidelines</span></span>

- <span data-ttu-id="56808-147">Nie rejestruj <xref:System.IDisposable> wystąpień z przejściowym okresem istnienia.</span><span class="sxs-lookup"><span data-stu-id="56808-147">Don't register <xref:System.IDisposable> instances with a transient lifetime.</span></span> <span data-ttu-id="56808-148">Zamiast tego użyj wzorca fabryki.</span><span class="sxs-lookup"><span data-stu-id="56808-148">Use the factory pattern instead.</span></span>
- <span data-ttu-id="56808-149">Nie należy rozwiązywać <xref:System.IDisposable> wystąpień z okresem przejściowym lub z określonym zakresem w zakresie głównym.</span><span class="sxs-lookup"><span data-stu-id="56808-149">Don't resolve <xref:System.IDisposable> instances with a transient or scoped lifetime in the root scope.</span></span> <span data-ttu-id="56808-150">Jedynym wyjątkiem jest to, że aplikacja tworzy/odtworzy i usuwa <xref:System.IServiceProvider> , ale nie jest idealnym wzorcem.</span><span class="sxs-lookup"><span data-stu-id="56808-150">The only exception to this is if the app creates/recreates and disposes <xref:System.IServiceProvider>, but this isn't an ideal pattern.</span></span>
- <span data-ttu-id="56808-151">Odebranie <xref:System.IDisposable> zależności za pośrednictwem programu di nie wymaga, aby odbiorca zaimplementował <xref:System.IDisposable> sam siebie.</span><span class="sxs-lookup"><span data-stu-id="56808-151">Receiving an <xref:System.IDisposable> dependency via DI doesn't require that the receiver implement <xref:System.IDisposable> itself.</span></span> <span data-ttu-id="56808-152">Odbiorca zależności nie <xref:System.IDisposable> powinien wywoływać <xref:System.IDisposable.Dispose%2A> tej zależności.</span><span class="sxs-lookup"><span data-stu-id="56808-152">The receiver of the <xref:System.IDisposable> dependency shouldn't call <xref:System.IDisposable.Dispose%2A> on that dependency.</span></span>
- <span data-ttu-id="56808-153">Używanie zakresów do kontrolowania okresów istnienia usług.</span><span class="sxs-lookup"><span data-stu-id="56808-153">Use scopes to control the lifetimes of services.</span></span> <span data-ttu-id="56808-154">Zakresy nie są hierarchiczne i nie ma żadnych specjalnych połączeń między zakresami.</span><span class="sxs-lookup"><span data-stu-id="56808-154">Scopes aren't hierarchical, and there's no special connection among scopes.</span></span>

<span data-ttu-id="56808-155">Aby uzyskać więcej informacji na temat oczyszczania zasobów, zobacz [implementowanie metody Dispose](../../standard/garbage-collection/implementing-dispose.md)</span><span class="sxs-lookup"><span data-stu-id="56808-155">For more information on resource cleanup, see [Implement a Dispose method](../../standard/garbage-collection/implementing-dispose.md)</span></span>

## <a name="default-service-container-replacement"></a><span data-ttu-id="56808-156">Zastępowanie kontenera usług domyślnych</span><span class="sxs-lookup"><span data-stu-id="56808-156">Default service container replacement</span></span>

<span data-ttu-id="56808-157">Wbudowany kontener usług został zaprojektowany z myślą o potrzebach platformy i większości aplikacji konsumenckich.</span><span class="sxs-lookup"><span data-stu-id="56808-157">The built-in service container is designed to serve the needs of the framework and most consumer apps.</span></span> <span data-ttu-id="56808-158">Zalecamy użycie wbudowanego kontenera, chyba że potrzebna jest określona funkcja, która nie jest obsługiwana przez program, na przykład:</span><span class="sxs-lookup"><span data-stu-id="56808-158">We recommend using the built-in container unless you need a specific feature that it doesn't support, such as:</span></span>

- <span data-ttu-id="56808-159">Iniekcja właściwości</span><span class="sxs-lookup"><span data-stu-id="56808-159">Property injection</span></span>
- <span data-ttu-id="56808-160">Iniekcja oparta na nazwie</span><span class="sxs-lookup"><span data-stu-id="56808-160">Injection based on name</span></span>
- <span data-ttu-id="56808-161">Kontenery podrzędne</span><span class="sxs-lookup"><span data-stu-id="56808-161">Child containers</span></span>
- <span data-ttu-id="56808-162">Niestandardowe zarządzanie okresem istnienia</span><span class="sxs-lookup"><span data-stu-id="56808-162">Custom lifetime management</span></span>
- <span data-ttu-id="56808-163">`Func<T>` Obsługa inicjowania z opóźnieniem</span><span class="sxs-lookup"><span data-stu-id="56808-163">`Func<T>` support for lazy initialization</span></span>
- <span data-ttu-id="56808-164">Rejestracja oparta na Konwencji</span><span class="sxs-lookup"><span data-stu-id="56808-164">Convention-based registration</span></span>

<span data-ttu-id="56808-165">Za pomocą aplikacji ASP.NET Core można używać następujących kontenerów innych firm:</span><span class="sxs-lookup"><span data-stu-id="56808-165">The following third-party containers can be used with ASP.NET Core apps:</span></span>

- [<span data-ttu-id="56808-166">Autofac</span><span class="sxs-lookup"><span data-stu-id="56808-166">Autofac</span></span>](https://autofac.readthedocs.io/en/latest/integration/aspnetcore.html)
- [<span data-ttu-id="56808-167">DryIoc</span><span class="sxs-lookup"><span data-stu-id="56808-167">DryIoc</span></span>](https://www.nuget.org/packages/DryIoc.Microsoft.DependencyInjection)
- [<span data-ttu-id="56808-168">Prolongaty</span><span class="sxs-lookup"><span data-stu-id="56808-168">Grace</span></span>](https://www.nuget.org/packages/Grace.DependencyInjection.Extensions)
- [<span data-ttu-id="56808-169">LightInject</span><span class="sxs-lookup"><span data-stu-id="56808-169">LightInject</span></span>](https://github.com/seesharper/LightInject.Microsoft.DependencyInjection)
- [<span data-ttu-id="56808-170">Lamar</span><span class="sxs-lookup"><span data-stu-id="56808-170">Lamar</span></span>](https://jasperfx.github.io/lamar/)
- [<span data-ttu-id="56808-171">Stashbox</span><span class="sxs-lookup"><span data-stu-id="56808-171">Stashbox</span></span>](https://github.com/z4kn4fein/stashbox-extensions-dependencyinjection)
- [<span data-ttu-id="56808-172">Unity</span><span class="sxs-lookup"><span data-stu-id="56808-172">Unity</span></span>](https://www.nuget.org/packages/Unity.Microsoft.DependencyInjection)

## <a name="thread-safety"></a><span data-ttu-id="56808-173">Bezpieczeństwo wątkowe</span><span class="sxs-lookup"><span data-stu-id="56808-173">Thread safety</span></span>

<span data-ttu-id="56808-174">Twórz bezpieczne dla wątków usługi pojedyncze.</span><span class="sxs-lookup"><span data-stu-id="56808-174">Create thread-safe singleton services.</span></span> <span data-ttu-id="56808-175">Jeśli usługa singleton ma zależność od przejściowej usługi, usługa przejściowa może również wymagać bezpieczeństwa wątków w zależności od tego, w jaki sposób jest używana przez pojedyncze.</span><span class="sxs-lookup"><span data-stu-id="56808-175">If a singleton service has a dependency on a transient service, the transient service may also require thread safety depending on how it's used by the singleton.</span></span>

<span data-ttu-id="56808-176">Metoda fabryki pojedynczej usługi, taka jak drugi argument funkcji [AddSingleton \<TService> (IServiceCollection, Func \<IServiceProvider,TService> )](xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A), nie musi być bezpieczna wątkowo.</span><span class="sxs-lookup"><span data-stu-id="56808-176">The factory method of single service, such as the second argument to [AddSingleton\<TService>(IServiceCollection, Func\<IServiceProvider,TService>)](xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A), doesn't need to be thread-safe.</span></span> <span data-ttu-id="56808-177">Podobnie jak w przypadku `static` konstruktora typu (), gwarantowane jest wywoływanie tylko raz przez pojedynczy wątek.</span><span class="sxs-lookup"><span data-stu-id="56808-177">Like a type (`static`) constructor, it's guaranteed to be called only once by a single thread.</span></span>

## <a name="recommendations"></a><span data-ttu-id="56808-178">Zalecenia</span><span class="sxs-lookup"><span data-stu-id="56808-178">Recommendations</span></span>

- <span data-ttu-id="56808-179">`async/await``Task`rozpoznawanie usług opartych na usłudze i nie jest obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="56808-179">`async/await` and `Task` based service resolution isn't supported.</span></span> <span data-ttu-id="56808-180">Ponieważ język C# nie obsługuje konstruktorów asynchronicznych, należy używać metod asynchronicznych po synchronicznym rozpoznaniu usługi.</span><span class="sxs-lookup"><span data-stu-id="56808-180">Because C# doesn't support asynchronous constructors, use asynchronous methods after synchronously resolving the service.</span></span>
- <span data-ttu-id="56808-181">Unikaj przechowywania danych i konfiguracji bezpośrednio w kontenerze usługi.</span><span class="sxs-lookup"><span data-stu-id="56808-181">Avoid storing data and configuration directly in the service container.</span></span> <span data-ttu-id="56808-182">Na przykład koszyk użytkownika nie powinien być zazwyczaj dodawany do kontenera usługi.</span><span class="sxs-lookup"><span data-stu-id="56808-182">For example, a user's shopping cart shouldn't typically be added to the service container.</span></span> <span data-ttu-id="56808-183">Konfiguracja powinna używać wzorca opcji.</span><span class="sxs-lookup"><span data-stu-id="56808-183">Configuration should use the options pattern.</span></span> <span data-ttu-id="56808-184">Podobnie należy unikać obiektów "posiadacz danych", które istnieją tylko w celu zezwalania na dostęp do innego obiektu.</span><span class="sxs-lookup"><span data-stu-id="56808-184">Similarly, avoid "data holder" objects that only exist to allow access to another object.</span></span> <span data-ttu-id="56808-185">Lepiej jest zażądać rzeczywistego elementu za pośrednictwem DI.</span><span class="sxs-lookup"><span data-stu-id="56808-185">It's better to request the actual item via DI.</span></span>
- <span data-ttu-id="56808-186">Unikaj statycznego dostępu do usług.</span><span class="sxs-lookup"><span data-stu-id="56808-186">Avoid static access to services.</span></span> <span data-ttu-id="56808-187">Na przykład Unikaj przechwytywania [IApplicationBuilder. ApplicationServices](xref:Microsoft.AspNetCore.Builder.IApplicationBuilder.ApplicationServices) jako statycznego pola lub właściwości do użycia w innym miejscu.</span><span class="sxs-lookup"><span data-stu-id="56808-187">For example, avoid capturing [IApplicationBuilder.ApplicationServices](xref:Microsoft.AspNetCore.Builder.IApplicationBuilder.ApplicationServices) as a static field or property for use elsewhere.</span></span>
- <span data-ttu-id="56808-188">Utrzymuj szybkie i synchroniczne operacje.</span><span class="sxs-lookup"><span data-stu-id="56808-188">Keep DI factories fast and synchronous.</span></span>
- <span data-ttu-id="56808-189">Unikaj używania *wzorca lokalizatora usługi*.</span><span class="sxs-lookup"><span data-stu-id="56808-189">Avoid using the *service locator pattern*.</span></span> <span data-ttu-id="56808-190">Na przykład nie wywołuj, <xref:System.IServiceProvider.GetService%2A> Aby uzyskać wystąpienie usługi, gdy będzie można użyć di zamiast.</span><span class="sxs-lookup"><span data-stu-id="56808-190">For example, don't invoke <xref:System.IServiceProvider.GetService%2A> to obtain a service instance when you can use DI instead.</span></span>
- <span data-ttu-id="56808-191">Inna odmiana lokalizatora usługi, aby uniknąć, wprowadza fabrykę, która rozwiązuje zależności w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="56808-191">Another service locator variation to avoid is injecting a factory that resolves dependencies at runtime.</span></span> <span data-ttu-id="56808-192">Obie te praktyki mieszają się [z niewersjami strategii kontroli](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#dependency-inversion) .</span><span class="sxs-lookup"><span data-stu-id="56808-192">Both of these practices mix [Inversion of Control](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#dependency-inversion) strategies.</span></span>
- <span data-ttu-id="56808-193">Należy unikać wywołań do <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> programu `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="56808-193">Avoid calls to <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> in `ConfigureServices`.</span></span> <span data-ttu-id="56808-194">Wywoływanie `BuildServiceProvider` zazwyczaj odbywa się, gdy deweloper chce rozwiązać usługę w programie `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="56808-194">Calling `BuildServiceProvider` typically happens when the developer wants to resolve a service in `ConfigureServices`.</span></span>
- <span data-ttu-id="56808-195">Nierozporządzalne usługi przejściowe są przechwytywane przez kontener do usuwania.</span><span class="sxs-lookup"><span data-stu-id="56808-195">Disposable transient services are captured by the container for disposal.</span></span> <span data-ttu-id="56808-196">Może to przeznaczyć przeciek pamięci, jeśli został rozwiązany z kontenera najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="56808-196">This can turn into a memory leak if resolved from the top-level container.</span></span>
- <span data-ttu-id="56808-197">Włącz weryfikację zakresu, aby upewnić się, że aplikacja nie ma pojedynczych, które przechwytują usługi o określonym zakresie.</span><span class="sxs-lookup"><span data-stu-id="56808-197">Enable scope validation to make sure the app doesn't have singletons that capture scoped services.</span></span> <span data-ttu-id="56808-198">Aby uzyskać więcej informacji, zobacz [Walidacja zakresu](dependency-injection.md#scope-validation).</span><span class="sxs-lookup"><span data-stu-id="56808-198">For more information, see [Scope validation](dependency-injection.md#scope-validation).</span></span>

<span data-ttu-id="56808-199">Podobnie jak w przypadku wszystkich zestawów zaleceń, mogą wystąpić sytuacje, w których ignorowanie zalecenia jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="56808-199">Like all sets of recommendations, you may encounter situations where ignoring a recommendation is required.</span></span> <span data-ttu-id="56808-200">Wyjątki są rzadkimi, głównie szczególnymi przypadkami w ramach samej struktury.</span><span class="sxs-lookup"><span data-stu-id="56808-200">Exceptions are rare, mostly special cases within the framework itself.</span></span>

<span data-ttu-id="56808-201">DI jest *alternatywą* dla wzorców dostępu do obiektów static/Global.</span><span class="sxs-lookup"><span data-stu-id="56808-201">DI is an *alternative* to static/global object access patterns.</span></span> <span data-ttu-id="56808-202">Możesz nie być w stanie korzystać z zalet programu DI w przypadku jego mieszania z dostępem do obiektów statycznych.</span><span class="sxs-lookup"><span data-stu-id="56808-202">You may not be able to realize the benefits of DI if you mix it with static object access.</span></span>

## <a name="see-also"></a><span data-ttu-id="56808-203">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="56808-203">See also</span></span>

- [<span data-ttu-id="56808-204">Iniekcja zależności w programie .NET</span><span class="sxs-lookup"><span data-stu-id="56808-204">Dependency injection in .NET</span></span>](dependency-injection.md)
