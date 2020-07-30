---
title: Programowanie z węzłami (C#)
description: Dowiedz się więcej na temat programowania z węzłami. Umożliwia to deweloperom pisanie programów, które pracują na bardziej szczegółowym poziomie niż elementy i atrybuty.
ms.date: 07/20/2015
ms.assetid: c38df0f2-c805-431a-93ff-9103a4284c2f
ms.openlocfilehash: 8a31d6459ab644a682d480239cabc3d88fd7dc14
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301687"
---
# <a name="programming-with-nodes-c"></a><span data-ttu-id="1fe4a-104">Programowanie z węzłami (C#)</span><span class="sxs-lookup"><span data-stu-id="1fe4a-104">Programming with Nodes (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="1fe4a-105">Deweloperzy, którzy muszą pisać programy takie jak Edytor XML, system transformacji lub moduł zapisujący raport często muszą pisać programy, które pracują na bardziej szczegółowym poziomie niż elementy i atrybuty.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-105">developers who need to write programs such as an XML editor, a transform system, or a report writer often need to write programs that work at a finer level of granularity than elements and attributes.</span></span> <span data-ttu-id="1fe4a-106">Często muszą oni korzystać z poziomu węzła, manipulowania węzłami tekstu, instrukcjami przetwarzania i komentarzami.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-106">They often need to work at the node level, manipulating text nodes, processing instructions, and comments.</span></span> <span data-ttu-id="1fe4a-107">W tym temacie przedstawiono szczegółowe informacje na temat programowania na poziomie węzła.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-107">This topic provides some details about programming at the node level.</span></span>  
  
## <a name="node-details"></a><span data-ttu-id="1fe4a-108">Szczegóły węzła</span><span class="sxs-lookup"><span data-stu-id="1fe4a-108">Node Details</span></span>  
 <span data-ttu-id="1fe4a-109">Istnieje kilka szczegółów programowania, które programista pracuje na poziomie węzła.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-109">There are a number of details of programming that a programmer working at the node level should know.</span></span>  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a><span data-ttu-id="1fe4a-110">Właściwość nadrzędna węzłów podrzędnych klasy XDocument ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-110">Parent Property of Children Nodes of XDocument is Set to Null</span></span>  
 <span data-ttu-id="1fe4a-111"><xref:System.Xml.Linq.XObject.Parent%2A>Właściwość zawiera element nadrzędny <xref:System.Xml.Linq.XElement> , a nie węzeł nadrzędny.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-111">The <xref:System.Xml.Linq.XObject.Parent%2A> property contains the parent <xref:System.Xml.Linq.XElement>, not the parent node.</span></span> <span data-ttu-id="1fe4a-112">Węzły podrzędne <xref:System.Xml.Linq.XDocument> nie mają elementu nadrzędnego <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="1fe4a-112">Child nodes of <xref:System.Xml.Linq.XDocument> have no parent <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="1fe4a-113">Ich element nadrzędny jest dokumentem, więc <xref:System.Xml.Linq.XObject.Parent%2A> Właściwość dla tych węzłów ma ustawioną wartość null.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-113">Their parent is the document, so the <xref:System.Xml.Linq.XObject.Parent%2A> property for those nodes is set to null.</span></span>  
  
 <span data-ttu-id="1fe4a-114">Poniższy przykład ilustruje:</span><span class="sxs-lookup"><span data-stu-id="1fe4a-114">The following example demonstrates this:</span></span>  
  
```csharp  
XDocument doc = XDocument.Parse(@"<!-- a comment --><Root/>");  
Console.WriteLine(doc.Nodes().OfType<XComment>().First().Parent == null);  
Console.WriteLine(doc.Root.Parent == null);  
```  
  
 <span data-ttu-id="1fe4a-115">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1fe4a-115">This example produces the following output:</span></span>  
  
```output  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a><span data-ttu-id="1fe4a-116">Możliwe są sąsiadujące węzły tekstowe</span><span class="sxs-lookup"><span data-stu-id="1fe4a-116">Adjacent Text Nodes are Possible</span></span>  
 <span data-ttu-id="1fe4a-117">W wielu modelach programowania XML sąsiadujące węzły tekstowe są zawsze scalane.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-117">In a number of XML programming models, adjacent text nodes are always merged.</span></span> <span data-ttu-id="1fe4a-118">Jest to czasami nazywane normalizacją węzłów tekstowych.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-118">This is sometimes called normalization of text nodes.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="1fe4a-119">nie normalizuje węzłów tekstowych.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-119">does not normalize text nodes.</span></span> <span data-ttu-id="1fe4a-120">Jeśli dodasz dwa węzły tekstowe do tego samego elementu, spowoduje to sąsiednie węzły tekstowe.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-120">If you add two text nodes to the same element, it will result in adjacent text nodes.</span></span> <span data-ttu-id="1fe4a-121">Jeśli jednak zostanie dodana zawartość określona jako ciąg, a nie jako <xref:System.Xml.Linq.XText> węzeł, program [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] może scalić ciąg z sąsiednim węzłem tekstowym.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-121">However, if you add content specified as a string rather than as an <xref:System.Xml.Linq.XText> node, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] might merge the string with an adjacent text node.</span></span>  
  
 <span data-ttu-id="1fe4a-122">Poniższy przykład ilustruje:</span><span class="sxs-lookup"><span data-stu-id="1fe4a-122">The following example demonstrates this:</span></span>  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does not add a new text node  
xmlTree.Add("new content");  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does add a new, adjacent text node  
xmlTree.Add(new XText("more text"));  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
```  
  
 <span data-ttu-id="1fe4a-123">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1fe4a-123">This example produces the following output:</span></span>  
  
```output  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a><span data-ttu-id="1fe4a-124">Możliwe są puste węzły tekstowe</span><span class="sxs-lookup"><span data-stu-id="1fe4a-124">Empty Text Nodes are Possible</span></span>  
 <span data-ttu-id="1fe4a-125">W niektórych modelach programowania XML węzły tekstowe są gwarantowane, że nie zawierają pustego ciągu.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-125">In some XML programming models, text nodes are guaranteed to not contain the empty string.</span></span> <span data-ttu-id="1fe4a-126">Powodem jest to, że taki węzeł tekstowy nie ma wpływu na serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-126">The reasoning is that such a text node has no impact on serialization of the XML.</span></span> <span data-ttu-id="1fe4a-127">Jednak z tego samego powodu, gdy jest możliwy sąsiednie węzły tekstowe, jeśli usuniesz tekst z węzła tekstowego przez ustawienie jego wartości na pusty ciąg, sam węzeł tekstu nie zostanie usunięty.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-127">However, for the same reason that adjacent text nodes are possible, if you remove the text from a text node by setting its value to the empty string, the text node itself will not be deleted.</span></span>  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
XText textNode = xmlTree.Nodes().OfType<XText>().First();  
  
// the following line does not cause the removal of the text node.  
textNode.Value = "";  
  
XText textNode2 = xmlTree.Nodes().OfType<XText>().First();  
Console.WriteLine(">>{0}<<", textNode2);
```  
  
 <span data-ttu-id="1fe4a-128">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1fe4a-128">This example produces the following output:</span></span>  
  
```output  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a><span data-ttu-id="1fe4a-129">Pusty węzeł tekstowy wpływa na serializację</span><span class="sxs-lookup"><span data-stu-id="1fe4a-129">An Empty Text Node Impacts Serialization</span></span>  
 <span data-ttu-id="1fe4a-130">Jeśli element zawiera tylko podrzędny węzeł tekstowy, który jest pusty, jest serializowany z składnią długiego tagu: `<Child></Child>` .</span><span class="sxs-lookup"><span data-stu-id="1fe4a-130">If an element contains only a child text node that is empty, it is serialized with the long tag syntax: `<Child></Child>`.</span></span> <span data-ttu-id="1fe4a-131">Jeśli element nie zawiera żadnych węzłów podrzędnych, zostaje Zserializowany za pomocą składni krótkiej tagu: `<Child />` .</span><span class="sxs-lookup"><span data-stu-id="1fe4a-131">If an element contains no child nodes whatsoever, it is serialized with the short tag syntax: `<Child />`.</span></span>  
  
```csharp  
XElement child1 = new XElement("Child1",  
    new XText("")  
);  
XElement child2 = new XElement("Child2");  
Console.WriteLine(child1);  
Console.WriteLine(child2);
```  
  
 <span data-ttu-id="1fe4a-132">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1fe4a-132">This example produces the following output:</span></span>  
  
```xml  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a><span data-ttu-id="1fe4a-133">Przestrzenie nazw są atrybutami drzewa LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="1fe4a-133">Namespaces are Attributes in the LINQ to XML Tree</span></span>  
 <span data-ttu-id="1fe4a-134">Mimo że deklaracje przestrzeni nazw mają identyczną składnię atrybutów, w niektórych interfejsach programowania, takich jak XSLT i XPath, deklaracje przestrzeni nazw nie są uważane za atrybuty.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-134">Even though namespace declarations have identical syntax to attributes, in some programming interfaces, such as XSLT and XPath, namespace declarations are not considered to be attributes.</span></span> <span data-ttu-id="1fe4a-135">Jednak w programie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] przestrzenie nazw są przechowywane jako <xref:System.Xml.Linq.XAttribute> obiekty w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-135">However, in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], namespaces are stored as <xref:System.Xml.Linq.XAttribute> objects in the XML tree.</span></span> <span data-ttu-id="1fe4a-136">W przypadku iteracji przez atrybuty elementu, który zawiera deklarację przestrzeni nazw, Deklaracja przestrzeni nazw będzie widoczna jako jeden z elementów w zwróconej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-136">If you iterate through the attributes for an element that contains a namespace declaration, you will see the namespace declaration as one of the items in the returned collection.</span></span>  
  
 <span data-ttu-id="1fe4a-137"><xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>Właściwość wskazuje, czy atrybut jest deklaracją przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-137">The <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> property indicates whether an attribute is a namespace declaration.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>");  
