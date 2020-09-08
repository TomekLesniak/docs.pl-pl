---
title: Przegląd klas LINQ to XML
description: Ten artykuł zawiera listę klas LINQ to XML z opisami każdego z nich.
ms.date: 07/20/2015
ms.assetid: bf666100-5392-4968-97f4-f6b9d3287d7b
ms.openlocfilehash: 83258425b464d8547def5cce6a3e8da19ef21966
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553352"
---
# <a name="linq-to-xml-classes-overview"></a><span data-ttu-id="975d8-103">Przegląd klas LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="975d8-103">LINQ to XML classes overview</span></span>

<span data-ttu-id="975d8-104">Ten artykuł zawiera listę klas LINQ to XML w <xref:System.Xml.Linq> przestrzeni nazw oraz Krótki opis każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="975d8-104">This article provides a list of the LINQ to XML classes in the <xref:System.Xml.Linq> namespace, and a short description of each.</span></span>

## <a name="linq-to-xml-classes"></a><span data-ttu-id="975d8-105">Klasy LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="975d8-105">LINQ to XML classes</span></span>

### <a name="xattribute-class"></a><span data-ttu-id="975d8-106">Klasa XAttribute</span><span class="sxs-lookup"><span data-stu-id="975d8-106">XAttribute class</span></span>

<span data-ttu-id="975d8-107"><xref:System.Xml.Linq.XAttribute> reprezentuje atrybut XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-107"><xref:System.Xml.Linq.XAttribute> represents an XML attribute.</span></span> <span data-ttu-id="975d8-108">Aby uzyskać szczegółowe informacje i przykłady, zobacz [XAttribute Class Overview](xattribute-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="975d8-108">For detailed information and examples, see [XAttribute class overview](xattribute-class-overview.md).</span></span>

### <a name="xcdata-class"></a><span data-ttu-id="975d8-109">Klasa XCData</span><span class="sxs-lookup"><span data-stu-id="975d8-109">XCData class</span></span>

<span data-ttu-id="975d8-110"><xref:System.Xml.Linq.XCData> reprezentuje węzeł tekstu CDATA.</span><span class="sxs-lookup"><span data-stu-id="975d8-110"><xref:System.Xml.Linq.XCData> represents a CDATA text node.</span></span>

### <a name="xcomment-class"></a><span data-ttu-id="975d8-111">Klasa XComment</span><span class="sxs-lookup"><span data-stu-id="975d8-111">XComment class</span></span>

<span data-ttu-id="975d8-112"><xref:System.Xml.Linq.XComment> Reprezentuje komentarz XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-112"><xref:System.Xml.Linq.XComment> represents an XML comment.</span></span>

### <a name="xcontainer-class"></a><span data-ttu-id="975d8-113">Klasa XContainer</span><span class="sxs-lookup"><span data-stu-id="975d8-113">XContainer class</span></span>

<span data-ttu-id="975d8-114"><xref:System.Xml.Linq.XContainer> jest abstrakcyjną klasą bazową dla wszystkich węzłów, które mogą mieć węzły podrzędne.</span><span class="sxs-lookup"><span data-stu-id="975d8-114"><xref:System.Xml.Linq.XContainer> is an abstract base class for all nodes that can have child nodes.</span></span> <span data-ttu-id="975d8-115">Następujące klasy pochodzą od <xref:System.Xml.Linq.XContainer> klasy:</span><span class="sxs-lookup"><span data-stu-id="975d8-115">The following classes derive from the <xref:System.Xml.Linq.XContainer> class:</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XDocument>

### <a name="xdeclaration-class"></a><span data-ttu-id="975d8-116">Klasa XDeclaration</span><span class="sxs-lookup"><span data-stu-id="975d8-116">XDeclaration class</span></span>

