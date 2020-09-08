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
# <a name="retrieve-the-paragraphs-and-their-styles-linq-to-xml"></a>Pobierz akapity i ich style (LINQ to XML)

W tym przykładzie napiszemy zapytanie, które pobiera węzły akapitu z dokumentu WordprocessingML. Identyfikuje także styl każdego akapitu.

To zapytanie kompiluje zapytanie w poprzednim przykładzie, [wyszukując domyślny styl akapitu](find-default-paragraph-style.md), który Pobiera domyślny styl z listy stylów. Te informacje są wymagane, aby zapytanie mogło zidentyfikować styl akapitów, dla których styl nie został jawnie ustawiony. Style akapitu są ustawiane za pomocą `w:pPr` elementu. Jeśli akapit nie zawiera tego elementu, jest sformatowany przy użyciu stylu domyślnego.

W tym artykule wyjaśniono istotność niektórych fragmentów zapytania, a następnie przedstawiono zapytanie w ramach pełnego przykładu pracy.

## <a name="example-retrieve-all-the-paragraphs-in-a-document-and-the-paragraph-styles"></a>Przykład: Pobierz wszystkie akapity w dokumencie i style akapitu

Poniższy kod jest zapytaniem do pobrania wszystkich akapitów w dokumencie i ich stylów:

```csharp
xDoc.Root.Element(w + "body").Descendants(w + "p")
```

```vb
xDoc.Root.<w:body>...<w:p>
```

To wyrażenie jest podobne do źródła zapytania w poprzednim przykładzie [Znajdź domyślny styl akapitu](find-default-paragraph-style.md). Główną różnicą jest to, że używa <xref:System.Xml.Linq.XContainer.Descendants%2A> osi zamiast <xref:System.Xml.Linq.XContainer.Elements%2A> osi. Zapytanie używa <xref:System.Xml.Linq.XContainer.Descendants%2A> osi, ponieważ w dokumentach, w których znajdują się sekcje, akapity nie będą bezpośrednimi elementami podrzędnymi elementu body, a akapity będą dwa poziomy w hierarchii. Korzystając z <xref:System.Xml.Linq.XContainer.Descendants%2A> osi, kod będzie działał niezależnie od tego, czy dokument korzysta z sekcji.

## <a name="example-use-a-let-clause-to-determine-the-element-that-contains-the-style-node"></a>Przykład: Użyj `let` klauzuli, aby określić element, który zawiera węzeł stylu

Poniższe zapytanie używa `let` klauzuli do określenia elementu zawierającego węzeł stylu:

```csharp
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()
```

 ```vb
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()
```

`let`Klauzula ( `Let` w wersji Visual Basic) najpierw używa <xref:System.Xml.Linq.XContainer.Elements%2A> osi do znajdowania wszystkich elementów o nazwie `pPr` , a następnie używa <xref:System.Xml.Linq.Extensions.Elements%2A> metody rozszerzenia do znajdowania wszystkich elementów podrzędnych o nazwie `pStyle` , a wreszcie używa <xref:System.Linq.Enumerable.FirstOrDefault%2A> standardowego operatora zapytań do konwertowania kolekcji na pojedynczą. Jeśli kolekcja jest pusta, `styleNode` jest ustawiona na `null` ( `Nothing` w wersji Visual Basic). Jest to przydatny idiom do wyszukiwania `pStyle` węzła podrzędnego. Należy pamiętać, że jeśli `pPr` węzeł podrzędny nie istnieje, kod nie kończy się niepowodzeniem, zwracając wyjątek; zamiast tego `styleNode` jest ustawiony na `null` ( `Nothing` ), który jest pożądanym zachowaniem tej `let` `Let` klauzuli ().

Jeśli nie ma elementu, `styleNode` jest ustawiony na `null` ( `Nothing` ).

Zapytanie projektuje kolekcję typu anonimowego z dwoma członkami `StyleName` i `ParagraphNode` .

## <a name="example-retrieve-the-paragraph-nodes-from-a-wordprocessingml-document"></a>Przykład: Pobierz węzły akapitu z dokumentu WordprocessingML

Ten przykład przetwarza dokument WordprocessingML, pobierając węzły akapitu. Identyfikuje także styl każdego akapitu. Ten przykład kompiluje się zgodnie z poprzednimi przykładami w tym samouczku. Nowe zapytanie jest wywoływane w komentarzach w poniższym kodzie.

Instrukcje dotyczące tworzenia dokumentu źródłowego dla tego przykładu znajdują się w [dokumencie Tworzenie źródła Office Open XML](create-source-office-open-xml-document.md).

Ten przykład używa klas znalezionych w zestawie 'Windowsbase. Używa typów w <xref:System.IO.Packaging?displayProperty=nameWithType> przestrzeni nazw.

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

Ten przykład generuje następujące wyniki:

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

W następnym artykule z tego samouczka pokazano, jak utworzyć zapytanie w celu pobrania tekstu akapitów:

- [Pobierz tekst akapitów](retrieve-text-paragraphs.md)

## <a name="see-also"></a>Zobacz też

- [Samouczek: manipulowanie zawartością w dokumencie WordprocessingML](xml-shape-wordprocessingml-documents.md)
