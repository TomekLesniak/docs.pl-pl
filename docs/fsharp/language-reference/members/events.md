---
title: Zdarzenia
description: 'Dowiedz się, jak zdarzenia języka F # umożliwiają kojarzenie wywołań funkcji z akcjami użytkownika, które są ważne w programowaniu graficznego interfejsu użytkownika.'
ms.date: 05/16/2016
ms.openlocfilehash: 682686ba58d0f7a56e7da2585e6507ccd0156a44
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854935"
---
# <a name="events"></a><span data-ttu-id="a6322-103">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="a6322-103">Events</span></span>

<span data-ttu-id="a6322-104">Zdarzenia umożliwiają kojarzenie wywołań funkcji z akcjami użytkownika i są ważne w programowaniu graficznych interfejsów użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a6322-104">Events enable you to associate function calls with user actions and are important in GUI programming.</span></span> <span data-ttu-id="a6322-105">Zdarzenia mogą być też wywoływane przez aplikacje lub system operacyjny.</span><span class="sxs-lookup"><span data-stu-id="a6322-105">Events can also be triggered by your applications or by the operating system.</span></span>

> [!NOTE]
> <span data-ttu-id="a6322-106">Dokumentacja interfejsu API docs.microsoft.com dla języka F # nie została ukończona.</span><span class="sxs-lookup"><span data-stu-id="a6322-106">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="a6322-107">Jeśli wystąpią jakieś przerwane linki, należy odwołać się do [dokumentacji podstawowej biblioteki języka F #](https://fsharp.github.io/fsharp-core-docs/) .</span><span class="sxs-lookup"><span data-stu-id="a6322-107">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

## <a name="handling-events"></a><span data-ttu-id="a6322-108">Obsługa zdarzeń</span><span class="sxs-lookup"><span data-stu-id="a6322-108">Handling Events</span></span>

<span data-ttu-id="a6322-109">Gdy jest używana biblioteka graficznych interfejsów użytkownika, taka jak Windows Forms lub Windows Presentation Foundation (WPF), większość kodu aplikacji działa w odpowiedzi na zdarzenia, które są wstępnie zdefiniowane w tej bibliotece.</span><span class="sxs-lookup"><span data-stu-id="a6322-109">When you use a GUI library like Windows Forms or Windows Presentation Foundation (WPF), much of the code in your application runs in response to events that are predefined by the library.</span></span> <span data-ttu-id="a6322-110">Te wstępnie zdefiniowane zdarzenia są składowymi klas graficznego interfejsu użytkownika, takich jak formularze i formanty.</span><span class="sxs-lookup"><span data-stu-id="a6322-110">These predefined events are members of GUI classes such as forms and controls.</span></span> <span data-ttu-id="a6322-111">Niestandardowe zachowanie można dodać do istniejącego zdarzenia, takiego jak kliknięcie przycisku, odwołując się do konkretnej nazwanego zdarzenia zainteresowania (na przykład `Click` zdarzenia `Form` klasy) i wywołując `Add` metodę, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="a6322-111">You can add custom behavior to a preexisting event, such as a button click, by referencing the specific named event of interest (for example, the `Click` event of the `Form` class) and invoking the `Add` method, as shown in the following code.</span></span> <span data-ttu-id="a6322-112">Jeśli uruchomisz ten program z F# Interactive, Pomiń wywołanie metody `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)` .</span><span class="sxs-lookup"><span data-stu-id="a6322-112">If you run this from F# Interactive, omit the call to `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

<span data-ttu-id="a6322-113">Typ `Add` metody to `('a -> unit) -> unit` .</span><span class="sxs-lookup"><span data-stu-id="a6322-113">The type of the `Add` method is `('a -> unit) -> unit`.</span></span> <span data-ttu-id="a6322-114">W związku z tym metoda obsługi zdarzeń przyjmuje jeden parametr, zazwyczaj argumenty zdarzenia i zwraca `unit` .</span><span class="sxs-lookup"><span data-stu-id="a6322-114">Therefore, the event handler method takes one parameter, typically the event arguments, and returns `unit`.</span></span> <span data-ttu-id="a6322-115">W poprzednim przykładzie pokazano program obsługi zdarzeń w postaci wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="a6322-115">The previous example shows the event handler as a lambda expression.</span></span> <span data-ttu-id="a6322-116">Program obsługi zdarzeń może być także wartością funkcji, tak jak w poniższym przykładzie kodu.</span><span class="sxs-lookup"><span data-stu-id="a6322-116">The event handler can also be a function value, as in the following code example.</span></span> <span data-ttu-id="a6322-117">W poniższym przykładzie kodu pokazano także użycie parametrów programu obsługi zdarzeń, które dostarczają informacje charakterystyczne dla typu zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="a6322-117">The following code example also shows the use of the event handler parameters, which provide information specific to the type of event.</span></span> <span data-ttu-id="a6322-118">Dla `MouseMove` zdarzenia system przekazuje `System.Windows.Forms.MouseEventArgs` obiekt, który zawiera `X` `Y` położenie wskaźnika i.</span><span class="sxs-lookup"><span data-stu-id="a6322-118">For a `MouseMove` event, the system passes a `System.Windows.Forms.MouseEventArgs` object, which contains the `X` and `Y` position of the pointer.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]

