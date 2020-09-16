---
title: Przetwarzanie danych XML w pamięci
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
ms.openlocfilehash: 0f64b53588e08520d38c05ec6060f9aef58bd7d6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556489"
---
# <a name="processing-xml-data-in-memory"></a>Przetwarzanie danych XML w pamięci
Microsoft .NET Framework zawiera trzy modele do przetwarzania danych XML: <xref:System.Xml.XmlDocument> Klasa, <xref:System.Xml.XPath.XPathDocument> klasa i [LINQ to XML (C#)](../../linq/linq-xml-overview.md) i [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md).  
  
 <xref:System.Xml.XmlDocument>Klasa implementuje podstawowe elementy poziomu modelu DOM (Document Object Model) 1 i podstawowe zalecenia poziomu 2 modelu DOM. DOM jest reprezentacją drzewa w pamięci (pamięć podręczna) dokumentu XML. Za pomocą <xref:System.Xml.XmlDocument> i pokrewnych klas można tworzyć dokumenty XML, ładować i uzyskiwać dostęp do danych, modyfikować dane i zapisywać zmiany.  
  
 <xref:System.Xml.XPath.XPathDocument>Klasa jest magazynem danych tylko do odczytu, który jest oparty na modelu danych XPath. <xref:System.Xml.XPath.XPathNavigator>Klasa oferuje kilka opcji edycji i możliwości nawigacji przy użyciu modelu kursorów na dokumentach XML zawartych w klasie tylko do odczytu <xref:System.Xml.XPath.XPathDocument> , a także <xref:System.Xml.XmlDocument> klasy.  
  
 [LINQ to XML](../../linq/linq-xml-overview.md) jest modelem wprowadzonym w .NET Framework wersji 3,5 na potrzeby przetwarzania danych XML. Jest to model znajdujący się w pamięci, który korzysta z [zapytań zintegrowanych z językiem (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md). LINQ rozszerza składnię języka C# i Visual Basic, aby zapewnić nowe możliwości zapytań.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Przetwarzanie danych XML przy użyciu modelu DOM](process-xml-data-using-the-dom-model.md)  
 W tym artykule omówiono użycie <xref:System.Xml.XmlDocument> i powiązane z nim klasy do przetwarzania danych XML.  
  
 [Przetwarzanie danych XML przy użyciu modelu danych XPath](process-xml-data-using-the-xpath-data-model.md)  
 W tym artykule omówiono korzystanie z <xref:System.Xml.XPath.XPathDocument> <xref:System.Xml.XmlDocument> klas, i <xref:System.Xml.XPath.XPathNavigator> do przetwarzania danych XML.  
  
 [Przetwarzanie danych XML przy użyciu modelu LINQ to XML](process-xml-data-using-linq-to-xml.md)  
 Zawiera krótkie omówienie LINQ to XML i zawiera linki do dokumentacji LINQ to XMLowej.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Dokumenty i dane XML](index.md)
