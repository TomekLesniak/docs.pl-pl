---
title: Literały XML w Visual Basic-LINQ to XML
description: Drzewo XML można utworzyć w Visual Basic przy użyciu literałów XML i osadzonych wyrażeń. Wyrażenia osadzone umożliwiają ocenę wyrażenia i wstawianie wyników wyrażenia do drzewa XML.
ms.date: 07/20/2015
ms.assetid: 94fc0e03-978e-4c08-ab6c-0dc3c1e64f10
ms.openlocfilehash: e3b1213672a6a7ddd71fcc38b4502108a6f49881
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553208"
---
# <a name="xml-literals-in-visual-basic-linq-to-xml"></a><span data-ttu-id="e28e4-104">Literały XML w Visual Basic (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="e28e4-104">XML Literals in Visual Basic (LINQ to XML)</span></span>

<span data-ttu-id="e28e4-105">Ten artykuł zawiera informacje dotyczące tworzenia drzew XML w Visual Basic przy użyciu literałów XML i osadzonych wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="e28e4-105">This article provides information about creating XML trees in Visual Basic using XML literals and embedded expressions.</span></span>

## <a name="example-use-xml-literals-to-create-an-xml-tree"></a><span data-ttu-id="e28e4-106">Przykład: Użyj literałów XML do utworzenia drzewa XML</span><span class="sxs-lookup"><span data-stu-id="e28e4-106">Example: Use XML literals to create an XML tree</span></span>

<span data-ttu-id="e28e4-107">Poniższy przykład pokazuje, jak utworzyć <xref:System.Xml.Linq.XElement> , w tym przypadku `contacts` , za pomocą literałów XML:</span><span class="sxs-lookup"><span data-stu-id="e28e4-107">The following example shows how to create an <xref:System.Xml.Linq.XElement>, in this case `contacts`, with XML literals:</span></span>

```vb
Dim contacts As XElement = _
    <Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone>206-555-0144</Phone>
            <Address>
                <Street1>123 Main St</Street1>
                <City>Mercer Island</City>
                <State>WA</State>
                <Postal>68042</Postal>
            </Address>
        </Contact>
    </Contacts>
```

## <a name="example-use-xml-literals-to-create-an-xelement-with-simple-content"></a><span data-ttu-id="e28e4-108">Przykład: Użyj literałów XML, aby utworzyć XElement z prostą zawartością</span><span class="sxs-lookup"><span data-stu-id="e28e4-108">Example: Use XML literals to create an XElement with simple content</span></span>

<span data-ttu-id="e28e4-109">Można utworzyć obiekt zawierający <xref:System.Xml.Linq.XElement> prostą zawartość w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="e28e4-109">You can create an <xref:System.Xml.Linq.XElement> that contains simple content, as follows:</span></span>

```vb
Dim n as XElement = <Customer>Adventure Works</Customer>
Console.WriteLine(n)
```

<span data-ttu-id="e28e4-110">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="e28e4-110">This example produces the following output:</span></span>

```xml
<Customer>Adventure Works</Customer>
```

## <a name="example-use-an-xml-literal-to-create-an-empty-element"></a><span data-ttu-id="e28e4-111">Przykład: Użyj literału XML do utworzenia pustego elementu</span><span class="sxs-lookup"><span data-stu-id="e28e4-111">Example: Use an XML literal to create an empty element</span></span>

<span data-ttu-id="e28e4-112">Można utworzyć pustą <xref:System.Xml.Linq.XElement> w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="e28e4-112">You can create an empty <xref:System.Xml.Linq.XElement>, as follows:</span></span>

```vb
Dim n As XElement = <Customer/>
Console.WriteLine(n)
```

<span data-ttu-id="e28e4-113">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="e28e4-113">This example produces the following output:</span></span>

```xml
<Customer />
```

## <a name="use-embedded-expressions-to-create-content"></a><span data-ttu-id="e28e4-114">Tworzenie zawartości za pomocą osadzonych wyrażeń</span><span class="sxs-lookup"><span data-stu-id="e28e4-114">Use embedded expressions to create content</span></span>

