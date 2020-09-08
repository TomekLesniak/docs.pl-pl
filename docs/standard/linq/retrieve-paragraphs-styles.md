---
title: Pobierz akapity i ich style — LINQ to XML
description: Dowiedz się, jak pobrać węzły akapitu i ich style z dokumentu WordprocessingML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
ms.openlocfilehash: 43c6173441dda841236a4397e28d0bb2c7c8d003
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553672"
---
# <a name="retrieve-the-paragraphs-and-their-styles-linq-to-xml"></a><span data-ttu-id="43b43-103">Pobierz akapity i ich style (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="43b43-103">Retrieve the paragraphs and their styles (LINQ to XML)</span></span>

<span data-ttu-id="43b43-104">W tym przykładzie napiszemy zapytanie, które pobiera węzły akapitu z dokumentu WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="43b43-104">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="43b43-105">Identyfikuje także styl każdego akapitu.</span><span class="sxs-lookup"><span data-stu-id="43b43-105">It also identifies the style of each paragraph.</span></span>

<span data-ttu-id="43b43-106">To zapytanie kompiluje zapytanie w poprzednim przykładzie, [wyszukując domyślny styl akapitu](find-default-paragraph-style.md), który Pobiera domyślny styl z listy stylów.</span><span class="sxs-lookup"><span data-stu-id="43b43-106">This query builds on the query in the previous example, [Find the default paragraph style](find-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="43b43-107">Te informacje są wymagane, aby zapytanie mogło zidentyfikować styl akapitów, dla których styl nie został jawnie ustawiony.</span><span class="sxs-lookup"><span data-stu-id="43b43-107">This information is required so that the query can identify the style of paragraphs that don't have a style explicitly set.</span></span> <span data-ttu-id="43b43-108">Style akapitu są ustawiane za pomocą `w:pPr` elementu. Jeśli akapit nie zawiera tego elementu, jest sformatowany przy użyciu stylu domyślnego.</span><span class="sxs-lookup"><span data-stu-id="43b43-108">Paragraph styles are set through the `w:pPr` element; if a paragraph doesn't contain this element, it's formatted with the default style.</span></span>

<span data-ttu-id="43b43-109">W tym artykule wyjaśniono istotność niektórych fragmentów zapytania, a następnie przedstawiono zapytanie w ramach pełnego przykładu pracy.</span><span class="sxs-lookup"><span data-stu-id="43b43-109">This article explains the significance of some pieces of the query, then shows the query as part of a complete working example.</span></span>

## <a name="example-retrieve-all-the-paragraphs-in-a-document-and-the-paragraph-styles"></a><span data-ttu-id="43b43-110">Przykład: Pobierz wszystkie akapity w dokumencie i style akapitu</span><span class="sxs-lookup"><span data-stu-id="43b43-110">Example: Retrieve all the paragraphs in a document, and the paragraph styles</span></span>

<span data-ttu-id="43b43-111">Poniższy kod jest zapytaniem do pobrania wszystkich akapitów w dokumencie i ich stylów:</span><span class="sxs-lookup"><span data-stu-id="43b43-111">The following code is a query to retrieve all the paragraphs in a document and their styles:</span></span>

```csharp
xDoc.Root.Element(w + "body").Descendants(w + "p")
```

```vb
xDoc.Root.<w:body>...<w:p>
```

<span data-ttu-id="43b43-112">To wyrażenie jest podobne do źródła zapytania w poprzednim przykładzie [Znajdź domyślny styl akapitu](find-default-paragraph-style.md).</span><span class="sxs-lookup"><span data-stu-id="43b43-112">This expression is similar to the source of the query in the previous example, [Find the default paragraph style](find-default-paragraph-style.md).</span></span> <span data-ttu-id="43b43-113">Główną różnicą jest to, że używa <xref:System.Xml.Linq.XContainer.Descendants%2A> osi zamiast <xref:System.Xml.Linq.XContainer.Elements%2A> osi.</span><span class="sxs-lookup"><span data-stu-id="43b43-113">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="43b43-114">Zapytanie używa <xref:System.Xml.Linq.XContainer.Descendants%2A> osi, ponieważ w dokumentach, w których znajdują się sekcje, akapity nie będą bezpośrednimi elementami podrzędnymi elementu body, a akapity będą dwa poziomy w hierarchii.</span><span class="sxs-lookup"><span data-stu-id="43b43-114">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs won't be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="43b43-115">Korzystając z <xref:System.Xml.Linq.XContainer.Descendants%2A> osi, kod będzie działał niezależnie od tego, czy dokument korzysta z sekcji.</span><span class="sxs-lookup"><span data-stu-id="43b43-115">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work whether or not the document uses sections.</span></span>

## <a name="example-use-a-let-clause-to-determine-the-element-that-contains-the-style-node"></a><span data-ttu-id="43b43-116">Przykład: Użyj `let` klauzuli, aby określić element, który zawiera węzeł stylu</span><span class="sxs-lookup"><span data-stu-id="43b43-116">Example: Use a `let` clause to determine the element that contains the style node</span></span>

<span data-ttu-id="43b43-117">Poniższe zapytanie używa `let` klauzuli do określenia elementu zawierającego węzeł stylu:</span><span class="sxs-lookup"><span data-stu-id="43b43-117">The following query uses a `let` clause to determine the element that contains the style node:</span></span>

```csharp
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()
```

 ```vb
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()
```

<span data-ttu-id="43b43-118">`let`Klauzula ( `Let` w wersji Visual Basic) najpierw używa <xref:System.Xml.Linq.XContainer.Elements%2A> osi do znajdowania wszystkich elementów o nazwie `pPr` , a następnie używa <xref:System.Xml.Linq.Extensions.Elements%2A> metody rozszerzenia do znajdowania wszystkich elementów podrzędnych o nazwie `pStyle` , a wreszcie używa <xref:System.Linq.Enumerable.FirstOrDefault%2A> standardowego operatora zapytań do konwertowania kolekcji na pojedynczą.</span><span class="sxs-lookup"><span data-stu-id="43b43-118">The `let` clause (`Let` in the Visual Basic version) first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="43b43-119">Jeśli kolekcja jest pusta, `styleNode` jest ustawiona na `null` ( `Nothing` w wersji Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="43b43-119">If the collection is empty, `styleNode` is set to `null` (`Nothing` in the Visual Basic version).</span></span> <span data-ttu-id="43b43-120">Jest to przydatny idiom do wyszukiwania `pStyle` węzła podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="43b43-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="43b43-121">Należy pamiętać, że jeśli `pPr` węzeł podrzędny nie istnieje, kod nie kończy się niepowodzeniem, zwracając wyjątek; zamiast tego `styleNode` jest ustawiony na `null` ( `Nothing` ), który jest pożądanym zachowaniem tej `let` `Let` klauzuli ().</span><span class="sxs-lookup"><span data-stu-id="43b43-121">Note that if the `pPr` child node doesn't exist, the code doesn't fail by throwing an exception; instead, `styleNode` is set to `null` (`Nothing`), which is the desired behavior of this `let`(`Let`) clause.</span></span>

<span data-ttu-id="43b43-122">Jeśli nie ma elementu, `styleNode` jest ustawiony na `null` ( `Nothing` ).</span><span class="sxs-lookup"><span data-stu-id="43b43-122">If there is no element, then `styleNode` is set to `null` (`Nothing`).</span></span>

<span data-ttu-id="43b43-123">Zapytanie projektuje kolekcję typu anonimowego z dwoma członkami `StyleName` i `ParagraphNode` .</span><span class="sxs-lookup"><span data-stu-id="43b43-123">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>

## <a name="example-retrieve-the-paragraph-nodes-from-a-wordprocessingml-document"></a><span data-ttu-id="43b43-124">Przykład: Pobierz węzły akapitu z dokumentu WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="43b43-124">Example: Retrieve the paragraph nodes from a WordprocessingML document</span></span>

<span data-ttu-id="43b43-125">Ten przykład przetwarza dokument WordprocessingML, pobierając węzły akapitu.</span><span class="sxs-lookup"><span data-stu-id="43b43-125">This example processes a WordprocessingML document, retrieving the paragraph nodes.</span></span> <span data-ttu-id="43b43-126">Identyfikuje także styl każdego akapitu.</span><span class="sxs-lookup"><span data-stu-id="43b43-126">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="43b43-127">Ten przykład kompiluje się zgodnie z poprzednimi przykładami w tym samouczku.</span><span class="sxs-lookup"><span data-stu-id="43b43-127">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="43b43-128">Nowe zapytanie jest wywoływane w komentarzach w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="43b43-128">The new query is called out in comments in the code below.</span></span>

<span data-ttu-id="43b43-129">Instrukcje dotyczące tworzenia dokumentu źródłowego dla tego przykładu znajdują się w [dokumencie Tworzenie źródła Office Open XML](create-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="43b43-129">The instructions for creating the source document for this example are in [Create the source Office Open XML document](create-source-office-open-xml-document.md).</span></span>

<span data-ttu-id="43b43-130">Ten przykład używa klas znalezionych w zestawie 'Windowsbase.</span><span class="sxs-lookup"><span data-stu-id="43b43-130">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="43b43-131">Używa typów w <xref:System.IO.Packaging?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="43b43-131">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>

```csharp
const string fileName = "SampleDoc.docx";

const string documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";
const string stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";
const string wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main";
XNamespace w = wordmlNamespace;

XDocument xDoc = null;
XDocument styleDoc = null;

using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))
{
    PackageRelationship docPackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();
    if (docPackageRelationship != null)
    {
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative), docPackageRelationship.TargetUri);
        PackagePart documentPart = wdPackage.GetPart(documentUri);

        //  Load the document XML in the part into an XDocument instance.
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));

        //  Find the styles part. There will only be one.
        PackageRelationship styleRelation = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();
        if (styleRelation != null)
        {
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);
            PackagePart stylePart = wdPackage.GetPart(styleUri);

            //  Load the style XML in the part into an XDocument instance.
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));
        }
    }
}

string defaultStyle =
    (string)(
        from style in styleDoc.Root.Elements(w + "style")
        where (string)style.Attribute(w + "type") == "paragraph"&&
              (string)style.Attribute(w + "default") == "1"
              select style
    ).First().Attribute(w + "styleId");

// Following is the new query that finds all paragraphs in the
// document and their styles.
var paragraphs =
    from para in xDoc
                 .Root
                 .Element(w + "body")
                 .Descendants(w + "p")
    let styleNode = para
                    .Elements(w + "pPr")
                    .Elements(w + "pStyle")
                    .FirstOrDefault()
    select new
    {
        ParagraphNode = para,
        StyleName = styleNode != null ?
            (string)styleNode.Attribute(w + "val") :
            defaultStyle
    };

foreach (var p in paragraphs)
    Console.WriteLine("StyleName:{0}", p.StyleName);
```

```vb
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">

Module Module1
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, ByVal defaultStyle As String) As String
        If (styleNode Is Nothing) Then
            Return defaultStyle
        Else
            Return styleNode.@w:val
        End If
    End Function

    Sub Main()
        Dim fileName = "SampleDoc.docx"

        Dim documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"
        Dim stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"
        Dim wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main"

        Dim xDoc As XDocument = Nothing
        Dim styleDoc As XDocument = Nothing
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)
            Dim docPackageRelationship As PackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()
            If (docPackageRelationship IsNot Nothing) Then
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), docPackageRelationship.TargetUri)
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)

                '  Load the document XML in the part into an XDocument instance.
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))

                '  Find the styles part. There will only be one.
                Dim styleRelation As PackageRelationship = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()
                If (styleRelation IsNot Nothing) Then
                    Dim styleUri As Uri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)

                    '  Load the style XML in the part into an XDocument instance.
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))
                End If
            End If
        End Using

        Dim defaultStyle As String = _
            ( _
                From style In styleDoc.Root.<w:style> _
                Where style.@w:type = "paragraph" And _
                      style.@w:default = "1" _
                Select style _
            ).First().@w:styleId

        ' Following is the new query that finds all paragraphs in the
        ' document and their styles.
        Dim paragraphs = _
            From para In xDoc.Root.<w:body>...<w:p> _
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault() _
        Select New With { _
            .ParagraphNode = para, _
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _
        }

        For Each p In paragraphs
            Console.WriteLine("StyleName:{0}", p.StyleName)
        Next

    End Sub
End Module
```

<span data-ttu-id="43b43-132">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="43b43-132">This example produces the following output:</span></span>

```output
StyleName:Heading1
StyleName:Normal
StyleName:Normal
StyleName:Normal
StyleName:Code
StyleName:Code
StyleName:Code
StyleName:Code
StyleName:Code
StyleName:Code
StyleName:Code
StyleName:Normal
StyleName:Normal
StyleName:Normal
StyleName:Code
```

<span data-ttu-id="43b43-133">W następnym artykule z tego samouczka pokazano, jak utworzyć zapytanie w celu pobrania tekstu akapitów:</span><span class="sxs-lookup"><span data-stu-id="43b43-133">The next article in this tutorial shows how to create a query to retrieve the text of paragraphs:</span></span>

- [<span data-ttu-id="43b43-134">Pobierz tekst akapitów</span><span class="sxs-lookup"><span data-stu-id="43b43-134">Retrieve the text of the paragraphs</span></span>](retrieve-text-paragraphs.md)

## <a name="see-also"></a><span data-ttu-id="43b43-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="43b43-135">See also</span></span>

- [<span data-ttu-id="43b43-136">Samouczek: manipulowanie zawartością w dokumencie WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="43b43-136">Tutorial: Manipulate content in a WordprocessingML document</span></span>](xml-shape-wordprocessingml-documents.md)
