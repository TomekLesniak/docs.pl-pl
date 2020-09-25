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
# <a name="dependency-injection-guidelines"></a>Wskazówki dotyczące iniekcji zależności

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

:::code language="csharp" source="snippets/configuration/console-di-disposable/ScopedDisposable.cs":::

:::code language="csharp" source="snippets/configuration/console-di-disposable/SingletonDisposable.cs":::

:::code language="csharp" source="snippets/configuration/console-di-disposable/Program.cs" range="1-21,41-60":::

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

Aby uzyskać więcej informacji na temat oczyszczania zasobów, zobacz [implementowanie metody Dispose](../../standard/garbage-collection/implementing-dispose.md)

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
- Utrzymuj szybkie i synchroniczne operacje.
- Unikaj używania *wzorca lokalizatora usługi*. Na przykład nie wywołuj, <xref:System.IServiceProvider.GetService%2A> Aby uzyskać wystąpienie usługi, gdy będzie można użyć di zamiast.
- Inna odmiana lokalizatora usługi, aby uniknąć, wprowadza fabrykę, która rozwiązuje zależności w czasie wykonywania. Obie te praktyki mieszają się [z niewersjami strategii kontroli](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#dependency-inversion) .
- Należy unikać wywołań do <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> programu `ConfigureServices` . Wywoływanie `BuildServiceProvider` zazwyczaj odbywa się, gdy deweloper chce rozwiązać usługę w programie `ConfigureServices` .
- Nierozporządzalne usługi przejściowe są przechwytywane przez kontener do usuwania. Może to przeznaczyć przeciek pamięci, jeśli został rozwiązany z kontenera najwyższego poziomu.
- Włącz weryfikację zakresu, aby upewnić się, że aplikacja nie ma pojedynczych, które przechwytują usługi o określonym zakresie. Aby uzyskać więcej informacji, zobacz [Walidacja zakresu](dependency-injection.md#scope-validation).

Podobnie jak w przypadku wszystkich zestawów zaleceń, mogą wystąpić sytuacje, w których ignorowanie zalecenia jest wymagane. Wyjątki są rzadkimi, głównie szczególnymi przypadkami w ramach samej struktury.

DI jest *alternatywą* dla wzorców dostępu do obiektów static/Global. Możesz nie być w stanie korzystać z zalet programu DI w przypadku jego mieszania z dostępem do obiektów statycznych.

## <a name="see-also"></a>Zobacz też

- [Iniekcja zależności w programie .NET](dependency-injection.md)
