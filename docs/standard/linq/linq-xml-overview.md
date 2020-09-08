---
title: Przegląd — LINQ to XML
description: LINQ to XML udostępnia interfejs programowania XML w pamięci, który jest oparty na możliwościach platformy .NET i porównywalny z zaktualizowanym interfejsem API modelu DOM.
ms.date: 10/30/2018
dev_langs:
- csharp
- vb
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: f805d757c9059a07988c6cb16e41ffed017fe853
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553355"
---
# <a name="linq-to-xml-overview"></a><span data-ttu-id="7e016-103">Przegląd LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="7e016-103">LINQ to XML overview</span></span>

<span data-ttu-id="7e016-104">LINQ to XML udostępnia interfejs programowania XML w pamięci, który wykorzystuje architekturę programu .NET Language-Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="7e016-104">LINQ to XML provides an in-memory XML programming interface that leverages the .NET Language-Integrated Query (LINQ) Framework.</span></span> <span data-ttu-id="7e016-105">LINQ to XML używa możliwości platformy .NET i jest porównywalna z zaktualizowanym, przeprojektowanym Document Object Model (DOM) interfejsem programowania XML.</span><span class="sxs-lookup"><span data-stu-id="7e016-105">LINQ to XML uses .NET capabilities and is comparable to an updated, redesigned Document Object Model (DOM) XML programming interface.</span></span>

<span data-ttu-id="7e016-106">Język XML został szeroko przyjęty jako sposób formatowania danych w wielu kontekstach.</span><span class="sxs-lookup"><span data-stu-id="7e016-106">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="7e016-107">Na przykład można znaleźć XML w sieci Web, w plikach konfiguracyjnych, w Microsoft Office pliki programu Word i w bazach danych.</span><span class="sxs-lookup"><span data-stu-id="7e016-107">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>

<span data-ttu-id="7e016-108">LINQ to XML to aktualne, przeprojektowane podejście do programowania w języku XML.</span><span class="sxs-lookup"><span data-stu-id="7e016-108">LINQ to XML is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="7e016-109">Zapewnia możliwości modyfikacji dokumentów w pamięci Document Object Model (DOM) i obsługuje wyrażenia zapytań LINQ.</span><span class="sxs-lookup"><span data-stu-id="7e016-109">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports LINQ query expressions.</span></span> <span data-ttu-id="7e016-110">Mimo że te wyrażenia zapytania różnią się od składni XPath, zapewniają podobną funkcjonalność.</span><span class="sxs-lookup"><span data-stu-id="7e016-110">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>

## <a name="linq-to-xml-developers"></a><span data-ttu-id="7e016-111">LINQ to XML deweloperzy</span><span class="sxs-lookup"><span data-stu-id="7e016-111">LINQ to XML developers</span></span>

<span data-ttu-id="7e016-112">LINQ to XML są przeznaczone dla wielu deweloperów.</span><span class="sxs-lookup"><span data-stu-id="7e016-112">LINQ to XML targets a variety of developers.</span></span> <span data-ttu-id="7e016-113">W przypadku przeciętnego dewelopera, który po prostu chce uzyskać coś gotowego, LINQ to XML ułatwia tworzenie kodu XML, zapewniając środowisko zapytania podobne do bazy danych SQL.</span><span class="sxs-lookup"><span data-stu-id="7e016-113">For an average developer who just wants to get something done, LINQ to XML makes XML easier by providing a query experience that's similar to SQL.</span></span> <span data-ttu-id="7e016-114">Mając zaledwie kilka analiz, programiści mogą uczyć się pisać zwięzłe i zaawansowane zapytania w wybranym języku programowania.</span><span class="sxs-lookup"><span data-stu-id="7e016-114">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>

