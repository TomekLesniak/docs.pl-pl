---
title: Klasa XDocument — Omówienie
description: Klasa LINQ to XML XDocument zawiera informacje niezbędne do prawidłowego dokumentu XML. W wielu przypadkach nie potrzebujesz funkcji obiektu XDocument i zamiast tego można użyć obiektu XElement.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: c26b7ac42733aad24d831f4a0a181e0fd8275eaf
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552924"
---
# <a name="xdocument-class-overview"></a><span data-ttu-id="3518c-104">Klasa XDocument — Omówienie</span><span class="sxs-lookup"><span data-stu-id="3518c-104">XDocument class overview</span></span>

<span data-ttu-id="3518c-105"><xref:System.Xml.Linq.XDocument>Klasa zawiera informacje niezbędne do prawidłowego dokumentu XML, który zawiera deklarację XML, instrukcje przetwarzania i komentarze.</span><span class="sxs-lookup"><span data-stu-id="3518c-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document, which includes an XML declaration, processing instructions, and comments.</span></span>

<span data-ttu-id="3518c-106">Tylko wtedy, <xref:System.Xml.Linq.XDocument> gdy wymagane są konkretne funkcje dostarczone przez klasę, należy utworzyć obiekty <xref:System.Xml.Linq.XDocument> .</span><span class="sxs-lookup"><span data-stu-id="3518c-106">You only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="3518c-107">W wielu przypadkach można bezpośrednio korzystać z programu <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="3518c-107">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="3518c-108">Praca bezpośrednio z programem <xref:System.Xml.Linq.XElement> to prostszy model programowania.</span><span class="sxs-lookup"><span data-stu-id="3518c-108">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>

<span data-ttu-id="3518c-109"><xref:System.Xml.Linq.XDocument> pochodzi z <xref:System.Xml.Linq.XContainer> , więc może zawierać węzły podrzędne.</span><span class="sxs-lookup"><span data-stu-id="3518c-109"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>, so it can contain child nodes.</span></span> <span data-ttu-id="3518c-110">Jednak <xref:System.Xml.Linq.XDocument> obiekty mogą mieć tylko jeden węzeł podrzędny <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="3518c-110">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="3518c-111">Odzwierciedla to standard XML, że w dokumencie XML może istnieć tylko jeden element główny.</span><span class="sxs-lookup"><span data-stu-id="3518c-111">This reflects the XML standard that there can be only one root element in an XML document.</span></span>

## <a name="components-of-xdocument"></a><span data-ttu-id="3518c-112">Składniki klasy XDocument</span><span class="sxs-lookup"><span data-stu-id="3518c-112">Components of XDocument</span></span>

<span data-ttu-id="3518c-113"><xref:System.Xml.Linq.XDocument>Może zawierać następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="3518c-113">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>

- <span data-ttu-id="3518c-114">Jeden <xref:System.Xml.Linq.XDeclaration> obiekt.</span><span class="sxs-lookup"><span data-stu-id="3518c-114">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="3518c-115"><xref:System.Xml.Linq.XDeclaration> umożliwia określenie odpowiednich części deklaracji XML: wersji XML, kodowania dokumentu oraz tego, czy dokument XML jest autonomiczny.</span><span class="sxs-lookup"><span data-stu-id="3518c-115"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is standalone.</span></span>
- <span data-ttu-id="3518c-116">Jeden <xref:System.Xml.Linq.XElement> obiekt.</span><span class="sxs-lookup"><span data-stu-id="3518c-116">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="3518c-117">Ten obiekt jest węzłem głównym dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="3518c-117">This object is the root node of the XML document.</span></span>
- <span data-ttu-id="3518c-118">Dowolna liczba <xref:System.Xml.Linq.XProcessingInstruction> obiektów.</span><span class="sxs-lookup"><span data-stu-id="3518c-118">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="3518c-119">Instrukcja przetwarzania komunikuje informacje z aplikacją, która przetwarza kod XML.</span><span class="sxs-lookup"><span data-stu-id="3518c-119">A processing instruction communicates information to an application that processes the XML.</span></span>
- <span data-ttu-id="3518c-120">Dowolna liczba <xref:System.Xml.Linq.XComment> obiektów.</span><span class="sxs-lookup"><span data-stu-id="3518c-120">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="3518c-121">Komentarze będą elementy równorzędne z elementem głównym.</span><span class="sxs-lookup"><span data-stu-id="3518c-121">The comments will be siblings to the root element.</span></span> <span data-ttu-id="3518c-122"><xref:System.Xml.Linq.XComment>Obiekt nie może być pierwszym argumentem na liście, ponieważ nie jest on prawidłowy dla dokumentu XML, aby można było zacząć od komentarza.</span><span class="sxs-lookup"><span data-stu-id="3518c-122">The <xref:System.Xml.Linq.XComment> object can't be the first argument in the list, because it's not valid for an XML document to start with a comment.</span></span>
- <span data-ttu-id="3518c-123">Jeden <xref:System.Xml.Linq.XDocumentType> dla DTD.</span><span class="sxs-lookup"><span data-stu-id="3518c-123">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>

