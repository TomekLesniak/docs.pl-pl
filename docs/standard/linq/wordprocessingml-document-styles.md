---
title: WordprocessingML dokument z stylami — LINQ to XML
description: Dowiedz się więcej o dokumentach WordprocessingML, których akapity są sformatowane przy użyciu stylów.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 40e35de6-ac93-4bba-88ab-a018cbe93873
ms.openlocfilehash: 7864ce5163d9dfb316c8288850210becdf55dc2d
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553235"
---
# <a name="wordprocessingml-document-with-styles-linq-to-xml"></a><span data-ttu-id="69a46-103">WordprocessingML dokument z stylami (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="69a46-103">WordprocessingML document with styles (LINQ to XML)</span></span>

<span data-ttu-id="69a46-104">W tym artykule przedstawiono dokument WordprocessingML, który jest bardziej skomplikowany niż ten w [kształcie XML w dokumentach WordprocessingML](xml-shape-wordprocessingml-documents.md); w odniesieniu do programu prezentowane są dokumenty, których akapity są sformatowane przy użyciu stylów.</span><span class="sxs-lookup"><span data-stu-id="69a46-104">This article presents a WordprocessingML document that is more complicated than the one in [The XML shape of WordprocessingML documents](xml-shape-wordprocessingml-documents.md); specifically, it presents a document whose paragraphs are formatted with styles.</span></span>

<span data-ttu-id="69a46-105">Aby poznać style, warto wiedzieć coś o strukturze dokumentu.</span><span class="sxs-lookup"><span data-stu-id="69a46-105">To understand styles, it's helpful to know something about document structure.</span></span> <span data-ttu-id="69a46-106">Dokument WordprocessingML jest przechowywany w *pakiecie* , który składa się z *części*.</span><span class="sxs-lookup"><span data-stu-id="69a46-106">A WordprocessingML document is stored in a *package* that comprises *parts*.</span></span> <span data-ttu-id="69a46-107">Termin *pakiet* odpowiada archiwum zip, a *część* terminu odpowiada plikowi przechowywanemu w pliku zip.</span><span class="sxs-lookup"><span data-stu-id="69a46-107">Specifically, the term *package* corresponds to a ZIP archive and the term *part* corresponds to a file stored within the ZIP.</span></span> <span data-ttu-id="69a46-108">Jeśli dokument zawiera akapity sformatowane za pomocą stylów, będzie to część dokumentu zawierająca akapity, do których zastosowano style, oraz część stylu, która definiuje style, do których odwołuje się część dokumentu.</span><span class="sxs-lookup"><span data-stu-id="69a46-108">If a document contains paragraphs that are formatted with styles, there will be a document part that contains paragraphs that have styles applied to them, and a style part that defines the styles referenced in the document part.</span></span>

<span data-ttu-id="69a46-109">Najprostszym sposobem na wyświetlenie kodu XML, który stanowi dokument pakietu Office Open XML, jest uruchomienie przykładu [, w którym są wyprowadzane części dokumentu Office Open XML](example-outputs-office-open-xml-document-parts.md).</span><span class="sxs-lookup"><span data-stu-id="69a46-109">The easiest way to see the XML that makes up an Office Open XML document is to run the example in [Example that outputs Office Open XML document parts](example-outputs-office-open-xml-document-parts.md).</span></span>

<span data-ttu-id="69a46-110">Podczas uzyskiwania dostępu do pakietu należy to zrobić poprzez relacje między częściami, a nie za pomocą dowolnej ścieżki.</span><span class="sxs-lookup"><span data-stu-id="69a46-110">When you access a package, you should do so through the relationships among parts, not through an arbitrary path.</span></span> <span data-ttu-id="69a46-111">Ten problem jest poza zakresem bieżącego samouczka, ale przykładowe programy w tym i innych artykułach samouczka demonstrują właściwe podejście.</span><span class="sxs-lookup"><span data-stu-id="69a46-111">This issue is beyond the scope of the current tutorial, but the example programs in this and other tutorial articles demonstrate the correct approach.</span></span>

## <a name="example-a-document-that-uses-styles"></a><span data-ttu-id="69a46-112">Przykład: dokument, który używa stylów</span><span class="sxs-lookup"><span data-stu-id="69a46-112">Example: A document that uses styles</span></span>

