---
ms.openlocfilehash: e92fe8364800b1775f0acc31d67aef66a42d0b95
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465892"
---
### <a name="obsolete-properties-on-consoleloggeroptions"></a><span data-ttu-id="2418c-101">Przestarzałe właściwości w ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="2418c-101">Obsolete properties on ConsoleLoggerOptions</span></span>

<span data-ttu-id="2418c-102"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType>Typ i niektóre właściwości <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> są obecnie przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="2418c-102">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and some properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are now obsolete.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2418c-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="2418c-103">Change description</span></span>

<span data-ttu-id="2418c-104">Począwszy od platformy .NET 5,0, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> Typ i kilka właściwości <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> są przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="2418c-104">Starting in .NET 5.0, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and several properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are obsolete.</span></span> <span data-ttu-id="2418c-105">Przestarzałe właściwości to:</span><span class="sxs-lookup"><span data-stu-id="2418c-105">The obsolete properties are:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

<span data-ttu-id="2418c-106">Po wprowadzeniu nowych elementów formatujących te właściwości są teraz dostępne dla poszczególnych elementów formatujących.</span><span class="sxs-lookup"><span data-stu-id="2418c-106">With the introduction of new formatters, these properties are now available on the individual formatters.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2418c-107">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="2418c-107">Reason for change</span></span>

<span data-ttu-id="2418c-108"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>Właściwość jest typem wyliczenia, który nie może reprezentować niestandardowego programu formatującego.</span><span class="sxs-lookup"><span data-stu-id="2418c-108">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> property is an enumeration type, which cannot represent a custom formatter.</span></span>

<span data-ttu-id="2418c-109">Pozostałe właściwości zostały ustawione na <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> poziomie i zastosowane do obu wbudowanych formatów dla dzienników konsoli.</span><span class="sxs-lookup"><span data-stu-id="2418c-109">The remaining properties were set on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> and applied to both of the built-in formats for console logs.</span></span> <span data-ttu-id="2418c-110">Jednak wprowadzenie nowego interfejsu API programu formatującego sprawia, że formatowanie jest reprezentowane w opcjach specyficznych dla programu formatującego.</span><span class="sxs-lookup"><span data-stu-id="2418c-110">However, with the introduction of a new formatter API, it makes more sense for formatting to be represented on the formatter-specific options.</span></span> <span data-ttu-id="2418c-111">Ta zmiana zapewnia lepszy rozdzielenie elementów formatujących Rejestrator i rejestratora.</span><span class="sxs-lookup"><span data-stu-id="2418c-111">This change provides better separation between the logger and logger formatters.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2418c-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="2418c-112">Version introduced</span></span>

<span data-ttu-id="2418c-113">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="2418c-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2418c-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="2418c-114">Recommended action</span></span>

- <span data-ttu-id="2418c-115">Użyj nowej <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> Właściwości zamiast <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="2418c-115">Use the new <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> property in place of the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2418c-116">Przykład:</span><span class="sxs-lookup"><span data-stu-id="2418c-116">For example:</span></span>

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  <span data-ttu-id="2418c-117">Istnieje kilka różnic między programami <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> i <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> :</span><span class="sxs-lookup"><span data-stu-id="2418c-117">There are several differences between <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span></span>

  - <span data-ttu-id="2418c-118"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> ma tylko dwie możliwe opcje: `Default` i `Systemd` .</span><span class="sxs-lookup"><span data-stu-id="2418c-118"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> has only two possible options: `Default` and `Systemd`.</span></span>
  - <span data-ttu-id="2418c-119"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> wielkość liter nie jest rozróżniana i może być dowolnym ciągiem.</span><span class="sxs-lookup"><span data-stu-id="2418c-119"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> is case insensitive and can be any string.</span></span> <span data-ttu-id="2418c-120">Zastrzeżone, wbudowane nazwy to `Simple` , `Systemd` , i `Json` (.NET 5,0 i nowsze).</span><span class="sxs-lookup"><span data-stu-id="2418c-120">The reserved, built-in names are `Simple`, `Systemd`, and `Json` (.NET 5.0 and later).</span></span>
  - <span data-ttu-id="2418c-121">`"Format": "Systemd"` mapuje do `"FormatterName": "Systemd"` .</span><span class="sxs-lookup"><span data-stu-id="2418c-121">`"Format": "Systemd"` maps to `"FormatterName": "Systemd"`.</span></span>
  - <span data-ttu-id="2418c-122">`"Format": "Default"` mapuje do `"FormatterName": "Simple"` .</span><span class="sxs-lookup"><span data-stu-id="2418c-122">`"Format": "Default"` maps to `"FormatterName": "Simple"`.</span></span>

- <span data-ttu-id="2418c-123">W przypadku <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors> <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes> właściwości,, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat> i <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> należy użyć odpowiedniej właściwości dla nowych typów, <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions> <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions> lub <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> .</span><span class="sxs-lookup"><span data-stu-id="2418c-123">For the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat>, and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> properties, use the corresponding property on the new <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions>, or <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> types instead.</span></span> <span data-ttu-id="2418c-124">Przykład:</span><span class="sxs-lookup"><span data-stu-id="2418c-124">For example:</span></span>

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

<span data-ttu-id="2418c-125">Poniższe dwa fragmenty kodu JSON pokazują, jak zmienia się plik konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="2418c-125">The following two JSON snippets show how the configuration file changes.</span></span> <span data-ttu-id="2418c-126">Stary plik konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="2418c-126">Old configuration file:</span></span>

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

<span data-ttu-id="2418c-127">Nowy plik konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="2418c-127">New configuration file:</span></span>

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

#### <a name="category"></a><span data-ttu-id="2418c-128">Kategoria</span><span class="sxs-lookup"><span data-stu-id="2418c-128">Category</span></span>

- <span data-ttu-id="2418c-129">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="2418c-129">Core .NET libraries</span></span>
- <span data-ttu-id="2418c-130">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2418c-130">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2418c-131">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="2418c-131">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=fullName>

<!--

#### Affected APIs

- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format`

-->
