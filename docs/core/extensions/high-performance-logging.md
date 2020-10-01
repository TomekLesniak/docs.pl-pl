---
title: Rejestrowanie o wysokiej wydajności w programie .NET
author: IEvangelist
description: Dowiedz się, jak używać LoggerMessage do tworzenia delegatów z pamięcią podręczną, które wymagają mniejszej liczby alokacji obiektów do scenariuszy rejestrowania o wysokiej wydajności.
ms.author: dapine
ms.date: 09/25/2020
ms.openlocfilehash: d722a3a5cb38f33b6833a5c280687ce6c1e46bf9
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91614757"
---
# <a name="high-performance-logging-in-net"></a><span data-ttu-id="791ff-103">Rejestrowanie o wysokiej wydajności w programie .NET</span><span class="sxs-lookup"><span data-stu-id="791ff-103">High-performance logging in .NET</span></span>

<span data-ttu-id="791ff-104"><xref:Microsoft.Extensions.Logging.LoggerMessage>Klasa udostępnia funkcje do tworzenia delegatów z pamięcią podręczną, które wymagają mniejszej liczby alokacji obiektów i mniejszego obciążenia obliczeniowego w porównaniu z [metodami rozszerzenia rejestratora](xref:Microsoft.Extensions.Logging.LoggerExtensions), takimi jak <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> i <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A> .</span><span class="sxs-lookup"><span data-stu-id="791ff-104">The <xref:Microsoft.Extensions.Logging.LoggerMessage> class exposes functionality to create cacheable delegates that require fewer object allocations and reduced computational overhead compared to [logger extension methods](xref:Microsoft.Extensions.Logging.LoggerExtensions), such as <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> and <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A>.</span></span> <span data-ttu-id="791ff-105">W przypadku scenariuszy rejestrowania o wysokiej wydajności Użyj <xref:Microsoft.Extensions.Logging.LoggerMessage> wzorca.</span><span class="sxs-lookup"><span data-stu-id="791ff-105">For high-performance logging scenarios, use the <xref:Microsoft.Extensions.Logging.LoggerMessage> pattern.</span></span>

<span data-ttu-id="791ff-106"><xref:Microsoft.Extensions.Logging.LoggerMessage> zapewnia następujące korzyści wynikające z wydajności w porównaniu z metodami rozszerzenia rejestratora:</span><span class="sxs-lookup"><span data-stu-id="791ff-106"><xref:Microsoft.Extensions.Logging.LoggerMessage> provides the following performance advantages over Logger extension methods:</span></span>

- <span data-ttu-id="791ff-107">Metody rozszerzenia rejestratora wymagają "opakowania" (do konwersji) typów wartości, takich jak `int` , do `object` .</span><span class="sxs-lookup"><span data-stu-id="791ff-107">Logger extension methods require "boxing" (converting) value types, such as `int`, into `object`.</span></span> <span data-ttu-id="791ff-108"><xref:Microsoft.Extensions.Logging.LoggerMessage>Wzorzec unika pakowania przy użyciu <xref:System.Action> pól statycznych i metod rozszerzających z parametrami o jednoznacznie określonym typie.</span><span class="sxs-lookup"><span data-stu-id="791ff-108">The <xref:Microsoft.Extensions.Logging.LoggerMessage> pattern avoids boxing by using static <xref:System.Action> fields and extension methods with strongly-typed parameters.</span></span>
- <span data-ttu-id="791ff-109">Metody rozszerzenia rejestratora muszą analizować szablon wiadomości (nazwanego ciągu formatu) za każdym razem, gdy zostanie zapisany komunikat dziennika.</span><span class="sxs-lookup"><span data-stu-id="791ff-109">Logger extension methods must parse the message template (named format string) every time a log message is written.</span></span> <span data-ttu-id="791ff-110"><xref:Microsoft.Extensions.Logging.LoggerMessage> tylko wymaga analizy szablonu tylko raz, gdy komunikat jest zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="791ff-110"><xref:Microsoft.Extensions.Logging.LoggerMessage> only requires parsing a template once when the message is defined.</span></span>