<span data-ttu-id="69a46-113">Następujący dokument zawiera akapity sformatowane za pomocą stylów.</span><span class="sxs-lookup"><span data-stu-id="69a46-113">The following document has paragraphs that are formatted with styles.</span></span> <span data-ttu-id="69a46-114">Pierwszy akapit ma styl `Heading1` i inne akapity mają `Code` styl lub styl domyślny.</span><span class="sxs-lookup"><span data-stu-id="69a46-114">The first paragraph has the style `Heading1` and other paragraphs have the `Code` style or the default style.</span></span> <span data-ttu-id="69a46-115">W przypadku akapitów z stylami innymi niż domyślne elementy akapitu mają element podrzędny o nazwie `w:pPr` , który z kolei ma element podrzędny `w:pStyle` .</span><span class="sxs-lookup"><span data-stu-id="69a46-115">For paragraphs with non-default styles the paragraph elements have a child element named `w:pPr`, which in turn has a child element `w:pStyle`.</span></span> <span data-ttu-id="69a46-116">Ten element ma atrybut, `w:val` który zawiera nazwę stylu.</span><span class="sxs-lookup"><span data-stu-id="69a46-116">That element has an attribute, `w:val`, which contains the style name.</span></span> <span data-ttu-id="69a46-117">Dla akapitów z stylem domyślnym element Paragraph nie ma `w:p.Pr` elementu podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="69a46-117">For paragraphs with the default style, the paragraph element doesn't have a `w:p.Pr` child element.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
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
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">
      <w:pPr>
        <w:pStyle w:val="Heading1" />
      </w:pPr>
      <w:r>
        <w:t>Parsing WordprocessingML with LINQ to XML</w:t>
      </w:r>
    </w:p>
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0">
      <w:r>
        <w:t>The following example prints to the console.</w:t>
      </w:r>
    </w:p>
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">
      <w:pPr>
        <w:pStyle w:val="Code" />
      </w:pPr>
      <w:r>
        <w:t>using System;</w:t>
      </w:r>
    </w:p>
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">
      <w:pPr>
        <w:pStyle w:val="Code" />
      </w:pPr>
    </w:p>
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">
      <w:pPr>
        <w:pStyle w:val="Code" />
      </w:pPr>
      <w:r w:rsidRPr="00876F34">
        <w:t>class Program {</w:t>
      </w:r>
    </w:p>
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">
      <w:pPr>
        <w:pStyle w:val="Code" />
      </w:pPr>
      <w:r w:rsidRPr="00876F34">
        <w:t xml:space="preserve">    public static void </w:t>
      </w:r>
      <w:smartTag w:uri="urn:schemas-microsoft-com:office:smarttags" w:element="place">
        <w:r w:rsidRPr="00876F34">
          <w:t>Main</w:t>
        </w:r>
      </w:smartTag>
      <w:r w:rsidRPr="00876F34">
        <w:t>(string[] args) {</w:t>
      </w:r>
    </w:p>
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">
      <w:pPr>
        <w:pStyle w:val="Code" />
      </w:pPr>
      <w:r w:rsidRPr="00876F34">
        <w:t xml:space="preserve">        Console.WriteLine("Hello World");</w:t>
      </w:r>
    </w:p>
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">
      <w:pPr>
        <w:pStyle w:val="Code" />
      </w:pPr>
      <w:r w:rsidRPr="00876F34">
        <w:t xml:space="preserve">    }</w:t>
      </w:r>
    </w:p>
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">
      <w:pPr>
        <w:pStyle w:val="Code" />
      </w:pPr>
      <w:r w:rsidRPr="00876F34">
        <w:t>}</w:t>
      </w:r>
    </w:p>
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0">
      <w:r>
        <w:t>This example produces the following output:</w:t>
      </w:r>
    </w:p>
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">
      <w:pPr>
        <w:pStyle w:val="Code" />
      </w:pPr>
      <w:r>
        <w:t>Hello World</w:t>
      </w:r>
    </w:p>
    <w:sectPr w:rsidR="00A75AE0" w:rsidSect="00A75AE0">
      <w:pgSz w:w="12240" w:h="15840" />
      <w:pgMar w:top="1440" w:right="1800" w:bottom="1440" w:left="1800" w:header="720" w:footer="720" w:gutter="0" />
      <w:cols w:space="720" />
      <w:docGrid w:linePitch="360" />
    </w:sectPr>
  </w:body>
</w:document>
```
