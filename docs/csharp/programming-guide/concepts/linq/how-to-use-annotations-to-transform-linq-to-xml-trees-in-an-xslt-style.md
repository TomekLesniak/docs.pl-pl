---
title: Jak używać adnotacji do przekształcania drzew LINQ to XML w stylu XSLT (C#)
description: Dowiedz się, jak przetwarzać drzewa LINQ to XML w stylu XSLT przy użyciu adnotacji. Zobacz przykład przekształcenia drzewa przy użyciu funkcji XForm.
ms.date: 07/20/2015
ms.assetid: 12a95902-a6b7-4a1e-ad52-04a518db226f
ms.openlocfilehash: 844ca08cb2c6b47f7803d388663daeacb65bdb68
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302883"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-c"></a><span data-ttu-id="10895-104">Jak używać adnotacji do przekształcania drzew LINQ to XML w stylu XSLT (C#)</span><span class="sxs-lookup"><span data-stu-id="10895-104">How to use annotations to transform LINQ to XML trees in an XSLT style (C#)</span></span>
<span data-ttu-id="10895-105">Adnotacje mogą służyć do ułatwienia transformacji drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="10895-105">Annotations can be used to facilitate transforms of an XML tree.</span></span>  
  
 <span data-ttu-id="10895-106">Niektóre dokumenty XML to "dokument zorientowany na zawartość mieszaną".</span><span class="sxs-lookup"><span data-stu-id="10895-106">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="10895-107">W takich dokumentach nie trzeba znać kształtu węzłów podrzędnych elementu.</span><span class="sxs-lookup"><span data-stu-id="10895-107">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="10895-108">Na przykład węzeł zawierający tekst może wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="10895-108">For instance, a node that contains text may look like this:</span></span>  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 <span data-ttu-id="10895-109">Dla dowolnego węzła tekstowego może istnieć wiele `<b>` elementów podrzędnych i `<i>` .</span><span class="sxs-lookup"><span data-stu-id="10895-109">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="10895-110">Takie podejście rozciąga się do wielu innych sytuacji, takich jak strony, które mogą zawierać różne elementy podrzędne, takie jak regularne akapity, punktowane akapity i mapy bitowe.</span><span class="sxs-lookup"><span data-stu-id="10895-110">This approach extends to a number of other situations, such as pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="10895-111">Komórki w tabeli mogą zawierać tekst, listy rozwijane lub mapy bitowe.</span><span class="sxs-lookup"><span data-stu-id="10895-111">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="10895-112">Jedną z podstawowych cech języka XML zorientowanego na dokument jest to, że nie wiesz, który element podrzędny ma określony element.</span><span class="sxs-lookup"><span data-stu-id="10895-112">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>  
  
 <span data-ttu-id="10895-113">Jeśli chcesz przekształcić elementy w drzewie, w której nie ma potrzeby bardzo często wiedzieć o elementach podrzędnych elementów, które chcesz przekształcić, to podejście wykorzystujące adnotacje jest skutecznym podejściem.</span><span class="sxs-lookup"><span data-stu-id="10895-113">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>  
  
 <span data-ttu-id="10895-114">Podsumowanie podejścia to:</span><span class="sxs-lookup"><span data-stu-id="10895-114">The summary of the approach is:</span></span>  
  
- <span data-ttu-id="10895-115">Najpierw Dodaj adnotację do elementów w drzewie z elementem zastępującym.</span><span class="sxs-lookup"><span data-stu-id="10895-115">First, annotate elements in the tree with a replacement element.</span></span>  
  
- <span data-ttu-id="10895-116">Następnie wykonaj iterację w całym drzewie, tworząc nowe drzewo, w którym każdy element jest zastępowany adnotacją.</span><span class="sxs-lookup"><span data-stu-id="10895-116">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="10895-117">Ten przykład implementuje iterację i tworzenie nowego drzewa w funkcji o nazwie `XForm` .</span><span class="sxs-lookup"><span data-stu-id="10895-117">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>  
  
 <span data-ttu-id="10895-118">Szczegółowo podejście obejmuje:</span><span class="sxs-lookup"><span data-stu-id="10895-118">In detail, the approach consists of:</span></span>  
  
- <span data-ttu-id="10895-119">Wykonaj co najmniej jedno LINQ to XML zapytania, które zwracają zestaw elementów, które chcesz przekształcić z jednego kształtu do drugiego.</span><span class="sxs-lookup"><span data-stu-id="10895-119">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="10895-120">Dla każdego elementu w zapytaniu Dodaj nowy <xref:System.Xml.Linq.XElement> obiekt jako adnotację do elementu.</span><span class="sxs-lookup"><span data-stu-id="10895-120">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="10895-121">Ten nowy element spowoduje zamianę elementu z adnotacją w nowym, przekształconym drzewie.</span><span class="sxs-lookup"><span data-stu-id="10895-121">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="10895-122">Jest to prosty kod do zapisu, jak pokazano na przykładzie.</span><span class="sxs-lookup"><span data-stu-id="10895-122">This is simple code to write, as demonstrated by the example.</span></span>  
  
- <span data-ttu-id="10895-123">Nowy element, który jest dodawany jako Adnotacja może zawierać nowe węzły podrzędne; można utworzyć poddrzewo z dowolnym żądanym kształtem.</span><span class="sxs-lookup"><span data-stu-id="10895-123">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>  
  
- <span data-ttu-id="10895-124">Istnieje specjalna reguła: Jeśli węzeł podrzędny nowego elementu znajduje się w innej przestrzeni nazw, przestrzeń nazw, która została wprowadzona do tego celu (w tym przykładzie przestrzeń nazw to `http://www.microsoft.com/LinqToXmlTransform/2007` ), ten element podrzędny nie jest kopiowany do nowego drzewa.</span><span class="sxs-lookup"><span data-stu-id="10895-124">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="10895-125">Zamiast tego, jeśli obszar nazw jest wyżej wspomnianą specjalną przestrzenią nazw, a lokalna nazwa elementu to `ApplyTransforms` , węzły podrzędne elementu w drzewie źródłowym są powtarzane i kopiowane do nowego drzewa (z wyjątkiem tego, że elementy podrzędne z adnotacjami są same przekształcone zgodnie z tymi regułami).</span><span class="sxs-lookup"><span data-stu-id="10895-125">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>  
  
- <span data-ttu-id="10895-126">Jest to nieco analogiczne do specyfikacji transformacji w kodzie XSL.</span><span class="sxs-lookup"><span data-stu-id="10895-126">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="10895-127">Zapytanie wybierające zestaw węzłów jest analogiczne do wyrażenia XPath dla szablonu.</span><span class="sxs-lookup"><span data-stu-id="10895-127">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="10895-128">Kod służący do tworzenia nowego <xref:System.Xml.Linq.XElement> , który jest zapisywany jako Adnotacja, jest analogiczny do konstruktora sekwencji w XSL, a `ApplyTransforms` element jest analogiczny w funkcji do `xsl:apply-templates` elementu w XSL.</span><span class="sxs-lookup"><span data-stu-id="10895-128">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>  
  
- <span data-ttu-id="10895-129">Jedną z zalet tego podejścia — podczas redagowania zapytań są zawsze zapisywane zapytania w niezmodyfikowanym drzewie źródła.</span><span class="sxs-lookup"><span data-stu-id="10895-129">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="10895-130">Nie musisz martwić się o to, jak zmiany w drzewie mają wpływ na zapisywanych zapytań.</span><span class="sxs-lookup"><span data-stu-id="10895-130">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>  
  
## <a name="transforming-a-tree"></a><span data-ttu-id="10895-131">Przekształcanie drzewa</span><span class="sxs-lookup"><span data-stu-id="10895-131">Transforming a Tree</span></span>  
 <span data-ttu-id="10895-132">W pierwszym przykładzie nazwa wszystkie węzły są zmieniane `Paragraph` na `para` .</span><span class="sxs-lookup"><span data-stu-id="10895-132">This first example renames all `Paragraph` nodes to `para`.</span></span>  
  
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
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newRoot = XForm(root);  
  
Console.WriteLine(newRoot);  
```  
  
 <span data-ttu-id="10895-133">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="10895-133">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a><span data-ttu-id="10895-134">Bardziej skomplikowana transformacja</span><span class="sxs-lookup"><span data-stu-id="10895-134">A More Complicated Transform</span></span>  
 <span data-ttu-id="10895-135">Poniższy przykład wykonuje zapytanie do drzewa i oblicza średnią i sumę `Data` elementów i dodaje je jako nowe elementy do drzewa.</span><span class="sxs-lookup"><span data-stu-id="10895-135">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement data = new XElement("Root",  
    new XElement("Data", 20),  
    new XElement("Data", 10),  
    new XElement("Data", 3)  
);  
  
// while adding annotations, you can query the source tree all you want,  
// as the tree is not mutated while annotating.
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
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newData = XForm(data);  
  
Console.WriteLine("After Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(newData);  
```  
  
 <span data-ttu-id="10895-136">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="10895-136">This example produces the following output:</span></span>  
  
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
  
## <a name="effecting-the-transform"></a><span data-ttu-id="10895-137">Efekt przekształcenia</span><span class="sxs-lookup"><span data-stu-id="10895-137">Effecting the Transform</span></span>  
 <span data-ttu-id="10895-138">Mała funkcja, `XForm` , tworzy nowe przekształcone drzewo z oryginalnego drzewa z adnotacjami.</span><span class="sxs-lookup"><span data-stu-id="10895-138">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>  
  
- <span data-ttu-id="10895-139">Pseudo kod dla funkcji jest bardzo prosty:</span><span class="sxs-lookup"><span data-stu-id="10895-139">The pseudo code for the function is quite simple:</span></span>  
  
```text  
The function takes an XElement as an argument and returns an XElement.
If an element has an XElement annotation, then  
    Return a new XElement  
        The name of the new XElement is the annotation element's name.  
        All attributes are copied from the annotation to the new node.  
        All child nodes are copied from the annotation, with the  
            exception that the special node xf:ApplyTransforms is  
            recognized, and the source element's child nodes are  
            iterated. If the source child node is not an XElement, it  
            is copied to the new tree. If the source child is an  
            XElement, then it is transformed by calling this function  
            recursively.  
If an element is not annotated  
    Return a new XElement  
        The name of the new XElement is the source element's name  
        All attributes are copied from the source element to the  
            destination's element.  
        All child nodes are copied from the source element.  
        If the source child node is not an XElement, it is copied to  
            the new tree. If the source child is an XElement, then it  
            is transformed by calling this function recursively.  
```  
  
 <span data-ttu-id="10895-140">Poniżej przedstawiono implementację tej funkcji:</span><span class="sxs-lookup"><span data-stu-id="10895-140">Following is the implementation of this function:</span></span>  
  
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
  
## <a name="complete-example"></a><span data-ttu-id="10895-141">Kompletny przykład</span><span class="sxs-lookup"><span data-stu-id="10895-141">Complete Example</span></span>  
 <span data-ttu-id="10895-142">Poniższy kod jest kompletnym przykładem zawierającym `XForm` funkcję.</span><span class="sxs-lookup"><span data-stu-id="10895-142">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="10895-143">Zawiera kilka typowych zastosowania tego typu transformacji:</span><span class="sxs-lookup"><span data-stu-id="10895-143">It includes a few of the typical uses of this type of transform:</span></span>  
  
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
  
 <span data-ttu-id="10895-144">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="10895-144">This example produces the following output:</span></span>  
  
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
  