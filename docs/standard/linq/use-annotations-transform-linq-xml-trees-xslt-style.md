---
title: Jak używać adnotacji do przekształcania drzew LINQ to XML w stylu XSLT — LINQ to XML
description: Dowiedz się, jak używać adnotacji do przekształcania dokumentów XML, które są zorientowane na dokumenty z zawartością mieszaną.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 12a95902-a6b7-4a1e-ad52-04a518db226f
ms.openlocfilehash: 3cecc1b868983f1fa19d29d4bf5e73182a1af295
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553137"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-linq-to-xml"></a><span data-ttu-id="47945-103">Jak używać adnotacji do przekształcania drzew LINQ to XML w stylu XSLT (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="47945-103">How to use annotations to transform LINQ to XML trees in an XSLT style (LINQ to XML)</span></span>

<span data-ttu-id="47945-104">Adnotacje mogą służyć do ułatwienia transformacji drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="47945-104">Annotations can be used to facilitate transforms of an XML tree.</span></span>

<span data-ttu-id="47945-105">Niektóre dokumenty XML są "skoncentrowane na dokumentach z zawartością mieszaną".</span><span class="sxs-lookup"><span data-stu-id="47945-105">Some XML documents are "document-centric with mixed content."</span></span> <span data-ttu-id="47945-106">W takich dokumentach nie trzeba znać kształtu węzłów podrzędnych elementu.</span><span class="sxs-lookup"><span data-stu-id="47945-106">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="47945-107">Na przykład węzeł zawierający tekst może wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="47945-107">For instance, a node that contains text may look like this:</span></span>

```xml
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>
```

<span data-ttu-id="47945-108">Dla dowolnego węzła tekstowego może istnieć wiele `<b>` elementów podrzędnych i `<i>` .</span><span class="sxs-lookup"><span data-stu-id="47945-108">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="47945-109">Takie podejście rozciąga się do wielu innych sytuacji, takich jak strony, które mogą zawierać różne elementy podrzędne, które mogą być zwykłymi akapitami, akapitami punktowanymi i mapami bitowymi.</span><span class="sxs-lookup"><span data-stu-id="47945-109">This approach extends to a number of other situations, such as pages that can contain a variety of child elements, which could be regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="47945-110">Komórki w tabeli mogą zawierać tekst, listy rozwijane lub mapy bitowe.</span><span class="sxs-lookup"><span data-stu-id="47945-110">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="47945-111">Jedną z podstawowych cech XML zorientowanym na dokumenty jest to, że nie wiesz, który element podrzędny ma jakikolwiek określony element.</span><span class="sxs-lookup"><span data-stu-id="47945-111">One of the primary characteristics of document-centric XML is that you don't know which child element any particular element will have.</span></span>

<span data-ttu-id="47945-112">Jeśli chcesz przekształcić elementy w drzewie, gdzie nie ma potrzeby bardzo często wiedzieć o elementach podrzędnych elementów, które chcesz przekształcić, to podejście, które używa adnotacji, jest skutecznym.</span><span class="sxs-lookup"><span data-stu-id="47945-112">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective one.</span></span>

<span data-ttu-id="47945-113">Podsumowanie podejścia to:</span><span class="sxs-lookup"><span data-stu-id="47945-113">The summary of the approach is:</span></span>

- <span data-ttu-id="47945-114">Najpierw Dodaj adnotację do elementów w drzewie z elementem zastępującym.</span><span class="sxs-lookup"><span data-stu-id="47945-114">First, annotate elements in the tree with a replacement element.</span></span>
- <span data-ttu-id="47945-115">Następnie wykonaj iterację w całym drzewie, tworząc nowe drzewo, w którym każdy element jest zastępowany adnotacją.</span><span class="sxs-lookup"><span data-stu-id="47945-115">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="47945-116">Przykłady w tym artykule implementują iterację i tworzenie nowego drzewa w funkcji o nazwie `XForm` .</span><span class="sxs-lookup"><span data-stu-id="47945-116">The examples in this article implement the iteration and creation of the new tree in a function named `XForm`.</span></span>

<span data-ttu-id="47945-117">Szczegółowo podejście obejmuje:</span><span class="sxs-lookup"><span data-stu-id="47945-117">In detail, the approach consists of:</span></span>

- <span data-ttu-id="47945-118">Wykonaj co najmniej jedno LINQ to XML zapytania, które zwracają zestaw elementów, które chcesz przekształcić z jednego kształtu do drugiego.</span><span class="sxs-lookup"><span data-stu-id="47945-118">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="47945-119">Dla każdego elementu w zapytaniu Dodaj nowy <xref:System.Xml.Linq.XElement> obiekt jako adnotację do elementu.</span><span class="sxs-lookup"><span data-stu-id="47945-119">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="47945-120">Ten nowy element spowoduje zamianę elementu z adnotacją w nowym, przekształconym drzewie.</span><span class="sxs-lookup"><span data-stu-id="47945-120">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="47945-121">Jest to prosty kod do zapisu, jak pokazano na przykładzie.</span><span class="sxs-lookup"><span data-stu-id="47945-121">This is simple code to write, as demonstrated by the example.</span></span>
- <span data-ttu-id="47945-122">Nowy element, który jest dodawany jako Adnotacja może zawierać nowe węzły podrzędne; można utworzyć poddrzewo z dowolnym żądanym kształtem.</span><span class="sxs-lookup"><span data-stu-id="47945-122">The new element that's added as an annotation can contain new child nodes; it can form a subtree with any desired shape.</span></span>
- <span data-ttu-id="47945-123">Istnieje specjalna reguła: Jeśli węzeł podrzędny nowego elementu znajduje się w innej przestrzeni nazw, przestrzeń nazw, która została zastosowana do tego celu (w tym przykładzie przestrzeń nazw jest `http://www.microsoft.com/LinqToXmlTransform/2007` ), wówczas ten element podrzędny nie jest kopiowany do nowego drzewa.</span><span class="sxs-lookup"><span data-stu-id="47945-123">There is a special rule: If a child node of the new element is in a different namespace, a namespace that's made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element isn't copied to the new tree.</span></span> <span data-ttu-id="47945-124">Zamiast tego, jeśli obszar nazw jest wyżej wspomnianą specjalną przestrzenią nazw, a lokalna nazwa elementu to `ApplyTransforms` , węzły podrzędne elementu w drzewie źródłowym są powtarzane i kopiowane do nowego drzewa (z wyjątkiem tego, że elementy podrzędne z adnotacjami są same przekształcone zgodnie z tymi regułami).</span><span class="sxs-lookup"><span data-stu-id="47945-124">Instead, if the namespace is the above-mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>
- <span data-ttu-id="47945-125">Jest to nieco analogiczne do specyfikacji transformacji w kodzie XSL.</span><span class="sxs-lookup"><span data-stu-id="47945-125">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="47945-126">Zapytanie wybierające zestaw węzłów jest analogiczne do wyrażenia XPath dla szablonu.</span><span class="sxs-lookup"><span data-stu-id="47945-126">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="47945-127">Kod służący do tworzenia nowego <xref:System.Xml.Linq.XElement> , który jest zapisywany jako Adnotacja, jest analogiczny do konstruktora sekwencji w XSL, a `ApplyTransforms` element jest analogiczny w funkcji do `xsl:apply-templates` elementu w XSL.</span><span class="sxs-lookup"><span data-stu-id="47945-127">The code to create the new <xref:System.Xml.Linq.XElement> that's saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>
- <span data-ttu-id="47945-128">Jedną z zalet tego podejścia jest to, że podczas redagowania zapytań, są zawsze zapisywane zapytania w niezmodyfikowanym drzewie źródła.</span><span class="sxs-lookup"><span data-stu-id="47945-128">One advantage to taking this approach is that, as you formulate queries, you're  always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="47945-129">Nie musisz martwić się o to, jak zmiany w drzewie mają wpływ na zapisywanych zapytań.</span><span class="sxs-lookup"><span data-stu-id="47945-129">You don't need to worry about how modifications to the tree affect the queries that you're writing.</span></span>

## <a name="example-rename-all-paragraph-nodes"></a><span data-ttu-id="47945-130">Przykład: Zmień nazwę wszystkich węzłów akapitu</span><span class="sxs-lookup"><span data-stu-id="47945-130">Example: Rename all paragraph nodes</span></span>

<span data-ttu-id="47945-131">Ten przykład zmienia nazwę wszystkich `Paragraph` węzłów na `para` .</span><span class="sxs-lookup"><span data-stu-id="47945-131">This example renames all `Paragraph` nodes to `para`.</span></span>

```csharp
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";
XName at = xf + "ApplyTransforms";

XElement root = XElement.Parse(@"
<Root>
    <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>
    <Paragraph>More text.</Paragraph>
</Root>");

// replace Paragraph with para
foreach (var el in root.Descendants("Paragraph"))
    el.AddAnnotation(
        new XElement("para",
            // same idea as xsl:apply-templates
            new XElement(xf + "ApplyTransforms")
        )
    );

// The XForm method, shown later in this article, accomplishes the transform
XElement newRoot = XForm(root);

Console.WriteLine(newRoot);
```

```vb
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    Sub Main()
        Dim root As XElement = _
            <Root>
                <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>
                <Paragraph>More text.</Paragraph>
            </Root>

        ' Replace Paragraph with p.
        For Each el In root...<Paragraph>
            ' same idea as xsl:apply-templates
            el.AddAnnotation( _
                <para>
                    <<%= at %>></>
                </para>)
        Next

        ' The XForm function, shown later in this article, accomplishes the transform
        Dim newRoot As XElement = XForm(root)
        Console.WriteLine(newRoot)
    End Sub
End Module
```

<span data-ttu-id="47945-132">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="47945-132">This example produces the following output:</span></span>

```xml
<Root>
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>
  <para>More text.</para>
</Root>
```

## <a name="example-calculate-averages-and-sums-and-add-them-as-new-elements-to-the-tree"></a><span data-ttu-id="47945-133">Przykład: Oblicz średnie i sumy i Dodaj je jako nowe elementy do drzewa</span><span class="sxs-lookup"><span data-stu-id="47945-133">Example: Calculate averages and sums and add them as new elements to the tree</span></span>

<span data-ttu-id="47945-134">Poniższy przykład oblicza średnią i sumę `Data` elementów i dodaje je jako nowe elementy do drzewa.</span><span class="sxs-lookup"><span data-stu-id="47945-134">The following example calculates the average and sum of the `Data` elements and adds them as new elements to the tree.</span></span>

```csharp
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";
XName at = xf + "ApplyTransforms";

XElement data = new XElement("Root",
    new XElement("Data", 20),
    new XElement("Data", 10),
    new XElement("Data", 3)
);

// while adding annotations, you can query the source tree all you want,
// as the tree isn't mutated while annotating.
var avg = data.Elements("Data").Select(z => (Decimal)z).Average();
data.AddAnnotation(
    new XElement("Root",
        new XElement(xf + "ApplyTransforms"),
        new XElement("Average", $"{avg:F4}"),
        new XElement("Sum",
            data
            .Elements("Data")
            .Select(z => (int)z)
            .Sum()
        )
    )
);

Console.WriteLine("Before Transform");
Console.WriteLine("----------------");
Console.WriteLine(data);
Console.WriteLine();
Console.WriteLine();

// The XForm method, shown later in this article, accomplishes the transform
XElement newData = XForm(data);

Console.WriteLine("After Transform");
Console.WriteLine("----------------");
Console.WriteLine(newData);
```

```vb
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    Sub Main()
        Dim data As XElement = _
            <Root>
                <Data>20</Data>
                <Data>10</Data>
                <Data>3</Data>
            </Root>

        ' While adding annotations, you can query the source tree all you want,
        ' as the tree isn't mutated while annotating.
        data.AddAnnotation( _
            <Root>
                <<%= at %>/>
                <Average>
                    <%= _
                        String.Format("{0:F4}", _
                        data.Elements("Data") _
                        .Select(Function(z) CDec(z)).Average()) _
                    %>
                </Average>
                <Sum>
                    <%= _
                        data.Elements("Data").Select(Function(z) CInt(z)).Sum() _
                    %>
                </Sum>
            </Root> _
        )

        Console.WriteLine("Before Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(data)
        Console.WriteLine(vbNewLine)

        ' The XForm function, shown later in this article, accomplishes the transform
        Dim newData As XElement = XForm(data)

        Console.WriteLine("After Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(newData)
    End Sub
End Module
```

<span data-ttu-id="47945-135">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="47945-135">This example produces the following output:</span></span>

```output
Before Transform
----------------
<Root>
  <Data>20</Data>
  <Data>10</Data>
  <Data>3</Data>
</Root>

After Transform
----------------
<Root>
  <Data>20</Data>
  <Data>10</Data>
  <Data>3</Data>
  <Average>11.0000</Average>
  <Sum>33</Sum>
</Root>
```

## <a name="example-create-a-new-transformed-tree-from-the-original-annotated-tree"></a><span data-ttu-id="47945-136">Przykład: Utwórz nowe przekształcone drzewo z oryginalnego drzewa z adnotacjami</span><span class="sxs-lookup"><span data-stu-id="47945-136">Example: Create a new transformed tree from the original annotated tree</span></span>

<span data-ttu-id="47945-137">Mała funkcja, `XForm` , tworzy nowe przekształcone drzewo z oryginalnego drzewa z adnotacjami.</span><span class="sxs-lookup"><span data-stu-id="47945-137">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span> <span data-ttu-id="47945-138">Dla tej funkcji jest pseudokodzie następujący:</span><span class="sxs-lookup"><span data-stu-id="47945-138">The following is pseudocode for this function:</span></span>

> <span data-ttu-id="47945-139">Funkcja przyjmuje XElement jako argument i zwraca XElement.</span><span class="sxs-lookup"><span data-stu-id="47945-139">The function takes an XElement as an argument and returns an XElement.</span></span>
>
> <span data-ttu-id="47945-140">Jeśli element ma adnotację XElement, zwrócone XElement ma następujące cechy:</span><span class="sxs-lookup"><span data-stu-id="47945-140">If an element has an XElement annotation, the returned XElement has these characteristics:</span></span>
>
> - <span data-ttu-id="47945-141">Nazwa nowego XElement jest nazwą elementu adnotacji.</span><span class="sxs-lookup"><span data-stu-id="47945-141">The name of the new XElement is the annotation element's name.</span></span>
> - <span data-ttu-id="47945-142">Wszystkie atrybuty są kopiowane z adnotacji do nowego węzła.</span><span class="sxs-lookup"><span data-stu-id="47945-142">All attributes are copied from the annotation to the new node.</span></span>
> - <span data-ttu-id="47945-143">Wszystkie węzły podrzędne są kopiowane z adnotacji, z wyjątkiem tego, że jest rozpoznawany węzeł specjalny XF: ApplyTransforms, a węzły podrzędne elementu źródłowego są powtarzane.</span><span class="sxs-lookup"><span data-stu-id="47945-143">All child nodes are copied from the annotation, with the exception that the special node xf:ApplyTransforms is recognized, and the source element's child nodes are iterated.</span></span> <span data-ttu-id="47945-144">Jeśli źródłowy węzeł podrzędny nie jest XElement, jest kopiowany do nowego drzewa.</span><span class="sxs-lookup"><span data-stu-id="47945-144">If the source child node isn't an XElement, it's copied to the new tree.</span></span> <span data-ttu-id="47945-145">Jeśli źródło jest XElement, jest przekształcane przez wywołanie tej funkcji cyklicznie.</span><span class="sxs-lookup"><span data-stu-id="47945-145">If the source child is an XElement, then it's transformed by calling this function recursively.</span></span>
>
> <span data-ttu-id="47945-146">W przeciwnym razie zwrócony XElement ma następujące cechy:</span><span class="sxs-lookup"><span data-stu-id="47945-146">Otherwise, the returned XElement has these characteristics:</span></span>
>
> - <span data-ttu-id="47945-147">Nazwą nowego XElement jest nazwa elementu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="47945-147">The name of the new XElement is the source element's name.</span></span>
> - <span data-ttu-id="47945-148">Wszystkie atrybuty są kopiowane z elementu źródłowego do elementu docelowego.</span><span class="sxs-lookup"><span data-stu-id="47945-148">All attributes are copied from the source element to the destination's element.</span></span>
> - <span data-ttu-id="47945-149">Wszystkie węzły podrzędne są kopiowane z elementu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="47945-149">All child nodes are copied from the source element.</span></span>
> - <span data-ttu-id="47945-150">Jeśli źródłowy węzeł podrzędny nie jest XElement, jest kopiowany do nowego drzewa.</span><span class="sxs-lookup"><span data-stu-id="47945-150">If the source child node isn't an XElement, it's copied to the new tree.</span></span> <span data-ttu-id="47945-151">Jeśli źródło jest XElement, jest przekształcane przez wywołanie tej funkcji cyklicznie.</span><span class="sxs-lookup"><span data-stu-id="47945-151">If the source child is an XElement, then it's transformed by calling this function recursively.</span></span>

<span data-ttu-id="47945-152">Poniżej przedstawiono kod dla tej funkcji:</span><span class="sxs-lookup"><span data-stu-id="47945-152">The following is code for this function:</span></span>

```csharp
// Build a transformed XML tree per the annotations
static XElement XForm(XElement source)
{
    XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";
    XName at = xf + "ApplyTransforms";

    if (source.Annotation<XElement>() != null)
    {
        XElement anno = source.Annotation<XElement>();
        return new XElement(anno.Name,
            anno.Attributes(),
            anno
            .Nodes()
            .Select(
                (XNode n) =>
                {
                    XElement annoEl = n as XElement;
                    if (annoEl != null)
                    {
                        if (annoEl.Name == at)
                            return (object)(
                                source.Nodes()
                                .Select(
                                    (XNode n2) =>
                                    {
                                        XElement e2 = n2 as XElement;
                                        if (e2 == null)
                                            return n2;
                                        else
                                            return XForm(e2);
                                    }
                                )
                            );
                        else
                            return n;
                    }
                    else
                        return n;
                }
            )
        );
    }
    else
    {
        return new XElement(source.Name,
            source.Attributes(),
            source
                .Nodes()
                .Select(n =>
                {
                    XElement el = n as XElement;
                    if (el == null)
                        return n;
                    else
                        return XForm(el);
                }
                )
        );
    }
}
```

```vb
' Build a transformed XML tree per the annotations.
Function XForm(ByVal source As XElement) As XElement
    If source.Annotation(Of XElement)() IsNot Nothing Then
        Dim anno As XElement = source.Annotation(Of XElement)()
        Return _
            <<%= anno.Name.ToString() %>>
                <%= anno.Attributes() %>
                <%= anno.Nodes().Select(Function(n As XNode) _
                    GetSubNodes(n, source)) %>
            </>
    Else
        Return _
            <<%= source.Name %>>
                <%= source.Attributes() %>
                <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>
            </>
    End If
End Function

Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object
    Dim annoEl As XElement = TryCast(n, XElement)
    If annoEl IsNot Nothing Then
        If annoEl.Name = at Then
            Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))
        End If
    End If
    Return n
End Function

Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode
    Dim e2 As XElement = TryCast(n2, XElement)
    If e2 Is Nothing Then
        Return n2
    Else
        Return XForm(e2)
    End If
End Function
```

## <a name="example-show-xform-in-typical-uses-of-this-type-of-transform"></a><span data-ttu-id="47945-153">Przykład: Pokaż `XForm` w typowym zastosowaniu tego typu transformacji</span><span class="sxs-lookup"><span data-stu-id="47945-153">Example: Show `XForm` in typical uses of this type of transform</span></span>

<span data-ttu-id="47945-154">Poniższy przykład obejmuje `XForm` funkcję i kilka typowych zastosowania tego typu transformacji:</span><span class="sxs-lookup"><span data-stu-id="47945-154">The following example includes the `XForm` function and a few of the typical uses of this type of transform:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Xml;
using System.Xml.Linq;

class Program
{
    static XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";
    static XName at = xf + "ApplyTransforms";

    // Build a transformed XML tree per the annotations
    static XElement XForm(XElement source)
    {
        if (source.Annotation<XElement>() != null)
        {
            XElement anno = source.Annotation<XElement>();
            return new XElement(anno.Name,
                anno.Attributes(),
                anno
                .Nodes()
                .Select(
                    (XNode n) =>
                    {
                        XElement annoEl = n as XElement;
                        if (annoEl != null)
                        {
                            if (annoEl.Name == at)
                                return (object)(
                                    source.Nodes()
                                    .Select(
                                        (XNode n2) =>
                                        {
                                            XElement e2 = n2 as XElement;
                                            if (e2 == null)
                                                return n2;
                                            else
                                                return XForm(e2);
                                        }
                                    )
                                );
                            else
                                return n;
                        }
                        else
                            return n;
                    }
                )
            );
        }
        else
        {
            return new XElement(source.Name,
                source.Attributes(),
                source
                    .Nodes()
                    .Select(n =>
                    {
                        XElement el = n as XElement;
                        if (el == null)
                            return n;
                        else
                            return XForm(el);
                    }
                    )
            );
        }
    }

    static void Main(string[] args)
    {
        XElement root = new XElement("Root",
            new XComment("A comment"),
            new XAttribute("Att1", 123),
            new XElement("Child", 1),
            new XElement("Child", 2),
            new XElement("Other",
                new XElement("GC", 3),
                new XElement("GC", 4)
            ),
            XElement.Parse(
              "<SomeMixedContent>This is <i>an</i> element that " +
              "<b>has</b> some mixed content</SomeMixedContent>"),
            new XElement("AnUnchangedElement", 42)
        );

        // each of the following serves the same semantic purpose as
        // XSLT templates and sequence constructors

        // replace Child with NewChild
        foreach (var el in root.Elements("Child"))
            el.AddAnnotation(new XElement("NewChild", (string)el));

        // replace first GC with GrandChild, add an attribute
        foreach (var el in root.Descendants("GC").Take(1))
            el.AddAnnotation(
                new XElement("GrandChild",
                    new XAttribute("ANewAttribute", 999),
                    (string)el
                )
            );

        // replace Other with NewOther, add new child elements around original content
        foreach (var el in root.Elements("Other"))
            el.AddAnnotation(
                new XElement("NewOther",
                    new XElement("MyNewChild", 1),
                    // same idea as xsl:apply-templates
                    new XElement(xf + "ApplyTransforms"),
                    new XElement("ChildThatComesAfter")
                )
            );

        // change name of element that has mixed content
        root.Descendants("SomeMixedContent").First().AddAnnotation(
            new XElement("MixedContent",
                new XElement(xf + "ApplyTransforms")
            )
        );

        // replace <b> with <Bold>
        foreach (var el in root.Descendants("b"))
            el.AddAnnotation(
                new XElement("Bold",
                    new XElement(xf + "ApplyTransforms")
                )
            );

        // replace <i> with <Italic>
        foreach (var el in root.Descendants("i"))
            el.AddAnnotation(
                new XElement("Italic",
                    new XElement(xf + "ApplyTransforms")
                )
            );

        Console.WriteLine("Before Transform");
        Console.WriteLine("----------------");
        Console.WriteLine(root);
        Console.WriteLine();
        Console.WriteLine();
        XElement newRoot = XForm(root);

        Console.WriteLine("After Transform");
        Console.WriteLine("----------------");
        Console.WriteLine(newRoot);
    }
}
```

```vb
Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports System.Xml
Imports System.Xml.Linq

Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    ' Build a transformed XML tree per the annotations.
    Function XForm(ByVal source As XElement) As XElement
        If source.Annotation(Of XElement)() IsNot Nothing Then
            Dim anno As XElement = source.Annotation(Of XElement)()
            Return _
                <<%= anno.Name.ToString() %>>
                    <%= anno.Attributes() %>
                    <%= anno.Nodes().Select(Function(n As XNode) _
                        GetSubNodes(n, source)) %>
                </>
        Else
            Return _
                <<%= source.Name %>>
                    <%= source.Attributes() %>
                    <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>
                </>
        End If
    End Function

    Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object
        Dim annoEl As XElement = TryCast(n, XElement)
        If annoEl IsNot Nothing Then
            If annoEl.Name = at Then
                Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))
            End If
        End If
        Return n
    End Function

    Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode
        Dim e2 As XElement = TryCast(n2, XElement)
        If e2 Is Nothing Then
            Return n2
        Else
            Return XForm(e2)
        End If
    End Function

    Sub Main()
        Dim root As XElement = _
