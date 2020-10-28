---
title: Formatowanie dziennika konsoli
description: Dowiedz się, jak korzystać z dostępnych formatów dzienników konsoli lub zaimplementować niestandardowe formatowanie dzienników dla aplikacji .NET.
author: IEvangelist
ms.author: dapine
ms.date: 10/22/2020
ms.openlocfilehash: 28a3de833b759e043ec3e2cb5016852f9a861cee
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92897677"
---
# <a name="console-log-formatting"></a><span data-ttu-id="4f804-103">Formatowanie dziennika konsoli</span><span class="sxs-lookup"><span data-stu-id="4f804-103">Console log formatting</span></span>

<span data-ttu-id="4f804-104">W programie .NET 5 obsługa niestandardowego formatowania została dodana do dzienników konsoli w `Microsoft.Extensions.Logging.Console` przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4f804-104">In .NET 5, support for custom formatting was added to console logs in the `Microsoft.Extensions.Logging.Console` namespace.</span></span> <span data-ttu-id="4f804-105">Dostępne są trzy wstępnie zdefiniowane opcje formatowania: [`Simple`](#simple) , [`Systemd`](#systemd) , i [`Json`](#json) .</span><span class="sxs-lookup"><span data-stu-id="4f804-105">There are three predefined formatting options available: [`Simple`](#simple), [`Systemd`](#systemd), and [`Json`](#json).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f804-106">Wcześniej <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> Wyliczenie dozwolone do wybrania żądanego formatu dziennika — można je odczytać przez człowieka `Default` lub pojedynczy wiersz, który jest również znany jako `Systemd` .</span><span class="sxs-lookup"><span data-stu-id="4f804-106">Previously, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> enum allowed for selecting the desired log format, either human readable which was the `Default`, or single line which is also known as `Systemd`.</span></span> <span data-ttu-id="4f804-107">**Nie** są one jednak dostosowywane i obecnie przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="4f804-107">However, these were **not** customizable, and are now deprecated.</span></span>

<span data-ttu-id="4f804-108">Ten artykuł zawiera informacje dotyczące programu formatującego dzienników konsoli.</span><span class="sxs-lookup"><span data-stu-id="4f804-108">In this article, you will learn about console log formatters.</span></span> <span data-ttu-id="4f804-109">Przykładowy kod źródłowy pokazuje, jak:</span><span class="sxs-lookup"><span data-stu-id="4f804-109">The sample source code demonstrates how to:</span></span>

- <span data-ttu-id="4f804-110">Rejestrowanie nowego programu formatującego</span><span class="sxs-lookup"><span data-stu-id="4f804-110">Register a new formatter</span></span>
- <span data-ttu-id="4f804-111">Wybieranie zarejestrowanego programu formatującego do użycia</span><span class="sxs-lookup"><span data-stu-id="4f804-111">Select a registered formatter to use</span></span>
  - <span data-ttu-id="4f804-112">Za pomocą kodu lub [konfiguracji](configuration.md)</span><span class="sxs-lookup"><span data-stu-id="4f804-112">Either through code, or [configuration](configuration.md)</span></span>
- <span data-ttu-id="4f804-113">Implementowanie niestandardowego programu formatującego</span><span class="sxs-lookup"><span data-stu-id="4f804-113">Implement a custom formatter</span></span>
  - <span data-ttu-id="4f804-114">Aktualizacja konfiguracji za pomocą <xref:Microsoft.Extensions.Options.IOptionsMonitor%601></span><span class="sxs-lookup"><span data-stu-id="4f804-114">Update configuration via <xref:Microsoft.Extensions.Options.IOptionsMonitor%601></span></span>
  - <span data-ttu-id="4f804-115">Włącz niestandardowe formatowanie kolorów</span><span class="sxs-lookup"><span data-stu-id="4f804-115">Enable custom color formatting</span></span>

## <a name="register-formatter"></a><span data-ttu-id="4f804-116">Rejestrowanie programu formatującego</span><span class="sxs-lookup"><span data-stu-id="4f804-116">Register formatter</span></span>

