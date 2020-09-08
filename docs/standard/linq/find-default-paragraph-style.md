---
title: Znajdź domyślny styl akapitu — LINQ to XML
description: Dowiedz się, jak znaleźć domyślny styl akapitów w dokumencie WordprocessingML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
ms.openlocfilehash: 0e66856a551410dd488148ff678b684489396d62
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552900"
---
# <a name="find-the-default-paragraph-style-linq-to-xml"></a><span data-ttu-id="1bb05-103">Znajdź domyślny styl akapitu (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1bb05-103">Find the default paragraph style (LINQ to XML)</span></span>

<span data-ttu-id="1bb05-104">Pierwsze zadanie w [samouczku: manipulowanie zawartością w dokumencie WordprocessingML](xml-shape-wordprocessingml-documents.md) polega na znalezieniu domyślnego stylu akapitów w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="1bb05-104">The first task in [Tutorial: Manipulate content in a WordprocessingML document](xml-shape-wordprocessingml-documents.md) is to find the default style of paragraphs in the document.</span></span>

## <a name="example-find-the-default-style-name"></a><span data-ttu-id="1bb05-105">Przykład: Znajdź nazwę stylu domyślnego</span><span class="sxs-lookup"><span data-stu-id="1bb05-105">Example: Find the default style name</span></span>

<span data-ttu-id="1bb05-106">W poniższym przykładzie zostanie otwarty dokument pakietu Office Open XML WordprocessingML, znajduje się w nim części dokumentu i stylu pakietu, a następnie wykonywana jest kwerenda, która znajduje domyślną nazwę stylu.</span><span class="sxs-lookup"><span data-stu-id="1bb05-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="1bb05-107">Aby uzyskać informacje na temat pakietów dokumentów Office Open XML i części, które zawierają, zobacz [szczegóły dotyczące dokumentów pakietu Office Open XML WordprocessingML](wordprocessingml-document-styles.md).</span><span class="sxs-lookup"><span data-stu-id="1bb05-107">For information about Office Open XML document packages, and the parts they comprise, see [Details of Office Open XML WordprocessingML documents](wordprocessingml-document-styles.md).</span></span>

<span data-ttu-id="1bb05-108">Zapytanie znajduje węzeł o nazwie `w:style` , który ma atrybut o nazwie o `w:type` wartości "Paragraph", a także ma atrybut o nazwie o `w:default` wartości "1".</span><span class="sxs-lookup"><span data-stu-id="1bb05-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="1bb05-109">Ponieważ będzie istnieć tylko jeden węzeł XML z tymi atrybutami, zapytanie używa <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operatora do konwersji kolekcji na pojedynczą.</span><span class="sxs-lookup"><span data-stu-id="1bb05-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="1bb05-110">Następnie pobiera wartość atrybutu o nazwie `w:styleId` .</span><span class="sxs-lookup"><span data-stu-id="1bb05-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>

<span data-ttu-id="1bb05-111">W tym przykładzie zastosowano klasy z zestawu 'Windowsbase.</span><span class="sxs-lookup"><span data-stu-id="1bb05-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="1bb05-112">Używa typów w <xref:System.IO.Packaging?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="1bb05-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>

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

// The following query finds all the paragraphs that have the default style.
string defaultStyle =
    (string)(
        from style in styleDoc.Root.Elements(w + "style")
        where (string)style.Attribute(w + "type") == "paragraph"&&
              (string)style.Attribute(w + "default") == "1"
              select style
    ).First().Attribute(w + "styleId");

Console.WriteLine("The default style is: {0}", defaultStyle);
```

```vb
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">

Module Module1

    Sub Main()

        Const fileName As String = "SampleDoc.docx"

        Const documentRelationshipType As String = _
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"
        Const stylesRelationshipType As String = _
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"

        Dim xDoc As XDocument = Nothing
        Dim styleDoc As XDocument = Nothing

        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)
            Dim docPackageRelationship As PackageRelationship = _
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()
            If docPackageRelationship IsNot Nothing Then
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _
                  docPackageRelationship.TargetUri)
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)

                ' Load the document XML in the part into an XDocument instance.
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))

                ' Find the styles part. There will only be one.
                Dim styleRelation As PackageRelationship = _
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()
                If styleRelation IsNot Nothing Then
                    Dim styleUri As Uri = _
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)

                    ' Load the style XML in the part into an XDocument instance.
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))
                End If
            End If
        End Using

        ' The following query finds all the paragraphs that have the default style.
        Dim defParas As IEnumerable(Of XElement) = _
            From style In styleDoc.Root.<w:style> _
            Where style.@w:type.Equals("paragraph") And _
                   style.@w:default.Equals("1") _
            Select style
        ' Then find the style of the first.
        Dim defaultStyle As String = defParas.First().@w:styleId

        Console.WriteLine("The default style is: " & defaultStyle)
    End Sub
End Module
```

<span data-ttu-id="1bb05-113">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1bb05-113">This example produces the following output:</span></span>

```output
The default style is: Normal
```

<span data-ttu-id="1bb05-114">W następnym artykule w tym samouczku utworzysz podobne zapytanie, które znajdzie wszystkie akapity w dokumencie i ich style:</span><span class="sxs-lookup"><span data-stu-id="1bb05-114">In the next article in this tutorial you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>

- [<span data-ttu-id="1bb05-115">Pobieranie akapitów i ich stylów</span><span class="sxs-lookup"><span data-stu-id="1bb05-115">Retrieve the paragraphs and their styles</span></span>](retrieve-paragraphs-styles.md)

## <a name="see-also"></a><span data-ttu-id="1bb05-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1bb05-116">See also</span></span>

- [<span data-ttu-id="1bb05-117">Samouczek: manipulowanie zawartością w dokumencie WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="1bb05-117">Tutorial: Manipulate content in a WordprocessingML document</span></span>](xml-shape-wordprocessingml-documents.md)
