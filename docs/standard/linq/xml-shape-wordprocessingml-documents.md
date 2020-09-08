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
# <a name="the-xml-shape-of-wordprocessingml-documents-linq-to-xml"></a><span data-ttu-id="696c6-103">Kształt XML dokumentów WordprocessingML (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="696c6-103">The XML shape of WordprocessingML documents (LINQ to XML)</span></span>

<span data-ttu-id="696c6-104">W tym artykule wprowadzono kształt XML dokumentu WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="696c6-104">This article introduces the XML shape of a WordprocessingML document.</span></span>

## <a name="microsoft-office-formats"></a><span data-ttu-id="696c6-105">Formaty Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="696c6-105">Microsoft Office formats</span></span>

<span data-ttu-id="696c6-106">Format pliku natywnego dla systemu 2007 Microsoft Office to Office Open XML (często nazywanego Open XML).</span><span class="sxs-lookup"><span data-stu-id="696c6-106">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="696c6-107">Open XML jest formatem opartym na formacie XML, który jest standardem ECMA i obecnie przechodzi przez proces standardów ISO-IEC.</span><span class="sxs-lookup"><span data-stu-id="696c6-107">Open XML is an XML-based format that's an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="696c6-108">Język znaczników dla plików edytora tekstu w formacie Open XML ma nazwę WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="696c6-108">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="696c6-109">Ten samouczek używa plików źródłowych WordprocessingML jako danych wejściowych dla przykładów.</span><span class="sxs-lookup"><span data-stu-id="696c6-109">This tutorial uses WordprocessingML source files as input for the examples.</span></span>

<span data-ttu-id="696c6-110">Jeśli używasz Microsoft Office 2003, możesz zapisać dokumenty w formacie Open XML pakietu Office, jeśli zainstalowano pakiet zgodności Microsoft Office dla formatów plików programów Word, Excel i PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="696c6-110">If you're using Microsoft Office 2003, you can save documents in the Office Open XML format if you've installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>

## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="696c6-111">Kształt dokumentów WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="696c6-111">The shape of WordprocessingML documents</span></span>

<span data-ttu-id="696c6-112">Pierwszą rzeczą, którą należy zrozumieć, jest kształt XML dokumentów WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="696c6-112">The first thing to understand is the XML shape of WordprocessingML documents.</span></span> <span data-ttu-id="696c6-113">Dokument WordprocessingML zawiera element Body (o nazwie `w:body` ) zawierający akapity dokumentu.</span><span class="sxs-lookup"><span data-stu-id="696c6-113">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="696c6-114">Każdy akapit zawiera jeden lub więcej uruchomień tekstu (o nazwie `w:r` ).</span><span class="sxs-lookup"><span data-stu-id="696c6-114">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="696c6-115">Każdy przebieg tekstowy zawiera jedną lub więcej fragmentów tekstu (o nazwie `w:t` ).</span><span class="sxs-lookup"><span data-stu-id="696c6-115">Each text run contains one or more text pieces (named `w:t`).</span></span>

<span data-ttu-id="696c6-116">Oto bardzo prosty dokument WordprocessingML:</span><span class="sxs-lookup"><span data-stu-id="696c6-116">The following is a very simple WordprocessingML document:</span></span>

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

<span data-ttu-id="696c6-117">Ten dokument zawiera dwa akapity.</span><span class="sxs-lookup"><span data-stu-id="696c6-117">This document contains two paragraphs.</span></span> <span data-ttu-id="696c6-118">Oba te elementy zawierają pojedynczy przebieg tekstowy, a każdy z nich jest pojedynczym fragmentem tekstu.</span><span class="sxs-lookup"><span data-stu-id="696c6-118">They both contain a single text run, and each text run contains a single text piece.</span></span>

<span data-ttu-id="696c6-119">Najprostszym sposobem wyświetlenia zawartości dokumentu WordprocessingML w formularzu XML jest utworzenie go przy użyciu programu Microsoft Word, zapisanie go, a następnie uruchomienie następującego programu, który drukuje plik XML do konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="696c6-119">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>

<span data-ttu-id="696c6-120">Ten przykład używa klas znalezionych w zestawie 'Windowsbase.</span><span class="sxs-lookup"><span data-stu-id="696c6-120">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="696c6-121">Używa typów w <xref:System.IO.Packaging?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="696c6-121">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="696c6-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="696c6-122">See also</span></span>

- <span data-ttu-id="696c6-123">[Wprowadzenie do pakietu Office (2007) otwartych formatów plików XML](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205(v=office.12))</span><span class="sxs-lookup"><span data-stu-id="696c6-123">[Introducing the Office (2007) Open XML File Formats](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205(v=office.12))</span></span>
- <span data-ttu-id="696c6-124">[Przegląd WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812(v=office.11))</span><span class="sxs-lookup"><span data-stu-id="696c6-124">[Overview of WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812(v=office.11))</span></span>
- [<span data-ttu-id="696c6-125">Anatomia pliku WordProcessingML</span><span class="sxs-lookup"><span data-stu-id="696c6-125">Anatomy of a WordProcessingML File</span></span>](http://officeopenxml.com/anatomyofOOXML.php)
- [<span data-ttu-id="696c6-126">Wprowadzenie do WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="696c6-126">Introduction to WordprocessingML</span></span>](https://ericwhite.com/blog/introduction-to-wordprocessingml-series/)
