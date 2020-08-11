---
title: Jak subskrybować i anulować subskrypcję zdarzeń — Przewodnik programowania w języku C#
description: Dowiedz się, jak subskrybować i anulować subskrypcję zdarzeń. Subskrybuj zdarzenia za pomocą środowiska IDE programu Visual Studio, programowo lub za pomocą metody anonimowej.
ms.date: 07/20/2015
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
ms.openlocfilehash: 4aecbbd58268e7b50a34f503160edd1eca4fe659
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063628"
---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a><span data-ttu-id="0a9b9-104">Subskrybowanie i anulowanie subskrypcji zdarzeń (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="0a9b9-104">How to subscribe to and unsubscribe from events (C# Programming Guide)</span></span>
<span data-ttu-id="0a9b9-105">Zasubskrybujesz zdarzenie, które jest publikowane przez inną klasę, gdy chcesz napisać niestandardowy kod, który jest wywoływany, gdy zdarzenie jest zgłaszane.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-105">You subscribe to an event that is published by another class when you want to write custom code that is called when that event is raised.</span></span> <span data-ttu-id="0a9b9-106">Na przykład można subskrybować zdarzenie przycisku, `click` Aby aplikacja była przydatna, gdy użytkownik kliknie przycisk.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-106">For example, you might subscribe to a button's `click` event in order to make your application do something useful when the user clicks the button.</span></span>  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a><span data-ttu-id="0a9b9-107">Aby subskrybować zdarzenia za pomocą środowiska IDE programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0a9b9-107">To subscribe to events by using the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="0a9b9-108">Jeśli nie widzisz okna **Właściwości** , w widoku **projektu** kliknij prawym przyciskiem myszy formularz lub kontrolkę, dla której chcesz utworzyć procedurę obsługi zdarzeń, a następnie wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-108">If you cannot see the **Properties** window, in **Design** view, right-click the form or control for which you want to create an event handler, and select **Properties**.</span></span>  
  
2. <span data-ttu-id="0a9b9-109">W górnej części okna **Właściwości** kliknij ikonę **zdarzenia** .</span><span class="sxs-lookup"><span data-stu-id="0a9b9-109">On top of the **Properties** window, click the **Events** icon.</span></span>  
  
3. <span data-ttu-id="0a9b9-110">Kliknij dwukrotnie zdarzenie, które chcesz utworzyć, na przykład `Load` zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-110">Double-click the event that you want to create, for example the `Load` event.</span></span>  
  
     <span data-ttu-id="0a9b9-111">Visual C# tworzy pustą metodę obsługi zdarzeń i dodaje ją do kodu.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-111">Visual C# creates an empty event handler method and adds it to your code.</span></span> <span data-ttu-id="0a9b9-112">Alternatywnie możesz dodać kod ręcznie w widoku **kodu** .</span><span class="sxs-lookup"><span data-stu-id="0a9b9-112">Alternatively you can add the code manually in **Code** view.</span></span> <span data-ttu-id="0a9b9-113">Na przykład następujące wiersze kodu deklarują metodę procedury obsługi zdarzeń, która zostanie wywołana, gdy `Form` Klasa zgłasza `Load` zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-113">For example, the following lines of code declare an event handler method that will be called when the `Form` class raises the `Load` event.</span></span>  
  
     [!code-csharp[csProgGuideEvents#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#11)]  
  
     <span data-ttu-id="0a9b9-114">Wiersz kodu, który jest wymagany do subskrybowania zdarzenia, jest również generowany automatycznie w `InitializeComponent` metodzie w pliku Form1.Designer.cs w projekcie.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-114">The line of code that is required to subscribe to the event is also automatically generated in the `InitializeComponent` method in the Form1.Designer.cs file in your project.</span></span> <span data-ttu-id="0a9b9-115">Przypomina to:</span><span class="sxs-lookup"><span data-stu-id="0a9b9-115">It resembles this:</span></span>  
  
    ```csharp
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a><span data-ttu-id="0a9b9-116">Aby programowo subskrybować zdarzenia</span><span class="sxs-lookup"><span data-stu-id="0a9b9-116">To subscribe to events programmatically</span></span>  
  
1. <span data-ttu-id="0a9b9-117">Zdefiniuj metodę procedury obsługi zdarzeń, której sygnatura pasuje do sygnatury delegata zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-117">Define an event handler method whose signature matches the delegate signature for the event.</span></span> <span data-ttu-id="0a9b9-118">Na przykład, jeśli zdarzenie jest oparte na <xref:System.EventHandler> typie delegata, poniższy kod reprezentuje element zastępczy metody:</span><span class="sxs-lookup"><span data-stu-id="0a9b9-118">For example, if the event is based on the <xref:System.EventHandler> delegate type, the following code represents the method stub:</span></span>  
  
    ```csharp
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2. <span data-ttu-id="0a9b9-119">Użyj operatora przypisania dodawania ( `+=` ), aby dołączyć procedurę obsługi zdarzeń do zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-119">Use the addition assignment operator (`+=`) to attach an event handler to the event.</span></span> <span data-ttu-id="0a9b9-120">W poniższym przykładzie Załóżmy, że obiekt o nazwie `publisher` ma zdarzenie o nazwie `RaiseCustomEvent` .</span><span class="sxs-lookup"><span data-stu-id="0a9b9-120">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent`.</span></span> <span data-ttu-id="0a9b9-121">Należy zauważyć, że Klasa subskrybenta wymaga odwołania do klasy wydawcy w celu subskrybowania jego zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-121">Note that the subscriber class needs a reference to the publisher class in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="0a9b9-122">Należy zauważyć, że poprzednia składnia jest nowa w języku C# 2,0.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-122">Note that the previous syntax is new in C# 2.0.</span></span> <span data-ttu-id="0a9b9-123">Jest to dokładnie równoważne składni języka C# 1,0, w której delegata hermetyzowania musi być jawnie utworzona przy użyciu `new` słowa kluczowego:</span><span class="sxs-lookup"><span data-stu-id="0a9b9-123">It is exactly equivalent to the C# 1.0 syntax in which the encapsulating delegate must be explicitly created by using the `new` keyword:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     <span data-ttu-id="0a9b9-124">Można również użyć [wyrażenia lambda](../../language-reference/operators/lambda-expressions.md) do określenia programu obsługi zdarzeń:</span><span class="sxs-lookup"><span data-stu-id="0a9b9-124">You can also use a [lambda expression](../../language-reference/operators/lambda-expressions.md) to specify an event handler:</span></span>
  
    ```csharp
    public Form1()  
    {  
        InitializeComponent();  
        this.Click += (s,e) =>
            {
                MessageBox.Show(((MouseEventArgs)e).Location.ToString());
            };
    }  
    ```  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a><span data-ttu-id="0a9b9-125">Aby subskrybować zdarzenia za pomocą metody anonimowej</span><span class="sxs-lookup"><span data-stu-id="0a9b9-125">To subscribe to events by using an anonymous method</span></span>  
  
- <span data-ttu-id="0a9b9-126">Jeśli nie musisz anulować subskrybowania zdarzenia później, możesz użyć operatora przypisania dodawania ( `+=` ) w celu dołączenia anonimowej metody do zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-126">If you will not have to unsubscribe to an event later, you can use the addition assignment operator (`+=`) to attach an anonymous method to the event.</span></span> <span data-ttu-id="0a9b9-127">W poniższym przykładzie Załóżmy, że obiekt o nazwie `publisher` ma zdarzenie o nazwie `RaiseCustomEvent` i że `CustomEventArgs` Klasa została również zdefiniowana w taki sposób, aby wykonywała wyspecjalizowane informacje o zdarzeniu.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-127">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent` and that a `CustomEventArgs` class has also been defined to carry some kind of specialized event information.</span></span> <span data-ttu-id="0a9b9-128">Należy zauważyć, że Klasa subskrybenta wymaga odwołania do, aby `publisher` subskrybować jego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-128">Note that the subscriber class needs a reference to `publisher` in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     <span data-ttu-id="0a9b9-129">Należy pamiętać, że nie można łatwo anulować subskrypcji zdarzenia, jeśli użyto anonimowej funkcji do subskrybowania.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-129">It is important to notice that you cannot easily unsubscribe from an event if you used an anonymous function to subscribe to it.</span></span> <span data-ttu-id="0a9b9-130">Aby anulować subskrypcję w tym scenariuszu, należy wrócić do kodu, w którym subskrybujesz zdarzenie, zapisać metodę anonimową w zmiennej delegata, a następnie dodać delegata do zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-130">To unsubscribe in this scenario, it is necessary to go back to the code where you subscribe to the event, store the anonymous method in a delegate variable, and then add the delegate to the event.</span></span> <span data-ttu-id="0a9b9-131">Ogólnie rzecz biorąc, firma Microsoft zaleca, aby nie używać funkcji anonimowych do subskrybowania zdarzeń, jeśli będzie konieczne anulowanie subskrypcji zdarzenia w pewnym momencie w kodzie.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-131">In general, we recommend that you do not use anonymous functions to subscribe to events if you will have to unsubscribe from the event at some later point in your code.</span></span> <span data-ttu-id="0a9b9-132">Aby uzyskać więcej informacji na temat funkcji anonimowych, zobacz [funkcje anonimowe](../statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="0a9b9-132">For more information about anonymous functions, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="unsubscribing"></a><span data-ttu-id="0a9b9-133">Anulowanie subskrypcji</span><span class="sxs-lookup"><span data-stu-id="0a9b9-133">Unsubscribing</span></span>  
 <span data-ttu-id="0a9b9-134">Aby uniemożliwić wywoływanie programu obsługi zdarzeń po podniesieniu zdarzenia, Anuluj subskrypcję zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-134">To prevent your event handler from being invoked when the event is raised, unsubscribe from the event.</span></span> <span data-ttu-id="0a9b9-135">Aby zapobiec przeciekom zasobów, należy anulować subskrypcję zdarzeń przed usunięciem obiektu subskrybenta.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-135">In order to prevent resource leaks, you should unsubscribe from events before you dispose of a subscriber object.</span></span> <span data-ttu-id="0a9b9-136">Dopóki nie subskrybujesz zdarzenia, delegat multiemisji, który opiera się na zdarzeniu w obiekcie do publikowania, ma odwołanie do delegata, który hermetyzuje procedurę obsługi zdarzeń subskrybenta.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-136">Until you unsubscribe from an event, the multicast delegate that underlies the event in the publishing object has a reference to the delegate that encapsulates the subscriber's event handler.</span></span> <span data-ttu-id="0a9b9-137">Tak długo, jak obiekt publikacji przechowuje to odwołanie, wyrzucanie elementów bezużytecznych nie usunie obiektu subskrybenta.</span><span class="sxs-lookup"><span data-stu-id="0a9b9-137">As long as the publishing object holds that reference, garbage collection will not delete your subscriber object.</span></span>  
  
#### <a name="to-unsubscribe-from-an-event"></a><span data-ttu-id="0a9b9-138">Aby anulować subskrypcję zdarzenia</span><span class="sxs-lookup"><span data-stu-id="0a9b9-138">To unsubscribe from an event</span></span>  
  
- <span data-ttu-id="0a9b9-139">Użyj operatora przypisywania odejmowania ( `-=` ), aby anulować subskrypcję zdarzenia:</span><span class="sxs-lookup"><span data-stu-id="0a9b9-139">Use the subtraction assignment operator (`-=`) to unsubscribe from an event:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="0a9b9-140">Gdy Wszyscy subskrybenci nie subskrybują zdarzenia, wystąpienie zdarzenia w klasie wydawcy jest ustawione na `null` .</span><span class="sxs-lookup"><span data-stu-id="0a9b9-140">When all subscribers have unsubscribed from an event, the event instance in the publisher class is set to `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9b9-141">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0a9b9-141">See also</span></span>

- [<span data-ttu-id="0a9b9-142">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="0a9b9-142">Events</span></span>](./index.md)
- [<span data-ttu-id="0a9b9-143">event</span><span class="sxs-lookup"><span data-stu-id="0a9b9-143">event</span></span>](../../language-reference/keywords/event.md)
- [<span data-ttu-id="0a9b9-144">Jak opublikować zdarzenia zgodne z zaleceniami dotyczącymi platformy .NET</span><span class="sxs-lookup"><span data-stu-id="0a9b9-144">How to publish events that conform to .NET Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)
- [<span data-ttu-id="0a9b9-145">Operatory-and-=</span><span class="sxs-lookup"><span data-stu-id="0a9b9-145">- and -= operators</span></span>](../../language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="0a9b9-146">Operatory + i + =</span><span class="sxs-lookup"><span data-stu-id="0a9b9-146">+ and += operators</span></span>](../../language-reference/operators/addition-operator.md)
