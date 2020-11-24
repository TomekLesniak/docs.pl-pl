---
title: Wczytywanie danych XML przy użyciu klas XPathDocument i XmlDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5711b225-6aa2-4e4f-9898-19f2d518ad1a
ms.openlocfilehash: 8ffd03d1a9915bade6c4d421d5fad096a4784fb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686790"
---
# <a name="reading-xml-data-using-xpathdocument-and-xmldocument"></a><span data-ttu-id="86ff1-102">Wczytywanie danych XML przy użyciu klas XPathDocument i XmlDocument</span><span class="sxs-lookup"><span data-stu-id="86ff1-102">Reading XML Data using XPathDocument and XmlDocument</span></span>

<span data-ttu-id="86ff1-103">Istnieją dwa sposoby odczytywania dokumentu XML w <xref:System.Xml.XPath?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="86ff1-103">There are two ways to read an XML document in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="86ff1-104">Jeden polega na odczytaniu dokumentu XML przy użyciu klasy tylko <xref:System.Xml.XPath.XPathDocument> do odczytu, a druga — do odczytywania dokumentu XML przy użyciu <xref:System.Xml.XmlDocument> klasy edytowalnej w <xref:System.Xml?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="86ff1-104">One is to read an XML document using the read-only <xref:System.Xml.XPath.XPathDocument> class and the other is to read an XML document using the editable <xref:System.Xml.XmlDocument> class in the <xref:System.Xml?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="reading-xml-documents-using-the-xpathdocument-class"></a><span data-ttu-id="86ff1-105">Odczytywanie dokumentów XML przy użyciu klasy XPathDocument</span><span class="sxs-lookup"><span data-stu-id="86ff1-105">Reading XML Documents using the XPathDocument Class</span></span>  

 <span data-ttu-id="86ff1-106"><xref:System.Xml.XPath.XPathDocument>Klasa zapewnia szybką, tylko do odczytu, reprezentację w pamięci dokumentu XML przy użyciu modelu danych XPath.</span><span class="sxs-lookup"><span data-stu-id="86ff1-106">The <xref:System.Xml.XPath.XPathDocument> class provides a fast, read-only, in-memory representation of an XML document using the XPath data model.</span></span> <span data-ttu-id="86ff1-107">Wystąpienia <xref:System.Xml.XPath.XPathDocument> klasy są tworzone przy użyciu jednego z sześciu konstruktorów.</span><span class="sxs-lookup"><span data-stu-id="86ff1-107">Instances of the <xref:System.Xml.XPath.XPathDocument> class are created using one of its six constructors.</span></span> <span data-ttu-id="86ff1-108">Te konstruktory umożliwiają odczytywanie dokumentu XML przy użyciu <xref:System.IO.Stream> obiektu, <xref:System.IO.TextReader> , lub <xref:System.Xml.XmlReader> , a także `string` ścieżkę do pliku XML.</span><span class="sxs-lookup"><span data-stu-id="86ff1-108">These constructors allow you to read an XML document using a <xref:System.IO.Stream>, <xref:System.IO.TextReader>, or <xref:System.Xml.XmlReader> object, as well as the `string` path to an XML file.</span></span>  
  
 <span data-ttu-id="86ff1-109">Poniższy przykład ilustruje użycie <xref:System.Xml.XPath.XPathDocument> `string` konstruktora klasy w celu odczytania dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="86ff1-109">The following example illustrates using the <xref:System.Xml.XPath.XPathDocument> class's `string` constructor to read an XML document.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