<span data-ttu-id="7e016-115">Profesjonalni deweloperzy mogą korzystać z LINQ to XML, aby znacznie zwiększyć swoją produktywność.</span><span class="sxs-lookup"><span data-stu-id="7e016-115">Professional developers can use LINQ to XML to greatly increase their productivity.</span></span> <span data-ttu-id="7e016-116">Dzięki LINQ to XML mogą pisać mniej kod, który jest bardziej wyraźny, bardziej kompaktowy i bardziej wydajny.</span><span class="sxs-lookup"><span data-stu-id="7e016-116">With LINQ to XML, they can write less code that's more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="7e016-117">Mogą używać wyrażeń zapytania z wielu domen danych w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="7e016-117">They can use query expressions from multiple data domains at the same time.</span></span>

## <a name="linq-to-xml-is-an-xml-programming-interface"></a><span data-ttu-id="7e016-118">LINQ to XML to interfejs programowania XML</span><span class="sxs-lookup"><span data-stu-id="7e016-118">LINQ to XML is an XML programming interface</span></span>

<span data-ttu-id="7e016-119">LINQ to XML to interfejs programowania XML obsługujący LINQ, który umożliwia współpracę z danymi XML z poziomu języków programowania .NET.</span><span class="sxs-lookup"><span data-stu-id="7e016-119">LINQ to XML is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the .NET programming languages.</span></span>

<span data-ttu-id="7e016-120">LINQ to XML przypomina Document Object Model (DOM) w tym, że dokument XML jest umieszczany w pamięci.</span><span class="sxs-lookup"><span data-stu-id="7e016-120">LINQ to XML is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="7e016-121">Możesz wysyłać zapytania i modyfikować dokument, a po zmodyfikowaniu go można zapisać do pliku lub serializować go i wysłać za pośrednictwem Internetu.</span><span class="sxs-lookup"><span data-stu-id="7e016-121">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="7e016-122">Jednak LINQ to XML różni się od modelu DOM:</span><span class="sxs-lookup"><span data-stu-id="7e016-122">However, LINQ to XML differs from DOM:</span></span>

- <span data-ttu-id="7e016-123">Udostępnia nowy model obiektów, który jest jaśniejszy i łatwiejszy do pracy z.</span><span class="sxs-lookup"><span data-stu-id="7e016-123">It provides a new object model that's lighter weight and easier to work with.</span></span>
- <span data-ttu-id="7e016-124">Korzysta ona z funkcji języka w języku C# i Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7e016-124">It takes advantage of language features in C# and Visual Basic.</span></span>

<span data-ttu-id="7e016-125">Najważniejszym zaletą LINQ to XML jest integracja z funkcją LINQ (Language-Integrated Query).</span><span class="sxs-lookup"><span data-stu-id="7e016-125">The most important advantage of LINQ to XML is its integration with Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="7e016-126">Ta Integracja umożliwia pisanie zapytań dotyczących dokumentu XML w pamięci w celu pobrania kolekcji elementów i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="7e016-126">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="7e016-127">Możliwość wykonywania zapytań w LINQ to XML jest porównywalna w funkcji (choć nie w składni) do XPath i XQuery.</span><span class="sxs-lookup"><span data-stu-id="7e016-127">The query capability of LINQ to XML is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="7e016-128">Integracja LINQ w języku C# i Visual Basic zapewnia lepsze wpisywanie, sprawdzanie czasu kompilowania i udoskonaloną obsługę debugera.</span><span class="sxs-lookup"><span data-stu-id="7e016-128">The integration of LINQ in C# and Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span></span>

<span data-ttu-id="7e016-129">Kolejną zaletą LINQ to XML jest możliwość używania wyników zapytania jako parametrów do <xref:System.Xml.Linq.XElement> i <xref:System.Xml.Linq.XAttribute> konstruktorów obiektów umożliwia zaawansowane podejście do tworzenia drzew XML.</span><span class="sxs-lookup"><span data-stu-id="7e016-129">Another advantage of LINQ to XML is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="7e016-130">Takie podejście, nazywane *konstrukcją funkcjonalną*, umożliwia deweloperom łatwe przekształcanie drzew XML z jednego kształtu do drugiego.</span><span class="sxs-lookup"><span data-stu-id="7e016-130">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>

