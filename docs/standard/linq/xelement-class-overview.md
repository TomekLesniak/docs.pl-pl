---
title: XElement, Klasa — Omówienie
description: Klasa XElement reprezentuje elementy XML. Można jej użyć do tworzenia i zmieniania elementów, dodawania atrybutów i elementów podrzędnych oraz do serializacji.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: 325afd09661532fe44aecf89fe9784520274638e
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553128"
---
# <a name="xelement-class-overview"></a><span data-ttu-id="4cf7d-104">XElement, Klasa — Omówienie</span><span class="sxs-lookup"><span data-stu-id="4cf7d-104">XElement class overview</span></span>

<span data-ttu-id="4cf7d-105"><xref:System.Xml.Linq.XElement>Klasa jest jedną z podstawowych klas w LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-105">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in LINQ to XML.</span></span> <span data-ttu-id="4cf7d-106">Reprezentuje element XML.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-106">It represents an XML element.</span></span> <span data-ttu-id="4cf7d-107">Na poniższej liście przedstawiono, co można użyć w tej klasie:</span><span class="sxs-lookup"><span data-stu-id="4cf7d-107">The following list shows what you can use this class for:</span></span>

- <span data-ttu-id="4cf7d-108">Utwórz elementy.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-108">Create elements.</span></span>
- <span data-ttu-id="4cf7d-109">Zmień zawartość elementu.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-109">Change the content of the element.</span></span>
- <span data-ttu-id="4cf7d-110">Dodawanie, zmienianie lub usuwanie elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-110">Add, change, or delete child elements.</span></span>
- <span data-ttu-id="4cf7d-111">Dodaj atrybuty do elementu.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-111">Add attributes to an element.</span></span>
- <span data-ttu-id="4cf7d-112">Serializacja zawartości elementu w postaci tekstu.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-112">Serialize the contents of an element in text form.</span></span>

<span data-ttu-id="4cf7d-113">Możesz również współpracować z innymi klasami w <xref:System.Xml?displayProperty=nameWithType> , takich jak <xref:System.Xml.XmlReader> , <xref:System.Xml.XmlWriter> , i <xref:System.Xml.Xsl.XslCompiledTransform> .</span><span class="sxs-lookup"><span data-stu-id="4cf7d-113">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>

<span data-ttu-id="4cf7d-114">W tym artykule opisano funkcje dostarczone przez <xref:System.Xml.Linq.XElement> klasę.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-114">This article describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>

## <a name="construct-xml-trees"></a><span data-ttu-id="4cf7d-115">Konstruowanie drzew XML</span><span class="sxs-lookup"><span data-stu-id="4cf7d-115">Construct XML trees</span></span>

<span data-ttu-id="4cf7d-116">Drzewa XML można konstruować na różne sposoby, w tym następujące:</span><span class="sxs-lookup"><span data-stu-id="4cf7d-116">You can construct XML trees in different ways, including the following:</span></span>