<span data-ttu-id="4f804-117">[ `Console` Dostawca rejestrowania](logging-providers.md#console) zawiera kilka wstępnie zdefiniowanych elementów formatujących i uwidacznia możliwość tworzenia własnego niestandardowego programu formatującego.</span><span class="sxs-lookup"><span data-stu-id="4f804-117">The [`Console` logging provider](logging-providers.md#console) has several predefined formatters, and exposes the ability to author your own custom formatter.</span></span> <span data-ttu-id="4f804-118">Aby zarejestrować dowolne z dostępnych elementów formatujących, użyj odpowiedniej `Add{Type}Console` metody rozszerzenia:</span><span class="sxs-lookup"><span data-stu-id="4f804-118">To register any of the available formatters, use the corresponding `Add{Type}Console` extension method:</span></span>

| <span data-ttu-id="4f804-119">Dostępne typy</span><span class="sxs-lookup"><span data-stu-id="4f804-119">Available types</span></span> | <span data-ttu-id="4f804-120">Metoda do rejestrowania typu</span><span class="sxs-lookup"><span data-stu-id="4f804-120">Method to register type</span></span> |
|--|--|
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddJsonConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSimpleConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSystemdConsole%2A?displayProperty=nameWithType> |

### <a name="simple"></a><span data-ttu-id="4f804-121">Prostota</span><span class="sxs-lookup"><span data-stu-id="4f804-121">Simple</span></span>

<span data-ttu-id="4f804-122">Aby użyć programu `Simple` formatującego konsoli, zarejestruj go przy użyciu `AddSimpleConsole` :</span><span class="sxs-lookup"><span data-stu-id="4f804-122">To use the `Simple` console formatter, register it with `AddSimpleConsole`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-simple/Program.cs" highlight="11-16":::

<span data-ttu-id="4f804-123">W poprzednim przykładowym kodzie źródłowym program <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> formatujący został zarejestrowany.</span><span class="sxs-lookup"><span data-stu-id="4f804-123">In the preceding sample source code, the <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> formatter was registered.</span></span> <span data-ttu-id="4f804-124">Udostępnia ona dzienniki z możliwością, aby nie tylko zawijać informacje, takie jak czas i poziom rejestrowania w każdym komunikacie dziennika, ale również umożliwia osadzanie i wcięcia kolorów ANSI.</span><span class="sxs-lookup"><span data-stu-id="4f804-124">It provides logs with the ability to not only wrap information such as time and log level in each log message, but also allows for ANSI color embedding and indentation of messages.</span></span>

### <a name="systemd"></a><span data-ttu-id="4f804-125">Usługę systemd</span><span class="sxs-lookup"><span data-stu-id="4f804-125">Systemd</span></span>

<span data-ttu-id="4f804-126"><xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>Rejestrator konsoli:</span><span class="sxs-lookup"><span data-stu-id="4f804-126">The <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> console logger:</span></span>

- <span data-ttu-id="4f804-127">Używa formatu i serwerów dziennika "Dziennik systemowy"</span><span class="sxs-lookup"><span data-stu-id="4f804-127">Uses the "Syslog" log level format and severities</span></span>
- <span data-ttu-id="4f804-128">Nie **formatuje** komunikatów z kolorami</span><span class="sxs-lookup"><span data-stu-id="4f804-128">Does **not** format messages with colors</span></span>
- <span data-ttu-id="4f804-129">Zawsze rejestruje komunikaty w pojedynczym wierszu</span><span class="sxs-lookup"><span data-stu-id="4f804-129">Always logs messages in a single line</span></span>

<span data-ttu-id="4f804-130">Jest to często przydatne w przypadku kontenerów, które często używają `Systemd` rejestrowania w konsoli.</span><span class="sxs-lookup"><span data-stu-id="4f804-130">This is commonly useful for containers, which often make use of `Systemd` console logging.</span></span> <span data-ttu-id="4f804-131">W przypadku platformy .NET 5 `Simple` konsola rejestratora umożliwia również kompaktowanie wersji, która jest rejestrowana w jednym wierszu, a także umożliwia wyłączenie kolorów, jak pokazano w wcześniejszym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="4f804-131">With .NET 5, the `Simple` console logger also enables a compact version that logs in a single line, and also allows for disabling colors as shown in an earlier sample.</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-systemd/Program.cs" highlight="11-15":::

### <a name="json"></a><span data-ttu-id="4f804-132">JSON</span><span class="sxs-lookup"><span data-stu-id="4f804-132">Json</span></span>

<span data-ttu-id="4f804-133">Do zapisu dzienników w formacie JSON `Json` jest używany program formatujący konsoli.</span><span class="sxs-lookup"><span data-stu-id="4f804-133">To write logs in a JSON format, the `Json` console formatter is used.</span></span> <span data-ttu-id="4f804-134">Przykładowy kod źródłowy pokazuje, jak aplikacja ASP.NET Core może ją zarejestrować.</span><span class="sxs-lookup"><span data-stu-id="4f804-134">The sample source code shows how an ASP.NET Core app might register it.</span></span> <span data-ttu-id="4f804-135">Za pomocą `webapp` szablonu Utwórz nową aplikację ASP.NET Core przy użyciu polecenia [dotnet New](../tools/dotnet-new.md) :</span><span class="sxs-lookup"><span data-stu-id="4f804-135">Using the `webapp` template, create a new ASP.NET Core app with the [dotnet new](../tools/dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new webapp -o Console.ExampleFormatters.Json
```

<span data-ttu-id="4f804-136">Podczas uruchamiania aplikacji przy użyciu kodu szablonu otrzymujesz domyślny format dziennika:</span><span class="sxs-lookup"><span data-stu-id="4f804-136">When running the app, using the template code, you get the default log format below:</span></span>

```
info: Microsoft.Hosting.Lifetime[0]
      Now listening on: https://localhost:5001
```

<span data-ttu-id="4f804-137">Domyślnie program `Simple` formatujący dziennik konsoli jest wybierany z domyślną konfiguracją.</span><span class="sxs-lookup"><span data-stu-id="4f804-137">By default, the `Simple` console log formatter is selected with default configuration.</span></span> <span data-ttu-id="4f804-138">Możesz to zmienić, wywołując `AddJsonConsole` w *program.cs* :</span><span class="sxs-lookup"><span data-stu-id="4f804-138">You change this by calling `AddJsonConsole` in the *Program.cs* :</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-json/Program.cs" highlight="17-26":::

<span data-ttu-id="4f804-139">Uruchom aplikację ponownie, używając powyższej zmiany, komunikat dziennika jest teraz sformatowany w formacie JSON:</span><span class="sxs-lookup"><span data-stu-id="4f804-139">Run the app again, with the above change, the log message is now formatted as JSON:</span></span>

:::code language="json" source="snippets/logging/console-formatter-json/example-output.json":::

> [!TIP]
> <span data-ttu-id="4f804-140">Program `Json` formatujący konsoli domyślnie rejestruje każdy komunikat w jednym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4f804-140">The `Json` console formatter, by default, logs each message in a single line.</span></span> <span data-ttu-id="4f804-141">Aby zwiększyć czytelność podczas konfigurowania programu formatującego, ustaw wartość <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType> na `true` .</span><span class="sxs-lookup"><span data-stu-id="4f804-141">In order to make it more readable while configuring the formatter, set <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType> to `true`.</span></span>

## <a name="set-formatter-with-configuration"></a><span data-ttu-id="4f804-142">Ustawianie programu formatującego z konfiguracją</span><span class="sxs-lookup"><span data-stu-id="4f804-142">Set formatter with configuration</span></span>

<span data-ttu-id="4f804-143">W poprzednich przykładach przedstawiono sposób programowego rejestrowania programu formatującego.</span><span class="sxs-lookup"><span data-stu-id="4f804-143">The previous samples have shown how to register a formatter programmatically.</span></span> <span data-ttu-id="4f804-144">Można to również zrobić z [konfiguracją](configuration.md).</span><span class="sxs-lookup"><span data-stu-id="4f804-144">Alternatively, this can be done with [configuration](configuration.md).</span></span> <span data-ttu-id="4f804-145">Rozważmy poprzedni kod źródłowy przykładowej aplikacji sieci Web, jeśli *appsettings.js* plik zostanie zaktualizowany zamiast wywoływania `ConfigureLogging` w pliku *program.cs* , można uzyskać ten sam wynik.</span><span class="sxs-lookup"><span data-stu-id="4f804-145">Consider the previous web application sample source code, if you update the *appsettings.json* file rather than calling `ConfigureLogging` in the *Program.cs* file, you could get the same outcome.</span></span> <span data-ttu-id="4f804-146">Zaktualizowany `appsettings.json` plik spowoduje skonfigurowanie programu formatującego w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="4f804-146">The updated `appsettings.json` file would configure the formatter as follows:</span></span>

:::code language="json" source="snippets/logging/console-formatter-json/appsettings.json" highlight="14-23":::

<span data-ttu-id="4f804-147">Dwie wartości klucza, które należy ustawić, to `"FormatterName"` i `"FormatterOptions"` .</span><span class="sxs-lookup"><span data-stu-id="4f804-147">The two key values that need to be set are `"FormatterName"` and `"FormatterOptions"`.</span></span> <span data-ttu-id="4f804-148">Jeśli program formatujący z ustawioną wartością dla `"FormatterName"` jest już zarejestrowany, ten program formatujący jest zaznaczony, a jego właściwości można skonfigurować tak długo, jak są one dostępne jako klucz w `"FormatterOptions"` węźle.</span><span class="sxs-lookup"><span data-stu-id="4f804-148">If a formatter with the value set for `"FormatterName"` is already registered, that formatter is selected, and its properties can be configured as long as they are provided as a key inside the `"FormatterOptions"` node.</span></span> <span data-ttu-id="4f804-149">Wstępnie zdefiniowane nazwy programu formatującego są zastrzeżone w <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames> :</span><span class="sxs-lookup"><span data-stu-id="4f804-149">The predefined formatter names are reserved under <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames>:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>

## <a name="implement-a-custom-formatter"></a><span data-ttu-id="4f804-150">Implementowanie niestandardowego programu formatującego</span><span class="sxs-lookup"><span data-stu-id="4f804-150">Implement a custom formatter</span></span>

<span data-ttu-id="4f804-151">W celu zaimplementowania niestandardowego programu formatującego należy wykonać następujące:</span><span class="sxs-lookup"><span data-stu-id="4f804-151">To implement a custom formatter, you need to:</span></span>

- <span data-ttu-id="4f804-152">Utwórz podklasę <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter> , która reprezentuje niestandardowy program formatujący</span><span class="sxs-lookup"><span data-stu-id="4f804-152">Create a subclass of <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter>, this represents your custom formatter</span></span>
- <span data-ttu-id="4f804-153">Rejestrowanie niestandardowego programu formatującego przy użyciu</span><span class="sxs-lookup"><span data-stu-id="4f804-153">Register your custom formatter with</span></span>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsole%2A?displayProperty=nameWithType>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsoleFormatter%60%602(Microsoft.Extensions.Logging.ILoggingBuilder,System.Action{%60%601})?displayProperty=nameWithType>

<span data-ttu-id="4f804-154">Utwórz metodę rozszerzenia, aby obsłużyć to:</span><span class="sxs-lookup"><span data-stu-id="4f804-154">Create an extension method to handle this for you:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/ConsoleLoggerExtensions.cs" highlight="11-12":::

<span data-ttu-id="4f804-155">`CustomOptions`Są zdefiniowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="4f804-155">The `CustomOptions` are defined as follows:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomOptions.cs":::

<span data-ttu-id="4f804-156">W poprzednim kodzie opcje są podklasą <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions> .</span><span class="sxs-lookup"><span data-stu-id="4f804-156">In the preceding code, the options are a subclass of <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>.</span></span>

<span data-ttu-id="4f804-157">`AddConsoleFormatter`Interfejs API:</span><span class="sxs-lookup"><span data-stu-id="4f804-157">The `AddConsoleFormatter` API:</span></span>

- <span data-ttu-id="4f804-158">Rejestruje podklasę `ConsoleFormatter`</span><span class="sxs-lookup"><span data-stu-id="4f804-158">Registers a subclass of `ConsoleFormatter`</span></span>
- <span data-ttu-id="4f804-159">Obsługuje konfigurację:</span><span class="sxs-lookup"><span data-stu-id="4f804-159">Handles configuration:</span></span>
  - <span data-ttu-id="4f804-160">Używa tokenu zmiany do synchronizowania aktualizacji na podstawie [wzorca opcji](options.md)i interfejsu [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601)</span><span class="sxs-lookup"><span data-stu-id="4f804-160">Uses a change token to synchronize updates, based on the [options pattern](options.md), and the [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601) interface</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/Program.cs" highlight="11-12":::

<span data-ttu-id="4f804-161">Zdefiniuj `CustomerFormatter` podklasę `ConsoleFormatter` :</span><span class="sxs-lookup"><span data-stu-id="4f804-161">Define a `CustomerFormatter` subclass of `ConsoleFormatter`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomFormatter.cs" highlight="24-45":::

<span data-ttu-id="4f804-162">Poprzedni `CustomFormatter.Write<TState>` interfejs API określa, jaki tekst jest zawijany wokół każdego komunikatu dziennika.</span><span class="sxs-lookup"><span data-stu-id="4f804-162">The preceding `CustomFormatter.Write<TState>` API dictates what text gets wrapped around each log message.</span></span> <span data-ttu-id="4f804-163">Standard `ConsoleFormatter` powinien być w stanie zawijać wokół zakresów, sygnatur czasowych i poziomu ważności dzienników co najmniej.</span><span class="sxs-lookup"><span data-stu-id="4f804-163">A standard `ConsoleFormatter` should be able to wrap around scopes, time stamps, and severity level of logs at a minimum.</span></span> <span data-ttu-id="4f804-164">Ponadto można kodować kolory ANSI w komunikatach dziennika i podać również odpowiednie wcięcia.</span><span class="sxs-lookup"><span data-stu-id="4f804-164">Additionally, you can encode ANSI colors in the log messages, and provide desired indentations as well.</span></span> <span data-ttu-id="4f804-165">Implementacja nie zawiera `CustomFormatter.Write<TState>` tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="4f804-165">The implementation of the `CustomFormatter.Write<TState>` lacks these capabilities.</span></span>

<span data-ttu-id="4f804-166">Aby dowiedzieć się więcej na temat dalszej dostosowywania formatowania, zobacz istniejące implementacje w `Microsoft.Extensions.Logging.Console` przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="4f804-166">For inspiration on further customizing formatting, see the existing implementations in the `Microsoft.Extensions.Logging.Console` namespace:</span></span>

- <span data-ttu-id="4f804-167">[SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs).</span><span class="sxs-lookup"><span data-stu-id="4f804-167">[SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs).</span></span>
- [<span data-ttu-id="4f804-168">SystemdConsoleFormatter</span><span class="sxs-lookup"><span data-stu-id="4f804-168">SystemdConsoleFormatter</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SystemdConsoleFormatter.cs)
- [<span data-ttu-id="4f804-169">JsonConsoleFormatter</span><span class="sxs-lookup"><span data-stu-id="4f804-169">JsonConsoleFormatter</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/JsonConsoleFormatter.cs)

## <a name="implement-custom-color-formatting"></a><span data-ttu-id="4f804-170">Zaimplementuj niestandardowe formatowanie koloru</span><span class="sxs-lookup"><span data-stu-id="4f804-170">Implement custom color formatting</span></span>

<span data-ttu-id="4f804-171">Aby zapewnić prawidłowe włączenie możliwości kolorów w niestandardowym programie formatującego rejestrowania, można ją rozłożyć, <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> ponieważ ma <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> Właściwość, która może być przydatna do włączania kolorów w dziennikach.</span><span class="sxs-lookup"><span data-stu-id="4f804-171">In order to properly enable color capabilities in your custom logging formatter, you can extend the <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> as it has a <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> property that can be useful for enabling colors in logs.</span></span>

<span data-ttu-id="4f804-172">Utwórz element `CustomColorOptions` pochodzący z `SimpleConsoleFormatterOptions` :</span><span class="sxs-lookup"><span data-stu-id="4f804-172">Create a `CustomColorOptions` that derives from `SimpleConsoleFormatterOptions`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorOptions.cs" highlight="5":::

<span data-ttu-id="4f804-173">Następnie napisz niektóre metody rozszerzające w `TextWriterExtensions` klasie, która pozwala wygodnie osadzać kodowane w formacie ANSI kolory dzienników:</span><span class="sxs-lookup"><span data-stu-id="4f804-173">Next, write some extension methods in a `TextWriterExtensions` class that allow for conveniently embedding ANSI coded colors within formatted log messages:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/TextWriterExtensions.cs":::

<span data-ttu-id="4f804-174">Niestandardowy program formatujący kolory obsługujący stosowanie kolorów niestandardowych można zdefiniować w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="4f804-174">A custom color formatter that handles applying custom colors could be defined as follows:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorFormatter.cs" highlight="15-18,52-65":::

<span data-ttu-id="4f804-175">Po uruchomieniu aplikacji dzienniki będą wyświetlać `CustomPrefix` komunikat w kolorze zielonym, gdy `FormatterOptions.ColorBehavior` jest `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="4f804-175">When you run the application, the logs will show the `CustomPrefix` message in the color green when `FormatterOptions.ColorBehavior` is `Enabled`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f804-176">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4f804-176">See also</span></span>

- [<span data-ttu-id="4f804-177">Rejestrowanie w programie .NET</span><span class="sxs-lookup"><span data-stu-id="4f804-177">Logging in .NET</span></span>](logging.md)
- [<span data-ttu-id="4f804-178">Implementowanie niestandardowego dostawcy rejestrowania w programie .NET</span><span class="sxs-lookup"><span data-stu-id="4f804-178">Implement a custom logging provider in .NET</span></span>](custom-logging-provider.md)
- [<span data-ttu-id="4f804-179">Rejestrowanie o wysokiej wydajności w programie .NET</span><span class="sxs-lookup"><span data-stu-id="4f804-179">High-performance logging in .NET</span></span>](high-performance-logging.md)
