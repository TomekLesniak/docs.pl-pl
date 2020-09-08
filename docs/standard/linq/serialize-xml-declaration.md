---
title: Serializacja przy użyciu deklaracji XML — LINQ to XML
description: Można kontrolować, czy deklaracja XML jest generowana podczas serializacji XML w języku C# lub Visual Basic.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 8d25d199b149ac6aeb2aa37dc248523e79847220
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552957"
---
# <a name="serialize-with-an-xml-declaration-linq-to-xml"></a><span data-ttu-id="36700-103">Serializacja przy użyciu deklaracji XML (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="36700-103">Serialize with an XML declaration (LINQ to XML)</span></span>

<span data-ttu-id="36700-104">W tym artykule opisano sposób kontrolowania, czy deklaracja XML jest generowana podczas serializacji kodu XML w języku C# lub Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="36700-104">This article describes how to control whether an XML declaration is generated when you serialize XML in C# or Visual Basic.</span></span>

<span data-ttu-id="36700-105">Serializacja do metody lub metody, <xref:System.IO.File> <xref:System.IO.TextWriter> <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> lub <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> Metoda generuje deklarację XML.</span><span class="sxs-lookup"><span data-stu-id="36700-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="36700-106">Podczas serializacji do <xref:System.Xml.XmlWriter> , ustawienia składnika zapisywania (określone w <xref:System.Xml.XmlWriterSettings> obiekcie) określają, czy jest generowana deklaracja XML.</span><span class="sxs-lookup"><span data-stu-id="36700-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated.</span></span>

<span data-ttu-id="36700-107">W przypadku serializacji do ciągu przy użyciu `ToString` metody, otrzymany kod XML nie będzie zawierał deklaracji XML.</span><span class="sxs-lookup"><span data-stu-id="36700-107">If you're serializing to a string using the `ToString` method, the resulting XML won't include an XML declaration.</span></span>

## <a name="example-serialize-with-an-xml-declaration"></a><span data-ttu-id="36700-108">Przykład: serializacji z deklaracją XML</span><span class="sxs-lookup"><span data-stu-id="36700-108">Example: Serialize with an XML declaration</span></span>

<span data-ttu-id="36700-109">Poniższy przykład tworzy <xref:System.Xml.Linq.XElement> , zapisuje dokument do pliku, a następnie drukuje plik do konsoli programu:</span><span class="sxs-lookup"><span data-stu-id="36700-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>

```csharp
XElement root = new XElement("Root",
    new XElement("Child", "child content")
);
root.Save("Root.xml");
string str = File.ReadAllText("Root.xml");
Console.WriteLine(str);
```

```vb
Dim root As XElement = <Root>
                           <Child>child content</Child>
                       </Root>
root.Save("Root.xml")
Dim str As String = File.ReadAllText("Root.xml")
Console.WriteLine(str)
```

<span data-ttu-id="36700-110">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="36700-110">This example produces the following output:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Root>
  <Child>child content</Child>
</Root>
```

## <a name="example-serialize-without-an-xml-declaration"></a><span data-ttu-id="36700-111">Przykład: serializacja bez deklaracji XML</span><span class="sxs-lookup"><span data-stu-id="36700-111">Example: Serialize without an XML declaration</span></span>

<span data-ttu-id="36700-112">Poniższy przykład pokazuje, jak zapisać element <xref:System.Xml.Linq.XElement> w <xref:System.Xml.XmlWriter> .</span><span class="sxs-lookup"><span data-stu-id="36700-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>

```csharp
StringBuilder sb = new StringBuilder();
XmlWriterSettings xws = new XmlWriterSettings();
xws.OmitXmlDeclaration = true;

using (XmlWriter xw = XmlWriter.Create(sb, xws)) {
    XElement root = new XElement("Root",
        new XElement("Child", "child content")
    );
    root.Save(xw);
}
Console.WriteLine(sb.ToString());
```

```vb
Dim sb As StringBuilder = New StringBuilder()
Dim xws As XmlWriterSettings = New XmlWriterSettings()
xws.OmitXmlDeclaration = True

Using xw As XmlWriter = XmlWriter.Create(sb, xws)
    Dim root = <Root>
                   <Child>child content</Child>
               </Root>
    root.Save(xw)
End Using
Console.WriteLine(sb.ToString())
```

<span data-ttu-id="36700-113">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="36700-113">This example produces the following output:</span></span>

```xml
<Root><Child>child content</Child></Root>
```