<span data-ttu-id="e28e4-115">Ważną funkcją literałów XML jest to, że dopuszczają one osadzone wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="e28e4-115">An important feature of XML literals is that they allow embedded expressions.</span></span> <span data-ttu-id="e28e4-116">Wyrażenia osadzone umożliwiają ocenę wyrażenia i wstawianie wyników wyrażenia do drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="e28e4-116">Embedded expressions enable you to evaluate an expression and insert the results of the expression into the XML tree.</span></span> <span data-ttu-id="e28e4-117">Jeśli wyrażenie szacuje typ <xref:System.Xml.Linq.XElement> , element zostanie wstawiony do drzewa.</span><span class="sxs-lookup"><span data-stu-id="e28e4-117">If the expression evaluates to a type of <xref:System.Xml.Linq.XElement>, an element is inserted into the tree.</span></span> <span data-ttu-id="e28e4-118">Jeśli wyrażenie szacuje typ <xref:System.Xml.Linq.XAttribute> , atrybut zostanie wstawiony do drzewa.</span><span class="sxs-lookup"><span data-stu-id="e28e4-118">If the expression evaluates to a type of <xref:System.Xml.Linq.XAttribute>, an attribute is inserted into the tree.</span></span> <span data-ttu-id="e28e4-119">Elementy i atrybuty można wstawiać do drzewa tylko wtedy, gdy są prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="e28e4-119">You can insert elements and attributes into the tree only where they're valid.</span></span>

<span data-ttu-id="e28e4-120">należy pamiętać, że tylko pojedyncze wyrażenie może przejść do wyrażenia osadzonego.</span><span class="sxs-lookup"><span data-stu-id="e28e4-120">it's important to note that only a single expression can go into an embedded expression.</span></span> <span data-ttu-id="e28e4-121">Nie można osadzić wielu instrukcji.</span><span class="sxs-lookup"><span data-stu-id="e28e4-121">You can't embed multiple statements.</span></span> <span data-ttu-id="e28e4-122">Jeśli wyrażenie wykracza poza pojedynczy wiersz, należy użyć znaku kontynuacji wiersza.</span><span class="sxs-lookup"><span data-stu-id="e28e4-122">If an expression extends beyond a single line, you must use the line continuation character.</span></span>

<span data-ttu-id="e28e4-123">Jeśli używasz wyrażenia osadzonego do dodawania istniejących węzłów (w tym elementów) i atrybutów do nowego drzewa XML i jeśli istniejące węzły są już nadrzędne, węzły są klonowane.</span><span class="sxs-lookup"><span data-stu-id="e28e4-123">If you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree and if the existing nodes are already parented, the nodes are cloned.</span></span> <span data-ttu-id="e28e4-124">Nowo sklonowane węzły są dołączone do nowego drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="e28e4-124">The newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="e28e4-125">Jeśli istniejące węzły nie są nadrzędne, węzły są po prostu dołączone do nowego drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="e28e4-125">If the existing nodes aren't parented, the nodes are simply attached to the new XML tree.</span></span> <span data-ttu-id="e28e4-126">W ostatnim przykładzie w tym artykule pokazano, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="e28e4-126">The last example in this article demonstrates this.</span></span>

## <a name="example-use-an-embedded-expression-to-insert-an-element"></a><span data-ttu-id="e28e4-127">Przykład: Użyj wyrażenia osadzonego do wstawienia elementu</span><span class="sxs-lookup"><span data-stu-id="e28e4-127">Example: Use an embedded expression to insert an element</span></span>

<span data-ttu-id="e28e4-128">W poniższym przykładzie do wstawienia elementu do drzewa jest stosowane wyrażenie osadzone:</span><span class="sxs-lookup"><span data-stu-id="e28e4-128">The following example uses an embedded expression to insert an element into the tree:</span></span>

```vb
xmlTree1 As XElement = _
    <Root>
        <Child>Contents</Child>
    </Root>
Dim xmlTree2 As XElement = _
    <Root>
        <%= xmlTree1.<Child> %>
    </Root>
Console.WriteLine(xmlTree2)
```

<span data-ttu-id="e28e4-129">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="e28e4-129">This example produces the following output:</span></span>

```xml
<Root>
  <Child>Contents</Child>
</Root>
```

## <a name="example-use-an-embedded-expression-for-content"></a><span data-ttu-id="e28e4-130">Przykład: Użyj wyrażenia osadzonego dla zawartości</span><span class="sxs-lookup"><span data-stu-id="e28e4-130">Example: Use an embedded expression for content</span></span>

<span data-ttu-id="e28e4-131">Możesz użyć wyrażenia osadzonego, aby dostarczyć zawartość elementu:</span><span class="sxs-lookup"><span data-stu-id="e28e4-131">You can use an embedded expression to supply the content of an element:</span></span>

```vb
Dim str As String
str = "Some content"
Dim root As XElement = <Root><%= str %></Root>
Console.WriteLine(root)
```

<span data-ttu-id="e28e4-132">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="e28e4-132">This example produces the following output:</span></span>

```xml
<Root>Some content</Root>
```

## <a name="example-use-a-linq-query-in-an-embedded-expression"></a><span data-ttu-id="e28e4-133">Przykład: użycie zapytania LINQ w wyrażeniu osadzonym</span><span class="sxs-lookup"><span data-stu-id="e28e4-133">Example: Use a LINQ query in an embedded expression</span></span>