```  
  
## <a name="reading-xml-documents-using-the-xmldocument-class"></a><span data-ttu-id="86ff1-110">Odczytywanie dokumentów XML przy użyciu klasy XmlDocument</span><span class="sxs-lookup"><span data-stu-id="86ff1-110">Reading XML Documents using the XmlDocument Class</span></span>  

 <span data-ttu-id="86ff1-111"><xref:System.Xml.XmlDocument>Klasa jest edytowalną reprezentacją w pamięci dokumentu XML implementującą W3C Document Object Model (dom) Level 1 Core i Core dom Level 2.</span><span class="sxs-lookup"><span data-stu-id="86ff1-111">The <xref:System.Xml.XmlDocument> class is an editable in-memory representation of an XML document implementing W3C Document Object Model (DOM) Level 1 Core and Core DOM Level 2.</span></span> <span data-ttu-id="86ff1-112">Wystąpienia <xref:System.Xml.XmlDocument> klasy są tworzone przy użyciu jednego z trzech konstruktorów.</span><span class="sxs-lookup"><span data-stu-id="86ff1-112">Instances of the <xref:System.Xml.XmlDocument> class are created using one of its three constructors.</span></span> <span data-ttu-id="86ff1-113">Można utworzyć nowy pusty <xref:System.Xml.XmlDocument> obiekt, wywołując <xref:System.Xml.XmlDocument> Konstruktor klasy bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="86ff1-113">You can create a new, empty <xref:System.Xml.XmlDocument> object by calling the <xref:System.Xml.XmlDocument> class constructor with no parameters.</span></span> <span data-ttu-id="86ff1-114">Po wywołaniu konstruktora Użyj <xref:System.Xml.XmlDocument.Load%2A> metody, aby załadować dane XML do nowego <xref:System.Xml.XmlDocument> obiektu z <xref:System.IO.Stream> obiektu, <xref:System.IO.TextReader> , lub <xref:System.Xml.XmlReader> , a także `string` ścieżkę do pliku XML.</span><span class="sxs-lookup"><span data-stu-id="86ff1-114">After calling the constructor, use the <xref:System.Xml.XmlDocument.Load%2A> method to load XML data into the new <xref:System.Xml.XmlDocument> object from a <xref:System.IO.Stream>, <xref:System.IO.TextReader>, or <xref:System.Xml.XmlReader> object, as well as the `string` path to an XML file.</span></span>  
  
 <span data-ttu-id="86ff1-115">Poniższy przykład ilustruje użycie <xref:System.Xml.XmlDocument> konstruktora klasy bez parametrów i <xref:System.Xml.XmlDocument.Load%2A> metody w celu odczytania dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="86ff1-115">The following example illustrates using the <xref:System.Xml.XmlDocument> class constructor with no parameters and the <xref:System.Xml.XmlDocument.Load%2A> method to read an XML document.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
```  
  
## <a name="determining-the-encoding-of-an-xml-document"></a><span data-ttu-id="86ff1-116">Określanie kodowania dokumentu XML</span><span class="sxs-lookup"><span data-stu-id="86ff1-116">Determining the Encoding of an XML Document</span></span>  

 <span data-ttu-id="86ff1-117"><xref:System.Xml.XmlReader>Obiekt może służyć do odczytywania dokumentu XML oraz do tworzenia <xref:System.Xml.XPath.XPathDocument> i <xref:System.Xml.XmlDocument> obiektów, jak pokazano w poprzednich sekcjach.</span><span class="sxs-lookup"><span data-stu-id="86ff1-117">An <xref:System.Xml.XmlReader> object can be used to read an XML document and to create <xref:System.Xml.XPath.XPathDocument> and <xref:System.Xml.XmlDocument> objects as shown in the previous sections.</span></span> <span data-ttu-id="86ff1-118">Jednak <xref:System.Xml.XmlReader> obiekt może odczytywać dane, które nie są zakodowane i w związku z tym nie udostępniają żadnych informacji o kodowaniu.</span><span class="sxs-lookup"><span data-stu-id="86ff1-118">However, an <xref:System.Xml.XmlReader> object may read data that is not encoded and as a result does not provide any encoding information.</span></span>  
  
 <span data-ttu-id="86ff1-119"><xref:System.Xml.XmlTextReader>Klasa dziedziczy z <xref:System.Xml.XmlReader> klasy, dostarcza informacje o kodowaniu przy użyciu jej <xref:System.Xml.XmlTextReader.Encoding%2A> właściwości i może służyć do tworzenia <xref:System.Xml.XPath.XPathDocument> obiektu lub <xref:System.Xml.XmlDocument> obiektu.</span><span class="sxs-lookup"><span data-stu-id="86ff1-119">The <xref:System.Xml.XmlTextReader> class inherits from the <xref:System.Xml.XmlReader> class, provides encoding information using its <xref:System.Xml.XmlTextReader.Encoding%2A> property, and can be used to create an <xref:System.Xml.XPath.XPathDocument> object or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 <span data-ttu-id="86ff1-120">Aby uzyskać więcej informacji na temat informacji o kodowaniu dostarczonych przez <xref:System.Xml.XmlTextReader> klasę, zapoznaj się z <xref:System.Xml.XmlTextReader.Encoding%2A> właściwością w <xref:System.Xml.XmlTextReader> dokumentacji dotyczącej klasy.</span><span class="sxs-lookup"><span data-stu-id="86ff1-120">For more information about the encoding information provided by the <xref:System.Xml.XmlTextReader> class, see the <xref:System.Xml.XmlTextReader.Encoding%2A> property in the <xref:System.Xml.XmlTextReader> class reference documentation.</span></span>  
  
