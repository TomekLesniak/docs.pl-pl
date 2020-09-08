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
# <a name="mixed-declarativeimperative-code-bugs-linq-to-xml"></a>Mieszane usterki kodu deklaracyjnego/bezwzględnego (LINQ to XML)

LINQ to XML zawiera różne metody, które umożliwiają bezpośrednie modyfikowanie drzewa XML. Możesz dodać elementy, usunąć elementy, zmienić zawartość elementu, dodać atrybuty i tak dalej. Ten interfejs programowania został opisany w temacie [Modyfikowanie drzew XML](in-memory-xml-tree-modification-vs-functional-construction.md). Jeśli testujesz jedną z osi, takich jak <xref:System.Xml.Linq.XContainer.Elements%2A> , i modyfikujesz drzewo XML podczas iteracji przez oś, możesz kończyć się niektórymi niektórymi usterkami.

Ten problem jest czasami znany jako "problem z Halloween".

Podczas pisania kodu przy użyciu LINQ, który wykonuje iterację kolekcji, piszesz kod w stylu deklaratywnym. Więcej informacji o tym, *co* chcesz zrobić, jest bardziej zbliżone, a tym samym, *jak* chcesz go wykonać. Jeśli napiszesz kod, który 1) pobierze pierwszy element, 2) testuje go w pewnym stanie, 3) modyfikuje go, a 4) umieszcza go z powrotem na liście, wówczas będzie to kod zapasowy. Użytkownik otrzymuje informację, *jak* to zrobić.

Mieszanie tych stylów kodu w tej samej operacji polega na tym, co prowadzi do problemów. Rozważ następujące źródła:

Załóżmy, że masz połączoną listę z trzema elementami (a, b i c):

> a-> b-> c

Teraz Załóżmy, że chcesz przejść przez połączoną listę, dodając trzy nowe elementy (a ", b" i c "). Chcesz, aby połączona lista wyglądała następująco:

 > a-> "-> b-> b"-> c-> c "

Dlatego Napisz kod, który wykonuje iterację na liście, i dla każdego elementu, dodaje nowy element po nim. Co się dzieje, gdy Twój kod będzie najpierw widział `a` element i Wstaw `a'` po nim. Teraz kod zostanie przeniesiony do następnego węzła na liście, który jest teraz `a'` , więc dodaje nowy element między "i b do listy!

Jak rozwiązać ten problem? Można również utworzyć kopię pierwotnej połączonej listy oraz zupełnie nową listę. Lub jeśli piszesz czysty kod, możesz znaleźć pierwszy element, dodać nowy element, a następnie dwukrotnie wykonać dwa razy na liście połączonej, przechodzenia nad element, który właśnie został dodany.

## <a name="example-adding-while-iterating"></a>Przykład: Dodawanie podczas iteracji

Załóżmy na przykład, że chcesz napisać kod w celu utworzenia duplikatu każdego elementu w drzewie:

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

Ten kod przechodzi do nieskończonej pętli. `foreach`Instrukcja iteruje przez `Elements()` oś, dodając nowe elementy do `doc` elementu. Zostanie ona zakończona również za pomocą elementów, które właśnie dodał. I ponieważ przydziela nowe obiekty do każdej iteracji pętli, ostatecznie zużywa całą dostępną pamięć.

Ten problem można rozwiązać, pobierając kolekcję do pamięci przy użyciu <xref:System.Linq.Enumerable.ToList%2A> standardowego operatora zapytania w następujący sposób:

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

Teraz kod działa. Utworzone drzewo XML jest następujące:

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

## <a name="example-deleting-while-iterating"></a>Przykład: usuwanie podczas iteracji

Jeśli chcesz usunąć wszystkie węzły na określonym poziomie, być może chcesz napisać kod podobny do poniższego:

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

Nie jest to jednak wykonywane. W tej sytuacji po usunięciu pierwszego elementu element zostanie usunięty z drzewa XML zawartego w katalogu głównym, a kod w metodzie elementy, który wykonuje iterację nie może znaleźć następnego elementu.

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <B>2</B>
  <C>3</C>
</Root>
```

Rozwiązanie to ponownie wywołuje <xref:System.Linq.Enumerable.ToList%2A> zmaterializowania kolekcji w następujący sposób:

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

Ten przykład generuje następujące wyniki:

```xml
<Root />
```

Alternatywnie można wyeliminować iterację całkowicie poprzez wywołanie <xref:System.Xml.Linq.XElement.RemoveAll%2A> elementu nadrzędnego:

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

## <a name="example-why-linq-cant-automatically-handle-these-issues"></a>Przykład: Dlaczego LINQ nie może automatycznie obsłużyć tych problemów

Jednym z metod jest zawsze umieszczenie wszystkiego w pamięci zamiast oceny z opóźnieniem. Jest to jednak bardzo kosztowne pod względem wydajności i użycia pamięci. W rzeczywistości, jeśli LINQ i LINQ to XML, miało to na celu podjęcie tego podejścia, wystąpi niepowodzenie w rzeczywistych sytuacjach.

Innym możliwym podejściem byłoby umieszczenie w kodzie LINQ pewnej składni transakcji, a kompilator próbuje analizować kod w celu ustalenia, czy jakakolwiek konkretna kolekcja jest wymagana do materiału. Jednak próba ustalenia całego kodu, który ma efekty uboczne, to niezwykle Complex. Spójrzmy na poniższy kod:

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

Taki kod analizy musi analizować metody TestSomeCondition i DoMyProjection, a także wszystkie metody wywoływane przez te metody, aby określić, czy dowolny kod ma efekty uboczne. Jednak kod analizy nie może wyszukać żadnego kodu, który miał skutki uboczne. Należy wybrać tylko kod, który miał skutki uboczne w elementach podrzędnych `root` w tej sytuacji.

LINQ to XML nie próbuje wykonać takiej analizy. Pozwala to uniknąć tych problemów.

## <a name="example-use-declarative-code-to-generate-a-new-xml-tree-rather-than-modify-the-existing-tree"></a>Przykład: Użyj kodu deklaracyjnego, aby wygenerować nowe drzewo XML zamiast modyfikować istniejące drzewo

Aby uniknąć takich problemów, nie należy mieszać kodu deklaratywnego i bezwzględnego, nawet jeśli znasz dokładnie semantykę kolekcji i semantykę metod, które modyfikują drzewo XML. Jeśli napiszesz kod, który pozwala uniknąć problemów, kod będzie musiał być obsługiwany przez innych deweloperów w przyszłości i nie będzie jak oczywisty w przypadku problemów. Jeśli Mieszasz deklaratywne i bezwzględne style kodowania, kod będzie bardziej kruchy.  Jeśli napiszesz kod, który materializuje kolekcję, aby uniknąć tych problemów, zwróć uwagę na to, że komentarze są odpowiednie w kodzie, dzięki czemu programiści mogą zrozumieć problem.

Jeśli jest to możliwe, należy używać tylko kodu deklaratywnego. Nie należy modyfikować istniejącego drzewa XML. Zamiast tego Generuj nowy, jak pokazano w następującym przykładzie:

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