## <a name="creating-custom-events"></a><span data-ttu-id="a6322-119">Tworzenie zdarzeń niestandardowych</span><span class="sxs-lookup"><span data-stu-id="a6322-119">Creating Custom Events</span></span>

<span data-ttu-id="a6322-120">Zdarzenia języka f # są reprezentowane przez klasę [zdarzeń](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) f #, która implementuje interfejs [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) .</span><span class="sxs-lookup"><span data-stu-id="a6322-120">F# events are represented by the F# [Event](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) class, which implements the [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) interface.</span></span> <span data-ttu-id="a6322-121">`IEvent`jest samym interfejsem, który łączy funkcje dwóch innych interfejsów `System.IObservable<'T>` i [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a).</span><span class="sxs-lookup"><span data-stu-id="a6322-121">`IEvent` is itself an interface that combines the functionality of two other interfaces, `System.IObservable<'T>` and [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a).</span></span> <span data-ttu-id="a6322-122">W związku z tym program `Event` s ma równoważne funkcje delegatów w innych językach oraz dodatkowe funkcje od `IObservable` , co oznacza, że zdarzenia języka f # obsługują filtrowanie zdarzeń oraz funkcje pierwszej klasy języka f # i wyrażenia lambda jako programy obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="a6322-122">Therefore, `Event`s have the equivalent functionality of delegates in other languages, plus the additional functionality from `IObservable`, which means that F# events support event filtering and using F# first-class functions and lambda expressions as event handlers.</span></span> <span data-ttu-id="a6322-123">Ta funkcja jest dostępna w [module Event](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).</span><span class="sxs-lookup"><span data-stu-id="a6322-123">This functionality is provided in the [Event module](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).</span></span>