<span data-ttu-id="791ff-111">W przykładowej aplikacji przedstawiono <xref:Microsoft.Extensions.Logging.LoggerMessage> funkcje z przetworzeniem kolejki priorytetowej usługi procesu roboczego.</span><span class="sxs-lookup"><span data-stu-id="791ff-111">The sample app demonstrates <xref:Microsoft.Extensions.Logging.LoggerMessage> features with a priority queue processing worker service.</span></span> <span data-ttu-id="791ff-112">Aplikacja przetwarza elementy robocze w kolejności priorytetu.</span><span class="sxs-lookup"><span data-stu-id="791ff-112">The app processes work items in priority order.</span></span> <span data-ttu-id="791ff-113">W przypadku wystąpienia tych operacji komunikaty dziennika są generowane przy użyciu <xref:Microsoft.Extensions.Logging.LoggerMessage> wzorca.</span><span class="sxs-lookup"><span data-stu-id="791ff-113">As these operations occur, log messages are generated using the <xref:Microsoft.Extensions.Logging.LoggerMessage> pattern.</span></span>

## <a name="define-a-logger-message"></a><span data-ttu-id="791ff-114">Zdefiniuj komunikat rejestratora</span><span class="sxs-lookup"><span data-stu-id="791ff-114">Define a logger message</span></span>

<span data-ttu-id="791ff-115">Użyj [Definiuj (LogLevel, EventId, String)](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A) , aby utworzyć <xref:System.Action> delegata do rejestrowania wiadomości.</span><span class="sxs-lookup"><span data-stu-id="791ff-115">Use [Define(LogLevel, EventId, String)](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A) to create an <xref:System.Action> delegate for logging a message.</span></span> <span data-ttu-id="791ff-116"><xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> przeciążenia dopuszczają przekazywanie do sześciu parametrów typu do nazwanego ciągu formatu (szablonu).</span><span class="sxs-lookup"><span data-stu-id="791ff-116"><xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> overloads permit passing up to six type parameters to a named format string (template).</span></span>

<span data-ttu-id="791ff-117">Ciąg dostarczony do <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> metody jest szablonem, a nie ciągiem interpolowanym.</span><span class="sxs-lookup"><span data-stu-id="791ff-117">The string provided to the <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> method is a template and not an interpolated string.</span></span> <span data-ttu-id="791ff-118">Symbole zastępcze są wypełniane w kolejności, w jakiej są określone typy.</span><span class="sxs-lookup"><span data-stu-id="791ff-118">Placeholders are filled in the order that the types are specified.</span></span> <span data-ttu-id="791ff-119">Nazwy symboli zastępczych w szablonie powinny być opisowe i spójne w szablonach.</span><span class="sxs-lookup"><span data-stu-id="791ff-119">Placeholder names in the template should be descriptive and consistent across templates.</span></span> <span data-ttu-id="791ff-120">Służą one jako nazwy właściwości w danych dziennika strukturalnego.</span><span class="sxs-lookup"><span data-stu-id="791ff-120">They serve as property names within structured log data.</span></span> <span data-ttu-id="791ff-121">Zalecamy używanie [wielkości liter](../../standard/design-guidelines/capitalization-conventions.md) w języku Pascal dla nazw zastępczych.</span><span class="sxs-lookup"><span data-stu-id="791ff-121">We recommend [Pascal casing](../../standard/design-guidelines/capitalization-conventions.md) for placeholder names.</span></span> <span data-ttu-id="791ff-122">Na przykład `{Item}` , `{DateTime}` .</span><span class="sxs-lookup"><span data-stu-id="791ff-122">For example, `{Item}`, `{DateTime}`.</span></span>