<Root Att1='123'>
    <!--A comment-->
    <Child>1</Child>
    <Child>2</Child>
    <Other>
        <GC>3</GC>
        <GC>4</GC>
    </Other>
    <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>
    <AnUnchangedElement>42</AnUnchangedElement>
</Root>

        ' Each of the following serves the same semantic purpose as
        ' XSLT templates and sequence constructors.

        ' Replace Child with NewChild.
        For Each el In root.<Child>
            el.AddAnnotation(<NewChild><%= CStr(el) %></NewChild>)
        Next

        ' Replace first GC with GrandChild, add an attribute.
        For Each el In root...<GC>.Take(1)
            el.AddAnnotation(<GrandChild ANewAttribute='999'><%= CStr(el) %></GrandChild>)
        Next

        ' Replace Other with NewOther, add new child elements around original content.
        For Each el In root.<Other>
            el.AddAnnotation( _
                <NewOther>
                    <MyNewChild>1</MyNewChild>
                    <<%= at %>></>
                    <ChildThatComesAfter/>
                </NewOther>)
        Next

        ' Change name of element that has mixed content.
        root...<SomeMixedContent>(0).AddAnnotation( _
                <MixedContent><<%= at %>></></MixedContent>)

        ' Replace <b> with <Bold>.
        For Each el In root...<b>
            el.AddAnnotation(<Bold><<%= at %>></></Bold>)
        Next

        ' Replace <i> with <Italic>.
        For Each el In root...<i>
            el.AddAnnotation(<Italic><<%= at %>></></Italic>)
        Next

        Console.WriteLine("Before Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(root)
        Console.WriteLine(vbNewLine)
        Dim newRoot As XElement = XForm(root)

        Console.WriteLine("After Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(newRoot)
    End Sub
End Module
```

<span data-ttu-id="47945-155">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="47945-155">This example produces the following output:</span></span>

```output
Before Transform
----------------
<Root Att1="123">
  <!--A comment-->
  <Child>1</Child>
  <Child>2</Child>
  <Other>
    <GC>3</GC>
    <GC>4</GC>
  </Other>
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>
  <AnUnchangedElement>42</AnUnchangedElement>
</Root>

After Transform
----------------
<Root Att1="123">
  <!--A comment-->
  <NewChild>1</NewChild>
  <NewChild>2</NewChild>
  <NewOther>
    <MyNewChild>1</MyNewChild>
    <GrandChild ANewAttribute="999">3</GrandChild>
    <GC>4</GC>
    <ChildThatComesAfter />
  </NewOther>
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>
  <AnUnchangedElement>42</AnUnchangedElement>
</Root>
```