## <a name="creating-xpathnavigator-objects"></a><span data-ttu-id="86ff1-121">Tworzenie obiektów XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="86ff1-121">Creating XPathNavigator Objects</span></span>  

 <span data-ttu-id="86ff1-122">Po przeczytaniu dokumentu XML do <xref:System.Xml.XPath.XPathDocument> obiektu lub, można <xref:System.Xml.XmlDocument> utworzyć <xref:System.Xml.XPath.XPathNavigator> obiekt do wyboru, szacowania, nawigowania i w niektórych przypadkach, edytować bazowe dane XML.</span><span class="sxs-lookup"><span data-stu-id="86ff1-122">After you have read an XML document into either an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object, you can create an <xref:System.Xml.XPath.XPathNavigator> object to select, evaluate, navigate, and in some cases, edit the underlying XML data.</span></span>  
  
 <span data-ttu-id="86ff1-123"><xref:System.Xml.XPath.XPathDocument> <xref:System.Xml.XmlDocument> Klasy i, oprócz <xref:System.Xml.XmlNode> klasy, implementują <xref:System.Xml.XPath.IXPathNavigable> Interfejs <xref:System.Xml.XPath?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="86ff1-123">Both the <xref:System.Xml.XPath.XPathDocument> and <xref:System.Xml.XmlDocument> classes, in addition to the <xref:System.Xml.XmlNode> class, implement the <xref:System.Xml.XPath.IXPathNavigable> interface of the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="86ff1-124">W związku z tym wszystkie trzy klasy zapewniają <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A> metodę, która zwraca <xref:System.Xml.XPath.XPathNavigator> obiekt.</span><span class="sxs-lookup"><span data-stu-id="86ff1-124">As a result, all three classes provide a <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A> method that returns an <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