<span data-ttu-id="791ff-123">Każdy komunikat dziennika jest <xref:System.Action> przechowywany w polu statycznym utworzonym przez [LoggerMessage. define](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A).</span><span class="sxs-lookup"><span data-stu-id="791ff-123">Each log message is an <xref:System.Action> held in a static field created by [LoggerMessage.Define](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A).</span></span> <span data-ttu-id="791ff-124">Przykładowo Przykładowa aplikacja tworzy pole opisujące komunikat dziennika do przetwarzania elementów roboczych:</span><span class="sxs-lookup"><span data-stu-id="791ff-124">For example, the sample app creates a field to describe a log message for the processing of work items:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkField":::

<span data-ttu-id="791ff-125">Dla <xref:System.Action> , określ:</span><span class="sxs-lookup"><span data-stu-id="791ff-125">For the <xref:System.Action>, specify:</span></span>

- <span data-ttu-id="791ff-126">Poziom dziennika.</span><span class="sxs-lookup"><span data-stu-id="791ff-126">The log level.</span></span>
- <span data-ttu-id="791ff-127">Unikatowy identyfikator zdarzenia ( <xref:Microsoft.Extensions.Logging.EventId> ) z nazwą statycznej metody rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="791ff-127">A unique event identifier (<xref:Microsoft.Extensions.Logging.EventId>) with the name of the static extension method.</span></span>
- <span data-ttu-id="791ff-128">Szablon wiadomości (nazwany ciąg formatu).</span><span class="sxs-lookup"><span data-stu-id="791ff-128">The message template (named format string).</span></span>

<span data-ttu-id="791ff-129">Ponieważ elementy robocze są dekolejkowane do przetwarzania aplikacji usługi procesu roboczego, ustawia:</span><span class="sxs-lookup"><span data-stu-id="791ff-129">As work items are dequeued for processing the worker service app sets the:</span></span>

- <span data-ttu-id="791ff-130">Poziom rejestrowania do `Critical` .</span><span class="sxs-lookup"><span data-stu-id="791ff-130">Log level to `Critical`.</span></span>
- <span data-ttu-id="791ff-131">Identyfikator zdarzenia do `13` nazwy `FailedToProcessWorkItem` metody.</span><span class="sxs-lookup"><span data-stu-id="791ff-131">Event id to `13` with the name of the `FailedToProcessWorkItem` method.</span></span>
- <span data-ttu-id="791ff-132">Szablon wiadomości (nazwany ciąg formatu) do ciągu.</span><span class="sxs-lookup"><span data-stu-id="791ff-132">Message template (named format string) to a string.</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkAssignment":::

<span data-ttu-id="791ff-133">Magazyny rejestrowania strukturalnego mogą używać nazwy zdarzenia, gdy jest ona dostarczana z identyfikatorem zdarzenia w celu wzbogacania rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="791ff-133">Structured logging stores may use the event name when it's supplied with the event id to enrich logging.</span></span> <span data-ttu-id="791ff-134">Na przykład [Serilog](https://github.com/serilog/serilog-extensions-logging) używa nazwy zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="791ff-134">For example, [Serilog](https://github.com/serilog/serilog-extensions-logging) uses the event name.</span></span>

<span data-ttu-id="791ff-135"><xref:System.Action>Jest wywoływany za pomocą metody rozszerzającej o jednoznacznie określonym typie.</span><span class="sxs-lookup"><span data-stu-id="791ff-135">The <xref:System.Action> is invoked through a strongly-typed extension method.</span></span> <span data-ttu-id="791ff-136">`FailedToProcessWorkItem`Metoda rejestruje komunikat za każdym razem, gdy element roboczy jest przetwarzany:</span><span class="sxs-lookup"><span data-stu-id="791ff-136">The `FailedToProcessWorkItem` method logs a message every time a work item is being processed:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkMethod":::

