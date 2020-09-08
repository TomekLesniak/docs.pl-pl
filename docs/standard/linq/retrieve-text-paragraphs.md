---
title: Pobierz tekst akapitów LINQ to XML
description: Dowiedz się, jak znaleźć węzły akapitu w dokumencie WordprocessingML i pobrać tekst z każdego węzła jako ciąg.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 127d635e-e559-408f-90c8-2bb621ca50ac
ms.openlocfilehash: f41e0206f91f022993ed2c48681f124bf84ec603
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553648"
---
# <a name="retrieve-the-text-of-the-paragraphs-linq-to-xml"></a>Pobierz tekst akapitów (LINQ to XML)

Ten przykład kompiluje się w poprzednim przykładzie, [Pobiera akapity i ich style](retrieve-paragraphs-styles.md). Ten nowy przykład pobiera tekst każdego akapitu w postaci ciągu.

Aby pobrać tekst, ten przykład dodaje dodatkowe zapytanie, które iteruje przez kolekcję typów anonimowych i projektów nowej kolekcji typu anonimowego z dodaniem nowego elementu członkowskiego `Text` . Używa <xref:System.Linq.Enumerable.Aggregate%2A> standardowego operatora zapytania do łączenia wielu ciągów w jeden ciąg.

Ta technika (czyli najpierw projekcja do kolekcji typu anonimowego, a następnie użycie tej kolekcji w celu utworzenia nowej kolekcji typu anonimowego) jest powszechną i użyteczną jedną z nich. To zapytanie mogło zostać zapisaną bez projekcji pierwszego typu anonimowego. Jednak ze względu na ocenę z opóźnieniem nie zużywamy znacznie dodatkowej mocy obliczeniowej. Technika tworzy bardziej krótkotrwałe obiekty na stercie, ale nie zmniejsza znacząco wydajności.

Oczywiście można napisać pojedyncze zapytanie, które zawiera funkcje umożliwiające pobranie akapitów, stylu każdego akapitu i tekstu każdego akapitu. Jednak często warto rozdzielić bardziej skomplikowane zapytanie na wiele zapytań, ponieważ otrzymany kod jest bardziej modularny i łatwiejszy w obsłudze. Ponadto, jeśli trzeba ponownie wykorzystać część zapytania, jest to łatwiejsze do refaktoryzacji, jeśli zapytania są zapisywane w ten sposób.

Te zapytania, które są połączone łańcuchowo, wykorzystują model przetwarzania, który jest sprawdzany w [przykładzie zapytań łańcucha](chain-queries-example.md)artykułu.

## <a name="example-determine-the-element-node-style-name-and-text-of-each-paragraph"></a>Przykład: Określanie węzła elementu, nazwy stylu i tekstu każdego akapitu

Ten przykład przetwarza dokument WordprocessingML, określając węzeł elementu, nazwę stylu i tekst każdego akapitu. Ten przykład kompiluje się zgodnie z poprzednimi przykładami w tym samouczku. Nowe zapytanie jest wywoływane w komentarzach w poniższym kodzie.

Instrukcje dotyczące tworzenia dokumentu źródłowego dla tego przykładu znajdują się w [dokumencie Tworzenie źródła Office Open XML](create-source-office-open-xml-document.md).

W tym przykładzie zastosowano klasy z zestawu 'Windowsbase. Używa typów w <xref:System.IO.Packaging?displayProperty=nameWithType> przestrzeni nazw.

```csharp
const string fileName = "SampleDoc.docx";

const string documentRelationshipType =
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";
const string stylesRelationshipType =
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";
const string wordmlNamespace =
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";
XNamespace w = wordmlNamespace;

XDocument xDoc = null;
XDocument styleDoc = null;

using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))
{
    PackageRelationship docPackageRelationship =
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();
    if (docPackageRelationship != null)
    {
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),
          docPackageRelationship.TargetUri);
        PackagePart documentPart = wdPackage.GetPart(documentUri);

        //  Load the document XML in the part into an XDocument instance.
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));

        //  Find the styles part. There will only be one.
        PackageRelationship styleRelation =
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();
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

// Find all paragraphs in the document.
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

// Following is the new query that retrieves the text of
// each paragraph.
var paraWithText =
    from para in paragraphs
    select new
    {
        ParagraphNode = para.ParagraphNode,
        StyleName = para.StyleName,
        Text = para
               .ParagraphNode
               .Elements(w + "r")
               .Elements(w + "t")
               .Aggregate(
                   new StringBuilder(),
                   (s, i) => s.Append((string)i),
                   s => s.ToString()
               )
    };

foreach (var p in paraWithText)
    Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);
```