<span data-ttu-id="a6322-124">Aby utworzyć zdarzenie na klasie, która działa podobnie jak wszystkie inne zdarzenia .NET Framework, Dodaj do klasy `let` powiązanie, które definiuje `Event` jako pole w klasie.</span><span class="sxs-lookup"><span data-stu-id="a6322-124">To create an event on a class that acts just like any other .NET Framework event, add to the class a `let` binding that defines an `Event` as a field in a class.</span></span> <span data-ttu-id="a6322-125">Odpowiedni typ argumentu zdarzenia można określić jako argument typu, ale można też pozostawić ten typu pusty, co spowoduje, że kompilator wywnioskuje odpowiedni typ.</span><span class="sxs-lookup"><span data-stu-id="a6322-125">You can specify the desired event argument type as the type argument, or leave it blank and have the compiler infer the appropriate type.</span></span> <span data-ttu-id="a6322-126">Należy także zdefiniować element członkowski zdarzenia, który będzie uwidaczniał zdarzenie jako zdarzenie CLI.</span><span class="sxs-lookup"><span data-stu-id="a6322-126">You also must define an event member that exposes the event as a CLI event.</span></span> <span data-ttu-id="a6322-127">Ten element członkowski powinien mieć atrybut [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) .</span><span class="sxs-lookup"><span data-stu-id="a6322-127">This member should have the [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) attribute.</span></span> <span data-ttu-id="a6322-128">Jest on zadeklarowany jako właściwość, a jego implementacja jest tylko wywołaniem właściwości [Publish](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="a6322-128">It is declared like a property and its implementation is just a call to the [Publish](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) property of the event.</span></span> <span data-ttu-id="a6322-129">Użytkownicy klasy mogą korzystać z `Add` metody opublikowanego zdarzenia w celu dodania procedury obsługi.</span><span class="sxs-lookup"><span data-stu-id="a6322-129">Users of your class can use the `Add` method of the published event to add a handler.</span></span> <span data-ttu-id="a6322-130">Argument `Add` metody może być wyrażeniem lambda.</span><span class="sxs-lookup"><span data-stu-id="a6322-130">The argument for the `Add` method can be a lambda expression.</span></span> <span data-ttu-id="a6322-131">Możesz użyć `Trigger` właściwości zdarzenia, aby zgłosić zdarzenie, przekazując argumenty do funkcji obsługi.</span><span class="sxs-lookup"><span data-stu-id="a6322-131">You can use the `Trigger` property of the event to raise the event, passing the arguments to the handler function.</span></span> <span data-ttu-id="a6322-132">Pokazano to w poniższym przykładzie kodu.</span><span class="sxs-lookup"><span data-stu-id="a6322-132">The following code example illustrates this.</span></span> <span data-ttu-id="a6322-133">W tym przykładzie wywnioskowany argument typu dla zdarzenia to spójna kolekcja, która reprezentuje argumenty wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="a6322-133">In this example, the inferred type argument for the event is a tuple, which represents the arguments for the lambda expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

<span data-ttu-id="a6322-134">Dane wyjściowe są następujące:</span><span class="sxs-lookup"><span data-stu-id="a6322-134">The output is as follows.</span></span>

```console
Event1 occurred! Object data: Hello World!
```

<span data-ttu-id="a6322-135">Dodatkowe funkcje zapewniane przez moduł przedstawiono w `Event` tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="a6322-135">The additional functionality provided by the `Event` module is illustrated here.</span></span> <span data-ttu-id="a6322-136">Poniższy przykład kodu ilustruje podstawowe użycie programu `Event.create` , aby utworzyć zdarzenie i metodę wyzwalacza, dodać dwa programy obsługi zdarzeń w postaci wyrażeń lambda, a następnie wyzwoli zdarzenie, aby wykonać oba wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="a6322-136">The following code example illustrates the basic use of `Event.create` to create an event and a trigger method, add two event handlers in the form of lambda expressions, and then trigger the event to execute both lambda expressions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

<span data-ttu-id="a6322-137">Dane wyjściowe poprzedniego kodu wyglądają następująco:</span><span class="sxs-lookup"><span data-stu-id="a6322-137">The output of the previous code is as follows.</span></span>

```console
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a><span data-ttu-id="a6322-138">Przetwarzanie strumieni zdarzeń</span><span class="sxs-lookup"><span data-stu-id="a6322-138">Processing Event Streams</span></span>

<span data-ttu-id="a6322-139">Zamiast tylko dodać procedurę obsługi zdarzeń dla zdarzenia przy użyciu funkcji [Event. Add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) , można użyć funkcji w `Event` module do przetwarzania strumieni zdarzeń w sposób wysoce dostosowany.</span><span class="sxs-lookup"><span data-stu-id="a6322-139">Instead of just adding an event handler for an event by using the [Event.add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) function, you can use the functions in the `Event` module to process streams of events in highly customized ways.</span></span> <span data-ttu-id="a6322-140">W tym celu należy użyć potoku do przodu ( `|>` ) wraz ze zdarzeniem jako pierwszą wartością w szeregu wywołań funkcji, a `Event` moduł działa jako kolejne wywołania funkcji.</span><span class="sxs-lookup"><span data-stu-id="a6322-140">To do this, you use the forward pipe (`|>`) together with the event as the first value in a series of function calls, and the `Event` module functions as subsequent function calls.</span></span>

<span data-ttu-id="a6322-141">W poniższym przykładzie kodu pokazano, jak skonfigurować zdarzenie, dla którego program obsługi jest wywoływany tylko w określonych warunkach.</span><span class="sxs-lookup"><span data-stu-id="a6322-141">The following code example shows how to set up an event for which the handler is only called under certain conditions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

<span data-ttu-id="a6322-142">[Moduł zauważalny](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) zawiera podobne funkcje, które działają na obiektach zauważalnych.</span><span class="sxs-lookup"><span data-stu-id="a6322-142">The [Observable module](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) contains similar functions that operate on observable objects.</span></span> <span data-ttu-id="a6322-143">Widoczne obiekty są podobne do zdarzeń, ale aktywnie subskrybują zdarzenia tylko wtedy, gdy same są subskrybowane.</span><span class="sxs-lookup"><span data-stu-id="a6322-143">Observable objects are similar to events but only actively subscribe to events if they themselves are being subscribed to.</span></span>

## <a name="implementing-an-interface-event"></a><span data-ttu-id="a6322-144">Implementowanie zdarzenia interfejsu</span><span class="sxs-lookup"><span data-stu-id="a6322-144">Implementing an Interface Event</span></span>

<span data-ttu-id="a6322-145">Projektowanie składników interfejsu użytkownika często rozpoczyna się od utworzenia nowego formularza lub nowego formantu, który dziedziczy z istniejącego formularza lub formantu.</span><span class="sxs-lookup"><span data-stu-id="a6322-145">As you develop UI components, you often start by creating a new form or a new control that inherits from an existing form or control.</span></span> <span data-ttu-id="a6322-146">Zdarzenia są często definiowane w interfejsie, a w takim przypadku trzeba zaimplementować interfejs służący do implementacji zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="a6322-146">Events are frequently defined on an interface, and, in that case, you must implement the interface to implement the event.</span></span> <span data-ttu-id="a6322-147">`System.ComponentModel.INotifyPropertyChanged`Interfejs definiuje pojedyncze `System.ComponentModel.INotifyPropertyChanged.PropertyChanged` zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="a6322-147">The `System.ComponentModel.INotifyPropertyChanged` interface defines a single `System.ComponentModel.INotifyPropertyChanged.PropertyChanged` event.</span></span> <span data-ttu-id="a6322-148">Poniższy kod ilustruje sposób implementacji zdarzenia definiowanego przez ten dziedziczony interfejs:</span><span class="sxs-lookup"><span data-stu-id="a6322-148">The following code illustrates how to implement the event that this inherited interface defined:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

type AppForm() as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
            this.Property2 <- "text3")

    // This property does not have the property-changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property-changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    // Expose the PropertyChanged event as a first class .NET event.
    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = propertyChanged.Publish.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = propertyChanged.Publish.RemoveHandler(handler)

    // This is the event-handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
let inpc = appForm :> INotifyPropertyChanged
inpc.PropertyChanged.Add(appForm.OnPropertyChanged)
Application.Run(appForm)
```

<span data-ttu-id="a6322-149">Jeśli chcesz podłączyć zdarzenie w konstruktorze, kod jest nieco bardziej skomplikowany, ponieważ usługa Event podłączenie musi znajdować się w `then` bloku w dodatkowym konstruktorze, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a6322-149">If you want to hook up the event in the constructor, the code is a bit more complicated because the event hookup must be in a `then` block in an additional constructor, as in the following example:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

// Create a private constructor with a dummy argument so that the public
// constructor can have no arguments.
type AppForm private (dummy) as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
            this.Property2 <- "text3")

    // This property does not have the property changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = this.PropertyChanged.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = this.PropertyChanged.RemoveHandler(handler)

    // This is the event handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

    new() as this =
        new AppForm(0)
        then
            let inpc = this :> INotifyPropertyChanged
            inpc.PropertyChanged.Add(this.OnPropertyChanged)

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
Application.Run(appForm)
```

## <a name="see-also"></a><span data-ttu-id="a6322-150">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a6322-150">See also</span></span>

- [<span data-ttu-id="a6322-151">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="a6322-151">Members</span></span>](index.md)
- [<span data-ttu-id="a6322-152">Obsługa i wywoływanie zdarzeń</span><span class="sxs-lookup"><span data-stu-id="a6322-152">Handling and Raising Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="a6322-153">Wyrażenia lambda: `fun` słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="a6322-153">Lambda Expressions: The `fun` Keyword</span></span>](../functions/lambda-expressions-the-fun-keyword.md)
- [<span data-ttu-id="a6322-154">Control. Event — Moduł</span><span class="sxs-lookup"><span data-stu-id="a6322-154">Control.Event Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event-module-%5bfsharp%5d)
- [<span data-ttu-id="a6322-155">Control. Event —&#60;&#62; Klasa</span><span class="sxs-lookup"><span data-stu-id="a6322-155">Control.Event&#60;'T&#62; Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27t%5d-class-%5bfsharp%5d)
- [<span data-ttu-id="a6322-156">Control. Event&#60; "delegat," args&#62; Class</span><span class="sxs-lookup"><span data-stu-id="a6322-156">Control.Event&#60;'Delegate,'Args&#62; Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27delegate%2c%27args%5d-class-%5bfsharp%5d)