<span data-ttu-id="791ff-137">`FailedToProcessWorkItem` jest wywoływana dla rejestratora w `ExecuteAsync` metodzie *Worker.cs* w przypadku wystąpienia błędu:</span><span class="sxs-lookup"><span data-stu-id="791ff-137">`FailedToProcessWorkItem` is called on the logger in the `ExecuteAsync` method in *Worker.cs* when an error occurs:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="15-18":::

<span data-ttu-id="791ff-138">Sprawdź dane wyjściowe konsoli aplikacji:</span><span class="sxs-lookup"><span data-stu-id="791ff-138">Inspect the app's console output:</span></span>

```console
crit: WorkerServiceOptions.Example.Worker[13]
      Epic failure processing item!
      System.Exception: Failed to verify communications.
         at WorkerServiceOptions.Example.Worker.ExecuteAsync(CancellationToken stoppingToken) in
         ..\Worker.cs:line 27
```

<span data-ttu-id="791ff-139">Aby przekazać parametry do komunikatu dziennika, zdefiniuj maksymalnie sześć typów podczas tworzenia pola statycznego.</span><span class="sxs-lookup"><span data-stu-id="791ff-139">To pass parameters to a log message, define up to six types when creating the static field.</span></span> <span data-ttu-id="791ff-140">Przykładowa aplikacja rejestruje szczegóły elementu pracy podczas przetwarzania elementów przez zdefiniowanie `WorkItem` typu dla <xref:System.Action> pola:</span><span class="sxs-lookup"><span data-stu-id="791ff-140">The sample app logs the work item details when processing items by defining a `WorkItem` type for the <xref:System.Action> field:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemField":::

<span data-ttu-id="791ff-141">Szablon komunikatu dziennika delegata otrzymuje wartości zastępcze z dostarczonych typów.</span><span class="sxs-lookup"><span data-stu-id="791ff-141">The delegate's log message template receives its placeholder values from the types provided.</span></span> <span data-ttu-id="791ff-142">Przykładowa aplikacja definiuje delegata do dodawania oferty, w której parametr Quote jest `WorkItem` :</span><span class="sxs-lookup"><span data-stu-id="791ff-142">The sample app defines a delegate for adding a quote where the quote parameter is a `WorkItem`:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemAssignment":::

<span data-ttu-id="791ff-143">Statyczna metoda rozszerzenia do rejestrowania, że element roboczy jest przetwarzany, `PriorityItemProcessed` odbiera wartość argumentu elementu pracy i przekazuje ją do <xref:System.Action> delegata:</span><span class="sxs-lookup"><span data-stu-id="791ff-143">The static extension method for logging that a work item is being processed, `PriorityItemProcessed`, receives the work item argument value and passes it to the <xref:System.Action> delegate:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemMethod":::

<span data-ttu-id="791ff-144">W metodzie usługi procesu roboczego `ExecuteAsync` `PriorityItemProcessed` jest wywoływana w celu zarejestrowania komunikatu:</span><span class="sxs-lookup"><span data-stu-id="791ff-144">In the worker service's `ExecuteAsync` method, `PriorityItemProcessed` is called to log the message:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="12":::

<span data-ttu-id="791ff-145">Sprawdź dane wyjściowe konsoli aplikacji:</span><span class="sxs-lookup"><span data-stu-id="791ff-145">Inspect the app's console output:</span></span>

```console
info: WorkerServiceOptions.Example.Worker[1]
      Processing priority item: Priority-Extreme (50db062a-9732-4418-936d-110549ad79e4): 'Verify communications'
```

## <a name="define-logger-message-scope"></a><span data-ttu-id="791ff-146">Zdefiniuj zakres komunikatów rejestratora</span><span class="sxs-lookup"><span data-stu-id="791ff-146">Define logger message scope</span></span>

