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
# <a name="implement-a-custom-logging-provider-in-net"></a><span data-ttu-id="e211b-103">Implementowanie niestandardowego dostawcy rejestrowania w programie .NET</span><span class="sxs-lookup"><span data-stu-id="e211b-103">Implement a custom logging provider in .NET</span></span>

<span data-ttu-id="e211b-104">Istnieje wielu [dostawców rejestrowania](logging-providers.md) dostępnych w przypadku typowych potrzeb dotyczących rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="e211b-104">There are many [logging providers](logging-providers.md) available for common logging needs.</span></span> <span data-ttu-id="e211b-105">Może być konieczne zaimplementowanie niestandardowego, <xref:Microsoft.Extensions.Logging.ILoggerProvider> gdy jeden z dostępnych dostawców nie spełnia wymagań aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e211b-105">You may need to implement a custom <xref:Microsoft.Extensions.Logging.ILoggerProvider> when one of the available providers doesn't suit your application needs.</span></span> <span data-ttu-id="e211b-106">W tym artykule dowiesz się, jak zaimplementować niestandardowego dostawcę rejestrowania, którego można użyć do kolorowania dzienników w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="e211b-106">In this article, you'll learn how to implement a custom logging provider that can be used to colorize logs in the console.</span></span>

### <a name="sample-custom-logger-configuration"></a><span data-ttu-id="e211b-107">Przykładowa konfiguracja rejestratora niestandardowego</span><span class="sxs-lookup"><span data-stu-id="e211b-107">Sample custom logger configuration</span></span>

<span data-ttu-id="e211b-108">Przykład tworzy różne wpisy konsoli kolorów dla każdego poziomu dziennika i identyfikatora zdarzenia przy użyciu następującego typu konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="e211b-108">The sample creates different color console entries per log level and event ID using the following configuration type:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLoggerConfiguration.cs":::

<span data-ttu-id="e211b-109">Poprzedni kod ustawia poziom domyślny na `Information` , kolor do `Green` i `EventId` jest niejawnie `0` .</span><span class="sxs-lookup"><span data-stu-id="e211b-109">The preceding code sets the default level to `Information`, the color to `Green`, and the `EventId` is implicitly `0`.</span></span>

### <a name="create-the-custom-logger"></a><span data-ttu-id="e211b-110">Tworzenie rejestratora niestandardowego</span><span class="sxs-lookup"><span data-stu-id="e211b-110">Create the custom logger</span></span>

<span data-ttu-id="e211b-111">`ILogger`Nazwa kategorii implementacji jest zwykle źródłem rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="e211b-111">The `ILogger` implementation category name is typically the logging source.</span></span> <span data-ttu-id="e211b-112">Na przykład typ, w którym jest tworzony Rejestrator:</span><span class="sxs-lookup"><span data-stu-id="e211b-112">For example, the type where the logger is created:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLogger.cs":::

<span data-ttu-id="e211b-113">Powyższy kod ma następujące działanie:</span><span class="sxs-lookup"><span data-stu-id="e211b-113">The preceding code:</span></span>

- <span data-ttu-id="e211b-114">Tworzy wystąpienie rejestratora na nazwę kategorii.</span><span class="sxs-lookup"><span data-stu-id="e211b-114">Creates a logger instance per category name.</span></span>
- <span data-ttu-id="e211b-115">Sprawdza `logLevel == _config.LogLevel` `IsEnabled` , czy każdy z nich `logLevel` ma unikatowy rejestrator.</span><span class="sxs-lookup"><span data-stu-id="e211b-115">Checks `logLevel == _config.LogLevel` in `IsEnabled`, so each `logLevel` has a unique logger.</span></span> <span data-ttu-id="e211b-116">Rejestratory powinny również być włączone dla wszystkich wyższych poziomów dzienników:</span><span class="sxs-lookup"><span data-stu-id="e211b-116">Loggers should also be enabled for all higher log levels:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLogger.cs" range="16-17":::

## <a name="custom-logger-provider"></a><span data-ttu-id="e211b-117">Niestandardowy dostawca rejestratora</span><span class="sxs-lookup"><span data-stu-id="e211b-117">Custom logger provider</span></span>

<span data-ttu-id="e211b-118">`ILoggerProvider`Obiekt jest odpowiedzialny za tworzenie wystąpień rejestratora.</span><span class="sxs-lookup"><span data-stu-id="e211b-118">The `ILoggerProvider` object is responsible for creating logger instances.</span></span> <span data-ttu-id="e211b-119">Być może nie jest to konieczne do utworzenia wystąpienia rejestratora dla kategorii, ale jest to zrozumiałe dla niektórych rejestratorów, takich jak NLog lub log4net.</span><span class="sxs-lookup"><span data-stu-id="e211b-119">Maybe it is not needed to create a logger instance per category, but this makes sense for some loggers, like NLog or log4net.</span></span> <span data-ttu-id="e211b-120">W tym celu można również wybrać różne docelowe dane wyjściowe rejestrowania według kategorii, jeśli jest to konieczne:</span><span class="sxs-lookup"><span data-stu-id="e211b-120">Doing this you are also able to choose different logging output targets per category if needed:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLoggerProvider.cs":::

