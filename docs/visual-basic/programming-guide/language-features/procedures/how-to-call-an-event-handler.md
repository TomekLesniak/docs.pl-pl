---
title: Jak wywołać procedurę obsługi zdarzeń
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
no-loc:
- WithEvents
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 3762c79dd3d883ae2ccfe76b335cf98ac87d4246
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89464964"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="c8053-102">Jak wywołać procedurę obsługi zdarzeń w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8053-102">How to call an event handler in Visual Basic</span></span>

<span data-ttu-id="c8053-103">*Zdarzenie* jest akcją lub wystąpieniem, takim jak kliknięcie myszą lub Przekroczono limit środków, który jest rozpoznawany przez jakiś składnik programu i dla którego można napisać kod, aby odpowiedzieć.</span><span class="sxs-lookup"><span data-stu-id="c8053-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="c8053-104">*Program obsługi zdarzeń* to kod, który można napisać, aby odpowiedzieć na zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="c8053-104">An *event handler* is the code you write to respond to an event.</span></span>

<span data-ttu-id="c8053-105">Procedura obsługi zdarzeń w Visual Basic jest `Sub` procedurą.</span><span class="sxs-lookup"><span data-stu-id="c8053-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="c8053-106">Nie jest to jednak zazwyczaj wywoływana w taki sam sposób jak w przypadku innych `Sub` procedur.</span><span class="sxs-lookup"><span data-stu-id="c8053-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="c8053-107">Zamiast tego należy zidentyfikować procedurę jako program obsługi zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c8053-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="c8053-108">Można to zrobić za pomocą [`Handles`](../../../language-reference/statements/handles-clause.md) klauzuli i [`WithEvents`](../../../language-reference/modifiers/withevents.md) zmiennej lub z [instrukcją AddHandler](../../../language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8053-108">You can do this either with a [`Handles`](../../../language-reference/statements/handles-clause.md) clause and a [`WithEvents`](../../../language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="c8053-109">Użycie `Handles` klauzuli jest domyślnym sposobem deklarowania procedury obsługi zdarzeń w Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c8053-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="c8053-110">Jest to sposób, w jaki programy obsługi zdarzeń są zapisywane przez projektantów podczas programowania w zintegrowanym środowisku programistycznym (IDE).</span><span class="sxs-lookup"><span data-stu-id="c8053-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="c8053-111">`AddHandler`Instrukcja jest odpowiednia do dynamicznego wywoływania zdarzeń w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="c8053-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>

<span data-ttu-id="c8053-112">Gdy wystąpi zdarzenie, Visual Basic automatycznie wywołuje procedurę obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="c8053-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="c8053-113">Każdy kod, który ma dostęp do zdarzenia może być spowodowany przez wykonanie [instrukcji RaiseEvent](../../../language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8053-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../language-reference/statements/raiseevent-statement.md).</span></span>

<span data-ttu-id="c8053-114">Można skojarzyć więcej niż jeden program obsługi zdarzeń z tym samym zdarzeniem.</span><span class="sxs-lookup"><span data-stu-id="c8053-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="c8053-115">W niektórych przypadkach można usunąć skojarzenie procedury obsługi ze zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c8053-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="c8053-116">Aby uzyskać więcej informacji, zobacz [zdarzenia](../events/index.md).</span><span class="sxs-lookup"><span data-stu-id="c8053-116">For more information, see [Events](../events/index.md).</span></span>

## <a name="call-an-event-handler-using-no-loc-texthandles-and-no-locwithevents"></a><span data-ttu-id="c8053-117">Wywoływanie procedury obsługi zdarzeń przy użyciu :::no-loc text="Handles"::: i WithEvents</span><span class="sxs-lookup"><span data-stu-id="c8053-117">Call an event handler using :::no-loc text="Handles"::: and WithEvents</span></span>

1. <span data-ttu-id="c8053-118">Upewnij się, że zdarzenie jest zadeklarowane za pomocą [instrukcji zdarzenia](../../../language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8053-118">Make sure the event is declared with an [Event Statement](../../../language-reference/statements/event-statement.md).</span></span>

2. <span data-ttu-id="c8053-119">Zadeklaruj zmienną obiektu na poziomie modułu lub klasy przy użyciu [`WithEvents`](../../../language-reference/modifiers/withevents.md) słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="c8053-119">Declare an object variable at module or class level, using the [`WithEvents`](../../../language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="c8053-120">`As`Klauzula dla tej zmiennej musi określać klasę, która wywołuje zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="c8053-120">The `As` clause for this variable must specify the class that raises the event.</span></span>

3. <span data-ttu-id="c8053-121">W deklaracji procedury obsługi zdarzeń `Sub` Dodaj [`Handles`](../../../language-reference/statements/handles-clause.md) klauzulę, która określa `WithEvents` zmienną i nazwę zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c8053-121">In the declaration of the event-handling `Sub` procedure, add a [`Handles`](../../../language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>

4. <span data-ttu-id="c8053-122">Gdy wystąpi zdarzenie, Visual Basic automatycznie wywoła `Sub` procedurę.</span><span class="sxs-lookup"><span data-stu-id="c8053-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="c8053-123">Kod może użyć instrukcji, `RaiseEvent` aby wystąpiło zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="c8053-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

    <span data-ttu-id="c8053-124">W poniższym przykładzie zdefiniowano zdarzenie i `WithEvents` zmienną, która odwołuje się do klasy, która wywołuje zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="c8053-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="c8053-125">Procedura obsługi zdarzeń `Sub` używa `Handles` klauzuli do określenia klasy i zdarzenia, które obsługuje.</span><span class="sxs-lookup"><span data-stu-id="c8053-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="4":::

## <a name="call-an-event-handler-using-addhandler"></a><span data-ttu-id="c8053-126">Wywoływanie procedury obsługi zdarzeń przy użyciu elementu AddHandler</span><span class="sxs-lookup"><span data-stu-id="c8053-126">Call an event handler using AddHandler</span></span>

1. <span data-ttu-id="c8053-127">Upewnij się, że zdarzenie jest zadeklarowane za pomocą `Event` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c8053-127">Make sure the event is declared with an `Event` statement.</span></span>

2. <span data-ttu-id="c8053-128">Wykonaj [instrukcję AddHandler](../../../language-reference/statements/addhandler-statement.md) , aby dynamicznie połączyć procedurę obsługi zdarzeń `Sub` ze zdarzeniem.</span><span class="sxs-lookup"><span data-stu-id="c8053-128">Execute an [AddHandler statement](../../../language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>

3. <span data-ttu-id="c8053-129">Gdy wystąpi zdarzenie, Visual Basic automatycznie wywoła `Sub` procedurę.</span><span class="sxs-lookup"><span data-stu-id="c8053-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="c8053-130">Kod może użyć instrukcji, `RaiseEvent` aby wystąpiło zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="c8053-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

    <span data-ttu-id="c8053-131">Poniższy przykład używa [instrukcji AddHandler](../../../language-reference/statements/addhandler-statement.md) w konstruktorze, aby skojarzyć `OnFormClosing` procedurę jako procedurę obsługi zdarzeń dla <xref:System.Windows.Forms.Form.FormClosing> .</span><span class="sxs-lookup"><span data-stu-id="c8053-131">The following example uses the [AddHandler statement](../../../language-reference/statements/addhandler-statement.md) in the constructor to associate the `OnFormClosing` procedure as an event handler for <xref:System.Windows.Forms.Form.FormClosing>.</span></span>

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="5":::

    <span data-ttu-id="c8053-132">Można usunąć skojarzenie programu obsługi zdarzeń ze zdarzenia przez wykonanie [instrukcji RemoveHandler](../../../language-reference/statements/removehandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8053-132">You can dissociate an event handler from an event by executing the [RemoveHandler statement](../../../language-reference/statements/removehandler-statement.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8053-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c8053-133">See also</span></span>

- [<span data-ttu-id="c8053-134">Procedury</span><span class="sxs-lookup"><span data-stu-id="c8053-134">Procedures</span></span>](index.md)
- [<span data-ttu-id="c8053-135">Sub, procedury</span><span class="sxs-lookup"><span data-stu-id="c8053-135">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="c8053-136">Sub, instrukcja</span><span class="sxs-lookup"><span data-stu-id="c8053-136">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="c8053-137">AddressOf, operator</span><span class="sxs-lookup"><span data-stu-id="c8053-137">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="c8053-138">Porady: tworzenie procedury</span><span class="sxs-lookup"><span data-stu-id="c8053-138">How to: Create a Procedure</span></span>](how-to-create-a-procedure.md)
- [<span data-ttu-id="c8053-139">Porady: wywoływanie procedury, która nie zwraca wartości</span><span class="sxs-lookup"><span data-stu-id="c8053-139">How to: Call a Procedure that Does Not Return a Value</span></span>](how-to-call-a-procedure-that-does-not-return-a-value.md)