<span data-ttu-id="e28e4-134">Wyniki zapytania LINQ można użyć do udostępnienia zawartości elementu:</span><span class="sxs-lookup"><span data-stu-id="e28e4-134">You can use the results of a LINQ query to provide the content of an element:</span></span>

```vb
Dim arr As Integer() = {1, 2, 3}

Dim n As XElement = _
    <Root>
        <%= From i In arr Select <Child><%= i %></Child> %>
    </Root>

Console.WriteLine(n)
```

<span data-ttu-id="e28e4-135">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="e28e4-135">This example produces the following output:</span></span>

```xml
<Root>
  <Child>1</Child>
  <Child>2</Child>
  <Child>3</Child>
</Root>
```

## <a name="example-use-an-embedded-expression-to-provide-node-names"></a><span data-ttu-id="e28e4-136">Przykład: Użyj wyrażenia osadzonego, aby podać nazwy węzłów</span><span class="sxs-lookup"><span data-stu-id="e28e4-136">Example: Use an embedded expression to provide node names</span></span>

<span data-ttu-id="e28e4-137">Można również użyć wyrażenia osadzonego do obliczania nazw atrybutów, wartości atrybutów, nazw elementów i wartości elementów:</span><span class="sxs-lookup"><span data-stu-id="e28e4-137">You can also use an embedded expression to calculate attribute names, attribute values, element names, and element values:</span></span>

```vb
Dim eleName As String = "ele"
Dim attName As String = "att"
Dim attValue As String = "aValue"
Dim eleValue As String = "eValue"
Dim n As XElement = _
    <Root <%= attName %>=<%= attValue %>>
        <<%= eleName %>>
            <%= eleValue %>
        </>
    </Root>
Console.WriteLine(n)
```

<span data-ttu-id="e28e4-138">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="e28e4-138">This example produces the following output:</span></span>

```xml
<Root att="aValue">
  <ele>eValue</ele>
</Root>
```

## <a name="example-use-an-embedded-expression-to-clone-and-attach-nodes"></a><span data-ttu-id="e28e4-139">Przykład: Użyj wyrażenia osadzonego do klonowania i dołączania węzłów</span><span class="sxs-lookup"><span data-stu-id="e28e4-139">Example: Use an embedded expression to clone and attach nodes</span></span>

<span data-ttu-id="e28e4-140">Jak wspomniano wcześniej, jeśli używasz wyrażenia osadzonego do dodawania istniejących węzłów (w tym elementów) i atrybutów do nowego drzewa XML, a węzły dodawane do węzłów są już nadrzędne, węzły są klonowane i klony są dołączone do nowego drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="e28e4-140">As mentioned earlier, if you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree, and if the nodes being added nodes are already parented, the nodes are cloned and the clones are attached to the new XML tree.</span></span> <span data-ttu-id="e28e4-141">Jeśli istniejące węzły nie są nadrzędne, są po prostu dołączone do nowego drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="e28e4-141">If the existing nodes aren't parented, they're simply attached to the new XML tree.</span></span>

<span data-ttu-id="e28e4-142">Poniższy kod ilustruje zachowanie po dodaniu elementu nadrzędnego do drzewa i po dodaniu elementu z elementem nadrzędnym do drzewa.</span><span class="sxs-lookup"><span data-stu-id="e28e4-142">The following code demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>

```vb
' Create a tree with a child element.
Dim xmlTree1 As XElement = _
    <Root>
        <Child1>1</Child1>
    </Root>

' Create an element that's not parented.
Dim child2 As XElement = <Child2>2</Child2>

' Create a tree and add Child1 and Child2 to it.
Dim xmlTree2 As XElement = _
    <Root>
        <%= xmlTree1.<Child1>(0) %>
        <%= child2 %>
    </Root>

' Compare Child1 identity.
Console.WriteLine("Child1 was {0}", _
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _
    "attached", "cloned"))

' Compare Child2 identity.
Console.WriteLine("Child2 was {0}", _
    IIf(child2 Is xmlTree2.Element("Child2"), _
    "attached", "cloned"))
```

<span data-ttu-id="e28e4-143">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="e28e4-143">This example produces the following output:</span></span>

```output
Child1 was cloned
Child2 was attached
```

## <a name="see-also"></a><span data-ttu-id="e28e4-144">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e28e4-144">See also</span></span>

- [<span data-ttu-id="e28e4-145">Konstrukcja funkcjonalna</span><span class="sxs-lookup"><span data-stu-id="e28e4-145">Functional construction</span></span>](functional-construction.md)
