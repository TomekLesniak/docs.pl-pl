---
title: 'Zmiana podziału: przestarzałe właściwości w ConsoleLoggerOptions'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których typ ConsoleLoggerFormat i niektóre właściwości ConsoleLoggerOptions są obecnie przestarzałe.
ms.date: 11/01/2020
ms.openlocfilehash: e38ba3bda371c713a8b2cb4cda8b4c585dac29f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761620"
---
# <a name="obsolete-properties-on-consoleloggeroptions"></a>Przestarzałe właściwości w ConsoleLoggerOptions

<xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType>Typ i niektóre właściwości <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> są obecnie przestarzałe.

## <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> Typ i kilka właściwości <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> są przestarzałe. Przestarzałe właściwości to:

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

Po wprowadzeniu nowych elementów formatujących te właściwości są teraz dostępne dla poszczególnych elementów formatujących.

## <a name="reason-for-change"></a>Przyczyna zmiany

<xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>Właściwość jest typem wyliczenia, który nie może reprezentować niestandardowego programu formatującego.

Pozostałe właściwości zostały ustawione na <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> poziomie i zastosowane do obu wbudowanych formatów dla dzienników konsoli. Jednak wprowadzenie nowego interfejsu API programu formatującego sprawia, że formatowanie jest reprezentowane w opcjach specyficznych dla programu formatującego. Ta zmiana zapewnia lepszy rozdzielenie elementów formatujących Rejestrator i rejestratora.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

- Użyj nowej <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> Właściwości zamiast <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> właściwości. Na przykład:

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  Istnieje kilka różnic między programami <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> i <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> :

  - <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> ma tylko dwie możliwe opcje: `Default` i `Systemd` .
  - <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> wielkość liter nie jest rozróżniana i może być dowolnym ciągiem. Zastrzeżone, wbudowane nazwy to `Simple` , `Systemd` , i `Json` (.NET 5,0 i nowsze).
  - `"Format": "Systemd"` mapuje do `"FormatterName": "Systemd"` .
  - `"Format": "Default"` mapuje do `"FormatterName": "Simple"` .

- W przypadku <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors> <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes> właściwości,, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat> i <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> należy użyć odpowiedniej właściwości dla nowych typów, <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions> <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions> lub <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> . Na przykład:

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

Poniższe dwa fragmenty kodu JSON pokazują, jak zmienia się plik konfiguracji. Stary plik konfiguracji:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "Format": "Systemd",
      "IncludeScopes": true,
      "TimestampFormat": "HH:mm:ss",
      "UseUtcTimestamp": true
    }
  },
  "AllowedHosts": "*"
}
```

Nowy plik konfiguracji:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "FormatterName": "Systemd",
      "FormatterOptions": {
        "IncludeScopes": true,
        "TimestampFormat": "HH:mm:ss",
        "UseUtcTimestamp": true
      }
    }
  },
  "AllowedHosts": "*"
}
```

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET

### Affected APIs

- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format`

-->
