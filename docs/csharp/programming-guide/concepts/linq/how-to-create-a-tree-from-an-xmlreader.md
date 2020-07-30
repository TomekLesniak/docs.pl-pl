---
title: Jak utworzyć drzewo na podstawie elementu XmlReader (C#)
description: Dowiedz się, jak utworzyć drzewo XML bezpośrednio z elementu XmlReader. Zobacz przykład pokazujący, jak utworzyć obiekt czytnika T:System.Xml.Xml.
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: 3801177e664d142652d38748d44eaf3f274239dd
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302662"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a>Jak utworzyć drzewo na podstawie elementu XmlReader (C#)
W tym temacie pokazano, jak utworzyć drzewo XML bezpośrednio z programu <xref:System.Xml.XmlReader> . Aby utworzyć obiekt <xref:System.Xml.Linq.XElement> z poziomu <xref:System.Xml.XmlReader> , należy umieścić <xref:System.Xml.XmlReader> w węźle elementu. <xref:System.Xml.XmlReader>Program pominie Komentarze i instrukcje przetwarzania, ale jeśli <xref:System.Xml.XmlReader> jest umieszczony w węźle tekstowym, zostanie wygenerowany błąd. Aby uniknąć takich błędów, należy zawsze umieścić <xref:System.Xml.XmlReader> element na elemencie przed utworzeniem drzewa XML z <xref:System.Xml.XmlReader> .  
  
## <a name="example"></a>Przykład  
 Ten przykład używa następującego dokumentu XML: [przykładowy plik XML: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).  
  
 Poniższy kod tworzy `T:System.Xml.XmlReader` obiekt, a następnie odczytuje węzły do momentu znalezienia węzła pierwszego elementu. Następnie ładuje <xref:System.Xml.Linq.XElement> obiekt.  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```xml  
<Catalog>  
   <Book id="bk101">  
      <Author>Garghentini, Davide</Author>  
      <Title>XML Developer's Guide</Title>  
      <Genre>Computer</Genre>  
      <Price>44.95</Price>  
      <PublishDate>2000-10-01</PublishDate>  
      <Description>An in-depth look at creating applications
      with XML.</Description>  
   </Book>  
   <Book id="bk102">  
      <Author>Garcia, Debra</Author>  
      <Title>Midnight Rain</Title>  
      <Genre>Fantasy</Genre>  
      <Price>5.95</Price>  
      <PublishDate>2000-12-16</PublishDate>  
      <Description>A former architect battles corporate zombies,
      an evil sorceress, and her own childhood to become queen
      of the world.</Description>  
   </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a>Zobacz też

- [Analizowanie pliku XML (C#)](how-to-parse-a-string.md)
