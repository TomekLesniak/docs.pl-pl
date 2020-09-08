---
title: Mieszane błędy kodu deklaracyjnego/bezwzględnego — LINQ to XML
description: Dowiedz się, jak rozpoznać i uniknąć problemów, które mogą wystąpić, gdy kod iteruje się, wprowadzając zmiany.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: fada62d0-0680-4e73-945a-2b00d7a507af
ms.openlocfilehash: 280bb62d15ff28d1fd09ca2d0c52c0a0c36d7282
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553275"
---
# <a name="mixed-declarativeimperative-code-bugs-linq-to-xml"></a><span data-ttu-id="fe349-103">Mieszane usterki kodu deklaracyjnego/bezwzględnego (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="fe349-103">Mixed declarative/imperative code bugs (LINQ to XML)</span></span>

<span data-ttu-id="fe349-104">LINQ to XML zawiera różne metody, które umożliwiają bezpośrednie modyfikowanie drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="fe349-104">LINQ to XML contains various methods that allow you to modify an XML tree directly.</span></span> <span data-ttu-id="fe349-105">Możesz dodać elementy, usunąć elementy, zmienić zawartość elementu, dodać atrybuty i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="fe349-105">You can add elements, delete elements, change the contents of an element, add attributes, and so on.</span></span> <span data-ttu-id="fe349-106">Ten interfejs programowania został opisany w temacie [Modyfikowanie drzew XML](in-memory-xml-tree-modification-vs-functional-construction.md).</span><span class="sxs-lookup"><span data-stu-id="fe349-106">This programming interface is described in [Modify XML trees](in-memory-xml-tree-modification-vs-functional-construction.md).</span></span> <span data-ttu-id="fe349-107">Jeśli testujesz jedną z osi, takich jak <xref:System.Xml.Linq.XContainer.Elements%2A> , i modyfikujesz drzewo XML podczas iteracji przez oś, możesz kończyć się niektórymi niektórymi usterkami.</span><span class="sxs-lookup"><span data-stu-id="fe349-107">If you're iterating through one of the axes, such as <xref:System.Xml.Linq.XContainer.Elements%2A>, and you're modifying the XML tree as you iterate through the axis, you can end up with some strange bugs.</span></span>

<span data-ttu-id="fe349-108">Ten problem jest czasami znany jako "problem z Halloween".</span><span class="sxs-lookup"><span data-stu-id="fe349-108">This problem is sometimes known as "The Halloween Problem".</span></span>

<span data-ttu-id="fe349-109">Podczas pisania kodu przy użyciu LINQ, który wykonuje iterację kolekcji, piszesz kod w stylu deklaratywnym.</span><span class="sxs-lookup"><span data-stu-id="fe349-109">When you write some code using LINQ that iterates through a collection, you're writing code in a declarative style.</span></span> <span data-ttu-id="fe349-110">Więcej informacji o tym, *co* chcesz zrobić, jest bardziej zbliżone, a tym samym, *jak* chcesz go wykonać.</span><span class="sxs-lookup"><span data-stu-id="fe349-110">It's more akin to describing *what* you want, rather that *how* you want to get it done.</span></span> <span data-ttu-id="fe349-111">Jeśli napiszesz kod, który 1) pobierze pierwszy element, 2) testuje go w pewnym stanie, 3) modyfikuje go, a 4) umieszcza go z powrotem na liście, wówczas będzie to kod zapasowy.</span><span class="sxs-lookup"><span data-stu-id="fe349-111">If you write code that 1) gets the first element, 2) tests it for some condition, 3) modifies it, and 4) puts it back into the list, then this would be imperative code.</span></span> <span data-ttu-id="fe349-112">Użytkownik otrzymuje informację, *jak* to zrobić.</span><span class="sxs-lookup"><span data-stu-id="fe349-112">You're telling the computer *how* to do what you want done.</span></span>

<span data-ttu-id="fe349-113">Mieszanie tych stylów kodu w tej samej operacji polega na tym, co prowadzi do problemów.</span><span class="sxs-lookup"><span data-stu-id="fe349-113">Mixing these styles of code in the same operation is what leads to problems.</span></span> <span data-ttu-id="fe349-114">Rozważ następujące źródła:</span><span class="sxs-lookup"><span data-stu-id="fe349-114">Consider the following:</span></span>

