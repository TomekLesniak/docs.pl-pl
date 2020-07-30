---
title: Kształt dokumentów WordprocessingML (C#)
description: Dowiedz się więcej na temat formatu dokumentu WordprocessingML. Kilka przykładów języka C# używa dokumentu WordprocessingML.
ms.date: 07/20/2015
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
ms.openlocfilehash: 4a7716d775a634c5ad3719714be68fce67d5cbfe
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302350"
---
# <a name="shape-of-wordprocessingml-documents-c"></a><span data-ttu-id="a5fe9-104">Kształt dokumentów WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="a5fe9-104">Shape of WordprocessingML Documents (C#)</span></span>
<span data-ttu-id="a5fe9-105">Ten temat zawiera wprowadzenie do kształtu XML dokumentu WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-105">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="a5fe9-106">Formaty Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="a5fe9-106">Microsoft Office Formats</span></span>  
 <span data-ttu-id="a5fe9-107">Format pliku natywnego dla systemu 2007 Microsoft Office to Office Open XML (często nazywanego Open XML).</span><span class="sxs-lookup"><span data-stu-id="a5fe9-107">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="a5fe9-108">Open XML jest formatem opartym na formacie XML, który Standard ECMA i jest obecnie przechodzący przez proces standardów ISO-IEC.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-108">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="a5fe9-109">Język znaczników dla plików edytora tekstu w formacie Open XML ma nazwę WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-109">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="a5fe9-110">Ten samouczek używa plików źródłowych WordprocessingML jako danych wejściowych dla przykładów.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-110">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="a5fe9-111">Jeśli używasz Microsoft Office 2003, możesz zapisać dokumenty w formacie Office Open XML, jeśli zainstalowano pakiet zgodności Microsoft Office dla formatów plików programów Word, Excel i PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-111">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="a5fe9-112">Kształt dokumentów WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="a5fe9-112">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="a5fe9-113">Pierwszą rzeczą, którą należy zrozumieć, jest kształt dokumentów WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-113">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="a5fe9-114">Dokument WordprocessingML zawiera element Body (o nazwie `w:body` ) zawierający akapity dokumentu.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-114">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="a5fe9-115">Każdy akapit zawiera jeden lub więcej uruchomień tekstu (o nazwie `w:r` ).</span><span class="sxs-lookup"><span data-stu-id="a5fe9-115">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="a5fe9-116">Każdy przebieg tekstowy zawiera jedną lub więcej fragmentów tekstu (o nazwie `w:t` ).</span><span class="sxs-lookup"><span data-stu-id="a5fe9-116">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="a5fe9-117">Oto bardzo prosty dokument WordprocessingML:</span><span class="sxs-lookup"><span data-stu-id="a5fe9-117">The following is a very simple WordprocessingML document:</span></span>  
  
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
  
 <span data-ttu-id="a5fe9-118">Ten dokument zawiera dwa akapity.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-118">This document contains two paragraphs.</span></span> <span data-ttu-id="a5fe9-119">Oba te elementy zawierają pojedynczy przebieg tekstowy, a każdy z nich jest pojedynczym fragmentem tekstu.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-119">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="a5fe9-120">Najprostszym sposobem wyświetlenia zawartości dokumentu WordprocessingML w formularzu XML jest utworzenie go przy użyciu programu Microsoft Word, zapisanie go, a następnie uruchomienie następującego programu, który drukuje plik XML do konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-120">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="a5fe9-121">Ten przykład używa klas znalezionych w zestawie 'Windowsbase.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-121">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="a5fe9-122">Używa typów w <xref:System.IO.Packaging?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="a5fe9-122">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
## <a name="external-resources"></a><span data-ttu-id="a5fe9-123">Zasoby zewnętrzne</span><span class="sxs-lookup"><span data-stu-id="a5fe9-123">External resources</span></span>

- [<span data-ttu-id="a5fe9-124">Wprowadzenie do pakietu Office (2007) otwartych formatów plików XML</span><span class="sxs-lookup"><span data-stu-id="a5fe9-124">Introducing the Office (2007) Open XML File Formats</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205%28v=office.12%29)
- [<span data-ttu-id="a5fe9-125">Przegląd WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="a5fe9-125">Overview of WordprocessingML</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812%28v=office.11%29)
- [<span data-ttu-id="a5fe9-126">Anatomia pliku WordProcessingML</span><span class="sxs-lookup"><span data-stu-id="a5fe9-126">Anatomy of a WordProcessingML File</span></span>](http://officeopenxml.com/anatomyofOOXML.php)
- [<span data-ttu-id="a5fe9-127">Wprowadzenie do WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="a5fe9-127">Introduction to WordprocessingML</span></span>](https://ericwhite.com/blog/introduction-to-wordprocessingml-series/)

## <a name="see-also"></a><span data-ttu-id="a5fe9-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a5fe9-128">See also</span></span>

- [<span data-ttu-id="a5fe9-129">Samouczek: manipulowanie zawartością w dokumencie WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="a5fe9-129">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
