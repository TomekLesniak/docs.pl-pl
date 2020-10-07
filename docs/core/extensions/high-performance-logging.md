---
title: Rejestrowanie o wysokiej wydajności w programie .NET
author: IEvangelist
description: Dowiedz się, jak używać LoggerMessage do tworzenia delegatów z pamięcią podręczną, które wymagają mniejszej liczby alokacji obiektów do scenariuszy rejestrowania o wysokiej wydajności.
ms.author: dapine
ms.date: 09/25/2020
ms.openlocfilehash: 9111b9553c913cff2937b574250b65e633250f4f
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804762"
---
# <a name="high-performance-logging-in-net"></a>Rejestrowanie o wysokiej wydajności w programie .NET

<xref:Microsoft.Extensions.Logging.LoggerMessage>Klasa udostępnia funkcje do tworzenia delegatów z pamięcią podręczną, które wymagają mniejszej liczby alokacji obiektów i mniejszego obciążenia obliczeniowego w porównaniu z [metodami rozszerzenia rejestratora](xref:Microsoft.Extensions.Logging.LoggerExtensions), takimi jak <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> i <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A> . W przypadku scenariuszy rejestrowania o wysokiej wydajności Użyj <xref:Microsoft.Extensions.Logging.LoggerMessage> wzorca.

<xref:Microsoft.Extensions.Logging.LoggerMessage> zapewnia następujące korzyści wynikające z wydajności w porównaniu z metodami rozszerzenia rejestratora:

- Metody rozszerzenia rejestratora wymagają "opakowania" (do konwersji) typów wartości, takich jak `int` , do `object` . <xref:Microsoft.Extensions.Logging.LoggerMessage>Wzorzec unika pakowania przy użyciu <xref:System.Action> pól statycznych i metod rozszerzających z parametrami o jednoznacznie określonym typie.
- Metody rozszerzenia rejestratora muszą analizować szablon wiadomości (nazwanego ciągu formatu) za każdym razem, gdy zostanie zapisany komunikat dziennika. <xref:Microsoft.Extensions.Logging.LoggerMessage> tylko wymaga analizy szablonu tylko raz, gdy komunikat jest zdefiniowany.

W przykładowej aplikacji przedstawiono <xref:Microsoft.Extensions.Logging.LoggerMessage> funkcje z przetworzeniem kolejki priorytetowej usługi procesu roboczego. Aplikacja przetwarza elementy robocze w kolejności priorytetu. W przypadku wystąpienia tych operacji komunikaty dziennika są generowane przy użyciu <xref:Microsoft.Extensions.Logging.LoggerMessage> wzorca.

## <a name="define-a-logger-message"></a>Zdefiniuj komunikat rejestratora

Użyj [Definiuj (LogLevel, EventId, String)](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A) , aby utworzyć <xref:System.Action> delegata do rejestrowania wiadomości. <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> przeciążenia dopuszczają przekazywanie do sześciu parametrów typu do nazwanego ciągu formatu (szablonu).

Ciąg dostarczony do <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> metody jest szablonem, a nie ciągiem interpolowanym. Symbole zastępcze są wypełniane w kolejności, w jakiej są określone typy. Nazwy symboli zastępczych w szablonie powinny być opisowe i spójne w szablonach. Służą one jako nazwy właściwości w danych dziennika strukturalnego. Zalecamy używanie [wielkości liter](../../standard/design-guidelines/capitalization-conventions.md) w języku Pascal dla nazw zastępczych. Na przykład `{Item}` , `{DateTime}` .

Każdy komunikat dziennika jest <xref:System.Action> przechowywany w polu statycznym utworzonym przez [LoggerMessage. define](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A). Przykładowo Przykładowa aplikacja tworzy pole opisujące komunikat dziennika do przetwarzania elementów roboczych:

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkField":::

Dla <xref:System.Action> , określ:

- Poziom dziennika.
- Unikatowy identyfikator zdarzenia ( <xref:Microsoft.Extensions.Logging.EventId> ) z nazwą statycznej metody rozszerzenia.
- Szablon wiadomości (nazwany ciąg formatu).

Ponieważ elementy robocze są dekolejkowane do przetwarzania aplikacji usługi procesu roboczego, ustawia:

- Poziom rejestrowania do `Critical` .
- Identyfikator zdarzenia do `13` nazwy `FailedToProcessWorkItem` metody.
- Szablon wiadomości (nazwany ciąg formatu) do ciągu.

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkAssignment":::