foreach (XAttribute att in root.Attributes())  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, att.IsNamespaceDeclaration);  
```  
  
 <span data-ttu-id="1fe4a-138">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1fe4a-138">This example produces the following output:</span></span>  
  
```output  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a><span data-ttu-id="1fe4a-139">Metody osi XPath nie zwracają białych znaków elementu XDocument</span><span class="sxs-lookup"><span data-stu-id="1fe4a-139">XPath Axis Methods Do Not Return Child White Space of XDocument</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="1fe4a-140">zezwala na podrzędne węzły tekstowe <xref:System.Xml.Linq.XDocument> , tak długo, jak węzły tekstowe zawierają tylko biały znak.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-140">allows for child text nodes of an <xref:System.Xml.Linq.XDocument>, as long as the text nodes contain only white space.</span></span> <span data-ttu-id="1fe4a-141">Jednak model obiektów XPath nie zawiera białych znaków jako węzłów podrzędnych dokumentu, więc gdy przejdziesz do iteracji przez elementy podrzędne <xref:System.Xml.Linq.XDocument> przy użyciu <xref:System.Xml.Linq.XContainer.Nodes%2A> osi, zostaną zwrócone węzły tekstu białych znaków.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-141">However, the XPath object model does not include white space as child nodes of a document, so when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the <xref:System.Xml.Linq.XContainer.Nodes%2A> axis, white-space text nodes will be returned.</span></span> <span data-ttu-id="1fe4a-142">Jednak podczas iteracji przez elementy podrzędne z <xref:System.Xml.Linq.XDocument> użyciem metody osi XPath, węzły tekstu białych znaków nie zostaną zwrócone.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-142">However, when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the XPath axis methods, white-space text nodes will not be returned.</span></span>  
  
