---
title: Dane wejściowe obiektu XPathDocument klasy XslTransform
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
ms.openlocfilehash: 29bb345c2654baec8fbd2adce3788a4b4f2d582d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720870"
---
# <a name="xpathdocument-input-to-xsltransform"></a><span data-ttu-id="602ba-102">Dane wejściowe obiektu XPathDocument klasy XslTransform</span><span class="sxs-lookup"><span data-stu-id="602ba-102">XPathDocument Input to XslTransform</span></span>

<span data-ttu-id="602ba-103"><xref:System.Xml.XPath.XPathDocument>Jest pamięcią podręczną tylko do odczytu, na potrzeby przetwarzania dokumentów przy użyciu programu <xref:System.Xml.Xsl.XslTransform> .</span><span class="sxs-lookup"><span data-stu-id="602ba-103">The <xref:System.Xml.XPath.XPathDocument> is a read-only cache, for processing documents with <xref:System.Xml.Xsl.XslTransform>.</span></span> <span data-ttu-id="602ba-104">Jest on strukturalnie podobny do Document Object Model XML (DOM), ale jest wysoce zoptymalizowany pod kątem przetwarzania Extensible Stylesheet Language for Transformations (XSLT) i modelu danych XML Path Language (XPath) przy użyciu funkcji optymalizacji XPath w <xref:System.Xml.XPath.XPathNavigator> .</span><span class="sxs-lookup"><span data-stu-id="602ba-104">It is structurally similar to the XML Document Object Model (DOM), but it is highly optimized for Extensible Stylesheet Language for Transformations (XSLT) processing and the XML Path Language (XPath) data model using the XPath optimization functions on the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="602ba-105"><xref:System.Xml.Xsl.XslTransform>Klasa jest przestarzała w .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="602ba-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="602ba-106">Można wykonać przekształcenia Extensible Stylesheet Language for Transformations (XSLT) przy użyciu <xref:System.Xml.Xsl.XslCompiledTransform> klasy.</span><span class="sxs-lookup"><span data-stu-id="602ba-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="602ba-107">Aby uzyskać więcej informacji, zobacz [Używanie klasy XslCompiledTransform](using-the-xslcompiledtransform-class.md) i [Migrowanie z klasy XslTransform](migrating-from-the-xsltransform-class.md) .</span><span class="sxs-lookup"><span data-stu-id="602ba-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="602ba-108">Poniższy przykład kodu tworzy <xref:System.Xml.XPath.XPathDocument> jako dane wejściowe do przekształcenia.</span><span class="sxs-lookup"><span data-stu-id="602ba-108">The following code sample creates an <xref:System.Xml.XPath.XPathDocument> as input to a transform.</span></span>  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a><span data-ttu-id="602ba-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="602ba-109">See also</span></span>

- [<span data-ttu-id="602ba-110">Implementowanie procesora XSLT przy użyciu klasy XslTransform</span><span class="sxs-lookup"><span data-stu-id="602ba-110">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