Magazyny rejestrowania strukturalnego mogą używać nazwy zdarzenia, gdy jest ona dostarczana z identyfikatorem zdarzenia w celu wzbogacania rejestrowania. Na przykład [Serilog](https://github.com/serilog/serilog-extensions-logging) używa nazwy zdarzenia.

<xref:System.Action>Jest wywoływany za pomocą metody rozszerzającej o jednoznacznie określonym typie. `FailedToProcessWorkItem`Metoda rejestruje komunikat za każdym razem, gdy element roboczy jest przetwarzany:

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkMethod":::

`FailedToProcessWorkItem` jest wywoływana dla rejestratora w `ExecuteAsync` metodzie *Worker.cs* w przypadku wystąpienia błędu:

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="15-18":::

Sprawdź dane wyjściowe konsoli aplikacji:

```console
crit: WorkerServiceOptions.Example.Worker[13]
      Epic failure processing item!
      System.Exception: Failed to verify communications.
         at WorkerServiceOptions.Example.Worker.ExecuteAsync(CancellationToken stoppingToken) in
         ..\Worker.cs:line 27
```

Aby przekazać parametry do komunikatu dziennika, zdefiniuj maksymalnie sześć typów podczas tworzenia pola statycznego. Przykładowa aplikacja rejestruje szczegóły elementu pracy podczas przetwarzania elementów przez zdefiniowanie `WorkItem` typu dla <xref:System.Action> pola:

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemField":::

Szablon komunikatu dziennika delegata otrzymuje wartości zastępcze z dostarczonych typów. Przykładowa aplikacja definiuje delegata do dodawania oferty, w której parametr Quote jest `WorkItem` :

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemAssignment":::

Statyczna metoda rozszerzenia do rejestrowania, że element roboczy jest przetwarzany, `PriorityItemProcessed` odbiera wartość argumentu elementu pracy i przekazuje ją do <xref:System.Action> delegata:

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemMethod":::

W metodzie usługi procesu roboczego `ExecuteAsync` `PriorityItemProcessed` jest wywoływana w celu zarejestrowania komunikatu:

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="12":::

Sprawdź dane wyjściowe konsoli aplikacji:

```console
info: WorkerServiceOptions.Example.Worker[1]
      Processing priority item: Priority-Extreme (50db062a-9732-4418-936d-110549ad79e4): 'Verify communications'
```

## <a name="define-logger-message-scope"></a>Zdefiniuj zakres komunikatów rejestratora

Metoda [DefineScope — (String)](xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A) tworzy <xref:System.Func%601> delegat do definiowania [zakresu dziennika](logging.md#log-scopes). <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> przeciążenia dopuszczają przekazywanie do trzech parametrów typu do nazwanego ciągu formatu (szablonu).

Podobnie jak w przypadku <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> metody, ciąg dostarczony do <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> metody jest szablonem, a nie ciągiem interpolowanym. Symbole zastępcze są wypełniane w kolejności, w jakiej są określone typy. Nazwy symboli zastępczych w szablonie powinny być opisowe i spójne w szablonach. Służą one jako nazwy właściwości w danych dziennika strukturalnego. Zalecamy używanie [wielkości liter](../../standard/design-guidelines/capitalization-conventions.md) w języku Pascal dla nazw zastępczych. Na przykład `{Item}` , `{DateTime}` .

Zdefiniuj [zakres dziennika](logging.md#log-scopes) , który ma zostać zastosowany do serii komunikatów dziennika przy użyciu <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> metody.

Przykładowa aplikacja ma przycisk **Wyczyść wszystko** , aby usunąć wszystkie cudzysłowy w bazie danych. Cudzysłowy są usuwane, usuwając je pojedynczo. Przy każdym usunięciu oferty `QuoteDeleted` Metoda jest wywoływana w rejestratorze. Do tych komunikatów dziennika jest dodawany zakres dziennika.

Włącz `IncludeScopes` w sekcji rejestratora konsoli *appsettings.jsna*:

:::code language="json" source="snippets/configuration/worker-service-options/appsettings.json" highlight="3-5":::

Aby utworzyć zakres dziennika, należy dodać pole do przechowywania <xref:System.Func%601> delegata dla zakresu. Przykładowa aplikacja tworzy pole o nazwie `_allQuotesDeletedScope` (*wewnętrzne/LoggerExtensions. cs*):

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkField":::

Użyj, <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> Aby utworzyć delegata. Można określić maksymalnie trzy typy do użycia jako argumenty szablonu, gdy obiekt delegowany jest wywoływany. Przykładowa aplikacja używa szablonu komunikatu zawierającego liczbę usuniętych cudzysłowów ( `int` Typ):

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkAssignment":::

Podaj statyczną metodę rozszerzenia dla komunikatu dziennika. Dołącz wszystkie parametry typu dla nazwanych właściwości, które są wyświetlane w szablonie wiadomości. Przykładowa aplikacja zajmuje się `DateTime` przez niestandardową sygnaturę czasową, aby rejestrować i zwracać `_processingWorkScope` :

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkMethod":::

Zakres zawija wywołania rozszerzenia rejestrowania w bloku [using](../../csharp/language-reference/keywords/using-statement.md) :

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="4":::

Sprawdź komunikaty dziennika w danych wyjściowych konsoli aplikacji. Poniższy wynik pokazuje trzy cudzysłowy usunięte z uwzględnieniem komunikatu o zakresie dziennika:

```console
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Extreme (f5090ede-a337-4041-b914-f6bc0db5ae64): 'Verify communications'
info: Microsoft.Hosting.Lifetime[0]
      Application started. Press Ctrl+C to shut down.
info: Microsoft.Hosting.Lifetime[0]
      Hosting environment: Development
info: Microsoft.Hosting.Lifetime[0]
      Content root path: ..\worker-service-options
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-High (496d440f-2007-4391-b179-09d75ab52373): 'Validate collection'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Medium (dea9e3f4-d7df-46d2-b7cd-5e0232eb98a5): 'Propagate selections'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Medium (089d7f0d-da72-4b55-92fe-57b147838056): 'Enter pooling [contention]'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Low (6e68c4be-089f-4450-9080-1ea63fcbb686): 'Health check network'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Deferred (6f324134-6bb6-455f-81d4-553ab307c421): 'Ping weather service'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Deferred (37bf736c-7a26-4a2a-9e56-e89bcf3b8f35): 'Set process state'
```

## <a name="see-also"></a>Zobacz też

- [Rejestrowanie w programie .NET](logging.md)