<span data-ttu-id="975d8-117"><xref:System.Xml.Linq.XDeclaration> reprezentuje deklarację XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-117"><xref:System.Xml.Linq.XDeclaration> represents an XML declaration.</span></span> <span data-ttu-id="975d8-118">Deklaracja XML jest używana do deklarowania wersji XML i kodowania dokumentu.</span><span class="sxs-lookup"><span data-stu-id="975d8-118">An XML declaration is used to declare the XML version and the encoding of a document.</span></span> <span data-ttu-id="975d8-119">Ponadto deklaracja XML określa, czy dokument XML jest autonomiczny.</span><span class="sxs-lookup"><span data-stu-id="975d8-119">In addition, an XML declaration specifies whether the XML document is stand-alone.</span></span> <span data-ttu-id="975d8-120">Jeśli dokument jest autonomiczny, nie ma żadnych deklaracji znaczników zewnętrznych, w zewnętrznym DTD lub w jednostce parametru zewnętrznego, do której odwołuje się podzbiór wewnętrzny.</span><span class="sxs-lookup"><span data-stu-id="975d8-120">If a document is stand-alone, there are no external markup declarations, either in an external DTD, or in an external parameter entity referenced from the internal subset.</span></span>

### <a name="xdocument-class"></a><span data-ttu-id="975d8-121">Klasa XDocument</span><span class="sxs-lookup"><span data-stu-id="975d8-121">XDocument class</span></span>

<span data-ttu-id="975d8-122"><xref:System.Xml.Linq.XDocument> reprezentuje dokument XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-122"><xref:System.Xml.Linq.XDocument> represents an XML document.</span></span> <span data-ttu-id="975d8-123">Aby uzyskać szczegółowe informacje i przykłady, zobacz MFC [Class Overview](xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="975d8-123">For detailed information and examples, see [XDocument class overview](xdocument-class-overview.md).</span></span>

### <a name="xdocumenttype-class"></a><span data-ttu-id="975d8-124">XDocumenttype — Klasa</span><span class="sxs-lookup"><span data-stu-id="975d8-124">XDocumentType class</span></span>

<span data-ttu-id="975d8-125"><xref:System.Xml.Linq.XDocumentType> reprezentuje definicję typu dokumentu XML (DTD).</span><span class="sxs-lookup"><span data-stu-id="975d8-125"><xref:System.Xml.Linq.XDocumentType> represents an XML Document Type Definition (DTD).</span></span>

### <a name="xelement-class"></a><span data-ttu-id="975d8-126">Klasa XElement</span><span class="sxs-lookup"><span data-stu-id="975d8-126">XElement class</span></span>

<span data-ttu-id="975d8-127"><xref:System.Xml.Linq.XElement> reprezentuje element XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-127"><xref:System.Xml.Linq.XElement> represents an XML element.</span></span> <span data-ttu-id="975d8-128">Aby uzyskać szczegółowe informacje i przykłady, zobacz [XElement Class Overview](xelement-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="975d8-128">For detailed information and examples, see [XElement class overview](xelement-class-overview.md).</span></span>

### <a name="xname-class"></a><span data-ttu-id="975d8-129">Klasa XName</span><span class="sxs-lookup"><span data-stu-id="975d8-129">XName class</span></span>

