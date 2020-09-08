---
title: LINQ to XML a DOM
description: Istnieją kluczowe różnice między LINQ to XML i DOM. LINQ to XML obsługuje konstrukcję funkcjonalną i literały XML, które lepiej pokazują strukturę drzew XML, które kompilują.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 51c0e3d2-c047-4e6a-a423-d61a882400b7
ms.openlocfilehash: 905fe1b47361e2b96c79bc56cb831b3cb298e4de
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553323"
---
# <a name="linq-to-xml-vs-dom"></a><span data-ttu-id="a5fb7-104">LINQ to XML a DOM</span><span class="sxs-lookup"><span data-stu-id="a5fb7-104">LINQ to XML vs. DOM</span></span>

<span data-ttu-id="a5fb7-105">W tym artykule opisano niektóre kluczowe różnice między LINQ to XML i bieżącym głównym interfejsem API programowania plików XML, W3C Document Object Model (DOM).</span><span class="sxs-lookup"><span data-stu-id="a5fb7-105">This article describes some key differences between LINQ to XML and the current predominant XML programming API, the W3C Document Object Model (DOM).</span></span>

## <a name="new-ways-to-construct-xml-trees"></a><span data-ttu-id="a5fb7-106">Nowe sposoby konstruowania drzew XML</span><span class="sxs-lookup"><span data-stu-id="a5fb7-106">New ways to construct XML trees</span></span>

<span data-ttu-id="a5fb7-107">W modelu W3C DOM utworzysz drzewo XML od dołu do góry. oznacza to, że tworzysz dokument, tworzysz elementy, a następnie dodasz elementy do dokumentu.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-107">In the W3C DOM, you build an XML tree from the bottom up; that is, you create a document, you create elements, and then you add the elements to the document.</span></span>

<span data-ttu-id="a5fb7-108">Na przykład w poniższym przykładzie użyto typowego sposobu tworzenia drzewa XML przy użyciu implementacji modelu DOM firmy Microsoft <xref:System.Xml.XmlDocument> .</span><span class="sxs-lookup"><span data-stu-id="a5fb7-108">For example, the following example uses a typical way to create an XML tree using the Microsoft implementation of DOM, <xref:System.Xml.XmlDocument>.</span></span>

```csharp
XmlDocument doc = new XmlDocument();
XmlElement name = doc.CreateElement("Name");
name.InnerText = "Patrick Hines";
XmlElement phone1 = doc.CreateElement("Phone");
phone1.SetAttribute("Type", "Home");
phone1.InnerText = "206-555-0144";
XmlElement phone2 = doc.CreateElement("Phone");
phone2.SetAttribute("Type", "Work");
phone2.InnerText = "425-555-0145";
XmlElement street1 = doc.CreateElement("Street1");
street1.InnerText = "123 Main St";
XmlElement city = doc.CreateElement("City");
city.InnerText = "Mercer Island";
XmlElement state = doc.CreateElement("State");
state.InnerText = "WA";
XmlElement postal = doc.CreateElement("Postal");
postal.InnerText = "68042";
XmlElement address = doc.CreateElement("Address");
address.AppendChild(street1);
address.AppendChild(city);
address.AppendChild(state);
address.AppendChild(postal);
XmlElement contact = doc.CreateElement("Contact");
contact.AppendChild(name);
contact.AppendChild(phone1);
contact.AppendChild(phone2);
contact.AppendChild(address);
XmlElement contacts = doc.CreateElement("Contacts");
contacts.AppendChild(contact);
doc.AppendChild(contacts);
```

```vb
Dim doc As XmlDocument = New XmlDocument()
Dim name As XmlElement = doc.CreateElement("Name")
name.InnerText = "Patrick Hines"
Dim phone1 As XmlElement = doc.CreateElement("Phone")
phone1.SetAttribute("Type", "Home")
phone1.InnerText = "206-555-0144"
Dim phone2 As XmlElement = doc.CreateElement("Phone")
phone2.SetAttribute("Type", "Work")
phone2.InnerText = "425-555-0145"
Dim street1 As XmlElement = doc.CreateElement("Street1")
street1.InnerText = "123 Main St"
Dim city As XmlElement = doc.CreateElement("City")
city.InnerText = "Mercer Island"
Dim state As XmlElement = doc.CreateElement("State")
state.InnerText = "WA"
Dim postal As XmlElement = doc.CreateElement("Postal")
postal.InnerText = "68042"
Dim address As XmlElement = doc.CreateElement("Address")
address.AppendChild(street1)
address.AppendChild(city)
address.AppendChild(state)
address.AppendChild(postal)
Dim contact As XmlElement = doc.CreateElement("Contact")
contact.AppendChild(name)
contact.AppendChild(phone1)
contact.AppendChild(phone2)
contact.AppendChild(address)
Dim contacts As XmlElement = doc.CreateElement("Contacts")
contacts.AppendChild(contact)
doc.AppendChild(contacts)
Console.WriteLine(doc.OuterXml)
```