```csharp  
// Create a document with some white-space child nodes of the document.  
XDocument root = XDocument.Parse(  
@"<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
  
<Root/>  
  
<!--a comment-->  
", LoadOptions.PreserveWhitespace);  
  
// count the white-space child nodes using LINQ to XML  
Console.WriteLine(root.Nodes().OfType<XText>().Count());  
  
// count the white-space child nodes using XPathEvaluate  
Console.WriteLine(((IEnumerable)root.XPathEvaluate("text()")).OfType<XText>().Count());
```  
  
 <span data-ttu-id="1fe4a-143">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1fe4a-143">This example produces the following output:</span></span>  
  
```output  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a><span data-ttu-id="1fe4a-144">Obiekty XDeclaration nie są węzłami</span><span class="sxs-lookup"><span data-stu-id="1fe4a-144">XDeclaration Objects are not Nodes</span></span>  
 <span data-ttu-id="1fe4a-145">Gdy przejdziesz do iteracji między węzłami podrzędnymi <xref:System.Xml.Linq.XDocument> , nie zobaczysz obiektu deklaracji XML.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-145">When you iterate through the children nodes of an <xref:System.Xml.Linq.XDocument>, you will not see the XML declaration object.</span></span> <span data-ttu-id="1fe4a-146">Jest to właściwość dokumentu, a nie jego węzeł podrzędny.</span><span class="sxs-lookup"><span data-stu-id="1fe4a-146">It is a property of the document, not a child node of it.</span></span>  
  
```csharp  
XDocument doc = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root")  
);  
doc.Save("Temp.xml");  
Console.WriteLine(File.ReadAllText("Temp.xml"));  
  
// this shows that there is only one child node of the document  
Console.WriteLine(doc.Nodes().Count());  
```  
  
 <span data-ttu-id="1fe4a-147">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1fe4a-147">This example produces the following output:</span></span>  
  
```output  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  