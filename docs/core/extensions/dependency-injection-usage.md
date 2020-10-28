---
title: Używanie iniekcji zależności w programie .NET
description: Dowiedz się, jak używać iniekcji zależności w aplikacjach .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/23/2020
ms.topic: tutorial
no-loc:
- Transient
- Scoped
- Singleton
- Example
ms.openlocfilehash: 589e15736c07b465fda308b04c91384a2502755c
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888586"
---
# <a name="tutorial-use-dependency-injection-in-net"></a>Samouczek: używanie iniekcji zależności w programie .NET

W tym samouczku pokazano, jak używać [iniekcji zależności (di) w programie .NET](dependency-injection.md). Przy użyciu *rozszerzeń Microsoft* di jest obywatelem pierwszej klasy, gdzie usługi są dodawane i konfigurowane w <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection> . <xref:Microsoft.Extensions.Hosting.IHost>Interfejs uwidacznia <xref:System.IServiceProvider> wystąpienie, które działa jako kontener wszystkich zarejestrowanych usług.

Ten samouczek zawiera informacje na temat wykonywania następujących czynności:

> [!div class="checklist"]
>
> - Tworzenie aplikacji konsolowej platformy .NET korzystającej z iniekcji zależności
> - Kompilowanie i Konfigurowanie [hosta ogólnego](generic-host.md)
> - Napisz kilka interfejsów i odpowiadające im implementacje
> - Używaj okresu istnienia usługi i zakresu dla DI

## <a name="prerequisites"></a>Wymagania wstępne

- [.NET Core 3,1 SDK](https://dotnet.microsoft.com/download/dotnet-core) lub nowszy.
- Znajomość tworzenia nowych aplikacji .NET i instalowania pakietów NuGet.

## <a name="create-a-new-console-application"></a>Utwórz nową aplikację konsolową

Za pomocą [nowego polecenia dotnet](../tools/dotnet-new.md) lub Kreatora nowego projektu środowiska IDE Utwórz nową aplikację konsolową .NET o nazwie **ConsoleDI. Example** . Dodaj pakiet NuGet [Microsoft. Extensions. host](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) do projektu.

## <a name="add-interfaces"></a>Dodaj interfejsy

Dodaj następujące interfejsy do katalogu głównego projektu:

*IOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/IOperation.cs":::

`IOperation`Interfejs definiuje pojedynczą `OperationId` Właściwość.

*TransientOperation.cs*

::: Code Language = "CSharp" source = "fragmenty kodu/Configuration/Console-di/I Transient Operation.cs"::

*ScopedOperation.cs*

::: Code Language = "CSharp" source = "fragmenty kodu/Configuration/Console-di/I Scoped Operation.cs"::

*SingletonOperation.cs*

::: Code Language = "CSharp" source = "fragmenty kodu/Configuration/Console-di/I Singleton Operation.cs"::

Wszystkie podinterfejsy `IOperation` nazwy mają swój przewidziany okres istnienia usługi. Na przykład " Transient " lub " Singleton ".

## <a name="add-default-implementation"></a>Dodaj implementację domyślną

Dodaj następującą implementację domyślną dla różnych operacji:

*DefaultOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/DefaultOperation.cs":::

`DefaultOperation`Implementuje wszystkie nazwane interfejsy znacznika i inicjuje `OperationId` Właściwość do czterech ostatnich znaków nowego unikatowego identyfikatora globalnego (GUID).

## <a name="add-service-that-requires-di"></a>Dodaj usługę wymagającą DI

Dodaj następujący obiekt rejestratora operacji, który działa jako usługa aplikacji konsolowej:

*OperationLogger.cs*

:::code language="csharp" source="snippets/configuration/console-di/OperationLogger.cs":::

`OperationLogger`Definiuje konstruktora, który wymaga każdego z powyższych interfejsów znacznika, czyli,, `ITransientOperation` `IScopedOperation` i `ISingletonOperation` . Obiekt ujawnia pojedynczą metodę, która umożliwia konsumentowi zarejestrowanie operacji przy użyciu danego `scope` parametru. Po wywołaniu `LogOperations` Metoda rejestruje unikatowy identyfikator każdej operacji przy użyciu ciągu zakresu i komunikatu.

## <a name="register-services-for-di"></a>Zarejestruj usługi dla DI

Zaktualizuj *program.cs* przy użyciu następującego kodu:

:::code language="csharp" source="snippets/configuration/console-di/Program.cs" range="1-18,35-60" highlight="22-26":::

Aplikacja:

- Tworzy <xref:Microsoft.Extensions.Hosting.IHostBuilder> wystąpienie z [domyślnymi ustawieniami spinacza](generic-host.md#default-builder-settings).
- Konfiguruje usługi i dodaje je wraz z odpowiednim okresem istnienia usługi.
- Wywołuje <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> i przypisuje wystąpienie elementu <xref:Microsoft.Extensions.Hosting.IHost> .
- Wywołania `ExemplifyScoping` , przekazywanie w <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType> .

## <a name="conclusion"></a>Podsumowanie

Aplikacja wyświetli dane wyjściowe podobne do następującego przykładu:

```console
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ 80f4...Always different        ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ f3c0...Always different        ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]

Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ f9af...Always different        ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ fa65...Always different        ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
```

W danych wyjściowych aplikacji można zobaczyć, że:

- Transient operacje są zawsze różne, nowe wystąpienie jest tworzone przy każdym pobieraniu usługi.
- Scoped operacje zmieniają się tylko z nowym zakresem, ale są tego samego wystąpienia w zakresie.
- Singleton operacje są zawsze takie same. nowe wystąpienie jest tworzone tylko raz.

## <a name="see-also"></a>Zobacz także

* [Wskazówki dotyczące wstrzykiwania zależności](dependency-injection-guidelines.md)
* [Wstrzykiwanie zależności w ASP.NET Core](/aspnet/core/fundamentals/dependency-injection)
