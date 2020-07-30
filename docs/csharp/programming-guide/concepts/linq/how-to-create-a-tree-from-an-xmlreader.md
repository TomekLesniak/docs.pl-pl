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
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a><span data-ttu-id="31749-104">Jak utworzyć drzewo na podstawie elementu XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="31749-104">How to create a tree from an XmlReader (C#)</span></span>
<span data-ttu-id="31749-105">W tym temacie pokazano, jak utworzyć drzewo XML bezpośrednio z programu <xref:System.Xml.XmlReader> .</span><span class="sxs-lookup"><span data-stu-id="31749-105">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="31749-106">Aby utworzyć obiekt <xref:System.Xml.Linq.XElement> z poziomu <xref:System.Xml.XmlReader> , należy umieścić <xref:System.Xml.XmlReader> w węźle elementu.</span><span class="sxs-lookup"><span data-stu-id="31749-106">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="31749-107"><xref:System.Xml.XmlReader>Program pominie Komentarze i instrukcje przetwarzania, ale jeśli <xref:System.Xml.XmlReader> jest umieszczony w węźle tekstowym, zostanie wygenerowany błąd.</span><span class="sxs-lookup"><span data-stu-id="31749-107">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="31749-108">Aby uniknąć takich błędów, należy zawsze umieścić <xref:System.Xml.XmlReader> element na elemencie przed utworzeniem drzewa XML z <xref:System.Xml.XmlReader> .</span><span class="sxs-lookup"><span data-stu-id="31749-108">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31749-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="31749-109">Example</span></span>  
 <span data-ttu-id="31749-110">Ten przykład używa następującego dokumentu XML: [przykładowy plik XML: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="31749-110">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="31749-111">Poniższy kod tworzy `T:System.Xml.XmlReader` obiekt, a następnie odczytuje węzły do momentu znalezienia węzła pierwszego elementu.</span><span class="sxs-lookup"><span data-stu-id="31749-111">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="31749-112">Następnie ładuje <xref:System.Xml.Linq.XElement> obiekt.</span><span class="sxs-lookup"><span data-stu-id="31749-112">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="31749-113">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="31749-113">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="31749-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="31749-114">See also</span></span>

- [<span data-ttu-id="31749-115">Analizowanie pliku XML (C#)</span><span class="sxs-lookup"><span data-stu-id="31749-115">Parsing XML (C#)</span></span>](how-to-parse-a-string.md)
