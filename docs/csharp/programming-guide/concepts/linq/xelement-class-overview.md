---
title: XElement — przegląd klas (C#)
description: Klasa XElement reprezentuje element XML w języku C#. Jest to jedna z podstawowych klas w LINQ to XML. Dowiedz się więcej o funkcjach zapewnianych przez XElement.
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: f76f51703de054443f47531294777b43a9c0b004
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302181"
---
# <a name="xelement-class-overview-c"></a><span data-ttu-id="00b66-105">XElement — przegląd klas (C#)</span><span class="sxs-lookup"><span data-stu-id="00b66-105">XElement Class Overview (C#)</span></span>
<span data-ttu-id="00b66-106"><xref:System.Xml.Linq.XElement>Klasa jest jedną z podstawowych klas w [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00b66-106">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="00b66-107">Reprezentuje element XML.</span><span class="sxs-lookup"><span data-stu-id="00b66-107">It represents an XML element.</span></span> <span data-ttu-id="00b66-108">Możesz użyć tej klasy do tworzenia elementów; Zmień zawartość elementu; Dodawanie, zmienianie lub usuwanie elementów podrzędnych; Dodaj atrybuty do elementu; lub serializować zawartości elementu w postaci tekstowej.</span><span class="sxs-lookup"><span data-stu-id="00b66-108">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="00b66-109">Możesz również współpracować z innymi klasami w <xref:System.Xml?displayProperty=nameWithType> , takich jak <xref:System.Xml.XmlReader> , <xref:System.Xml.XmlWriter> , i <xref:System.Xml.Xsl.XslCompiledTransform> .</span><span class="sxs-lookup"><span data-stu-id="00b66-109">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
<span data-ttu-id="00b66-110">W tym temacie opisano funkcje udostępniane przez <xref:System.Xml.Linq.XElement> klasę.</span><span class="sxs-lookup"><span data-stu-id="00b66-110">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
## <a name="constructing-xml-trees"></a><span data-ttu-id="00b66-111">Konstruowanie drzew XML</span><span class="sxs-lookup"><span data-stu-id="00b66-111">Constructing XML Trees</span></span>  
 <span data-ttu-id="00b66-112">Drzewa XML można konstruować na różne sposoby, w tym następujące:</span><span class="sxs-lookup"><span data-stu-id="00b66-112">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
- <span data-ttu-id="00b66-113">Drzewo XML można skonstruować w kodzie.</span><span class="sxs-lookup"><span data-stu-id="00b66-113">You can construct an XML tree in code.</span></span> <span data-ttu-id="00b66-114">Aby uzyskać więcej informacji, zobacz [Tworzenie drzew XML (C#)](./linq-to-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="00b66-114">For more information, see [Creating XML Trees (C#)](./linq-to-xml-overview.md).</span></span>  
  
- <span data-ttu-id="00b66-115">Można analizować XML z różnych źródeł, w tym <xref:System.IO.TextReader> plików tekstowych lub adresów sieci Web (URL).</span><span class="sxs-lookup"><span data-stu-id="00b66-115">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="00b66-116">Aby uzyskać więcej informacji, zobacz [Analizowanie XML (C#)](./how-to-parse-a-string.md).</span><span class="sxs-lookup"><span data-stu-id="00b66-116">For more information, see [Parsing XML (C#)](./how-to-parse-a-string.md).</span></span>  
  
- <span data-ttu-id="00b66-117"><xref:System.Xml.XmlReader>Aby wypełnić drzewo, można użyć elementu.</span><span class="sxs-lookup"><span data-stu-id="00b66-117">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="00b66-118">Aby uzyskać więcej informacji, zobacz <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="00b66-118">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
- <span data-ttu-id="00b66-119">Jeśli masz moduł, który może zapisywać zawartość w <xref:System.Xml.XmlWriter> programie, możesz użyć <xref:System.Xml.Linq.XContainer.CreateWriter%2A> metody do utworzenia składnika zapisywania, przekazania składnika zapisywania do modułu, a następnie użyć zawartości zapisanej w programie w <xref:System.Xml.XmlWriter> celu wypełnienia drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="00b66-119">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="00b66-120">Jednak najbardziej typowym sposobem tworzenia drzewa XML jest:</span><span class="sxs-lookup"><span data-stu-id="00b66-120">However, the most common way to create an XML tree is as follows:</span></span>  
  
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
  
 <span data-ttu-id="00b66-121">Inna bardzo często stosowana technika tworzenia drzewa XML obejmuje użycie wyników zapytania LINQ do wypełnienia drzewa XML, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="00b66-121">Another very common technique for creating an XML tree involves using the results of a LINQ query to populate an XML tree, as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="00b66-122">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="00b66-122">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="serializing-xml-trees"></a><span data-ttu-id="00b66-123">Serializowanie drzew XML</span><span class="sxs-lookup"><span data-stu-id="00b66-123">Serializing XML Trees</span></span>  
 <span data-ttu-id="00b66-124">Można serializować drzewo XML do <xref:System.IO.File> , a <xref:System.IO.TextWriter> lub <xref:System.Xml.XmlWriter> .</span><span class="sxs-lookup"><span data-stu-id="00b66-124">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="00b66-125">Aby uzyskać więcej informacji, zobacz [Serializowanie drzew XML (C#)](./preserving-white-space-while-serializing.md).</span><span class="sxs-lookup"><span data-stu-id="00b66-125">For more information, see [Serializing XML Trees (C#)](./preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="00b66-126">Pobieranie danych XML za pomocą metod osi</span><span class="sxs-lookup"><span data-stu-id="00b66-126">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="00b66-127">Możesz użyć metod osi do pobierania atrybutów, elementów podrzędnych, elementów podrzędnych i elementów nadrzędnych.</span><span class="sxs-lookup"><span data-stu-id="00b66-127">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="00b66-128">Zapytania LINQ działają na podstawie metod osi i zapewniają kilka elastycznych i wydajnych sposobów nawigowania i przetwarzania drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="00b66-128">LINQ queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="00b66-129">Aby uzyskać więcej informacji, zobacz [LINQ to XML osi (C#)](./linq-to-xml-axes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="00b66-129">For more information, see [LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md).</span></span>  
  
## <a name="querying-xml-trees"></a><span data-ttu-id="00b66-130">Tworzenie zapytań dotyczących drzew XML</span><span class="sxs-lookup"><span data-stu-id="00b66-130">Querying XML Trees</span></span>  
 <span data-ttu-id="00b66-131">Można napisać zapytania LINQ wyodrębniające dane z drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="00b66-131">You can write LINQ queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="00b66-132">Aby uzyskać więcej informacji, zobacz Tworzenie [zapytań dotyczących drzew XML (C#)](./how-to-find-an-element-with-a-specific-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="00b66-132">For more information, see [Querying XML Trees (C#)](./how-to-find-an-element-with-a-specific-attribute.md).</span></span>  
  
## <a name="modifying-xml-trees"></a><span data-ttu-id="00b66-133">Modyfikowanie drzew XML</span><span class="sxs-lookup"><span data-stu-id="00b66-133">Modifying XML Trees</span></span>  
 <span data-ttu-id="00b66-134">Można zmodyfikować element na różne sposoby, w tym zmieniać jego zawartość lub atrybuty.</span><span class="sxs-lookup"><span data-stu-id="00b66-134">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="00b66-135">Można również usunąć element z jego elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="00b66-135">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="00b66-136">Aby uzyskać więcej informacji, zobacz [Modyfikowanie drzew XML (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="00b66-136">For more information, see [Modifying XML Trees (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b66-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="00b66-137">See also</span></span>

- [<span data-ttu-id="00b66-138">Omówienie programowania LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="00b66-138">LINQ to XML Programming Overview (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
