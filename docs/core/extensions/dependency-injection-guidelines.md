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
# <a name="dependency-injection-guidelines"></a>Wskazówki dotyczące wstrzykiwania zależności

Ten artykuł zawiera ogólne wskazówki i najlepsze rozwiązania dotyczące implementowania iniekcji zależności w aplikacjach .NET.

## <a name="design-services-for-dependency-injection"></a>Projektowanie usług do iniekcji zależności

Podczas projektowania usług pod kątem iniekcji zależności:

- Unikaj stanowych, statycznych klas i elementów członkowskich. Należy unikać tworzenia stanu globalnego przez projektowanie aplikacji do korzystania z usług pojedynczych.
- Unikaj bezpośredniego tworzenia wystąpień klas zależnych w ramach usług. Bezpośrednie utworzenie wystąpienia Couples kod do konkretnej implementacji.
- Zapewnianie niewielkich, dobrze przeprowadzonych i łatwych do przetestowania usług.

Jeśli klasa ma liczne wstrzykiwane zależności, może być znak, że Klasa ma zbyt wiele obowiązków i narusza [zasadę pojedynczej odpowiedzialności (SRP)](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#single-responsibility). Próba refaktoryzacji klasy przez przeniesienie niektórych jej obowiązków do nowych klas.

### <a name="disposal-of-services"></a>Usuwanie usług

Kontener jest odpowiedzialny za oczyszczanie typów, które tworzy, i <xref:System.IDisposable.Dispose%2A> wywołuje <xref:System.IDisposable> wystąpienia. Usługi rozpoznane przez kontener nigdy nie powinny zostać usunięte przez dewelopera. Jeśli typ lub fabryka są zarejestrowane jako pojedyncze, kontener usuwa pojedyncze automatycznie.

W poniższym przykładzie usługi są tworzone przez kontener usługi i usuwane automatycznie:

:::code language="csharp" source="snippets/configuration/console-di-disposable/TransientDisposable.cs":::

Wcześniejszy okres istnienia ma być przejściowy.

:::code language="csharp" source="snippets/configuration/console-di-disposable/ScopedDisposable.cs":::

Wcześniejszy zakres jest przeznaczony do posiadania okresu istnienia w zakresie.

:::code language="csharp" source="snippets/configuration/console-di-disposable/SingletonDisposable.cs":::

Wcześniejszy okres istnienia jest przeznaczony do posiadania pojedynczej ważności.

:::code language="csharp" source="snippets/configuration/console-di-disposable/Program.cs" range="1-21,41-60" highlight="":::

Konsola debugowania wyświetla następujące przykładowe dane wyjściowe po uruchomieniu:

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

### <a name="services-not-created-by-the-service-container"></a>Usługi, które nie zostały utworzone przez kontener usługi

Spójrzmy na poniższy kod:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddSingleton(new ExampleService());

    // ...
}
```

Powyższy kod ma następujące działanie:

- `ExampleService`Wystąpienie **nie** jest tworzone przez kontener usługi.
- Platforma **nie usuwa automatycznie** usług.
- Deweloper jest odpowiedzialny za likwidację usług.

### <a name="idisposable-guidance-for-transient-and-shared-instances"></a>Wskazówki interfejsu IDisposable dla wystąpień przejściowych i współużytkowanych

#### <a name="transient-limited-lifetime"></a>Przejściowy, ograniczony okres istnienia

**Scenariusz**

Aplikacja wymaga <xref:System.IDisposable> wystąpienia z przejściowym okresem istnienia dla jednego z następujących scenariuszy:

- Wystąpienie jest rozwiązane w zakresie głównym (kontener główny).
- Wystąpienie powinno zostać usunięte przed zakończeniem zakresu.

**Rozwiązanie**

Użyj wzorca fabryki, aby utworzyć wystąpienie poza zakresem nadrzędnym. W tej sytuacji aplikacja zwykle ma `Create` metodę, która wywołuje bezpośrednio Konstruktor typu końcowego. Jeśli typ końcowy ma inne zależności, fabryka może:

- Odbierz <xref:System.IServiceProvider> w konstruktorze.
- Użyj polecenia, <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities.CreateInstance%2A?displayProperty=nameWithType> Aby utworzyć wystąpienie wystąpienia poza kontenerem, przy użyciu kontenera dla jego zależności.

#### <a name="shared-instance-limited-lifetime"></a>Wystąpienie udostępnione, ograniczony okres istnienia

**Scenariusz**

Aplikacja wymaga <xref:System.IDisposable> wystąpienia udostępnionego w wielu usługach, ale <xref:System.IDisposable> wystąpienie powinno mieć ograniczony okres istnienia.

**Rozwiązanie**

Zarejestruj wystąpienie z okresem istnienia w zakresie. Użyj <xref:Microsoft.Extensions.DependencyInjection.IServiceScopeFactory.CreateScope%2A?displayProperty=nameWithType> , aby utworzyć nowy <xref:Microsoft.Extensions.DependencyInjection.IServiceScope> . Użyj zakresu, <xref:System.IServiceProvider> Aby uzyskać wymagane usługi. Usuń zakres, gdy nie jest już wymagany.

#### <a name="general-idisposable-guidelines"></a>Ogólne `IDisposable` wytyczne

- Nie rejestruj <xref:System.IDisposable> wystąpień z przejściowym okresem istnienia. Zamiast tego użyj wzorca fabryki.
- Nie należy rozwiązywać <xref:System.IDisposable> wystąpień z okresem przejściowym lub z określonym zakresem w zakresie głównym. Jedynym wyjątkiem jest to, że aplikacja tworzy/odtworzy i usuwa <xref:System.IServiceProvider> , ale nie jest idealnym wzorcem.
- Odebranie <xref:System.IDisposable> zależności za pośrednictwem programu di nie wymaga, aby odbiorca zaimplementował <xref:System.IDisposable> sam siebie. Odbiorca zależności nie <xref:System.IDisposable> powinien wywoływać <xref:System.IDisposable.Dispose%2A> tej zależności.
- Używanie zakresów do kontrolowania okresów istnienia usług. Zakresy nie są hierarchiczne i nie ma żadnych specjalnych połączeń między zakresami.

Aby uzyskać więcej informacji na temat oczyszczania zasobów, zobacz [Implementuj `Dispose` metodę](../../standard/garbage-collection/implementing-dispose.md)lub [Zaimplementuj `DisposeAsync` metodę](../../standard/garbage-collection/implementing-disposeasync.md). Dodatkowo Rozważ możliwość wypróbowania [usług przejściowych przechwyconych przez scenariusz kontenera](#disposable-transient-services-captured-by-container) w miarę odnoszących się do oczyszczania zasobów.

## <a name="default-service-container-replacement"></a>Zastępowanie kontenera usług domyślnych

Wbudowany kontener usług został zaprojektowany z myślą o potrzebach platformy i większości aplikacji konsumenckich. Zalecamy użycie wbudowanego kontenera, chyba że potrzebna jest określona funkcja, która nie jest obsługiwana przez program, na przykład:

- Iniekcja właściwości
- Iniekcja oparta na nazwie
- Kontenery podrzędne
- Niestandardowe zarządzanie okresem istnienia
- `Func<T>` Obsługa inicjowania z opóźnieniem
- Rejestracja oparta na Konwencji

Za pomocą aplikacji ASP.NET Core można używać następujących kontenerów innych firm:

- [Autofac](https://autofac.readthedocs.io/en/latest/integration/aspnetcore.html)
- [DryIoc](https://www.nuget.org/packages/DryIoc.Microsoft.DependencyInjection)
- [Prolongaty](https://www.nuget.org/packages/Grace.DependencyInjection.Extensions)
- [LightInject](https://github.com/seesharper/LightInject.Microsoft.DependencyInjection)
- [Lamar](https://jasperfx.github.io/lamar/)
- [Stashbox](https://github.com/z4kn4fein/stashbox-extensions-dependencyinjection)
- [Unity](https://www.nuget.org/packages/Unity.Microsoft.DependencyInjection)

## <a name="thread-safety"></a>Bezpieczeństwo wątkowe

Twórz bezpieczne dla wątków usługi pojedyncze. Jeśli usługa singleton ma zależność od przejściowej usługi, usługa przejściowa może również wymagać bezpieczeństwa wątków w zależności od tego, w jaki sposób jest używana przez pojedyncze.

Metoda fabryki pojedynczej usługi, taka jak drugi argument funkcji [AddSingleton \<TService> (IServiceCollection, Func \<IServiceProvider,TService> )](xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A), nie musi być bezpieczna wątkowo. Podobnie jak w przypadku `static` konstruktora typu (), gwarantowane jest wywoływanie tylko raz przez pojedynczy wątek.

## <a name="recommendations"></a>Zalecenia

- `async/await``Task`rozpoznawanie usług opartych na usłudze i nie jest obsługiwane. Ponieważ język C# nie obsługuje konstruktorów asynchronicznych, należy używać metod asynchronicznych po synchronicznym rozpoznaniu usługi.
- Unikaj przechowywania danych i konfiguracji bezpośrednio w kontenerze usługi. Na przykład koszyk użytkownika nie powinien być zazwyczaj dodawany do kontenera usługi. Konfiguracja powinna używać wzorca opcji. Podobnie należy unikać obiektów "posiadacz danych", które istnieją tylko w celu zezwalania na dostęp do innego obiektu. Lepiej jest zażądać rzeczywistego elementu za pośrednictwem DI.
- Unikaj statycznego dostępu do usług. Na przykład Unikaj przechwytywania [IApplicationBuilder. ApplicationServices](xref:Microsoft.AspNetCore.Builder.IApplicationBuilder.ApplicationServices) jako statycznego pola lub właściwości do użycia w innym miejscu.
- Utrzymuj [szybkie](#async-di-factories-can-cause-deadlocks) i synchroniczne operacje.
- Unikaj używania [*wzorca lokalizatora usługi*](#scoped-service-as-singleton). Na przykład nie wywołuj, <xref:System.IServiceProvider.GetService%2A> Aby uzyskać wystąpienie usługi, gdy będzie można użyć di zamiast.
- Inna odmiana lokalizatora usługi, aby uniknąć, wprowadza fabrykę, która rozwiązuje zależności w czasie wykonywania. Obie te praktyki mieszają się [z niewersjami strategii kontroli](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#dependency-inversion) .
- Należy unikać wywołań do <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> programu `ConfigureServices` . Wywoływanie `BuildServiceProvider` zazwyczaj odbywa się, gdy deweloper chce rozwiązać usługę w programie `ConfigureServices` .
- [Nierozporządzalne usługi przejściowe są przechwytywane](#disposable-transient-services-captured-by-container) przez kontener do usuwania. Może to przeznaczyć przeciek pamięci, jeśli został rozwiązany z kontenera najwyższego poziomu.
- Włącz weryfikację zakresu, aby upewnić się, że aplikacja nie ma pojedynczych, które przechwytują usługi o określonym zakresie. Aby uzyskać więcej informacji, zobacz [Walidacja zakresu](dependency-injection.md#scope-validation).

Podobnie jak w przypadku wszystkich zestawów zaleceń, mogą wystąpić sytuacje, w których ignorowanie zalecenia jest wymagane. Wyjątki są rzadkimi, głównie szczególnymi przypadkami w ramach samej struktury.

DI jest *alternatywą* dla wzorców dostępu do obiektów static/Global. Możesz nie być w stanie korzystać z zalet programu DI w przypadku jego mieszania z dostępem do obiektów statycznych.

## <a name="example-anti-patterns"></a>Przykładowe antywzorce

Oprócz wytycznych opisanych w tym artykule, istnieje kilka antywzorców, *których **należy** unikać* . Niektóre z tych antywzorców zapoznają się z tworzeniem środowiska uruchomieniowego.

> [!WARNING]
> Są to przykładowe *wzorce,* *nie Kopiuj kodu, nie używaj* tych wzorców i unikaj tych wzorców we wszystkich kosztach.

### <a name="disposable-transient-services-captured-by-container"></a>Jednorazowe usługi przejściowe przechwycone przez kontener

Po zarejestrowaniu usług *przejściowych* , które implementują <xref:System.IDisposable> , domyślnie do tych odwołań są przechowywane kontenery di, a nie <xref:System.IDisposable.Dispose> ich do momentu zatrzymania aplikacji. Przyczyną może być przeciek pamięci, jeśli został on rozwiązany z poziomu kontenera.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="18-30":::

W poprzednim wzorcu `ExampleDisposable` są tworzone wystąpienia 1 000 obiektów i są one odblokowane. Nie zostaną usunięte, dopóki `serviceProvider` wystąpienie nie zostanie usunięte.

Aby uzyskać więcej informacji na temat debugowania przecieków pamięci, zobacz [debugowanie przecieku pamięci w programie .NET](../diagnostics/debug-memory-leak.md).

### <a name="async-di-factories-can-cause-deadlocks"></a>Asynchroniczne operacje DI mogą spowodować zakleszczenie

Termin "DI Factors" oznacza metody przeciążenia, które istnieją podczas wywoływania `Add{LIFETIME}` . Istnieją przeciążenia akceptujące `Func<IServiceProvider, T>` miejsce `T` , gdzie jest rejestrowana usługa, a parametr ma nazwę `implementationFactory` . `implementationFactory`Można podać jako wyrażenie lambda, funkcję lokalną lub metodę. Jeśli fabryka jest asynchroniczna i używasz <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> , spowoduje to zakleszczenie.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="32-45" highlight="4-8":::

W poprzednim kodzie, `implementationFactory` otrzymuje wyrażenie lambda, gdzie treść wywołuje <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> `Task<Bar>` metodę zwracającą. ***Powoduje to zakleszczenie*** . `GetBarAsync`Metoda po prostu emuluje asynchroniczne operacje pracy z <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> , a następnie wywołuje <xref:Microsoft.Extensions.DependencyInjection.ServiceProviderServiceExtensions.GetRequiredService%60%601(System.IServiceProvider)> .

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="47-53":::

Aby uzyskać więcej informacji na temat wskazówek asynchronicznych, zobacz [programowanie asynchroniczne: ważne informacje i porady](../../csharp/async.md#important-info-and-advice). Aby uzyskać więcej informacji na temat zakleszczenia debugowania, zobacz [debugowanie zakleszczenia w programie .NET](../diagnostics/debug-deadlock.md).

W przypadku korzystania z tego oprogramowania antywzorca i wystąpienia zakleszczenia można wyświetlić dwa wątki oczekujące w oknie stosów równoległych programu Visual Studio. Aby uzyskać więcej informacji, zobacz [Wyświetlanie wątków i zadań w oknie stosów równoległych](/visualstudio/debugger/using-the-parallel-stacks-window).

### <a name="captive-dependency"></a>Zależność podrzędna

Termin ["zależność podrzędna"](https://blog.ploeh.dk/2014/06/02/captive-dependency) został zastosowany przez [oznaczenie Seeman](https://blog.ploeh.dk/about)i odnosi się do nieprawdziwej konfiguracji okresów istnienia usługi, w przypadku których usługa o dłuższym czasie utrzymuje nieprzerwaną usługę.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="55-65":::

W powyższym kodzie `Foo` jest zarejestrowany jako pojedynczy i `Bar` ma zakres, który na powierzchni jest prawidłowy. Należy jednak wziąć pod uwagę implementację programu `Foo` .

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Foo.cs" highlight="5":::

`Foo`Obiekt wymaga `Bar` obiektu, a ponieważ `Foo` jest elementem pojedynczym i `Bar` ma zakres-nieprawidłową konfigurację. W takim przypadku `Foo` można utworzyć wystąpienie tylko raz, a jego `Bar` okres istnienia będzie dłuższy niż przewidziany okres istnienia w zakresie `Bar` . Należy rozważyć sprawdzenie poprawności zakresów, przekazanie `validateScopes: true` do <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Boolean)> . Podczas sprawdzania poprawności zakresów uzyskasz <xref:System.InvalidOperationException> komunikat podobny do "nie można korzystać z usługi w zakresie" z pojedynczego elementu "foo".

Aby uzyskać więcej informacji, zobacz [Walidacja zakresu](dependency-injection.md#scope-validation).

### <a name="scoped-service-as-singleton"></a>Usługa objęta zakresem jako pojedyncza

W przypadku korzystania z usług objętych zakresem, jeśli nie tworzysz zakresu lub w istniejącym zakresie — usługa zostanie poprzednia.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="68-82" highlight="13-14":::

W powyższym kodzie `Bar` jest pobierany w <xref:Microsoft.Extensions.DependencyInjection.IServiceScope> , który jest prawidłowy. Antywzorzec to pobieranie `Bar` poza zakresem, a zmienna nosi nazwę, `avoid` Aby pokazać, które przykładowe pobieranie jest nieprawidłowe.

## <a name="see-also"></a>Zobacz też

- [Iniekcja zależności w programie .NET](dependency-injection.md)
- [Samouczek: używanie iniekcji zależności w programie .NET](dependency-injection-usage.md)