<span data-ttu-id="a5fb7-109">Ten styl kodowania ukrywa strukturę drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-109">This style of coding hides the structure of the XML tree.</span></span> <span data-ttu-id="a5fb7-110">LINQ to XML również obsługuje alternatywne podejście, *konstrukcja funkcjonalna*, która lepiej pokazuje strukturę.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-110">LINQ to XML also supports an alternative approach, *functional construction*, that better shows the structure.</span></span> <span data-ttu-id="a5fb7-111">Takie podejście można wykonać za pomocą <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XAttribute> konstruktorów i.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-111">This approach can be done with the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors.</span></span> <span data-ttu-id="a5fb7-112">W Visual Basic można również wykonać za pomocą literałów XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-112">In Visual Basic, it can also be done with XML literals.</span></span> <span data-ttu-id="a5fb7-113">W tym przykładzie przedstawiono konstruowanie tego samego drzewa XML przy użyciu konstrukcji funkcjonalnej:</span><span class="sxs-lookup"><span data-stu-id="a5fb7-113">This example demonstrates construction of the same XML tree using functional construction:</span></span>

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
Dim contacts = _
    <Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type="Home">206-555-0144</Phone>
            <Phone Type="Work">425-555-0145</Phone>
            <Address>
                <Street1>123 Main St</Street1>
                <City>Mercer Island</City>
                <State>WA</State>
                <Postal>68042</Postal>
            </Address>
        </Contact>
    </Contacts>
