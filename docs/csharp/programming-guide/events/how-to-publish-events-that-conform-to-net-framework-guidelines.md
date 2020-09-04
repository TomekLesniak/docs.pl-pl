---
title: Publikuj zdarzenia zgodne z zaleceniami platformy .NET — Przewodnik programowania w języku C#
description: Dowiedz się, jak publikować zdarzenia zgodne z zaleceniami dotyczącymi platformy .NET. Wszystkie zdarzenia w bibliotece klas .NET są oparte na delegatze EventHandler.
ms.date: 05/26/2020
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 8cc8b0a9fdaeeb6ab6290630c5d78044c2696b9a
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466173"
---
# <a name="how-to-publish-events-that-conform-to-net-guidelines-c-programming-guide"></a><span data-ttu-id="7a773-104">Jak opublikować zdarzenia zgodne z zaleceniami dotyczącymi platformy .NET (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="7a773-104">How to publish events that conform to .NET Guidelines (C# Programming Guide)</span></span>

<span data-ttu-id="7a773-105">Poniższa procedura pokazuje, jak dodać zdarzenia zgodne ze standardowym wzorcem .NET do klas i struktur.</span><span class="sxs-lookup"><span data-stu-id="7a773-105">The following procedure demonstrates how to add events that follow the standard .NET pattern to your classes and structs.</span></span> <span data-ttu-id="7a773-106">Wszystkie zdarzenia w bibliotece klas .NET są oparte na <xref:System.EventHandler> delegatze, który jest zdefiniowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="7a773-106">All events in the .NET class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>

```csharp
public delegate void EventHandler(object sender, EventArgs e);
```

> [!NOTE]
> <span data-ttu-id="7a773-107">.NET Framework 2,0 wprowadza ogólną wersję tego delegata, <xref:System.EventHandler%601> .</span><span class="sxs-lookup"><span data-stu-id="7a773-107">.NET Framework 2.0 introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="7a773-108">W poniższych przykładach pokazano, jak używać obu wersji.</span><span class="sxs-lookup"><span data-stu-id="7a773-108">The following examples show how to use both versions.</span></span>

<span data-ttu-id="7a773-109">Chociaż zdarzenia w zdefiniowanych klasach mogą opierać się na dowolnym prawidłowym typie delegata, nawet delegatów zwracających wartość, zazwyczaj zaleca się oparcie zdarzeń na wzorcu .NET przy użyciu <xref:System.EventHandler> , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="7a773-109">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the .NET pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>

<span data-ttu-id="7a773-110">Nazwa `EventHandler` może prowadzić do nieprawidłowych pomyłek, ponieważ nie jest w rzeczywistości obsługiwana dla zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="7a773-110">The name `EventHandler` can lead to a bit of confusion as it doesn't actually handle the event.</span></span> <span data-ttu-id="7a773-111"><xref:System.EventHandler>, I ogólne <xref:System.EventHandler%601> są typami delegatów.</span><span class="sxs-lookup"><span data-stu-id="7a773-111">The <xref:System.EventHandler>, and generic <xref:System.EventHandler%601> are delegate types.</span></span> <span data-ttu-id="7a773-112">Metoda lub wyrażenie lambda, którego sygnatura jest zgodna z definicją delegata, jest *obsługą zdarzeń* i zostanie wywołana, gdy zdarzenie zostanie zgłoszone.</span><span class="sxs-lookup"><span data-stu-id="7a773-112">A method or lambda expression whose signature matches the delegate definition is the *event handler* and will be invoked when the event is raised.</span></span>

## <a name="publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="7a773-113">Publikuj zdarzenia na podstawie wzorca EventHandler</span><span class="sxs-lookup"><span data-stu-id="7a773-113">Publish events based on the EventHandler pattern</span></span>

