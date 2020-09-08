---
title: Kształt XML WordprocessingML Documents-LINQ to XML
description: Dowiedz się więcej o kształcie XML dokumentu WordprocessingML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
ms.openlocfilehash: 0c6ed589556eb35a5741739c1f87e1e175476c89
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553211"
---
# <a name="the-xml-shape-of-wordprocessingml-documents-linq-to-xml"></a>Kształt XML dokumentów WordprocessingML (LINQ to XML)

W tym artykule wprowadzono kształt XML dokumentu WordprocessingML.

## <a name="microsoft-office-formats"></a>Formaty Microsoft Office

Format pliku natywnego dla systemu 2007 Microsoft Office to Office Open XML (często nazywanego Open XML). Open XML jest formatem opartym na formacie XML, który jest standardem ECMA i obecnie przechodzi przez proces standardów ISO-IEC. Język znaczników dla plików edytora tekstu w formacie Open XML ma nazwę WordprocessingML. Ten samouczek używa plików źródłowych WordprocessingML jako danych wejściowych dla przykładów.

Jeśli używasz Microsoft Office 2003, możesz zapisać dokumenty w formacie Open XML pakietu Office, jeśli zainstalowano pakiet zgodności Microsoft Office dla formatów plików programów Word, Excel i PowerPoint 2007.

## <a name="the-shape-of-wordprocessingml-documents"></a>Kształt dokumentów WordprocessingML

Pierwszą rzeczą, którą należy zrozumieć, jest kształt XML dokumentów WordprocessingML. Dokument WordprocessingML zawiera element Body (o nazwie `w:body` ) zawierający akapity dokumentu. Każdy akapit zawiera jeden lub więcej uruchomień tekstu (o nazwie `w:r` ). Każdy przebieg tekstowy zawiera jedną lub więcej fragmentów tekstu (o nazwie `w:t` ).

Oto bardzo prosty dokument WordprocessingML:

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<w:document
xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"
xmlns:o="urn:schemas-microsoft-com:office:office"
xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"
xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"
xmlns:v="urn:schemas-microsoft-com:vml"
xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"
xmlns:w10="urn:schemas-microsoft-com:office:word"
xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"
xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">
  <w:body>
    <w:p w:rsidR="00E22EB6"
         w:rsidRDefault="00E22EB6">
      <w:r>
        <w:t>This is a paragraph.</w:t>
      </w:r>
    </w:p>
    <w:p w:rsidR="00E22EB6"
         w:rsidRDefault="00E22EB6">
      <w:r>
        <w:t>This is another paragraph.</w:t>
      </w:r>
    </w:p>
  </w:body>
</w:document>
```

Ten dokument zawiera dwa akapity. Oba te elementy zawierają pojedynczy przebieg tekstowy, a każdy z nich jest pojedynczym fragmentem tekstu.

Najprostszym sposobem wyświetlenia zawartości dokumentu WordprocessingML w formularzu XML jest utworzenie go przy użyciu programu Microsoft Word, zapisanie go, a następnie uruchomienie następującego programu, który drukuje plik XML do konsoli programu.

Ten przykład używa klas znalezionych w zestawie 'Windowsbase. Używa typów w <xref:System.IO.Packaging?displayProperty=nameWithType> przestrzeni nazw.

```csharp
const string documentRelationshipType =
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";
const string wordmlNamespace =
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";
XNamespace w = wordmlNamespace;

using (Package wdPackage = Package.Open("SampleDoc.docx", FileMode.Open, FileAccess.Read))
{
    PackageRelationship relationship =
        wdPackage
        .GetRelationshipsByType(documentRelationshipType)
        .FirstOrDefault();
    if (relationship != null)
    {
        Uri documentUri =
            PackUriHelper.ResolvePartUri(
                new Uri("/", UriKind.Relative),
                relationship.TargetUri);
        PackagePart documentPart = wdPackage.GetPart(documentUri);

        //  Get the officeDocument part from the package.
        //  Load the XML in the part into an XDocument instance.
        XDocument xdoc =
            XDocument.Load(XmlReader.Create(documentPart.GetStream()));
        Console.WriteLine(xdoc.Root);
    }
}
```

```vb
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">

Module Module1
    Sub Main()
        Dim documentRelationshipType = _
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"

        Using wdPackage As Package = _
          Package.Open("SampleDoc.docx", _
                       FileMode.Open, FileAccess.Read)
            Dim docPackageRelationship As PackageRelationship = wdPackage _
                .GetRelationshipsByType(documentRelationshipType).FirstOrDefault()
            If (docPackageRelationship IsNot Nothing) Then
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri( _
                            New Uri("/", UriKind.Relative), _
                            docPackageRelationship.TargetUri)
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)

                ' Get the officeDocument part from the package.
                ' Load the XML in the part into an XDocument instance.
                Dim xDoc As XDocument = _
                    XDocument.Load(XmlReader.Create(documentPart.GetStream()))
                Console.WriteLine(xDoc.Root)
            End If
        End Using
    End Sub
End Module
```

## <a name="see-also"></a>Zobacz też

- [Wprowadzenie do pakietu Office (2007) otwartych formatów plików XML](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205(v=office.12))
- [Przegląd WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812(v=office.11))
- [Anatomia pliku WordProcessingML](http://officeopenxml.com/anatomyofOOXML.php)
- [Wprowadzenie do WordprocessingML](https://ericwhite.com/blog/introduction-to-wordprocessingml-series/)
