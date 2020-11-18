---
title: Dane wyjściowe klasy XslTransform
ms.date: 03/30/2017
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
ms.openlocfilehash: 765f6f9a91cc44a55ab0d66ed71f19f60ef81a56
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830067"
---
# <a name="outputs-from-an-xsltransform"></a>Dane wyjściowe klasy XslTransform
Ponieważ arkusze stylów mogą określić format danych wyjściowych przy użyciu `<xsl:output>` instrukcji z `method` atrybutem, w poniższej tabeli opisano, w jaki sposób format danych wyjściowych jest <xref:System.Xml.Xsl.XslTransform.Transform%2A> używany do pisania danych wyjściowych, a format danych wyjściowych jest zadeklarowany jako <xref:System.IO.Stream> lub <xref:System.IO.TextWriter> .  
  
> [!NOTE]
> <xref:System.Xml.Xsl.XslTransform>Klasa jest przestarzała w .NET Framework 2,0. Można wykonać przekształcenia Extensible Stylesheet Language for Transformations (XSLT) przy użyciu <xref:System.Xml.Xsl.XslCompiledTransform> klasy. Aby uzyskać więcej informacji, zobacz [Używanie klasy XslCompiledTransform](using-the-xslcompiledtransform-class.md) i [Migrowanie z klasy XslTransform](migrating-from-the-xsltransform-class.md) .  
  
 Ponieważ arkusze stylów mogą określić format danych wyjściowych przy użyciu `<xsl:output>` instrukcji z `method` atrybutem, w poniższej tabeli opisano, w jaki sposób format danych wyjściowych jest <xref:System.Xml.Xsl.XslTransform.Transform%2A> używany do pisania danych wyjściowych, a format danych wyjściowych jest zadeklarowany jako <xref:System.IO.Stream> lub <xref:System.IO.TextWriter> . W poniższej tabeli opisano, co się dzieje, gdy typ danych wyjściowych jest zadeklarowany przez <xref:System.Xml.Xsl.XslTransform.Transform%2A> metodę w połączeniu z użyciem `<xsl:output>` instrukcji:  
  
|Atrybut \<xsl:output method = >|Format wyniku|  
|-----------------------------------------|-------------------|  
|Metoda = "XML"|XML|  
|Metoda = "HTML"|HTML|  
|Metoda = "text"|Tekst|  
  
> [!NOTE]
> Uwaga: `<xsl:output>` instrukcja jest ignorowana, jeśli dane wyjściowe <xref:System.Xml.Xsl.XslTransform.Transform%2A> metody są <xref:System.Xml.XmlReader> lub <xref:System.Xml.XmlWriter> .  
  
 Następujące atrybuty są obsługiwane, gdy <xref:System.Xml.Xsl.XslTransform.Transform%2A> wynikiem metody jest <xref:System.IO.Stream> lub <xref:System.IO.TextWriter> :  
  
- Kody  
  
- Pomiń deklarację XML  
  
- niezależne  
  
- DOCTYPE — publiczny  
  
- DOCTYPE — system  
  
- CDATA-elementy sekcji  
  
- wyświetlane  
  
    > [!NOTE]
    > \*Atrybut Encoding jest ignorowany, gdy <xref:System.Xml.Xsl.XslTransform.Transform%2A> Metoda wysyła dane wyjściowe do <xref:System.IO.TextWriter> . Właściwość Encoding w <xref:System.IO.TextWriter> jest używana w zamian.
  
 Następujący atrybut jest ignorowany, gdy <xref:System.Xml.Xsl.XslTransform.Transform%2A> wyjście metody jest <xref:System.IO.Stream> :  
  
- Wersja: wersja jest zawsze 1,0  
  
- Typ nośnika: typ nośnika  
  
## <a name="escaping-special-characters"></a>Znaki specjalne ucieczki  
 `<xsl:text disable-output-escaping>`Tag służy do wskazywania, czy znaki specjalne muszą być wyprowadzane do formularza XML (na przykład przy użyciu `<&lt>` zamiast `"<"` symbolu) lub pozostawione w stanie obecne. `disable-output-escaping`Atrybut jest ignorowany podczas przekształcania do <xref:System.Xml.XmlReader> <xref:System.Xml.XmlWriter> obiektu lub i nie ma wpływu na znaki specjalne.  
  
## <a name="see-also"></a>Zobacz także

- [Implementowanie procesora XSLT przy użyciu klasy XslTransform](xsltransform-class-implements-the-xslt-processor.md)