```vb
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">

Module Module1
    ' Following function is required because Visual Basic doesn't support short circuit evaluation
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, _
                                         ByVal defaultStyle As String) As String
        If (styleNode Is Nothing) Then
            Return defaultStyle
        Else
            Return styleNode.@w:val
        End If
    End Function

    Sub Main()
        Dim fileName = "SampleDoc.docx"

        Dim documentRelationshipType = _
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"
        Dim stylesRelationshipType = _
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"
        Dim wordmlNamespace = _
          "http://schemas.openxmlformats.org/wordprocessingml/2006/main"

        Dim xDoc As XDocument = Nothing
        Dim styleDoc As XDocument = Nothing
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)
            Dim docPackageRelationship As PackageRelationship = _
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()
            If (docPackageRelationship IsNot Nothing) Then
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _
                  docPackageRelationship.TargetUri)
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)

                '  Load the document XML in the part into an XDocument instance.
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))

                '  Find the styles part. There will only be one.
                Dim styleRelation As PackageRelationship = _
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()
                If (styleRelation IsNot Nothing) Then
                    Dim styleUri As Uri = _
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)
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

        ' Find all paragraphs in the document.
        Dim paragraphs = _
            From para In xDoc.Root.<w:body>...<w:p> _
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault _
        Select New With { _
            .ParagraphNode = para, _
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _
        }

        ' Following is the new query that retrieves the text of
        ' each paragraph.
        Dim paraWithText = _
            From para In paragraphs _
            Select New With { _
                .ParagraphNode = para.ParagraphNode, _
                .StyleName = para.StyleName, _
                .Text = para.ParagraphNode.<w:r>.<w:t> _
                    .Aggregate(New StringBuilder(), _
                               Function(s As StringBuilder, i As String) s.Append(CStr(i)), _
                               Function(s As StringBuilder) s.ToString) _
            }

        For Each p In paraWithText
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)
        Next

    End Sub
End Module
```

Wersja języka C# tego przykładu generuje następujące dane wyjściowe:

```conssole
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<
StyleName:Normal ><
StyleName:Normal >The following example prints to the console.<
StyleName:Normal ><
StyleName:Code >using System;<
StyleName:Code ><
StyleName:Code >class Program {<
StyleName:Code >    public static void (string[] args) {<
StyleName:Code >        Console.WriteLine("Hello World");<
StyleName:Code >    }<
StyleName:Code >}<
StyleName:Normal ><
StyleName:Normal >This example produces the following output:<
StyleName:Normal ><
StyleName:Code >Hello World<
```

Wersja Visual Basic tego przykładu generuje następujące dane wyjściowe:

```output
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<
StyleName:Normal ><
StyleName:Normal >The following example prints to the console.<
StyleName:Normal ><
StyleName:Code >Imports System<
StyleName:Code ><
StyleName:Code >Class Program<
StyleName:Code >    Public Shared  Sub Main(ByVal args() As String)<
StyleName:Code >        Console.WriteLine("Hello World")<
StyleName:Code >   End Sub<
StyleName:Code >End Class<
StyleName:Normal ><
StyleName:Normal >This example produces the following output:<
StyleName:Normal ><
StyleName:Code >Hello World<
```

Następny artykuł w tym samouczku pokazuje, jak używać metody rozszerzenia zamiast <xref:System.Linq.Enumerable.Aggregate%2A> , aby połączyć wiele ciągów w jeden ciąg:

- [Refaktoryzacja przy użyciu metody rozszerzenia](refactor-extension-method.md)

## <a name="see-also"></a>Zobacz też

- [Samouczek: manipulowanie zawartością w dokumencie WordprocessingML](xml-shape-wordprocessingml-documents.md)
- [Wykonywanie odroczone i Ocena z opóźnieniem](deferred-execution-lazy-evaluation.md)