```

<span data-ttu-id="a5fb7-114">Zwróć uwagę, że Wcięcie kodu w celu skonstruowania drzewa XML pokazuje strukturę bazowego kodu XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-114">Notice that indenting the code to construct the XML tree shows the structure of the underlying XML.</span></span> <span data-ttu-id="a5fb7-115">Wersja Visual Basic używa literałów XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-115">The Visual Basic version uses XML literals.</span></span>

<span data-ttu-id="a5fb7-116">Aby uzyskać więcej informacji, zobacz [drzewa XML](functional-construction.md).</span><span class="sxs-lookup"><span data-stu-id="a5fb7-116">For more information, see [XML trees](functional-construction.md).</span></span>

## <a name="work-directly-with-xml-elements"></a><span data-ttu-id="a5fb7-117">Pracuj bezpośrednio z elementami XML</span><span class="sxs-lookup"><span data-stu-id="a5fb7-117">Work directly with XML elements</span></span>

<span data-ttu-id="a5fb7-118">Gdy program jest używany w języku XML, główny fokus jest zazwyczaj na elementach XML i prawdopodobnie na atrybutach.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-118">When you program with XML, your primary focus is usually on XML elements and perhaps on attributes.</span></span> <span data-ttu-id="a5fb7-119">W LINQ to XML można bezpośrednio korzystać z elementów i atrybutów XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-119">In LINQ to XML, you can work directly with XML elements and attributes.</span></span> <span data-ttu-id="a5fb7-120">Można na przykład wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a5fb7-120">For example, you can do the following:</span></span>

- <span data-ttu-id="a5fb7-121">Utwórz elementy XML bez używania obiektu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-121">Create XML elements without using a document object at all.</span></span> <span data-ttu-id="a5fb7-122">Upraszcza to programowanie, gdy trzeba będzie korzystać z fragmentów drzew XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-122">This simplifies programming when you have to work with fragments of XML trees.</span></span>
- <span data-ttu-id="a5fb7-123">Załaduj `T:System.Xml.Linq.XElement` obiekty bezpośrednio z pliku XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-123">Load `T:System.Xml.Linq.XElement` objects directly from an XML file.</span></span>
- <span data-ttu-id="a5fb7-124">Serializacja `T:System.Xml.Linq.XElement` obiektów do pliku lub strumienia.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-124">Serialize `T:System.Xml.Linq.XElement` objects to a file or a stream.</span></span>

<span data-ttu-id="a5fb7-125">Porównaj ten element z W3C DOM, w którym dokument XML jest używany jako kontener logiczny dla drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-125">Compare this to the W3C DOM, in which the XML document is used as a logical container for the XML tree.</span></span> <span data-ttu-id="a5fb7-126">W modelu DOM, węzły XML, w tym elementy i atrybuty, muszą zostać utworzone w kontekście dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-126">In DOM, XML nodes, including elements and attributes, must be created in the context of an XML document.</span></span> <span data-ttu-id="a5fb7-127">Oto fragment kodu do utworzenia elementu Name w modelu DOM:</span><span class="sxs-lookup"><span data-stu-id="a5fb7-127">Here is a fragment of code to create a name element in DOM:</span></span>

```csharp
XmlDocument doc = new XmlDocument();
XmlElement name = doc.CreateElement("Name");
name.InnerText = "Patrick Hines";
doc.AppendChild(name);
```

```vb
Dim doc As XmlDocument = New XmlDocument()
Dim name As XmlElement = doc.CreateElement("Name")
name.InnerText = "Patrick Hines"
doc.AppendChild(name)
```

<span data-ttu-id="a5fb7-128">Jeśli chcesz użyć elementu w wielu dokumentach, należy zaimportować węzły między dokumentami.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-128">If you want to use an element across multiple documents, you must import the nodes across documents.</span></span> <span data-ttu-id="a5fb7-129">LINQ to XML pozwala uniknąć tej warstwy złożoności.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-129">LINQ to XML avoids this layer of complexity.</span></span>

<span data-ttu-id="a5fb7-130">W przypadku używania LINQ to XML Klasa jest używana <xref:System.Xml.Linq.XDocument> tylko wtedy, gdy chcesz dodać komentarz lub instrukcję przetwarzania na poziomie głównym dokumentu.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-130">When using LINQ to XML, you use the <xref:System.Xml.Linq.XDocument> class only if you want to add a comment or processing instruction at the root level of the document.</span></span>

## <a name="simplified-handling-of-names-and-namespaces"></a><span data-ttu-id="a5fb7-131">Uproszczona obsługa nazw i przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="a5fb7-131">Simplified handling of names and namespaces</span></span>

<span data-ttu-id="a5fb7-132">Obsługa nazw, przestrzeni nazw i prefiksów przestrzeni nazw jest ogólnie złożonym elementem programowania XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-132">Handling names, namespaces, and namespace prefixes is generally a complex part of XML programming.</span></span> <span data-ttu-id="a5fb7-133">LINQ to XML upraszcza nazwy i przestrzenie nazw, eliminując wymóg postępowania z prefiksami przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-133">LINQ to XML simplifies names and namespaces by eliminating the requirement to deal with namespace prefixes.</span></span> <span data-ttu-id="a5fb7-134">Jeśli chcesz kontrolować prefiksy przestrzeni nazw, możesz.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-134">If you want to control namespace prefixes, you can.</span></span> <span data-ttu-id="a5fb7-135">Ale jeśli zdecydujesz się nie jawnie kontrolować prefiksów przestrzeni nazw, LINQ to XML przypisze prefiksy przestrzeni nazw podczas serializacji, jeśli są wymagane lub będą serializować przy użyciu domyślnych przestrzeni nazw, jeśli nie są.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-135">But if you decide to not explicitly control namespace prefixes, LINQ to XML will assign namespace prefixes during serialization if they're required, or will serialize using default namespaces if they're not.</span></span> <span data-ttu-id="a5fb7-136">Jeśli są używane domyślne przestrzenie nazw, nie będzie żadnych prefiksów przestrzeni nazw w dokumencie będącym wynikiem.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-136">If default namespaces are used, there will be no namespace prefixes in the resulting document.</span></span> <span data-ttu-id="a5fb7-137">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a5fb7-137">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

<span data-ttu-id="a5fb7-138">Innym problemem z modelem DOM jest to, że nie pozwala na zmianę nazwy węzła.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-138">Another problem with the DOM is that it doesn't let you change the name of a node.</span></span> <span data-ttu-id="a5fb7-139">Zamiast tego należy utworzyć nowy węzeł i skopiować do niego wszystkie węzły podrzędne, tracąc oryginalną tożsamość węzła.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-139">Instead, you have to create a new node and copy all the child nodes to it, losing the original node identity.</span></span> <span data-ttu-id="a5fb7-140">LINQ to XML uniknąć tego problemu, umożliwiając ustawienie <xref:System.Xml.Linq.XName> właściwości w węźle.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-140">LINQ to XML avoids this problem by enabling you to set the <xref:System.Xml.Linq.XName> property on a node.</span></span>

## <a name="static-method-support-for-loading-xml"></a><span data-ttu-id="a5fb7-141">Obsługa metody statycznej do ładowania pliku XML</span><span class="sxs-lookup"><span data-stu-id="a5fb7-141">Static method support for loading XML</span></span>

<span data-ttu-id="a5fb7-142">LINQ to XML umożliwia ładowanie XML przy użyciu metod statycznych zamiast metod instancji.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-142">LINQ to XML lets you load XML by using static methods, instead of instance methods.</span></span> <span data-ttu-id="a5fb7-143">Upraszcza to ładowanie i analizowanie.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-143">This simplifies loading and parsing.</span></span> <span data-ttu-id="a5fb7-144">Aby uzyskać więcej informacji, zobacz [jak załadować XML z pliku](load-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="a5fb7-144">For more information, see [How to load XML from a file](load-xml-file.md).</span></span>

## <a name="removal-of-support-for-dtd-constructs"></a><span data-ttu-id="a5fb7-145">Usuwanie obsługi dla konstrukcji DTD</span><span class="sxs-lookup"><span data-stu-id="a5fb7-145">Removal of support for DTD constructs</span></span>

<span data-ttu-id="a5fb7-146">LINQ to XML bardziej upraszcza programowanie XML przez usunięcie obsługi jednostek i odwołań do jednostek.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-146">LINQ to XML further simplifies XML programming by removing support for entities and entity references.</span></span> <span data-ttu-id="a5fb7-147">Zarządzanie jednostkami jest skomplikowane i rzadko jest używane.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-147">The management of entities is complex, and is rarely used.</span></span> <span data-ttu-id="a5fb7-148">Usunięcie ich obsługi zwiększa wydajność i upraszcza interfejs programowania.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-148">Removing their support increases performance and simplifies the programming interface.</span></span> <span data-ttu-id="a5fb7-149">Gdy zostanie wypełnione drzewo LINQ to XML, wszystkie jednostki DTD są rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-149">When a LINQ to XML tree is populated, all DTD entities are expanded.</span></span>

## <a name="support-for-fragments"></a><span data-ttu-id="a5fb7-150">Obsługa fragmentów</span><span class="sxs-lookup"><span data-stu-id="a5fb7-150">Support for fragments</span></span>

<span data-ttu-id="a5fb7-151">LINQ to XML nie zapewnia równoważnej `XmlDocumentFragment` klasy.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-151">LINQ to XML doesn't provide an equivalent for the `XmlDocumentFragment` class.</span></span> <span data-ttu-id="a5fb7-152">W wielu przypadkach `XmlDocumentFragment` koncepcje mogą być obsługiwane przez wynik zapytania, które zostało wpisane w <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XNode> lub <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="a5fb7-152">In many cases, however, the `XmlDocumentFragment` concept can be handled by the result of a query that's typed as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XNode>, or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>.</span></span>

## <a name="support-for-xpathnavigator"></a><span data-ttu-id="a5fb7-153">Obsługa elementu XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a5fb7-153">Support for XPathNavigator</span></span>

<span data-ttu-id="a5fb7-154">LINQ to XML zapewnia obsługę <xref:System.Xml.XPath.XPathNavigator> za pomocą metod rozszerzających w <xref:System.Xml.XPath?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-154">LINQ to XML provides support for <xref:System.Xml.XPath.XPathNavigator> through extension methods in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="a5fb7-155">Aby uzyskać więcej informacji, zobacz <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-155">For more information, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>

## <a name="support-for-white-space-and-indentation"></a><span data-ttu-id="a5fb7-156">Obsługa białych znaków i wcięć</span><span class="sxs-lookup"><span data-stu-id="a5fb7-156">Support for white space and indentation</span></span>

<span data-ttu-id="a5fb7-157">LINQ to XML obsługuje biały znak więcej niż w modelu DOM.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-157">LINQ to XML handles white space more simply than the DOM.</span></span>

<span data-ttu-id="a5fb7-158">Typowym scenariuszem jest odczytywanie wciętych plików XML, tworzenie drzewa XML w pamięci bez jakichkolwiek białych węzłów tekstowych (to nie zachowuje białych znaków), wykonywanie niektórych operacji na pliku XML, a następnie zapisywanie kodu XML z wcięciem.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-158">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), do some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="a5fb7-159">Podczas serializacji pliku XML z formatowaniem zachowywana jest tylko znaczący biały znak w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-159">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="a5fb7-160">Jest to domyślne zachowanie LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-160">This is the default behavior for LINQ to XML.</span></span>

<span data-ttu-id="a5fb7-161">Inny typowy scenariusz polega na odczytaniu i zmodyfikowaniu kodu XML, który został już celowo wcięty.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-161">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="a5fb7-162">W żaden sposób nie trzeba zmieniać tego wcięcia.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-162">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="a5fb7-163">W LINQ to XML można to zrobić, wykonując następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a5fb7-163">In LINQ to XML, you can do this by:</span></span>

- <span data-ttu-id="a5fb7-164">Zachowywanie białych znaków podczas ładowania lub analizowania kodu XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-164">Preserving white space when you load or parse the XML.</span></span>
- <span data-ttu-id="a5fb7-165">Wyłączanie formatowania podczas serializacji kodu XML.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-165">Disabling formatting when you serialize the XML.</span></span>

<span data-ttu-id="a5fb7-166">LINQ to XML przechowuje biały znak jako <xref:System.Xml.Linq.XText> węzeł, zamiast mieć wyspecjalizowany <xref:System.Xml.XmlNodeType.Whitespace> Typ węzła, jak dom.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-166">LINQ to XML stores white space as an <xref:System.Xml.Linq.XText> node, instead of having a specialized <xref:System.Xml.XmlNodeType.Whitespace> node type, as the DOM does.</span></span>

## <a name="support-for-annotations"></a><span data-ttu-id="a5fb7-167">Obsługa adnotacji</span><span class="sxs-lookup"><span data-stu-id="a5fb7-167">Support for annotations</span></span>

<span data-ttu-id="a5fb7-168">Elementy LINQ to XML obsługują rozszerzalny zestaw adnotacji.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-168">LINQ to XML elements support an extensible set of annotations.</span></span> <span data-ttu-id="a5fb7-169">Jest to przydatne do śledzenia różnych informacji o elemencie, takich jak informacje o schemacie, informacje o tym, czy element jest powiązany z interfejsem użytkownika, czy też innym rodzajem informacji specyficznych dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-169">This is useful for tracking miscellaneous information about an element, such as schema information, information about whether the element is bound to a UI, or any other kind of application-specific information.</span></span> <span data-ttu-id="a5fb7-170">Aby uzyskać więcej informacji, zobacz [LINQ to XML adnotacje](linq-xml-annotations.md).</span><span class="sxs-lookup"><span data-stu-id="a5fb7-170">For more information, see [LINQ to XML annotations](linq-xml-annotations.md).</span></span>

## <a name="support-for-schema-information"></a><span data-ttu-id="a5fb7-171">Obsługa informacji o schemacie</span><span class="sxs-lookup"><span data-stu-id="a5fb7-171">Support for schema information</span></span>

<span data-ttu-id="a5fb7-172">LINQ to XML zapewnia obsługę walidacji XSD za pomocą metod rozszerzających w <xref:System.Xml.Schema?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-172">LINQ to XML provides support for XSD validation through extension methods in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="a5fb7-173">Można sprawdzić, czy drzewo XML jest zgodne z XSD.</span><span class="sxs-lookup"><span data-stu-id="a5fb7-173">You can validate that an XML tree complies with an XSD.</span></span> <span data-ttu-id="a5fb7-174">Drzewo XML można wypełnić za pomocą sprawdzonych po walidacji schematu (PSVI).</span><span class="sxs-lookup"><span data-stu-id="a5fb7-174">You can populate the XML tree with the post-schema-validation infoset (PSVI).</span></span> <span data-ttu-id="a5fb7-175">Aby uzyskać więcej informacji, zobacz [Jak sprawdzić przy użyciu XSD](validate-xsd.md) i <xref:System.Xml.Schema.Extensions> .</span><span class="sxs-lookup"><span data-stu-id="a5fb7-175">For more information, see [How to validate using XSD](validate-xsd.md) and <xref:System.Xml.Schema.Extensions>.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5fb7-176">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a5fb7-176">See also</span></span>

- [<span data-ttu-id="a5fb7-177">Przegląd LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="a5fb7-177">LINQ to XML overview</span></span>](linq-xml-overview.md)