<span data-ttu-id="7e016-131">Można na przykład mieć typowe zamówienie zakupu XML, zgodnie z opisem w [przykładowym pliku XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).</span><span class="sxs-lookup"><span data-stu-id="7e016-131">For example, you might have a typical XML purchase order as described in [Sample XML file: Typical purchase order](sample-xml-file-typical-purchase-order.md).</span></span> <span data-ttu-id="7e016-132">Za pomocą LINQ to XML można uruchomić następujące zapytanie w celu uzyskania wartości atrybutu numer części dla każdego elementu elementu w zamówieniu zakupu:</span><span class="sxs-lookup"><span data-stu-id="7e016-132">By using LINQ to XML, you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")
                               select (string) item.Attribute("PartNumber");
```

```vb
' Load the XML file from our project directory containing the purchase orders
Dim filename = "PurchaseOrder.xml"
Dim currentDirectory = Directory.GetCurrentDirectory()
Dim purchaseOrderFilepath = Path.Combine(currentDirectory, filename)

Dim purchaseOrder As XElement = XElement.Load(purchaseOrderFilepath)

Dim partNos = _
    From item In purchaseOrder...<Item> _
    Select item.@PartNumber
```

<span data-ttu-id="7e016-133">W języku C# można to napisać ponownie w postaci składni metody:</span><span class="sxs-lookup"><span data-stu-id="7e016-133">In C# this can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

<span data-ttu-id="7e016-134">Innym przykładem może być lista, posortowana według numeru części, dla elementów o wartości większej niż $100.</span><span class="sxs-lookup"><span data-stu-id="7e016-134">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="7e016-135">Aby uzyskać te informacje, można uruchomić następujące zapytanie:</span><span class="sxs-lookup"><span data-stu-id="7e016-135">To obtain this information, you could run the following query:</span></span>

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100
                                 orderby (string)item.Element("PartNumber")
                                 select item;
```

```vb
' Load the XML file from our project directory containing the purchase orders
Dim filename = "PurchaseOrder.xml"
Dim currentDirectory = Directory.GetCurrentDirectory()
Dim purchaseOrderFilepath = Path.Combine(currentDirectory, filename)

Dim purchaseOrder As XElement = XElement.Load(purchaseOrderFilepath)

Dim partNos = _
From item In purchaseOrder...<Item> _
Where (item.<Quantity>.Value * _
       item.<USPrice>.Value) > 100 _
Order By item.<PartNumber>.Value _
Select item
```

<span data-ttu-id="7e016-136">W języku C# można ponownie napisać w formie składni metody:</span><span class="sxs-lookup"><span data-stu-id="7e016-136">Again, in C# this can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

<span data-ttu-id="7e016-137">Oprócz tych możliwości LINQ LINQ to XML udostępnia udoskonalony interfejs programowania XML.</span><span class="sxs-lookup"><span data-stu-id="7e016-137">In addition to these LINQ capabilities, LINQ to XML provides an improved XML programming interface.</span></span> <span data-ttu-id="7e016-138">Za pomocą LINQ to XML można:</span><span class="sxs-lookup"><span data-stu-id="7e016-138">Using LINQ to XML, you can:</span></span>

