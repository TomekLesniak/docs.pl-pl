---
title: Serializacja przy użyciu deklaracji XML (C#)
description: Informacje o konfiguracjach, w których Serializacja w języku C# generuje deklarację XML, łącznie z serializowaniem do pliku, TextWriter i XmlWriter.
ms.date: 07/20/2015
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 7e91b61f037d28149f7c2355f4233dc319b54627
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302363"
---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="f3853-103">Serializacja przy użyciu deklaracji XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f3853-103">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="f3853-104">W tym temacie opisano sposób kontrolowania, czy Serializacja generuje deklarację XML.</span><span class="sxs-lookup"><span data-stu-id="f3853-104">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="f3853-105">Generowanie deklaracji XML</span><span class="sxs-lookup"><span data-stu-id="f3853-105">XML Declaration Generation</span></span>  
 <span data-ttu-id="f3853-106">Serializacja do metody lub metody, <xref:System.IO.File> <xref:System.IO.TextWriter> <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> lub <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> Metoda generuje deklarację XML.</span><span class="sxs-lookup"><span data-stu-id="f3853-106">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="f3853-107">Podczas serializacji do <xref:System.Xml.XmlWriter> , ustawienia składnika zapisywania (określone w <xref:System.Xml.XmlWriterSettings> obiekcie) określają, czy deklaracja XML jest generowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="f3853-107">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="f3853-108">W przypadku serializacji do ciągu przy użyciu `ToString` metody, otrzymany kod XML nie będzie zawierał deklaracji XML.</span><span class="sxs-lookup"><span data-stu-id="f3853-108">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="f3853-109">Serializowanie przy użyciu deklaracji XML</span><span class="sxs-lookup"><span data-stu-id="f3853-109">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="f3853-110">Poniższy przykład tworzy <xref:System.Xml.Linq.XElement> , zapisuje dokument do pliku, a następnie drukuje plik do konsoli programu:</span><span class="sxs-lookup"><span data-stu-id="f3853-110">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="f3853-111">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="f3853-111">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="f3853-112">Serializacja bez deklaracji XML</span><span class="sxs-lookup"><span data-stu-id="f3853-112">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="f3853-113">Poniższy przykład pokazuje, jak zapisać element <xref:System.Xml.Linq.XElement> w <xref:System.Xml.XmlWriter> .</span><span class="sxs-lookup"><span data-stu-id="f3853-113">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
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
  
 <span data-ttu-id="f3853-114">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="f3853-114">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3853-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f3853-115">See also</span></span>

- [<span data-ttu-id="f3853-116">Serializowanie drzew XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f3853-116">Serializing XML Trees (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