<span data-ttu-id="3518c-124">W przypadku serializacji elementu <xref:System.Xml.Linq.XDocument> , nawet jeśli `XDocument.Declaration` jest `null` , wynik będzie miał deklarację XML, jeśli moduł zapisujący ma `Writer.Settings.OmitXmlDeclaration` ustawioną wartość `false` (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="3518c-124">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>

<span data-ttu-id="3518c-125">Domyślnie program LINQ to XML ustawia wersję na "1,0" i ustawia kodowanie na "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="3518c-125">By default, LINQ to XML sets the version to "1.0", and sets the encoding to "utf-8".</span></span>

## <a name="use-xelement-without-xdocument"></a><span data-ttu-id="3518c-126">Użyj XElement bez metody XDocument</span><span class="sxs-lookup"><span data-stu-id="3518c-126">Use XElement without XDocument</span></span>

<span data-ttu-id="3518c-127">Jak wspomniano wcześniej, <xref:System.Xml.Linq.XElement> Klasa jest klasą główną w interfejsie programowania LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="3518c-127">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the LINQ to XML programming interface.</span></span> <span data-ttu-id="3518c-128">W wielu przypadkach aplikacja nie będzie wymagać tworzenia dokumentu.</span><span class="sxs-lookup"><span data-stu-id="3518c-128">In many cases, your application won't require that you create a document.</span></span> <span data-ttu-id="3518c-129">Korzystając z <xref:System.Xml.Linq.XElement> klasy, można:</span><span class="sxs-lookup"><span data-stu-id="3518c-129">By using the <xref:System.Xml.Linq.XElement> class, you can:</span></span>

- <span data-ttu-id="3518c-130">Utwórz drzewo XML.</span><span class="sxs-lookup"><span data-stu-id="3518c-130">Create an XML tree.</span></span>
- <span data-ttu-id="3518c-131">Dodaj do niego inne drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="3518c-131">Add other XML trees to it.</span></span>
- <span data-ttu-id="3518c-132">Zmodyfikuj drzewo XML.</span><span class="sxs-lookup"><span data-stu-id="3518c-132">Modify the XML tree.</span></span>
- <span data-ttu-id="3518c-133">Zapisz go.</span><span class="sxs-lookup"><span data-stu-id="3518c-133">Save it.</span></span>

## <a name="use-xdocument"></a><span data-ttu-id="3518c-134">Użyj metody XDocument</span><span class="sxs-lookup"><span data-stu-id="3518c-134">Use XDocument</span></span>

<span data-ttu-id="3518c-135">Aby utworzyć obiekt <xref:System.Xml.Linq.XDocument> , użyj konstrukcji funkcjonalnej, tak jak w przypadku konstruowania <xref:System.Xml.Linq.XElement> obiektów.</span><span class="sxs-lookup"><span data-stu-id="3518c-135">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>

<span data-ttu-id="3518c-136">Poniższy przykład tworzy <xref:System.Xml.Linq.XDocument> obiekt i powiązane z nim obiekty zawarte.</span><span class="sxs-lookup"><span data-stu-id="3518c-136">The following example creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>

```csharp
XDocument d = new XDocument(
    new XComment("This is a comment."),
    new XProcessingInstruction("xml-stylesheet",
        "href='mystyle.css' title='Compact' type='text/css'"),
    new XElement("Pubs",
        new XElement("Book",
            new XElement("Title", "Artifacts of Roman Civilization"),
            new XElement("Author", "Moreno, Jordao")
        ),
        new XElement("Book",
            new XElement("Title", "Midieval Tools and Implements"),
            new XElement("Author", "Gazit, Inbar")
        )
    ),
    new XComment("This is another comment.")
);
d.Declaration = new XDeclaration("1.0", "utf-8", "true");
Console.WriteLine(d);

d.Save("test.xml");
```

```vb
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>
                       <!--This is a comment.-->
                       <?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>
                       <Pubs>
                           <Book>
                               <Title>Artifacts of Roman Civilization</Title>
                               <Author>Moreno, Jordao</Author>
                           </Book>
                           <Book>
                               <Title>Midieval Tools and Implements</Title>
                               <Author>Gazit, Inbar</Author>
                           </Book>
                       </Pubs>
                       <!--This is another comment.-->
doc.Save("test.xml")
```

<span data-ttu-id="3518c-137">Przykład generuje dane wyjściowe w test.xml:</span><span class="sxs-lookup"><span data-stu-id="3518c-137">The example produces this output in test.xml:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--This is a comment.-->
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>
<Pubs>
  <Book>
    <Title>Artifacts of Roman Civilization</Title>
    <Author>Moreno, Jordao</Author>
  </Book>
  <Book>
    <Title>Midieval Tools and Implements</Title>
    <Author>Gazit, Inbar</Author>
  </Book>
</Pubs>
<!--This is another comment.-->
```

## <a name="see-also"></a><span data-ttu-id="3518c-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3518c-138">See also</span></span>

- [<span data-ttu-id="3518c-139">Przegląd LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="3518c-139">LINQ to XML overview</span></span>](linq-xml-overview.md)
