---
title: Zdarzenia — Przewodnik programowania w języku C#
description: Dowiedz się więcej o zdarzeniach. Zdarzenia umożliwiają klasie lub obiektowi powiadamianie innych klas lub obiektów w przypadku wystąpienia czegoś zainteresowania.
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 86ded81de4b9191c50b993c08b0e87712ff69020
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545496"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="859ae-104">Zdarzenia (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="859ae-104">Events (C# Programming Guide)</span></span>
<span data-ttu-id="859ae-105">Zdarzenia umożliwiają [klasie](../../language-reference/keywords/class.md) lub obiektowi powiadamianie innych klas lub obiektów w przypadku wystąpienia czegoś zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="859ae-105">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="859ae-106">Klasa, która wysyła (lub *podnosi*) zdarzenie, jest nazywana *wydawcą* i klasy, które odbierają (lub *obsługują*) zdarzenie są nazywane *subskrybentami*.</span><span class="sxs-lookup"><span data-stu-id="859ae-106">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="859ae-107">W typowej Windows Forms lub aplikacji sieci Web w języku C# zasubskrybujesz zdarzenia wywoływane przez kontrolki, takie jak przyciski i pola listy.</span><span class="sxs-lookup"><span data-stu-id="859ae-107">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="859ae-108">Do przeglądania zdarzeń publikowanych przez formant i wybierania tych, które mają być obsługiwane, można użyć zintegrowanego środowiska programistycznego (IDE) języka Visual C#.</span><span class="sxs-lookup"><span data-stu-id="859ae-108">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="859ae-109">Środowisko IDE zapewnia łatwy sposób automatycznego dodawania pustej metody obsługi zdarzeń i kodu w celu subskrybowania zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="859ae-109">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="859ae-110">Aby uzyskać więcej informacji, zobacz [subskrybowanie i anulowanie subskrypcji zdarzeń](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="859ae-110">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="859ae-111">Przegląd zdarzeń</span><span class="sxs-lookup"><span data-stu-id="859ae-111">Events Overview</span></span>  
 <span data-ttu-id="859ae-112">Zdarzenia mają następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="859ae-112">Events have the following properties:</span></span>  
  
- <span data-ttu-id="859ae-113">Wydawca określa, kiedy zdarzenie jest zgłaszane; Subskrybenci określają, jakie działania są podejmowane w odpowiedzi na zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="859ae-113">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="859ae-114">Wydarzenie może mieć wielu subskrybentów.</span><span class="sxs-lookup"><span data-stu-id="859ae-114">An event can have multiple subscribers.</span></span> <span data-ttu-id="859ae-115">Subskrybenci mogą obsługiwać wiele zdarzeń z wielu wydawców.</span><span class="sxs-lookup"><span data-stu-id="859ae-115">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="859ae-116">Zdarzenia, które nie mają subskrybentów nigdy nie są zgłaszane.</span><span class="sxs-lookup"><span data-stu-id="859ae-116">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="859ae-117">Zdarzenia są zwykle używane do sygnalizowania akcji użytkownika, takich jak kliknięcia przycisków lub menu w graficznym interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="859ae-117">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="859ae-118">Gdy zdarzenie ma wielu subskrybentów, programy obsługi zdarzeń są wywoływane synchronicznie, gdy zdarzenie jest zgłaszane.</span><span class="sxs-lookup"><span data-stu-id="859ae-118">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="859ae-119">Aby wywoływać zdarzenia asynchronicznie, zobacz [wywoływanie metod synchronicznych asynchronicznie](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="859ae-119">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="859ae-120">W bibliotece klas .NET zdarzenia są oparte na <xref:System.EventHandler> delegatze i <xref:System.EventArgs> klasie bazowej.</span><span class="sxs-lookup"><span data-stu-id="859ae-120">In the .NET class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="859ae-121">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="859ae-121">Related Sections</span></span>  
 <span data-ttu-id="859ae-122">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="859ae-122">For more information, see:</span></span>  
  
- [<span data-ttu-id="859ae-123">Subskrybowanie i anulowanie subskrypcji zdarzeń</span><span class="sxs-lookup"><span data-stu-id="859ae-123">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="859ae-124">Publikowanie zdarzeń zgodnych ze wskazówkami dotyczącymi programu .NET</span><span class="sxs-lookup"><span data-stu-id="859ae-124">How to publish events that conform to .NET Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="859ae-125">Wywoływanie zdarzeń klasy podstawowej w klasach pochodnych</span><span class="sxs-lookup"><span data-stu-id="859ae-125">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="859ae-126">Implementowanie zdarzeń interfejsu</span><span class="sxs-lookup"><span data-stu-id="859ae-126">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="859ae-127">Implementowanie niestandardowych metod dostępu zdarzeń</span><span class="sxs-lookup"><span data-stu-id="859ae-127">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="859ae-128">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="859ae-128">C# Language Specification</span></span>  

<span data-ttu-id="859ae-129">Aby uzyskać więcej informacji, zobacz [zdarzenia](~/_csharplang/spec/classes.md#events) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="859ae-129">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="859ae-130">Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="859ae-130">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="859ae-131">Polecane rozdziały książki</span><span class="sxs-lookup"><span data-stu-id="859ae-131">Featured Book Chapters</span></span>  
 <span data-ttu-id="859ae-132">[Delegaty, zdarzenia i wyrażenia lambda](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) w [języku c# 3,0 Cookbook, wydanie trzecie: więcej niż 250 rozwiązań dla programistów 3,0 c#](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="859ae-132">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span></span>  
  
 <span data-ttu-id="859ae-133">[Delegaty i zdarzenia](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) w [uczeniu C# 3,0: główne podstawy języka c# 3,0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="859ae-133">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) in [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859ae-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="859ae-134">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="859ae-135">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="859ae-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="859ae-136">Delegaci</span><span class="sxs-lookup"><span data-stu-id="859ae-136">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="859ae-137">Tworzenie programów obsługi zdarzeń w formularzach systemu Windows</span><span class="sxs-lookup"><span data-stu-id="859ae-137">Creating Event Handlers in Windows Forms</span></span>](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms)