### <a name="editing-xml-documents-using-the-xpathnavigator-class"></a><span data-ttu-id="86ff1-125">Edytowanie dokumentów XML przy użyciu klasy XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="86ff1-125">Editing XML Documents using the XPathNavigator Class</span></span>  

 <span data-ttu-id="86ff1-126">Oprócz wyboru, oceny i nawigowania po danych XML, <xref:System.Xml.XPath.XPathNavigator> Klasa może być używana do edycji dokumentu XML w niektórych przypadkach na podstawie obiektu, który go utworzył.</span><span class="sxs-lookup"><span data-stu-id="86ff1-126">In addition to selecting, evaluating, and navigating XML data, the <xref:System.Xml.XPath.XPathNavigator> class can be used to edit an XML document in some cases, based on the object that created it.</span></span>  
  
 <span data-ttu-id="86ff1-127"><xref:System.Xml.XPath.XPathDocument>Klasa jest tylko do odczytu, podczas gdy <xref:System.Xml.XmlDocument> Klasa jest edytowalna i w związku z <xref:System.Xml.XPath.XPathNavigator> tym obiekty utworzone na podstawie <xref:System.Xml.XPath.XPathDocument> obiektu nie mogą być używane do edytowania dokumentu XML, podczas gdy mogą one być utworzone na podstawie <xref:System.Xml.XmlDocument> obiektu.</span><span class="sxs-lookup"><span data-stu-id="86ff1-127">The <xref:System.Xml.XPath.XPathDocument> class is read-only while the <xref:System.Xml.XmlDocument> class is editable and as a result, <xref:System.Xml.XPath.XPathNavigator> objects created from an <xref:System.Xml.XPath.XPathDocument> object cannot be used to edit an XML document while those created from an <xref:System.Xml.XmlDocument> object can.</span></span> <span data-ttu-id="86ff1-128"><xref:System.Xml.XPath.XPathDocument>Klasa powinna być używana do odczytu tylko dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="86ff1-128">The <xref:System.Xml.XPath.XPathDocument> class should be used to read an XML document only.</span></span> <span data-ttu-id="86ff1-129">W przypadkach, gdy konieczne jest edytowanie dokumentu XML lub wymaganie dostępu do dodatkowych funkcji udostępnianych przez <xref:System.Xml.XmlDocument> klasę, takich jak obsługa zdarzeń, <xref:System.Xml.XmlDocument> należy użyć klasy.</span><span class="sxs-lookup"><span data-stu-id="86ff1-129">In cases where you need to edit an XML document, or require access to the additional functionality provided by the <xref:System.Xml.XmlDocument> class, like event handling, the <xref:System.Xml.XmlDocument> class should be used.</span></span>  
  
 <span data-ttu-id="86ff1-130"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>Właściwość <xref:System.Xml.XPath.XPathNavigator> klasy określa, czy <xref:System.Xml.XPath.XPathNavigator> obiekt może edytować dane XML.</span><span class="sxs-lookup"><span data-stu-id="86ff1-130">The <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class specifies if an <xref:System.Xml.XPath.XPathNavigator> object may edit XML data.</span></span>  
  
 <span data-ttu-id="86ff1-131">W poniższej tabeli opisano wartość <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> właściwości dla każdej klasy.</span><span class="sxs-lookup"><span data-stu-id="86ff1-131">The following table describes the value of the <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property for each class.</span></span>  
  
|<span data-ttu-id="86ff1-132"><xref:System.Xml.XPath.IXPathNavigable> Realizacji</span><span class="sxs-lookup"><span data-stu-id="86ff1-132"><xref:System.Xml.XPath.IXPathNavigable> Implementation</span></span>|<span data-ttu-id="86ff1-133"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> Wartościami</span><span class="sxs-lookup"><span data-stu-id="86ff1-133"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> Value</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Xml.XPath.XPathDocument>|`false`|  
|<xref:System.Xml.XmlDocument>|`true`|  
  
## <a name="see-also"></a><span data-ttu-id="86ff1-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="86ff1-134">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="86ff1-135">Przetwarzanie danych XML przy użyciu modelu danych XPath</span><span class="sxs-lookup"><span data-stu-id="86ff1-135">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="86ff1-136">Uzyskiwanie dostępu do danych XML przy użyciu klasy XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="86ff1-136">Accessing XML Data using XPathNavigator</span></span>](accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="86ff1-137">Edytowanie danych XML przy użyciu klasy XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="86ff1-137">Editing XML Data using XPathNavigator</span></span>](editing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="86ff1-138">Weryfikacja schematu przy użyciu klasy XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="86ff1-138">Schema Validation using XPathNavigator</span></span>](schema-validation-using-xpathnavigator.md)
