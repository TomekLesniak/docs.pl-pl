---
title: Używanie iniekcji zależności w programie .NET
description: Dowiedz się, jak używać iniekcji zależności w aplikacjach .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/23/2020
ms.topic: tutorial
ms.openlocfilehash: f2298cb0be6d555a7636903dc251f022a6a62a43
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247909"
---
# <a name="tutorial-use-dependency-injection-in-net"></a>Samouczek: używanie iniekcji zależności w programie .NET

W tym samouczku pokazano, jak używać [iniekcji zależności (di) w programie .NET](dependency-injection.md). Przy użyciu *rozszerzeń Microsoft*di jest obywatelem pierwszej klasy, gdzie usługi są dodawane i konfigurowane w <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection> . <xref:Microsoft.Extensions.Hosting.IHost>Interfejs uwidacznia <xref:System.IServiceProvider> wystąpienie, które działa jako kontener wszystkich zarejestrowanych usług.

Ten samouczek zawiera informacje na temat wykonywania następujących czynności:

> [!div class="checklist"]
>
> - Tworzenie aplikacji konsolowej platformy .NET korzystającej z iniekcji zależności
> - Kompilowanie i Konfigurowanie [hosta ogólnego](generic-host.md)
> - Napisz kilka interfejsów i odpowiadające im implementacje
> - Używaj okresu istnienia usługi i zakresu dla DI

## <a name="prerequisites"></a>Wymagania wstępne

- [.NET Core 3,1 SDK](https://dotnet.microsoft.com/download/dotnet-core) lub nowsza wersja.
- Zintegrowane środowisko programistyczne (IDE), [Visual Studio, Visual Studio Code lub Visual Studio dla komputerów Mac](https://visualstudio.microsoft.com) są prawidłowymi opcjami.
- Znajomość tworzenia nowych aplikacji .NET i instalowania pakietów NuGet.

## <a name="create-a-new-console-application"></a>Utwórz nową aplikację konsolową

Za pomocą [nowego polecenia dotnet](../tools/dotnet-new.md) lub Kreatora nowego projektu środowiska IDE Utwórz nową aplikację konsolową .NET o nazwie **ConsoleDI. example**. Dodaj pakiet NuGet [Microsoft. Extensions. host](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) do projektu.

## <a name="add-interfaces"></a>Dodaj interfejsy

Dodaj następujące interfejsy do katalogu głównego projektu:

*IOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/IOperation.cs":::

`IOperation`Interfejs definiuje pojedynczą `OperationId` Właściwość.

*ITransientOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/ITransientOperation.cs":::

*IScopedOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/IScopedOperation.cs":::

*ISingletonOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/ISingletonOperation.cs":::

Wszystkie podinterfejsy `IOperation` nazwy mają swój przewidziany okres istnienia usługi. Na przykład "przejściowe" lub "pojedyncze".

## <a name="add-default-implementation"></a>Dodaj implementację domyślną

Dodaj następującą implementację domyślną dla różnych operacji:

*DefaultOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/DefaultOperation.cs":::

`DefaultOperation`Implementuje wszystkie interfejsy nazwanego/znacznika i inicjuje `OperationId` Właściwość dla ostatnich czterech znaków nowego unikatowego identyfikatora globalnego (GUID).

## <a name="add-service-that-requires-di"></a>Dodaj usługę wymagającą DI

Dodaj następujący obiekt rejestratora operacji, który działa jako usługa dla aplikacji konsolowej:

*OperationLogger.cs*

:::code language="csharp" source="snippets/configuration/console-di/OperationLogger.cs":::

`OperationLogger`Definiuje konstruktora, który wymaga każdego z powyższych interfejsów znacznika, czyli,, `ITransientOperation` `IScopedOperation` i `ISingletonOperation` . Obiekt ujawnia pojedynczą metodę, która umożliwia konsumentowi zarejestrowanie operacji przy użyciu danego `scope` parametru. Po wywołaniu `LogOperations` Metoda będzie rejestrować unikatowy identyfikator każdej operacji z ciągiem zakresu i komunikatem.

## <a name="register-services-for-di"></a>Zarejestruj usługi dla DI

Na koniec Zaktualizuj plik *program.cs* tak, aby był zgodny z następującymi:

:::code language="csharp" source="snippets/configuration/console-di/Program.cs" range="1-18,35-60" highlight="22-26":::

Aplikacja:

- Tworzy <xref:Microsoft.Extensions.Hosting.IHostBuilder> wystąpienie z [domyślnymi ustawieniami spinacza](generic-host.md#default-builder-settings).
- Konfiguruje usługi i dodaje je wraz z odpowiednim okresem istnienia usługi.
- Wywołuje <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> i przypisuje wystąpienie elementu <xref:Microsoft.Extensions.Hosting.IHost> .
- Wywołania `ExemplifyScoping` , przekazywanie w <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType> .

## <a name="conclusion"></a>Podsumowanie

Aplikacja generuje dane wyjściowe podobne do następującego przykładu:

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

- Operacje przejściowe są zawsze różne, co oznacza, że nowe wystąpienie jest tworzone przy każdym pobieraniu usługi.
- Operacje w zakresie zmieniają się tylko z nowym zakresem, ale są tego samego wystąpienia w zakresie.
- Operacje pojedyncze są zawsze takie same, co oznacza, że nowe wystąpienie jest tworzone tylko raz.

## <a name="next-steps"></a>Następne kroki

> [!div class="nextstepaction"]
> [Wskazówki dotyczące iniekcji zależności](dependency-injection-guidelines.md)