<span data-ttu-id="fe349-115">Załóżmy, że masz połączoną listę z trzema elementami (a, b i c):</span><span class="sxs-lookup"><span data-stu-id="fe349-115">Suppose you have a linked list with three items in it (a, b, and c):</span></span>

> <span data-ttu-id="fe349-116">a-> b-> c</span><span class="sxs-lookup"><span data-stu-id="fe349-116">a -> b -> c</span></span>

<span data-ttu-id="fe349-117">Teraz Załóżmy, że chcesz przejść przez połączoną listę, dodając trzy nowe elementy (a ", b" i c ").</span><span class="sxs-lookup"><span data-stu-id="fe349-117">Now, suppose that you want to move through the linked list, adding three new items (a', b', and c').</span></span> <span data-ttu-id="fe349-118">Chcesz, aby połączona lista wyglądała następująco:</span><span class="sxs-lookup"><span data-stu-id="fe349-118">You want the resulting linked list to look like this:</span></span>

 > <span data-ttu-id="fe349-119">a-> "-> b-> b"-> c-> c "</span><span class="sxs-lookup"><span data-stu-id="fe349-119">a -> a' -> b -> b' -> c -> c'</span></span>

<span data-ttu-id="fe349-120">Dlatego Napisz kod, który wykonuje iterację na liście, i dla każdego elementu, dodaje nowy element po nim.</span><span class="sxs-lookup"><span data-stu-id="fe349-120">So you write code that iterates through the list, and for every item, adds a new item right after it.</span></span> <span data-ttu-id="fe349-121">Co się dzieje, gdy Twój kod będzie najpierw widział `a` element i Wstaw `a'` po nim.</span><span class="sxs-lookup"><span data-stu-id="fe349-121">What happens is that your code will first see the `a` element, and insert `a'` after it.</span></span> <span data-ttu-id="fe349-122">Teraz kod zostanie przeniesiony do następnego węzła na liście, który jest teraz `a'` , więc dodaje nowy element między "i b do listy!</span><span class="sxs-lookup"><span data-stu-id="fe349-122">Now, your code will move to the next node in the list, which is now `a'`, so it adds a new item between a' and b to the list!</span></span>

<span data-ttu-id="fe349-123">Jak rozwiązać ten problem?</span><span class="sxs-lookup"><span data-stu-id="fe349-123">How would you solve this?</span></span> <span data-ttu-id="fe349-124">Można również utworzyć kopię pierwotnej połączonej listy oraz zupełnie nową listę.</span><span class="sxs-lookup"><span data-stu-id="fe349-124">Well, you might make a copy of the original linked list, and create a completely new list.</span></span> <span data-ttu-id="fe349-125">Lub jeśli piszesz czysty kod, możesz znaleźć pierwszy element, dodać nowy element, a następnie dwukrotnie wykonać dwa razy na liście połączonej, przechodzenia nad element, który właśnie został dodany.</span><span class="sxs-lookup"><span data-stu-id="fe349-125">Or if you're writing purely imperative code, you might find the first item, add the new item, and then advance twice in the linked list, advancing over the element that you just added.</span></span>

## <a name="example-adding-while-iterating"></a><span data-ttu-id="fe349-126">Przykład: Dodawanie podczas iteracji</span><span class="sxs-lookup"><span data-stu-id="fe349-126">Example: Adding while iterating</span></span>

<span data-ttu-id="fe349-127">Załóżmy na przykład, że chcesz napisać kod w celu utworzenia duplikatu każdego elementu w drzewie:</span><span class="sxs-lookup"><span data-stu-id="fe349-127">For example, suppose you want to write code to create a duplicate of every element in a tree:</span></span>

```csharp
XElement root = new XElement("Root",
    new XElement("A", "1"),
    new XElement("B", "2"),
    new XElement("C", "3")
);
foreach (XElement e in root.Elements())
    root.Add(new XElement(e.Name, (string)e));
```

```vb
Dim root As XElement = _
    <Root>
        <A>1</A>
        <B>2</B>
        <C>3</C>
    </Root>
For Each e As XElement In root.Elements()
    root.Add(New XElement(e.Name, e.Value))
Next
```

<span data-ttu-id="fe349-128">Ten kod przechodzi do nieskończonej pętli.</span><span class="sxs-lookup"><span data-stu-id="fe349-128">This code goes into an infinite loop.</span></span> <span data-ttu-id="fe349-129">`foreach`Instrukcja iteruje przez `Elements()` oś, dodając nowe elementy do `doc` elementu.</span><span class="sxs-lookup"><span data-stu-id="fe349-129">The `foreach` statement iterates through the `Elements()` axis, adding new elements to the `doc` element.</span></span> <span data-ttu-id="fe349-130">Zostanie ona zakończona również za pomocą elementów, które właśnie dodał.</span><span class="sxs-lookup"><span data-stu-id="fe349-130">It ends up iterating also through the elements it just added.</span></span> <span data-ttu-id="fe349-131">I ponieważ przydziela nowe obiekty do każdej iteracji pętli, ostatecznie zużywa całą dostępną pamięć.</span><span class="sxs-lookup"><span data-stu-id="fe349-131">And because it allocates new objects with every iteration of the loop, it will eventually consume all available memory.</span></span>

<span data-ttu-id="fe349-132">Ten problem można rozwiązać, pobierając kolekcję do pamięci przy użyciu <xref:System.Linq.Enumerable.ToList%2A> standardowego operatora zapytania w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="fe349-132">You can fix this problem by pulling the collection into memory using the <xref:System.Linq.Enumerable.ToList%2A> standard query operator, as follows:</span></span>

```csharp
XElement root = new XElement("Root",
    new XElement("A", "1"),
    new XElement("B", "2"),
    new XElement("C", "3")
);
foreach (XElement e in root.Elements().ToList())
    root.Add(new XElement(e.Name, (string)e));
Console.WriteLine(root);
```

```vb
Dim root As XElement = _
    <Root>
        <A>1</A>
        <B>2</B>
        <C>3</C>
    </Root>
For Each e As XElement In root.Elements().ToList()
    root.Add(New XElement(e.Name, e.Value))
Next
Console.WriteLine(root)
```

<span data-ttu-id="fe349-133">Teraz kod działa.</span><span class="sxs-lookup"><span data-stu-id="fe349-133">Now the code works.</span></span> <span data-ttu-id="fe349-134">Utworzone drzewo XML jest następujące:</span><span class="sxs-lookup"><span data-stu-id="fe349-134">The resulting XML tree is the following:</span></span>

```xml
<Root>
  <A>1</A>
  <B>2</B>
  <C>3</C>
  <A>1</A>
  <B>2</B>
  <C>3</C>
</Root>
```

## <a name="example-deleting-while-iterating"></a><span data-ttu-id="fe349-135">Przykład: usuwanie podczas iteracji</span><span class="sxs-lookup"><span data-stu-id="fe349-135">Example: Deleting while iterating</span></span>

<span data-ttu-id="fe349-136">Jeśli chcesz usunąć wszystkie węzły na określonym poziomie, być może chcesz napisać kod podobny do poniższego:</span><span class="sxs-lookup"><span data-stu-id="fe349-136">If you want to delete all nodes at a certain level, you might be tempted to write code like the following:</span></span>

```csharp
XElement root = new XElement("Root",
    new XElement("A", "1"),
    new XElement("B", "2"),
    new XElement("C", "3")
);
foreach (XElement e in root.Elements())
    e.Remove();
Console.WriteLine(root);
```

```vb
Dim root As XElement = _
    <Root>
        <A>1</A>
        <B>2</B>
        <C>3</C>
    </Root>
For Each e As XElement In root.Elements()
    e.Remove()
Next
Console.WriteLine(root)
```

<span data-ttu-id="fe349-137">Nie jest to jednak wykonywane.</span><span class="sxs-lookup"><span data-stu-id="fe349-137">However, this doesn't do what you want.</span></span> <span data-ttu-id="fe349-138">W tej sytuacji po usunięciu pierwszego elementu element zostanie usunięty z drzewa XML zawartego w katalogu głównym, a kod w metodzie elementy, który wykonuje iterację nie może znaleźć następnego elementu.</span><span class="sxs-lookup"><span data-stu-id="fe349-138">In this situation, after you've removed the first element, A, it's removed from the XML tree contained in root, and the code in the Elements method that does the iterating can't find the next element.</span></span>

<span data-ttu-id="fe349-139">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="fe349-139">This example produces the following output:</span></span>

```xml
<Root>
  <B>2</B>
  <C>3</C>
</Root>
```

<span data-ttu-id="fe349-140">Rozwiązanie to ponownie wywołuje <xref:System.Linq.Enumerable.ToList%2A> zmaterializowania kolekcji w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="fe349-140">The solution again is to call <xref:System.Linq.Enumerable.ToList%2A> to materialize the collection, as follows:</span></span>

```csharp
XElement root = new XElement("Root",
    new XElement("A", "1"),
    new XElement("B", "2"),
    new XElement("C", "3")
);
foreach (XElement e in root.Elements().ToList())
    e.Remove();
Console.WriteLine(root);
```

```vb
Dim root As XElement = _
    <Root>
        <A>1</A>
        <B>2</B>
        <C>3</C>
    </Root>
For Each e As XElement In root.Elements().ToList()
    e.Remove()
Next
Console.WriteLine(root)
```

<span data-ttu-id="fe349-141">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="fe349-141">This example produces the following output:</span></span>

```xml
<Root />
```

<span data-ttu-id="fe349-142">Alternatywnie można wyeliminować iterację całkowicie poprzez wywołanie <xref:System.Xml.Linq.XElement.RemoveAll%2A> elementu nadrzędnego:</span><span class="sxs-lookup"><span data-stu-id="fe349-142">Alternatively, you can eliminate the iteration altogether by calling <xref:System.Xml.Linq.XElement.RemoveAll%2A> on the parent element:</span></span>

```csharp
XElement root = new XElement("Root",
    new XElement("A", "1"),
    new XElement("B", "2"),
    new XElement("C", "3")
);
root.RemoveAll();
Console.WriteLine(root);
```

```vb
Dim root As XElement = _
    <Root>
        <A>1</A>
        <B>2</B>
        <C>3</C>
    </Root>
root.RemoveAll()
Console.WriteLine(root)
```

## <a name="example-why-linq-cant-automatically-handle-these-issues"></a><span data-ttu-id="fe349-143">Przykład: Dlaczego LINQ nie może automatycznie obsłużyć tych problemów</span><span class="sxs-lookup"><span data-stu-id="fe349-143">Example: Why LINQ can't automatically handle these issues</span></span>

<span data-ttu-id="fe349-144">Jednym z metod jest zawsze umieszczenie wszystkiego w pamięci zamiast oceny z opóźnieniem.</span><span class="sxs-lookup"><span data-stu-id="fe349-144">One approach would be to always bring everything into memory instead of doing lazy evaluation.</span></span> <span data-ttu-id="fe349-145">Jest to jednak bardzo kosztowne pod względem wydajności i użycia pamięci.</span><span class="sxs-lookup"><span data-stu-id="fe349-145">However, it would be very expensive in terms of performance and memory use.</span></span> <span data-ttu-id="fe349-146">W rzeczywistości, jeśli LINQ i LINQ to XML, miało to na celu podjęcie tego podejścia, wystąpi niepowodzenie w rzeczywistych sytuacjach.</span><span class="sxs-lookup"><span data-stu-id="fe349-146">In fact, if LINQ, and LINQ to XML, were to take this approach, it would fail in real-world situations.</span></span>

<span data-ttu-id="fe349-147">Innym możliwym podejściem byłoby umieszczenie w kodzie LINQ pewnej składni transakcji, a kompilator próbuje analizować kod w celu ustalenia, czy jakakolwiek konkretna kolekcja jest wymagana do materiału.</span><span class="sxs-lookup"><span data-stu-id="fe349-147">Another possible approach would be to put some sort of transaction syntax into LINQ, and have the compiler attempt to analyze the code to determine if any particular collection needed to be materialized.</span></span> <span data-ttu-id="fe349-148">Jednak próba ustalenia całego kodu, który ma efekty uboczne, to niezwykle Complex.</span><span class="sxs-lookup"><span data-stu-id="fe349-148">However, attempting to determine all code that has side-effects is incredibly complex.</span></span> <span data-ttu-id="fe349-149">Spójrzmy na poniższy kod:</span><span class="sxs-lookup"><span data-stu-id="fe349-149">Consider the following code:</span></span>

```csharp
var z =
    from e in root.Elements()
    where TestSomeCondition(e)
    select DoMyProjection(e);
```

```vb
Dim z = _
    From e In root.Elements() _
    Where (TestSomeCondition(e)) _
    Select DoMyProjection(e)
```

<span data-ttu-id="fe349-150">Taki kod analizy musi analizować metody TestSomeCondition i DoMyProjection, a także wszystkie metody wywoływane przez te metody, aby określić, czy dowolny kod ma efekty uboczne.</span><span class="sxs-lookup"><span data-stu-id="fe349-150">Such analysis code would need to analyze the methods TestSomeCondition and DoMyProjection, and all methods that those methods called, to determine if any code had side-effects.</span></span> <span data-ttu-id="fe349-151">Jednak kod analizy nie może wyszukać żadnego kodu, który miał skutki uboczne.</span><span class="sxs-lookup"><span data-stu-id="fe349-151">But the analysis code could not just look for any code that had side-effects.</span></span> <span data-ttu-id="fe349-152">Należy wybrać tylko kod, który miał skutki uboczne w elementach podrzędnych `root` w tej sytuacji.</span><span class="sxs-lookup"><span data-stu-id="fe349-152">It would need to select for just the code that had side-effects on the child elements of `root` in this situation.</span></span>

<span data-ttu-id="fe349-153">LINQ to XML nie próbuje wykonać takiej analizy.</span><span class="sxs-lookup"><span data-stu-id="fe349-153">LINQ to XML doesn't attempt to do any such analysis.</span></span> <span data-ttu-id="fe349-154">Pozwala to uniknąć tych problemów.</span><span class="sxs-lookup"><span data-stu-id="fe349-154">It's up to you to avoid these problems.</span></span>

## <a name="example-use-declarative-code-to-generate-a-new-xml-tree-rather-than-modify-the-existing-tree"></a><span data-ttu-id="fe349-155">Przykład: Użyj kodu deklaracyjnego, aby wygenerować nowe drzewo XML zamiast modyfikować istniejące drzewo</span><span class="sxs-lookup"><span data-stu-id="fe349-155">Example: Use declarative code to generate a new XML tree rather than modify the existing tree</span></span>

<span data-ttu-id="fe349-156">Aby uniknąć takich problemów, nie należy mieszać kodu deklaratywnego i bezwzględnego, nawet jeśli znasz dokładnie semantykę kolekcji i semantykę metod, które modyfikują drzewo XML.</span><span class="sxs-lookup"><span data-stu-id="fe349-156">To avoid such problems, don't mix declarative and imperative code, even if you know exactly the semantics of your collections and the semantics of the methods that modify the XML tree.</span></span> <span data-ttu-id="fe349-157">Jeśli napiszesz kod, który pozwala uniknąć problemów, kod będzie musiał być obsługiwany przez innych deweloperów w przyszłości i nie będzie jak oczywisty w przypadku problemów.</span><span class="sxs-lookup"><span data-stu-id="fe349-157">If you write code that avoids problems, your code will need to be maintained by other developers in the future, and they may not be as clear on the issues.</span></span> <span data-ttu-id="fe349-158">Jeśli Mieszasz deklaratywne i bezwzględne style kodowania, kod będzie bardziej kruchy.</span><span class="sxs-lookup"><span data-stu-id="fe349-158">If you mix declarative and imperative coding styles, your code will be more brittle.</span></span>  <span data-ttu-id="fe349-159">Jeśli napiszesz kod, który materializuje kolekcję, aby uniknąć tych problemów, zwróć uwagę na to, że komentarze są odpowiednie w kodzie, dzięki czemu programiści mogą zrozumieć problem.</span><span class="sxs-lookup"><span data-stu-id="fe349-159">If you write code that materializes a collection so that these problems are avoided, note it with comments as appropriate in your code, so that maintenance programmers will understand the issue.</span></span>

<span data-ttu-id="fe349-160">Jeśli jest to możliwe, należy używać tylko kodu deklaratywnego.</span><span class="sxs-lookup"><span data-stu-id="fe349-160">If performance and other considerations allow, use only declarative code.</span></span> <span data-ttu-id="fe349-161">Nie należy modyfikować istniejącego drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="fe349-161">Don't modify your existing XML tree.</span></span> <span data-ttu-id="fe349-162">Zamiast tego Generuj nowy, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="fe349-162">Instead, generate a new one as shown in the following example:</span></span>

```csharp
XElement root = new XElement("Root",
    new XElement("A", "1"),
    new XElement("B", "2"),
    new XElement("C", "3")
);
XElement newRoot = new XElement("Root",
    root.Elements(),
    root.Elements()
);
Console.WriteLine(newRoot);
```

```vb
Dim root As XElement = _
    <Root>
        <A>1</A>
        <B>2</B>
        <C>3</C>
    </Root>
Dim newRoot As XElement = New XElement("Root", _
    root.Elements(), root.Elements())
Console.WriteLine(newRoot)
```