<span data-ttu-id="791ff-147">Metoda [DefineScope — (String)](xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A) tworzy <xref:System.Func%601> delegat do definiowania [zakresu dziennika](logging.md#log-scopes).</span><span class="sxs-lookup"><span data-stu-id="791ff-147">The [DefineScope(string)](xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A) method creates a <xref:System.Func%601> delegate for defining a [log scope](logging.md#log-scopes).</span></span> <span data-ttu-id="791ff-148"><xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> przeciążenia dopuszczają przekazywanie do trzech parametrów typu do nazwanego ciągu formatu (szablonu).</span><span class="sxs-lookup"><span data-stu-id="791ff-148"><xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> overloads permit passing up to three type parameters to a named format string (template).</span></span>

<span data-ttu-id="791ff-149">Podobnie jak w przypadku <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> metody, ciąg dostarczony do <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> metody jest szablonem, a nie ciągiem interpolowanym.</span><span class="sxs-lookup"><span data-stu-id="791ff-149">As is the case with the <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> method, the string provided to the <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> method is a template and not an interpolated string.</span></span> <span data-ttu-id="791ff-150">Symbole zastępcze są wypełniane w kolejności, w jakiej są określone typy.</span><span class="sxs-lookup"><span data-stu-id="791ff-150">Placeholders are filled in the order that the types are specified.</span></span> <span data-ttu-id="791ff-151">Nazwy symboli zastępczych w szablonie powinny być opisowe i spójne w szablonach.</span><span class="sxs-lookup"><span data-stu-id="791ff-151">Placeholder names in the template should be descriptive and consistent across templates.</span></span> <span data-ttu-id="791ff-152">Służą one jako nazwy właściwości w danych dziennika strukturalnego.</span><span class="sxs-lookup"><span data-stu-id="791ff-152">They serve as property names within structured log data.</span></span> <span data-ttu-id="791ff-153">Zalecamy używanie [wielkości liter](/dotnet/standard/design-guidelines/capitalization-conventions) w języku Pascal dla nazw zastępczych.</span><span class="sxs-lookup"><span data-stu-id="791ff-153">We recommend [Pascal casing](/dotnet/standard/design-guidelines/capitalization-conventions) for placeholder names.</span></span> <span data-ttu-id="791ff-154">Na przykład `{Item}` , `{DateTime}` .</span><span class="sxs-lookup"><span data-stu-id="791ff-154">For example, `{Item}`, `{DateTime}`.</span></span>

<span data-ttu-id="791ff-155">Zdefiniuj [zakres dziennika](logging.md#log-scopes) , który ma zostać zastosowany do serii komunikatów dziennika przy użyciu <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="791ff-155">Define a [log scope](logging.md#log-scopes) to apply to a series of log messages using the <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> method.</span></span>

<span data-ttu-id="791ff-156">Przykładowa aplikacja ma przycisk **Wyczyść wszystko** , aby usunąć wszystkie cudzysłowy w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="791ff-156">The sample app has a **Clear All** button for deleting all of the quotes in the database.</span></span> <span data-ttu-id="791ff-157">Cudzysłowy są usuwane, usuwając je pojedynczo.</span><span class="sxs-lookup"><span data-stu-id="791ff-157">The quotes are deleted by removing them one at a time.</span></span> <span data-ttu-id="791ff-158">Przy każdym usunięciu oferty `QuoteDeleted` Metoda jest wywoływana w rejestratorze.</span><span class="sxs-lookup"><span data-stu-id="791ff-158">Each time a quote is deleted, the `QuoteDeleted` method is called on the logger.</span></span> <span data-ttu-id="791ff-159">Do tych komunikatów dziennika jest dodawany zakres dziennika.</span><span class="sxs-lookup"><span data-stu-id="791ff-159">A log scope is added to these log messages.</span></span>

<span data-ttu-id="791ff-160">Włącz `IncludeScopes` w sekcji rejestratora konsoli *appsettings.jsna*:</span><span class="sxs-lookup"><span data-stu-id="791ff-160">Enable `IncludeScopes` in the console logger section of *appsettings.json*:</span></span>

:::code language="json" source="snippets/configuration/worker-service-options/appsettings.json" highlight="3-5":::

<span data-ttu-id="791ff-161">Aby utworzyć zakres dziennika, należy dodać pole do przechowywania <xref:System.Func%601> delegata dla zakresu.</span><span class="sxs-lookup"><span data-stu-id="791ff-161">To create a log scope, add a field to hold a <xref:System.Func%601> delegate for the scope.</span></span> <span data-ttu-id="791ff-162">Przykładowa aplikacja tworzy pole o nazwie `_allQuotesDeletedScope` (*wewnętrzne/LoggerExtensions. cs*):</span><span class="sxs-lookup"><span data-stu-id="791ff-162">The sample app creates a field called `_allQuotesDeletedScope` (*Internal/LoggerExtensions.cs*):</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkField":::

<span data-ttu-id="791ff-163">Użyj, <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> Aby utworzyć delegata.</span><span class="sxs-lookup"><span data-stu-id="791ff-163">Use <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> to create the delegate.</span></span> <span data-ttu-id="791ff-164">Można określić maksymalnie trzy typy do użycia jako argumenty szablonu, gdy obiekt delegowany jest wywoływany.</span><span class="sxs-lookup"><span data-stu-id="791ff-164">Up to three types can be specified for use as template arguments when the delegate is invoked.</span></span> <span data-ttu-id="791ff-165">Przykładowa aplikacja używa szablonu komunikatu zawierającego liczbę usuniętych cudzysłowów ( `int` Typ):</span><span class="sxs-lookup"><span data-stu-id="791ff-165">The sample app uses a message template that includes the number of deleted quotes (an `int` type):</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkAssignment":::

<span data-ttu-id="791ff-166">Podaj statyczną metodę rozszerzenia dla komunikatu dziennika.</span><span class="sxs-lookup"><span data-stu-id="791ff-166">Provide a static extension method for the log message.</span></span> <span data-ttu-id="791ff-167">Dołącz wszystkie parametry typu dla nazwanych właściwości, które są wyświetlane w szablonie wiadomości.</span><span class="sxs-lookup"><span data-stu-id="791ff-167">Include any type parameters for named properties that appear in the message template.</span></span> <span data-ttu-id="791ff-168">Przykładowa aplikacja zajmuje się `DateTime` przez niestandardową sygnaturę czasową, aby rejestrować i zwracać `_processingWorkScope` :</span><span class="sxs-lookup"><span data-stu-id="791ff-168">The sample app takes in a `DateTime` for a custom time stamp to log and returns `_processingWorkScope`:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkMethod":::

<span data-ttu-id="791ff-169">Zakres zawija wywołania rozszerzenia rejestrowania w bloku [using](../../csharp/language-reference/keywords/using-statement.md) :</span><span class="sxs-lookup"><span data-stu-id="791ff-169">The scope wraps the logging extension calls in a [using](../../csharp/language-reference/keywords/using-statement.md) block:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="4":::

<span data-ttu-id="791ff-170">Sprawdź komunikaty dziennika w danych wyjściowych konsoli aplikacji.</span><span class="sxs-lookup"><span data-stu-id="791ff-170">Inspect the log messages in the app's console output.</span></span> <span data-ttu-id="791ff-171">Poniższy wynik pokazuje trzy cudzysłowy usunięte z uwzględnieniem komunikatu o zakresie dziennika:</span><span class="sxs-lookup"><span data-stu-id="791ff-171">The following result shows three quotes deleted with the log scope message included:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="791ff-172">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="791ff-172">See also</span></span>

- [<span data-ttu-id="791ff-173">Rejestrowanie w programie .NET</span><span class="sxs-lookup"><span data-stu-id="791ff-173">Logging in .NET</span></span>](logging.md)