<span data-ttu-id="975d8-130"><xref:System.Xml.Linq.XName> reprezentuje nazwy elementów ( <xref:System.Xml.Linq.XElement> ) i atrybutów ( <xref:System.Xml.Linq.XAttribute> ).</span><span class="sxs-lookup"><span data-stu-id="975d8-130"><xref:System.Xml.Linq.XName> represents names of elements (<xref:System.Xml.Linq.XElement>) and attributes (<xref:System.Xml.Linq.XAttribute>).</span></span> <span data-ttu-id="975d8-131">Aby uzyskać szczegółowe informacje i przykłady, zobacz MFC [Class Overview](xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="975d8-131">For detailed information and examples, see [XDocument class overview](xdocument-class-overview.md).</span></span>

<span data-ttu-id="975d8-132">LINQ to XML jest zaprojektowana tak, aby nazwy XML były możliwie jak najprostsze.</span><span class="sxs-lookup"><span data-stu-id="975d8-132">LINQ to XML is designed to make XML names as straightforward as possible.</span></span> <span data-ttu-id="975d8-133">Ze względu na złożoność nazw XML często są uważane za zaawansowaną artykuł XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-133">Due to their complexity, XML names are often considered to be an advanced article in XML.</span></span> <span data-ttu-id="975d8-134">Raczej, ta złożoność nie pochodzi z przestrzeni nazw, które deweloperzy wykorzystują regularnie w programowaniu, ale z prefiksów przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="975d8-134">Arguably, this complexity comes not from namespaces, which developers use regularly in programming, but from namespace prefixes.</span></span> <span data-ttu-id="975d8-135">Prefiksy przestrzeni nazw mogą być przydatne, aby zmniejszyć liczbę naciśnięć klawiszy wymaganych podczas wprowadzania danych XML lub ułatwić odczytywanie kodu XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-135">Namespace prefixes can be useful to reduce the keystrokes required when you input XML, or to make XML easier to read.</span></span> <span data-ttu-id="975d8-136">Jednak prefiksy są często tylko skrótem do używania pełnej przestrzeni nazw XML i nie są wymagane w większości przypadków.</span><span class="sxs-lookup"><span data-stu-id="975d8-136">However, prefixes are often just a shortcut for using the full XML namespace, and aren't required in most cases.</span></span> <span data-ttu-id="975d8-137">LINQ to XML upraszcza nazwy XML, rozwiązując wszystkie prefiksy do odpowiednich przestrzeni nazw XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-137">LINQ to XML simplifies XML names by resolving all prefixes to their corresponding XML namespace.</span></span> <span data-ttu-id="975d8-138">Prefiksy są dostępne, jeśli są wymagane przez <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="975d8-138">Prefixes are available, if they're required, through the <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> method.</span></span>

<span data-ttu-id="975d8-139">w razie potrzeby można kontrolować prefiksy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="975d8-139">it's possible, if necessary, to control namespace prefixes.</span></span> <span data-ttu-id="975d8-140">W niektórych sytuacjach, jeśli pracujesz z innymi systemami XML, takimi jak XSLT lub XAML, musisz kontrolować prefiksy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="975d8-140">In some circumstances, if you're working with other XML systems, such as XSLT or XAML, you need to control namespace prefixes.</span></span> <span data-ttu-id="975d8-141">Na przykład jeśli masz wyrażenie XPath używające prefiksów przestrzeni nazw i osadzone w arkuszu stylów XSLT, musisz upewnić się, że dokument XML jest serializowany z prefiksami przestrzeni nazw, które pasują do tych używanych w wyrażeniu XPath.</span><span class="sxs-lookup"><span data-stu-id="975d8-141">For example, if you have an XPath expression that uses namespace prefixes and is embedded in an XSLT stylesheet, you must make sure that your XML document is serialized with namespace prefixes that match those used in the XPath expression.</span></span>

### <a name="xnamespace-class"></a><span data-ttu-id="975d8-142">Klasa XNamespace</span><span class="sxs-lookup"><span data-stu-id="975d8-142">XNamespace class</span></span>

<span data-ttu-id="975d8-143"><xref:System.Xml.Linq.XNamespace> reprezentuje przestrzeń nazw dla <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute> .</span><span class="sxs-lookup"><span data-stu-id="975d8-143"><xref:System.Xml.Linq.XNamespace> represents a namespace for an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="975d8-144">Przestrzenie nazw są składnikiem <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="975d8-144">Namespaces are a component of an <xref:System.Xml.Linq.XName>.</span></span>

### <a name="xnode-class"></a><span data-ttu-id="975d8-145">Klasa XNode</span><span class="sxs-lookup"><span data-stu-id="975d8-145">XNode class</span></span>

<span data-ttu-id="975d8-146"><xref:System.Xml.Linq.XNode> jest klasą abstrakcyjną, która reprezentuje węzły drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-146"><xref:System.Xml.Linq.XNode> is an abstract class that represents the nodes of an XML tree.</span></span> <span data-ttu-id="975d8-147">Następujące klasy pochodzą od <xref:System.Xml.Linq.XNode> klasy:</span><span class="sxs-lookup"><span data-stu-id="975d8-147">The following classes derive from the <xref:System.Xml.Linq.XNode> class:</span></span>

- <xref:System.Xml.Linq.XText>
- <xref:System.Xml.Linq.XContainer>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XDocumentType>

### <a name="xnodedocumentordercomparer-class"></a><span data-ttu-id="975d8-148">Klasa XNodeDocumentOrderComparer</span><span class="sxs-lookup"><span data-stu-id="975d8-148">XNodeDocumentOrderComparer class</span></span>

<span data-ttu-id="975d8-149"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> oferuje funkcje do porównywania węzłów dla ich kolejności dokumentów.</span><span class="sxs-lookup"><span data-stu-id="975d8-149"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> provides functionality to compare nodes for their document order.</span></span>

### <a name="xnodeequalitycomparer-class"></a><span data-ttu-id="975d8-150">Klasa XNodeEqualityComparer</span><span class="sxs-lookup"><span data-stu-id="975d8-150">XNodeEqualityComparer class</span></span>

<span data-ttu-id="975d8-151"><xref:System.Xml.Linq.XNodeEqualityComparer> oferuje funkcje do porównywania węzłów pod kątem równości wartości.</span><span class="sxs-lookup"><span data-stu-id="975d8-151"><xref:System.Xml.Linq.XNodeEqualityComparer> provides functionality to compare nodes for value equality.</span></span>

### <a name="xobject-class"></a><span data-ttu-id="975d8-152">Klasa XObject</span><span class="sxs-lookup"><span data-stu-id="975d8-152">XObject class</span></span>

<span data-ttu-id="975d8-153"><xref:System.Xml.Linq.XObject> jest abstrakcyjną klasą bazową <xref:System.Xml.Linq.XNode> i <xref:System.Xml.Linq.XAttribute> .</span><span class="sxs-lookup"><span data-stu-id="975d8-153"><xref:System.Xml.Linq.XObject> is an abstract base class of <xref:System.Xml.Linq.XNode> and <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="975d8-154">Zapewnia funkcję adnotacji i zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="975d8-154">It provides annotation and event functionality.</span></span>

### <a name="xobjectchange-class"></a><span data-ttu-id="975d8-155">Klasa XObjectChange</span><span class="sxs-lookup"><span data-stu-id="975d8-155">XObjectChange class</span></span>

<span data-ttu-id="975d8-156"><xref:System.Xml.Linq.XObjectChange> Określa typ zdarzenia, gdy zdarzenie jest zgłaszane dla elementu <xref:System.Xml.Linq.XObject> .</span><span class="sxs-lookup"><span data-stu-id="975d8-156"><xref:System.Xml.Linq.XObjectChange> specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>

### <a name="xobjectchangeeventargs-class"></a><span data-ttu-id="975d8-157">Klasa XObjectChangeEventArgs</span><span class="sxs-lookup"><span data-stu-id="975d8-157">XObjectChangeEventArgs class</span></span>

<span data-ttu-id="975d8-158"><xref:System.Xml.Linq.XObjectChangeEventArgs> dostarcza dane dla <xref:System.Xml.Linq.XObject.Changing> zdarzeń i <xref:System.Xml.Linq.XObject.Changed> .</span><span class="sxs-lookup"><span data-stu-id="975d8-158"><xref:System.Xml.Linq.XObjectChangeEventArgs> provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>

### <a name="xprocessinginstruction-class"></a><span data-ttu-id="975d8-159">Klasa XProcessingInstruction</span><span class="sxs-lookup"><span data-stu-id="975d8-159">XProcessingInstruction class</span></span>

<span data-ttu-id="975d8-160"><xref:System.Xml.Linq.XProcessingInstruction> reprezentuje instrukcję przetwarzania XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-160"><xref:System.Xml.Linq.XProcessingInstruction> represents an XML processing instruction.</span></span> <span data-ttu-id="975d8-161">Instrukcja przetwarzania komunikuje informacje z aplikacją, która przetwarza kod XML.</span><span class="sxs-lookup"><span data-stu-id="975d8-161">A processing instruction communicates information to an application that processes the XML.</span></span>

### <a name="xtext-class"></a><span data-ttu-id="975d8-162">Klasa XText</span><span class="sxs-lookup"><span data-stu-id="975d8-162">XText class</span></span>

<span data-ttu-id="975d8-163"><xref:System.Xml.Linq.XText> reprezentuje węzeł tekstowy.</span><span class="sxs-lookup"><span data-stu-id="975d8-163"><xref:System.Xml.Linq.XText> represents a text node.</span></span> <span data-ttu-id="975d8-164">W większości przypadków nie trzeba używać tej klasy.</span><span class="sxs-lookup"><span data-stu-id="975d8-164">In most cases, you don't have to use this class.</span></span> <span data-ttu-id="975d8-165">Ta klasa jest używana głównie do zawartości mieszanej.</span><span class="sxs-lookup"><span data-stu-id="975d8-165">This class is primarily used for mixed content.</span></span>