- <span data-ttu-id="7e016-139">Załaduj plik XML z [plików](load-xml-file.md) lub [strumieni](stream-xml-fragments-xmlreader.md).</span><span class="sxs-lookup"><span data-stu-id="7e016-139">Load XML from [files](load-xml-file.md) or [streams](stream-xml-fragments-xmlreader.md).</span></span>
- <span data-ttu-id="7e016-140">Serializacja XML do plików lub strumieni.</span><span class="sxs-lookup"><span data-stu-id="7e016-140">Serialize XML to files or streams.</span></span>
- <span data-ttu-id="7e016-141">Utwórz plik XML od podstaw przy użyciu konstrukcji funkcjonalnej.</span><span class="sxs-lookup"><span data-stu-id="7e016-141">Create XML from scratch by using functional construction.</span></span>
- <span data-ttu-id="7e016-142">Kwerenda XML przy użyciu osi podobnej do XPath.</span><span class="sxs-lookup"><span data-stu-id="7e016-142">Query XML using XPath-like axes.</span></span>
- <span data-ttu-id="7e016-143">Manipulowanie drzewem XML w pamięci za pomocą metod takich jak <xref:System.Xml.Linq.XContainer.Add%2A> , <xref:System.Xml.Linq.XNode.Remove%2A> , <xref:System.Xml.Linq.XNode.ReplaceWith%2A> i <xref:System.Xml.Linq.XElement.SetValue%2A> .</span><span class="sxs-lookup"><span data-stu-id="7e016-143">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>
- <span data-ttu-id="7e016-144">Sprawdzanie poprawności drzew XML przy użyciu XSD.</span><span class="sxs-lookup"><span data-stu-id="7e016-144">Validate XML trees using XSD.</span></span>
- <span data-ttu-id="7e016-145">Aby przekształcić drzewa XML z jednego kształtu na inny, należy użyć kombinacji tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="7e016-145">Use a combination of these features to transform XML trees from one shape into another.</span></span>

## <a name="create-xml-trees"></a><span data-ttu-id="7e016-146">Tworzenie drzew XML</span><span class="sxs-lookup"><span data-stu-id="7e016-146">Create XML trees</span></span>

<span data-ttu-id="7e016-147">Jedną z najbardziej znaczących zalet programowania przy użyciu LINQ to XML jest łatwość tworzenia drzew XML.</span><span class="sxs-lookup"><span data-stu-id="7e016-147">One of the most significant advantages of programming with LINQ to XML is that it's easy to create XML trees.</span></span> <span data-ttu-id="7e016-148">Na przykład, aby utworzyć małe drzewo XML, można napisać kod w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="7e016-148">For example, to create a small XML tree, you can write code as follows:</span></span>

```csharp
XElement contacts =
new XElement("Contacts",
    new XElement("Contact",
        new XElement("Name", "Patrick Hines"),
        new XElement("Phone", "206-555-0144",
            new XAttribute("Type", "Home")),
        new XElement("phone", "425-555-0145",
            new XAttribute("Type", "Work")),
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

> [!NOTE]
> <span data-ttu-id="7e016-149">W Visual Basic wersji tego przykładu są używane literały XML.</span><span class="sxs-lookup"><span data-stu-id="7e016-149">The Visual Basic version of the example uses XML literals.</span></span> <span data-ttu-id="7e016-150">Można również użyć <xref:System.Xml.Linq.XElement> w Visual Basic, jak w wersji języka C#.</span><span class="sxs-lookup"><span data-stu-id="7e016-150">You can also use <xref:System.Xml.Linq.XElement> in Visual Basic, as in the C# version.</span></span>

<span data-ttu-id="7e016-151">Aby uzyskać więcej informacji, zobacz [drzewa XML](functional-construction.md).</span><span class="sxs-lookup"><span data-stu-id="7e016-151">For more information, see [XML trees](functional-construction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e016-152">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7e016-152">See also</span></span>

- [<span data-ttu-id="7e016-153">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="7e016-153">Reference</span></span>](reference.md)
- [<span data-ttu-id="7e016-154">LINQ to XML a DOM</span><span class="sxs-lookup"><span data-stu-id="7e016-154">LINQ to XML vs. DOM</span></span>](linq-xml-vs-dom.md)
- [<span data-ttu-id="7e016-155">LINQ to XML a inne technologie XML</span><span class="sxs-lookup"><span data-stu-id="7e016-155">LINQ to XML vs. other XML technologies</span></span>](linq-xml-vs-xml-technologies.md)
- <xref:System.Xml.Linq>