1. <span data-ttu-id="7a773-114">(Pomiń ten krok i przejdź do kroku 3a, jeśli nie musisz wysyłać niestandardowych danych do zdarzenia). Zadeklaruj klasę niestandardowych danych w zakresie, który jest widoczny dla obu klas wydawcy i subskrybenta.</span><span class="sxs-lookup"><span data-stu-id="7a773-114">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="7a773-115">Następnie Dodaj wymagane elementy członkowskie, aby przechowywać dane niestandardowego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="7a773-115">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="7a773-116">W tym przykładzie jest zwracany prosty ciąg.</span><span class="sxs-lookup"><span data-stu-id="7a773-116">In this example, a simple string is returned.</span></span>

    ```csharp
    public class CustomEventArgs : EventArgs
    {
        public CustomEventArgs(string message)
        {
            Message = message;
        }

        public string Message { get; set; }
    }
    ```

2. <span data-ttu-id="7a773-117">(Pomiń ten krok, jeśli używasz ogólnej wersji programu <xref:System.EventHandler%601> ). Zadeklaruj delegat w klasie publikacji.</span><span class="sxs-lookup"><span data-stu-id="7a773-117">(Skip this step if you are using the generic version of <xref:System.EventHandler%601>.) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="7a773-118">Nadaj jej nazwę kończącą się na `EventHandler` .</span><span class="sxs-lookup"><span data-stu-id="7a773-118">Give it a name that ends with `EventHandler`.</span></span> <span data-ttu-id="7a773-119">Drugi parametr określa `EventArgs` typ niestandardowy.</span><span class="sxs-lookup"><span data-stu-id="7a773-119">The second parameter specifies your custom `EventArgs` type.</span></span>

    ```csharp
    public delegate void CustomEventHandler(object sender, CustomEventArgs args);
    ```

3. <span data-ttu-id="7a773-120">Zadeklaruj zdarzenie w klasie publikacji przy użyciu jednego z następujących kroków.</span><span class="sxs-lookup"><span data-stu-id="7a773-120">Declare the event in your publishing class by using one of the following steps.</span></span>

    1. <span data-ttu-id="7a773-121">Jeśli nie masz niestandardowej klasy EventArgs, typ zdarzenia będzie nieogólnym delegatem EventHandler.</span><span class="sxs-lookup"><span data-stu-id="7a773-121">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="7a773-122">Nie trzeba deklarować delegata, ponieważ jest on już zadeklarowany w <xref:System> przestrzeni nazw, która jest uwzględniona podczas tworzenia projektu w języku C#.</span><span class="sxs-lookup"><span data-stu-id="7a773-122">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="7a773-123">Dodaj następujący kod do klasy wydawcy.</span><span class="sxs-lookup"><span data-stu-id="7a773-123">Add the following code to your publisher class.</span></span>

        ```csharp
        public event EventHandler RaiseCustomEvent;
        ```

    2. <span data-ttu-id="7a773-124">Jeśli używasz nieogólnej wersji programu <xref:System.EventHandler> i masz klasę niestandardową pochodną od <xref:System.EventArgs> , zadeklaruj zdarzenie wewnątrz klasy publikacji i użyj delegata z kroku 2 jako typ.</span><span class="sxs-lookup"><span data-stu-id="7a773-124">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>

        ```csharp
        public event CustomEventHandler RaiseCustomEvent;
        ```

    3. <span data-ttu-id="7a773-125">Jeśli używasz wersji ogólnej, nie potrzebujesz niestandardowego delegata.</span><span class="sxs-lookup"><span data-stu-id="7a773-125">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="7a773-126">Zamiast tego w klasie publikacji należy określić typ zdarzenia jako `EventHandler<CustomEventArgs>` , zastępując nazwę własnej klasy między nawiasami kątowymi.</span><span class="sxs-lookup"><span data-stu-id="7a773-126">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>

        ```csharp
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;
        ```

## <a name="example"></a><span data-ttu-id="7a773-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="7a773-127">Example</span></span>

<span data-ttu-id="7a773-128">Poniższy przykład demonstruje poprzednie kroki przy użyciu niestandardowej klasy EventArgs i <xref:System.EventHandler%601> jako typ zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="7a773-128">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>

[!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]

## <a name="see-also"></a><span data-ttu-id="7a773-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7a773-129">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="7a773-130">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="7a773-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7a773-131">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="7a773-131">Events</span></span>](index.md)
- [<span data-ttu-id="7a773-132">Delegaci</span><span class="sxs-lookup"><span data-stu-id="7a773-132">Delegates</span></span>](../delegates/index.md)
