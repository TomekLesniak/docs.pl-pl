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
# <a name="console-log-formatting"></a>Formatowanie dziennika konsoli

W programie .NET 5 obsługa niestandardowego formatowania została dodana do dzienników konsoli w `Microsoft.Extensions.Logging.Console` przestrzeni nazw. Dostępne są trzy wstępnie zdefiniowane opcje formatowania: [`Simple`](#simple) , [`Systemd`](#systemd) , i [`Json`](#json) .

> [!IMPORTANT]
> Wcześniej <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> Wyliczenie dozwolone do wybrania żądanego formatu dziennika — można je odczytać przez człowieka `Default` lub pojedynczy wiersz, który jest również znany jako `Systemd` . **Nie** są one jednak dostosowywane i obecnie przestarzałe.

Ten artykuł zawiera informacje dotyczące programu formatującego dzienników konsoli. Przykładowy kod źródłowy pokazuje, jak:

- Rejestrowanie nowego programu formatującego
- Wybieranie zarejestrowanego programu formatującego do użycia
  - Za pomocą kodu lub [konfiguracji](configuration.md)
- Implementowanie niestandardowego programu formatującego
  - Aktualizacja konfiguracji za pomocą <xref:Microsoft.Extensions.Options.IOptionsMonitor%601>
  - Włącz niestandardowe formatowanie kolorów

## <a name="register-formatter"></a>Rejestrowanie programu formatującego

[ `Console` Dostawca rejestrowania](logging-providers.md#console) zawiera kilka wstępnie zdefiniowanych elementów formatujących i uwidacznia możliwość tworzenia własnego niestandardowego programu formatującego. Aby zarejestrować dowolne z dostępnych elementów formatujących, użyj odpowiedniej `Add{Type}Console` metody rozszerzenia:

| Dostępne typy | Metoda do rejestrowania typu |
|--|--|
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddJsonConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSimpleConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSystemdConsole%2A?displayProperty=nameWithType> |

### <a name="simple"></a>Prostota

Aby użyć programu `Simple` formatującego konsoli, zarejestruj go przy użyciu `AddSimpleConsole` :

:::code language="csharp" source="snippets/logging/console-formatter-simple/Program.cs" highlight="11-16":::

W poprzednim przykładowym kodzie źródłowym program <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> formatujący został zarejestrowany. Udostępnia ona dzienniki z możliwością, aby nie tylko zawijać informacje, takie jak czas i poziom rejestrowania w każdym komunikacie dziennika, ale również umożliwia osadzanie i wcięcia kolorów ANSI.

### <a name="systemd"></a>Usługę systemd

<xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>Rejestrator konsoli:

- Używa formatu i serwerów dziennika "Dziennik systemowy"
- Nie **formatuje** komunikatów z kolorami
- Zawsze rejestruje komunikaty w pojedynczym wierszu

Jest to często przydatne w przypadku kontenerów, które często używają `Systemd` rejestrowania w konsoli. W przypadku platformy .NET 5 `Simple` konsola rejestratora umożliwia również kompaktowanie wersji, która jest rejestrowana w jednym wierszu, a także umożliwia wyłączenie kolorów, jak pokazano w wcześniejszym przykładzie.

:::code language="csharp" source="snippets/logging/console-formatter-systemd/Program.cs" highlight="11-15":::

### <a name="json"></a>JSON

Do zapisu dzienników w formacie JSON `Json` jest używany program formatujący konsoli. Przykładowy kod źródłowy pokazuje, jak aplikacja ASP.NET Core może ją zarejestrować. Za pomocą `webapp` szablonu Utwórz nową aplikację ASP.NET Core przy użyciu polecenia [dotnet New](../tools/dotnet-new.md) :

```dotnetcli
dotnet new webapp -o Console.ExampleFormatters.Json
```

Podczas uruchamiania aplikacji przy użyciu kodu szablonu otrzymujesz domyślny format dziennika:

```
info: Microsoft.Hosting.Lifetime[0]
      Now listening on: https://localhost:5001
```

Domyślnie program `Simple` formatujący dziennik konsoli jest wybierany z domyślną konfiguracją. Możesz to zmienić, wywołując `AddJsonConsole` w *program.cs* :

:::code language="csharp" source="snippets/logging/console-formatter-json/Program.cs" highlight="17-26":::

Uruchom aplikację ponownie, używając powyższej zmiany, komunikat dziennika jest teraz sformatowany w formacie JSON:

:::code language="json" source="snippets/logging/console-formatter-json/example-output.json":::

> [!TIP]
> Program `Json` formatujący konsoli domyślnie rejestruje każdy komunikat w jednym wierszu. Aby zwiększyć czytelność podczas konfigurowania programu formatującego, ustaw wartość <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType> na `true` .

## <a name="set-formatter-with-configuration"></a>Ustawianie programu formatującego z konfiguracją

W poprzednich przykładach przedstawiono sposób programowego rejestrowania programu formatującego. Można to również zrobić z [konfiguracją](configuration.md). Rozważmy poprzedni kod źródłowy przykładowej aplikacji sieci Web, jeśli *appsettings.js* plik zostanie zaktualizowany zamiast wywoływania `ConfigureLogging` w pliku *program.cs* , można uzyskać ten sam wynik. Zaktualizowany `appsettings.json` plik spowoduje skonfigurowanie programu formatującego w następujący sposób:

:::code language="json" source="snippets/logging/console-formatter-json/appsettings.json" highlight="14-23":::

Dwie wartości klucza, które należy ustawić, to `"FormatterName"` i `"FormatterOptions"` . Jeśli program formatujący z ustawioną wartością dla `"FormatterName"` jest już zarejestrowany, ten program formatujący jest zaznaczony, a jego właściwości można skonfigurować tak długo, jak są one dostępne jako klucz w `"FormatterOptions"` węźle. Wstępnie zdefiniowane nazwy programu formatującego są zastrzeżone w <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames> :

- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>

## <a name="implement-a-custom-formatter"></a>Implementowanie niestandardowego programu formatującego

W celu zaimplementowania niestandardowego programu formatującego należy wykonać następujące:

- Utwórz podklasę <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter> , która reprezentuje niestandardowy program formatujący
- Rejestrowanie niestandardowego programu formatującego przy użyciu
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsole%2A?displayProperty=nameWithType>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsoleFormatter%60%602(Microsoft.Extensions.Logging.ILoggingBuilder,System.Action{%60%601})?displayProperty=nameWithType>

Utwórz metodę rozszerzenia, aby obsłużyć to:

:::code language="csharp" source="snippets/logging/console-formatter-custom/ConsoleLoggerExtensions.cs" highlight="11-12":::

`CustomOptions`Są zdefiniowane w następujący sposób:

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomOptions.cs":::

W poprzednim kodzie opcje są podklasą <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions> .

`AddConsoleFormatter`Interfejs API:

- Rejestruje podklasę `ConsoleFormatter`
- Obsługuje konfigurację:
  - Używa tokenu zmiany do synchronizowania aktualizacji na podstawie [wzorca opcji](options.md)i interfejsu [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601)

:::code language="csharp" source="snippets/logging/console-formatter-custom/Program.cs" highlight="11-12":::

Zdefiniuj `CustomerFormatter` podklasę `ConsoleFormatter` :

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomFormatter.cs" highlight="24-45":::

Poprzedni `CustomFormatter.Write<TState>` interfejs API określa, jaki tekst jest zawijany wokół każdego komunikatu dziennika. Standard `ConsoleFormatter` powinien być w stanie zawijać wokół zakresów, sygnatur czasowych i poziomu ważności dzienników co najmniej. Ponadto można kodować kolory ANSI w komunikatach dziennika i podać również odpowiednie wcięcia. Implementacja nie zawiera `CustomFormatter.Write<TState>` tych funkcji.

Aby dowiedzieć się więcej na temat dalszej dostosowywania formatowania, zobacz istniejące implementacje w `Microsoft.Extensions.Logging.Console` przestrzeni nazw:

- [SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs).
- [SystemdConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SystemdConsoleFormatter.cs)
- [JsonConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/JsonConsoleFormatter.cs)

## <a name="implement-custom-color-formatting"></a>Zaimplementuj niestandardowe formatowanie koloru

Aby zapewnić prawidłowe włączenie możliwości kolorów w niestandardowym programie formatującego rejestrowania, można ją rozłożyć, <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> ponieważ ma <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> Właściwość, która może być przydatna do włączania kolorów w dziennikach.

Utwórz element `CustomColorOptions` pochodzący z `SimpleConsoleFormatterOptions` :

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorOptions.cs" highlight="5":::

Następnie napisz niektóre metody rozszerzające w `TextWriterExtensions` klasie, która pozwala wygodnie osadzać kodowane w formacie ANSI kolory dzienników:

:::code language="csharp" source="snippets/logging/console-formatter-custom/TextWriterExtensions.cs":::

Niestandardowy program formatujący kolory obsługujący stosowanie kolorów niestandardowych można zdefiniować w następujący sposób:

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorFormatter.cs" highlight="15-18,52-65":::

Po uruchomieniu aplikacji dzienniki będą wyświetlać `CustomPrefix` komunikat w kolorze zielonym, gdy `FormatterOptions.ColorBehavior` jest `Enabled` .

## <a name="see-also"></a>Zobacz także

- [Rejestrowanie w programie .NET](logging.md)
- [Implementowanie niestandardowego dostawcy rejestrowania w programie .NET](custom-logging-provider.md)
- [Rejestrowanie o wysokiej wydajności w programie .NET](high-performance-logging.md)
