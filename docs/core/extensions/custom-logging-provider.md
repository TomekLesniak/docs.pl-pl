---
title: Implementowanie niestandardowego dostawcy rejestrowania w programie .NET
description: Dowiedz się, jak zaimplementować niestandardowego dostawcę rejestrowania w aplikacjach .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/25/2020
ms.topic: how-to
ms.openlocfilehash: 3a0af6296c2ade15ff1b75dce5a5f99bfe235ebf
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91614733"
---
# <a name="implement-a-custom-logging-provider-in-net"></a>Implementowanie niestandardowego dostawcy rejestrowania w programie .NET

Istnieje wielu [dostawców rejestrowania](logging-providers.md) dostępnych w przypadku typowych potrzeb dotyczących rejestrowania. Może być konieczne zaimplementowanie niestandardowego, <xref:Microsoft.Extensions.Logging.ILoggerProvider> gdy jeden z dostępnych dostawców nie spełnia wymagań aplikacji. W tym artykule dowiesz się, jak zaimplementować niestandardowego dostawcę rejestrowania, którego można użyć do kolorowania dzienników w konsoli programu.

### <a name="sample-custom-logger-configuration"></a>Przykładowa konfiguracja rejestratora niestandardowego

Przykład tworzy różne wpisy konsoli kolorów dla każdego poziomu dziennika i identyfikatora zdarzenia przy użyciu następującego typu konfiguracji:

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLoggerConfiguration.cs":::

Poprzedni kod ustawia poziom domyślny na `Information` , kolor do `Green` i `EventId` jest niejawnie `0` .

### <a name="create-the-custom-logger"></a>Tworzenie rejestratora niestandardowego

`ILogger`Nazwa kategorii implementacji jest zwykle źródłem rejestrowania. Na przykład typ, w którym jest tworzony Rejestrator:

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLogger.cs":::

Powyższy kod ma następujące działanie:

- Tworzy wystąpienie rejestratora na nazwę kategorii.
- Sprawdza `logLevel == _config.LogLevel` `IsEnabled` , czy każdy z nich `logLevel` ma unikatowy rejestrator. Rejestratory powinny również być włączone dla wszystkich wyższych poziomów dzienników:

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLogger.cs" range="16-17":::

## <a name="custom-logger-provider"></a>Niestandardowy dostawca rejestratora

`ILoggerProvider`Obiekt jest odpowiedzialny za tworzenie wystąpień rejestratora. Być może nie jest to konieczne do utworzenia wystąpienia rejestratora dla kategorii, ale jest to zrozumiałe dla niektórych rejestratorów, takich jak NLog lub log4net. W tym celu można również wybrać różne docelowe dane wyjściowe rejestrowania według kategorii, jeśli jest to konieczne:

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLoggerProvider.cs":::

W powyższym kodzie <xref:Microsoft.Build.Logging.LoggerDescription.CreateLogger%2A> tworzy pojedyncze wystąpienie dla `ColorConsoleLogger` nazwy kategorii i zapisuje je w [`ConcurrentDictionary<TKey,TValue>`](/dotnet/api/system.collections.concurrent.concurrentdictionary-2) .

## <a name="usage-and-registration-of-the-custom-logger"></a>Użycie i rejestracja rejestratora niestandardowego

Aby dodać niestandardowego dostawcę rejestrowania i odpowiedni rejestrator, Dodaj element <xref:Microsoft.Extensions.Logging.ILoggerProvider> z <xref:Microsoft.Extensions.Logging.ILoggingBuilder> <xref:Microsoft.Extensions.Hosting.HostingHostBuilderExtensions.ConfigureLogging(Microsoft.Extensions.Hosting.IHostBuilder,System.Action{Microsoft.Extensions.Logging.ILoggingBuilder})?displayProperty=nameWithType> :

:::code language="csharp" source="snippets/configuration/console-custom-logging/Program.cs" range="23-39":::

`ILoggingBuilder`Tworzy co najmniej jedno `ILogger` wystąpienie. `ILogger`Wystąpienia są używane przez platformę do rejestrowania informacji.

Dla poprzedniego kodu, należy podać co najmniej jedną metodę rozszerzającą dla `ILoggerFactory` :

:::code language="csharp" source="snippets/configuration/console-custom-logging/Extensions/ColorConsoleLoggerExtensions.cs":::

Uruchomienie tej prostej aplikacji będzie wyglądać podobnie do następującego okna konsoli:

:::image type="content" source="media/color-console-logger.png" alt-text="Przykładowe dane wyjściowe rejestratora konsoli kolorów":::

## <a name="see-also"></a>Zobacz także

- [Rejestrowanie w programie .NET](logging.md).
- [Dostawcy rejestrowania w programie .NET](logging-providers.md).
- [Rejestrowanie o wysokiej wydajności w programie .NET](high-performance-logging.md).
