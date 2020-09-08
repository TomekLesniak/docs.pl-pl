---
title: Jak wypełnić drzewo XML elementem XmlWriter LINQ to XML
description: Aby wypełnić drzewo XML w języku C# i Visual Basic, Utwórz element XMLWriter przy użyciu funkcji tworzenia i zapisu do elementu XmlWriter.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
ms.openlocfilehash: 3f8005eca009ae5f2102444a5494336d2caa2450
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553456"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml"></a><span data-ttu-id="74b67-103">Wypełnianie drzewa XML elementem XmlWriter (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="74b67-103">How to populate an XML tree with an XmlWriter (LINQ to XML)</span></span>

<span data-ttu-id="74b67-104">Jednym ze sposobów wypełnienia drzewa XML jest użycie <xref:System.Xml.Linq.XContainer.CreateWriter%2A> do utworzenia <xref:System.Xml.XmlWriter> , a następnie zapisanie w <xref:System.Xml.XmlWriter> .</span><span class="sxs-lookup"><span data-stu-id="74b67-104">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="74b67-105">Drzewo XML jest wypełniane wszystkimi węzłami, które są zapisywane w <xref:System.Xml.XmlWriter> .</span><span class="sxs-lookup"><span data-stu-id="74b67-105">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>

<span data-ttu-id="74b67-106">Ta metoda jest zwykle używana w przypadku używania LINQ to XML z inną klasą, która oczekuje na zapis w, na przykład <xref:System.Xml.XmlWriter> <xref:System.Xml.Xsl.XslCompiledTransform> .</span><span class="sxs-lookup"><span data-stu-id="74b67-106">You'd typically use this method when you use LINQ to XML with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>

## <a name="example-create-an-xmlwriter-to-accept-the-output-of-an-xslt-transformation"></a><span data-ttu-id="74b67-107">Przykład: Tworzenie elementu XmlWriter do akceptowania danych wyjściowych transformacji XSLT</span><span class="sxs-lookup"><span data-stu-id="74b67-107">Example: Create an XmlWriter to accept the output of an XSLT transformation</span></span>

<span data-ttu-id="74b67-108">Za pomocą programu można <xref:System.Xml.Linq.XContainer.CreateWriter%2A> utworzyć element, <xref:System.Xml.XmlWriter> Aby akceptować dane wyjściowe transformacji XSLT.</span><span class="sxs-lookup"><span data-stu-id="74b67-108">You can use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter> to accept the output of an XSLT transformation.</span></span> <span data-ttu-id="74b67-109">Jest to pokazane w poniższym przykładzie, który wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="74b67-109">This is shown in the following example, which does the following:</span></span>

- <span data-ttu-id="74b67-110">Tworzy drzewo XML i <xref:System.Xml.XmlReader> do odczytu z niego.</span><span class="sxs-lookup"><span data-stu-id="74b67-110">Creates an XML tree and an <xref:System.Xml.XmlReader> to read from it.</span></span>
- <span data-ttu-id="74b67-111">Tworzy nowe drzewo i zapisuje w <xref:System.Xml.XmlWriter> nim.</span><span class="sxs-lookup"><span data-stu-id="74b67-111">Creates a new tree and an <xref:System.Xml.XmlWriter> to write to it.</span></span>
- <span data-ttu-id="74b67-112">Wywołuje transformację XSLT, dostarczając ją z  <xref:System.Xml.XmlReader> i <xref:System.Xml.XmlWriter> .</span><span class="sxs-lookup"><span data-stu-id="74b67-112">Invokes the XSLT transformation, providing it with the  <xref:System.Xml.XmlReader> and the <xref:System.Xml.XmlWriter>.</span></span>

<span data-ttu-id="74b67-113">Przekształcenie wypełnia następnie nowe drzewo.</span><span class="sxs-lookup"><span data-stu-id="74b67-113">The transformation then populates the new tree.</span></span>

```csharp
string xslMarkup = @"<?xml version='1.0'?>
<xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>
    <xsl:template match='/Parent'>
        <Root>
            <C1>
            <xsl:value-of select='Child1'/>
            </C1>
            <C2>
            <xsl:value-of select='Child2'/>
            </C2>
        </Root>
    </xsl:template>
</xsl:stylesheet>";

XDocument xmlTree = new XDocument(
    new XElement("Parent",
        new XElement("Child1", "Child1 data"),
        new XElement("Child2", "Child2 data")
    )
);

XDocument newTree = new XDocument();
using (XmlWriter writer = newTree.CreateWriter())
{
    // Load the style sheet.
    XslCompiledTransform xslt = new XslCompiledTransform();
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));

    // Execute the transformation and output the results to a writer.
    xslt.Transform(xmlTree.CreateReader(), writer);
}

Console.WriteLine(newTree);
```

```vb
Dim xslMarkup As XDocument = _
    <?xml version='1.0'?>
    <xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>
        <xsl:template match='/Parent'>
            <Root>
                <C1>
                    <xsl:value-of select='Child1'/>
                </C1>
                <C2>
                    <xsl:value-of select='Child2'/>
                </C2>
            </Root>
        </xsl:template>
    </xsl:stylesheet>

Dim xmlTree As XDocument = _
    <?xml version='1.0'?>
    <Parent>
        <Child1>Child1 data</Child1>
        <Child2>Child2 data</Child2>
    </Parent>

Dim newTree As XDocument = New XDocument()
Using writer As XmlWriter = newTree.CreateWriter()
    ' Load the style sheet.
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()
    xslt.Load(xslMarkup.CreateReader())

    ' Execute the transformation and output the results to a writer.
    xslt.Transform(xmlTree.CreateReader(), writer)
End Using

Console.WriteLine(newTree)
```

<span data-ttu-id="74b67-114">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="74b67-114">This example produces the following output:</span></span>

```xml
<Root>
  <C1>Child1 data</C1>
  <C2>Child2 data</C2>
</Root>
```

## <a name="see-also"></a><span data-ttu-id="74b67-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="74b67-115">See also</span></span>

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="74b67-116">Drzewa XML</span><span class="sxs-lookup"><span data-stu-id="74b67-116">XML trees</span></span>](functional-construction.md)
