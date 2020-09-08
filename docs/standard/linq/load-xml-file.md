---
title: Jak załadować XML z pliku LINQ to XML
description: Do załadowania dokumentu XML z pliku można użyć metody XElement. Load w języku C# i Visual Basic.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 3ed38487-8028-4209-9872-c8dce0ed4dfe
ms.openlocfilehash: 7ac77205eb1f7637982e8f40d31df0a422ecba22
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553299"
---
# <a name="how-to-load-xml-from-a-file-linq-to-xml"></a><span data-ttu-id="84288-103">Jak załadować plik XML z pliku (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="84288-103">How to load XML from a file (LINQ to XML)</span></span>

<span data-ttu-id="84288-104">W tym artykule przedstawiono sposób ładowania XML z pliku w języku C# i Visual Basic przy użyciu <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="84288-104">This article shows how to load XML from a file in C# and Visual Basic using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>

## <a name="example-load-xml-document-from-a-file"></a><span data-ttu-id="84288-105">Przykład: Załaduj dokument XML z pliku</span><span class="sxs-lookup"><span data-stu-id="84288-105">Example: Load XML document from a file</span></span>

<span data-ttu-id="84288-106">Poniższy przykład pokazuje, jak załadować dokument XML z pliku, podając <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> Identyfikator URI, który odwołuje się do pliku.</span><span class="sxs-lookup"><span data-stu-id="84288-106">The following example shows how to load an XML document from a file by providing <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> with the URI that references the file.</span></span> <span data-ttu-id="84288-107">Przykład ładuje books.xml i wyprowadza drzewo XML do konsoli.</span><span class="sxs-lookup"><span data-stu-id="84288-107">The example loads books.xml and outputs the XML tree to the console.</span></span>

<span data-ttu-id="84288-108">Zawartość books.xml są pokazane w [przykładowym pliku XML: Books](sample-xml-file-books.md).</span><span class="sxs-lookup"><span data-stu-id="84288-108">The contents of books.xml are shown in [Sample XML file: Books](sample-xml-file-books.md).</span></span>

```csharp
XElement booksFromFile = XElement.Load(@"books.xml");
Console.WriteLine(booksFromFile);
```

```vb
Dim booksFromFile As XElement = XElement.Load("books.xml")
Console.WriteLine(booksFromFile)
```

<span data-ttu-id="84288-109">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="84288-109">This example produces the following output:</span></span>

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