- <span data-ttu-id="4cf7d-117">Drzewo XML można skonstruować w kodzie.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-117">You can construct an XML tree in code.</span></span> <span data-ttu-id="4cf7d-118">Aby uzyskać więcej informacji, zobacz [drzewa XML](functional-construction.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7d-118">For more information, see [XML trees](functional-construction.md).</span></span>
- <span data-ttu-id="4cf7d-119">Można analizować XML z różnych źródeł, w tym <xref:System.IO.TextReader> plików tekstowych lub adresów sieci Web (URL).</span><span class="sxs-lookup"><span data-stu-id="4cf7d-119">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="4cf7d-120">Aby uzyskać więcej informacji, zobacz [Analizowanie XML](parse-string.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7d-120">For more information, see [Parse XML](parse-string.md).</span></span>
- <span data-ttu-id="4cf7d-121"><xref:System.Xml.XmlReader>Aby wypełnić drzewo, można użyć elementu.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-121">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="4cf7d-122">Aby uzyskać więcej informacji, zobacz <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-122">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>
- <span data-ttu-id="4cf7d-123">Jeśli masz moduł, który może zapisywać zawartość w <xref:System.Xml.XmlWriter> programie, możesz użyć <xref:System.Xml.Linq.XContainer.CreateWriter%2A> metody do utworzenia składnika zapisywania, przekazania składnika zapisywania do modułu, a następnie użyć zawartości zapisanej w programie w <xref:System.Xml.XmlWriter> celu wypełnienia drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-123">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that's written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>

<span data-ttu-id="4cf7d-124">Poniższy przykład tworzy drzewo.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-124">The following example creates a tree.</span></span> <span data-ttu-id="4cf7d-125">Wersja języka C# używa zagnieżdżonych operacji tworzenia elementów.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-125">The C# version uses nested element creations.</span></span> <span data-ttu-id="4cf7d-126">Możesz użyć tej samej techniki w Visual Basic, ale w tym przykładzie użyto literałów XML.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-126">You can use the same technique in Visual Basic, but this example uses XML literals.</span></span>

```csharp
XElement contacts =
    new XElement("Contacts",
        new XElement("Contact",
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),
            new XElement("Address",
                new XElement("Street1", "123 Main St"),
                new XElement("City", "Mercer Island"),
                new XElement("State", "WA"),
                new XElement("Postal", "68042")
            )
        )
    );
```

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

<span data-ttu-id="4cf7d-127">Można również użyć zapytania LINQ to XML, aby wypełnić drzewo XML, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="4cf7d-127">You can also use a LINQ to XML query to populate an XML tree, as shown in the following example:</span></span>

```csharp
XElement srcTree = new XElement("Root",
    new XElement("Element", 1),
    new XElement("Element", 2),
    new XElement("Element", 3),
    new XElement("Element", 4),
    new XElement("Element", 5)
);
XElement xmlTree = new XElement("Root",
    new XElement("Child", 1),
    new XElement("Child", 2),
    from el in srcTree.Elements()
    where (int)el > 2
    select el
);
Console.WriteLine(xmlTree);
```

```vb
Dim srcTree As XElement = _
    <Root>
        <Element>1</Element>
        <Element>2</Element>
        <Element>3</Element>
        <Element>4</Element>
        <Element>5</Element>
    </Root>
Dim xmlTree As XElement = _
    <Root>
        <Child>1</Child>
        <Child>2</Child>
        <%= From el In srcTree.Elements() _
            Where el.Value > 2 _
            Select el %>
    </Root>
Console.WriteLine(xmlTree)
```

<span data-ttu-id="4cf7d-128">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="4cf7d-128">This example produces the following output:</span></span>

```xml
<Root>
  <Child>1</Child>
  <Child>2</Child>
  <Element>3</Element>
  <Element>4</Element>
  <Element>5</Element>
</Root>
```

## <a name="serialize-xml-trees"></a><span data-ttu-id="4cf7d-129">Serializowanie drzew XML</span><span class="sxs-lookup"><span data-stu-id="4cf7d-129">Serialize XML trees</span></span>

<span data-ttu-id="4cf7d-130">Można serializować drzewo XML do <xref:System.IO.File> , a <xref:System.IO.TextWriter> lub <xref:System.Xml.XmlWriter> .</span><span class="sxs-lookup"><span data-stu-id="4cf7d-130">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>

<span data-ttu-id="4cf7d-131">Aby uzyskać więcej informacji, zobacz [Serializowanie drzew XML](preserve-white-space-serializing.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7d-131">For more information, see [Serialize XML trees](preserve-white-space-serializing.md).</span></span>

## <a name="retrieve-xml-data-via-axis-methods"></a><span data-ttu-id="4cf7d-132">Pobieranie danych XML za pomocą metod osi</span><span class="sxs-lookup"><span data-stu-id="4cf7d-132">Retrieve XML data via axis methods</span></span>

<span data-ttu-id="4cf7d-133">Możesz użyć metod osi do pobierania atrybutów, elementów podrzędnych, elementów podrzędnych i elementów nadrzędnych.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-133">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="4cf7d-134">LINQ to XML zapytania działają na podstawie metod osi i zapewniają kilka elastycznych i wydajnych sposobów nawigowania i przetwarzania drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-134">LINQ to XML queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>

<span data-ttu-id="4cf7d-135">Aby uzyskać więcej informacji, zobacz [LINQ to XML osi — Omówienie](linq-xml-axes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7d-135">For more information, see [LINQ to XML axes overview](linq-xml-axes-overview.md).</span></span>

## <a name="query-xml-trees"></a><span data-ttu-id="4cf7d-136">Tworzenie zapytań dotyczących drzew XML</span><span class="sxs-lookup"><span data-stu-id="4cf7d-136">Query XML trees</span></span>

<span data-ttu-id="4cf7d-137">Można pisać LINQ to XML zapytań, które wyodrębniają dane z drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-137">You can write LINQ to XML queries that extract data from an XML tree.</span></span>

<span data-ttu-id="4cf7d-138">Aby uzyskać więcej informacji, zobacz temat [Omówienie drzew XML dla zapytań](query-xml-trees-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7d-138">For more information, see [Query XML trees overview](query-xml-trees-overview.md).</span></span>

## <a name="modify-xml-trees"></a><span data-ttu-id="4cf7d-139">Modyfikowanie drzew XML</span><span class="sxs-lookup"><span data-stu-id="4cf7d-139">Modify XML trees</span></span>

<span data-ttu-id="4cf7d-140">Można modyfikować element na różne sposoby, w tym zmieniać jego zawartość lub atrybuty.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-140">You can modify an element in different ways, including changing its content or attributes.</span></span> <span data-ttu-id="4cf7d-141">Można również usunąć element z jego elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="4cf7d-141">You can also remove an element from its parent.</span></span>

<span data-ttu-id="4cf7d-142">Aby uzyskać więcej informacji, zobacz [Modyfikowanie drzew XML](in-memory-xml-tree-modification-vs-functional-construction.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7d-142">For more information, see [Modify XML trees](in-memory-xml-tree-modification-vs-functional-construction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4cf7d-143">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4cf7d-143">See also</span></span>

- [<span data-ttu-id="4cf7d-144">Omówienie programowania LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="4cf7d-144">LINQ to XML programming overview</span></span>](functional-vs-procedural-programming.md)