<span data-ttu-id="e211b-121">W powyższym kodzie <xref:Microsoft.Build.Logging.LoggerDescription.CreateLogger%2A> tworzy pojedyncze wystąpienie dla `ColorConsoleLogger` nazwy kategorii i zapisuje je w [`ConcurrentDictionary<TKey,TValue>`](/dotnet/api/system.collections.concurrent.concurrentdictionary-2) .</span><span class="sxs-lookup"><span data-stu-id="e211b-121">In the preceding code, <xref:Microsoft.Build.Logging.LoggerDescription.CreateLogger%2A> creates a single instance of the `ColorConsoleLogger` per category name and stores it in the [`ConcurrentDictionary<TKey,TValue>`](/dotnet/api/system.collections.concurrent.concurrentdictionary-2).</span></span>

## <a name="usage-and-registration-of-the-custom-logger"></a><span data-ttu-id="e211b-122">Użycie i rejestracja rejestratora niestandardowego</span><span class="sxs-lookup"><span data-stu-id="e211b-122">Usage and registration of the custom logger</span></span>

<span data-ttu-id="e211b-123">Aby dodać niestandardowego dostawcę rejestrowania i odpowiedni rejestrator, Dodaj element <xref:Microsoft.Extensions.Logging.ILoggerProvider> z <xref:Microsoft.Extensions.Logging.ILoggingBuilder> <xref:Microsoft.Extensions.Hosting.HostingHostBuilderExtensions.ConfigureLogging(Microsoft.Extensions.Hosting.IHostBuilder,System.Action{Microsoft.Extensions.Logging.ILoggingBuilder})?displayProperty=nameWithType> :</span><span class="sxs-lookup"><span data-stu-id="e211b-123">To add the custom logging provider and corresponding logger, add an <xref:Microsoft.Extensions.Logging.ILoggerProvider> with <xref:Microsoft.Extensions.Logging.ILoggingBuilder> from the <xref:Microsoft.Extensions.Hosting.HostingHostBuilderExtensions.ConfigureLogging(Microsoft.Extensions.Hosting.IHostBuilder,System.Action{Microsoft.Extensions.Logging.ILoggingBuilder})?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/Program.cs" range="23-39":::

<span data-ttu-id="e211b-124">`ILoggingBuilder`Tworzy co najmniej jedno `ILogger` wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="e211b-124">The `ILoggingBuilder` creates one or more `ILogger` instances.</span></span> <span data-ttu-id="e211b-125">`ILogger`Wystąpienia są używane przez platformę do rejestrowania informacji.</span><span class="sxs-lookup"><span data-stu-id="e211b-125">The `ILogger` instances are used by the framework to log the information.</span></span>

<span data-ttu-id="e211b-126">Dla poprzedniego kodu, należy podać co najmniej jedną metodę rozszerzającą dla `ILoggerFactory` :</span><span class="sxs-lookup"><span data-stu-id="e211b-126">For the preceding code, provide at least one extension method for the `ILoggerFactory`:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/Extensions/ColorConsoleLoggerExtensions.cs":::

<span data-ttu-id="e211b-127">Uruchomienie tej prostej aplikacji będzie wyglądać podobnie do następującego okna konsoli:</span><span class="sxs-lookup"><span data-stu-id="e211b-127">Running this simple application will render similar to the following console window:</span></span>

:::image type="content" source="media/color-console-logger.png" alt-text="Przykładowe dane wyjściowe rejestratora konsoli kolorów":::

## <a name="see-also"></a><span data-ttu-id="e211b-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e211b-129">See also</span></span>

- <span data-ttu-id="e211b-130">[Rejestrowanie w programie .NET](logging.md).</span><span class="sxs-lookup"><span data-stu-id="e211b-130">[Logging in .NET](logging.md).</span></span>
- <span data-ttu-id="e211b-131">[Dostawcy rejestrowania w programie .NET](logging-providers.md).</span><span class="sxs-lookup"><span data-stu-id="e211b-131">[Logging providers in .NET](logging-providers.md).</span></span>
- <span data-ttu-id="e211b-132">[Rejestrowanie o wysokiej wydajności w programie .NET](high-performance-logging.md).</span><span class="sxs-lookup"><span data-stu-id="e211b-132">[High-performance logging in .NET](high-performance-logging.md).</span></span>
