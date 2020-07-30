---
title: XDocument — Omówienie klasy (C#)
description: Klasa XDocument w języku C# zawiera informacje niezbędne do prawidłowego dokumentu XML, w tym deklarację XML, instrukcje przetwarzania i komentarze.
ms.date: 07/20/2015
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: 6d522cef25e99e4a5ea54e644855c8dfa7a05f4a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302194"
---
# <a name="xdocument-class-overview-c"></a><span data-ttu-id="73890-103">XDocument — Omówienie klasy (C#)</span><span class="sxs-lookup"><span data-stu-id="73890-103">XDocument Class Overview (C#)</span></span>
<span data-ttu-id="73890-104">Ten temat zawiera wprowadzenie do <xref:System.Xml.Linq.XDocument> klasy.</span><span class="sxs-lookup"><span data-stu-id="73890-104">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="73890-105">Przegląd klasy XDocument</span><span class="sxs-lookup"><span data-stu-id="73890-105">Overview of the XDocument class</span></span>  
 <span data-ttu-id="73890-106"><xref:System.Xml.Linq.XDocument>Klasa zawiera informacje niezbędne do prawidłowego dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="73890-106">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="73890-107">Obejmuje to deklarację XML, instrukcje przetwarzania i komentarze.</span><span class="sxs-lookup"><span data-stu-id="73890-107">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="73890-108">Należy pamiętać, że tylko należy utworzyć <xref:System.Xml.Linq.XDocument> obiekty, jeśli wymagane są konkretne funkcje dostarczone przez <xref:System.Xml.Linq.XDocument> klasę.</span><span class="sxs-lookup"><span data-stu-id="73890-108">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="73890-109">W wielu przypadkach można bezpośrednio korzystać z programu <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="73890-109">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="73890-110">Praca bezpośrednio z programem <xref:System.Xml.Linq.XElement> to prostszy model programowania.</span><span class="sxs-lookup"><span data-stu-id="73890-110">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="73890-111"><xref:System.Xml.Linq.XDocument>pochodzi od <xref:System.Xml.Linq.XContainer> .</span><span class="sxs-lookup"><span data-stu-id="73890-111"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="73890-112">W związku z tym może zawierać węzłów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="73890-112">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="73890-113">Jednak <xref:System.Xml.Linq.XDocument> obiekty mogą mieć tylko jeden węzeł podrzędny <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="73890-113">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="73890-114">Odzwierciedla to standard XML, że w dokumencie XML może istnieć tylko jeden element główny.</span><span class="sxs-lookup"><span data-stu-id="73890-114">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="73890-115">Składniki klasy XDocument</span><span class="sxs-lookup"><span data-stu-id="73890-115">Components of XDocument</span></span>  
 <span data-ttu-id="73890-116"><xref:System.Xml.Linq.XDocument>Może zawierać następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="73890-116">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
- <span data-ttu-id="73890-117">Jeden <xref:System.Xml.Linq.XDeclaration> obiekt.</span><span class="sxs-lookup"><span data-stu-id="73890-117">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="73890-118"><xref:System.Xml.Linq.XDeclaration>umożliwia określenie odpowiednich części deklaracji XML: wersji XML, kodowania dokumentu oraz tego, czy dokument XML jest autonomiczny.</span><span class="sxs-lookup"><span data-stu-id="73890-118"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
- <span data-ttu-id="73890-119">Jeden <xref:System.Xml.Linq.XElement> obiekt.</span><span class="sxs-lookup"><span data-stu-id="73890-119">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="73890-120">Jest to główny węzeł dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="73890-120">This is the root node of the XML document.</span></span>  
  
- <span data-ttu-id="73890-121">Dowolna liczba <xref:System.Xml.Linq.XProcessingInstruction> obiektów.</span><span class="sxs-lookup"><span data-stu-id="73890-121">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="73890-122">Instrukcja przetwarzania komunikuje informacje z aplikacją, która przetwarza kod XML.</span><span class="sxs-lookup"><span data-stu-id="73890-122">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
- <span data-ttu-id="73890-123">Dowolna liczba <xref:System.Xml.Linq.XComment> obiektów.</span><span class="sxs-lookup"><span data-stu-id="73890-123">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="73890-124">Komentarze będą elementy równorzędne z elementem głównym.</span><span class="sxs-lookup"><span data-stu-id="73890-124">The comments will be siblings to the root element.</span></span> <span data-ttu-id="73890-125"><xref:System.Xml.Linq.XComment>Obiekt nie może być pierwszym argumentem na liście, ponieważ nie jest on prawidłowy dla dokumentu XML, aby można było zacząć od komentarza.</span><span class="sxs-lookup"><span data-stu-id="73890-125">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
- <span data-ttu-id="73890-126">Jeden <xref:System.Xml.Linq.XDocumentType> dla DTD.</span><span class="sxs-lookup"><span data-stu-id="73890-126">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="73890-127">W przypadku serializacji elementu <xref:System.Xml.Linq.XDocument> , nawet jeśli `XDocument.Declaration` jest `null` , wynik będzie miał deklarację XML, jeśli moduł zapisujący ma `Writer.Settings.OmitXmlDeclaration` ustawioną wartość `false` (wartość domyślna).</span><span class="sxs-lookup"><span data-stu-id="73890-127">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="73890-128">Domyślnie program [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Ustawia wersję na "1,0" i ustawia kodowanie na "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="73890-128">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="73890-129">Korzystanie z XElement bez klasy XDocument</span><span class="sxs-lookup"><span data-stu-id="73890-129">Using XElement without XDocument</span></span>  
 <span data-ttu-id="73890-130">Jak wspomniano wcześniej, <xref:System.Xml.Linq.XElement> Klasa jest klasą główną w [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] interfejsie programowania.</span><span class="sxs-lookup"><span data-stu-id="73890-130">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="73890-131">W wielu przypadkach aplikacja nie będzie wymagać tworzenia dokumentu.</span><span class="sxs-lookup"><span data-stu-id="73890-131">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="73890-132">Korzystając z <xref:System.Xml.Linq.XElement> klasy, można utworzyć drzewo XML, dodać do niego inne drzewa XML, zmodyfikować drzewo XML i zapisać.</span><span class="sxs-lookup"><span data-stu-id="73890-132">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="73890-133">Przy użyciu metody XDocument</span><span class="sxs-lookup"><span data-stu-id="73890-133">Using XDocument</span></span>  
 <span data-ttu-id="73890-134">Aby utworzyć obiekt <xref:System.Xml.Linq.XDocument> , użyj konstrukcji funkcjonalnej, tak jak w przypadku konstruowania <xref:System.Xml.Linq.XElement> obiektów.</span><span class="sxs-lookup"><span data-stu-id="73890-134">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="73890-135">Poniższy kod tworzy <xref:System.Xml.Linq.XDocument> obiekt i powiązane z nim obiekty zawarte.</span><span class="sxs-lookup"><span data-stu-id="73890-135">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
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
  
 <span data-ttu-id="73890-136">Podczas badania test.xml pliku otrzymujesz następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="73890-136">When you examine the file test.xml, you get the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73890-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="73890-137">See also</span></span>

- [<span data-ttu-id="73890-138">Omówienie programowania LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="73890-138">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
