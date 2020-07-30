---
title: Wykonywanie zapytania dotyczącego elementu XDocument a zapytania dotyczącego elementu XElement (C#)
description: Dowiedz się więcej o różnicach między wykonywaniem zapytań dotyczących elementu XDocument i wykonywaniem zapytania dotyczącego elementu XElement. Zapoznaj się z przykładami kodu, które przedstawiają te różnice.
ms.date: 07/20/2015
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
ms.openlocfilehash: 0c81768f06148308a639f96f4041e464b24edd33
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87300322"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a><span data-ttu-id="dfc3f-104">Wykonywanie zapytania dotyczącego elementu XDocument a zapytania dotyczącego elementu XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="dfc3f-104">Querying an XDocument vs. Querying an XElement (C#)</span></span>
<span data-ttu-id="dfc3f-105">Podczas ładowania dokumentu za pośrednictwem programu należy <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> zauważyć, że trzeba pisać zapytania nieco inaczej niż podczas ładowania za pośrednictwem <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="dfc3f-105">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="dfc3f-106">Porównanie elementów XDocument. Load i XElement. Load</span><span class="sxs-lookup"><span data-stu-id="dfc3f-106">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="dfc3f-107">Podczas ładowania dokumentu XML do elementu <xref:System.Xml.Linq.XElement> za pośrednictwem <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> <xref:System.Xml.Linq.XElement> katalog główny drzewa XML zawiera element główny załadowanego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="dfc3f-107">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="dfc3f-108">Jednak podczas ładowania tego samego dokumentu XML do elementu <xref:System.Xml.Linq.XDocument> za pośrednictwem <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> katalog główny drzewa jest <xref:System.Xml.Linq.XDocument> węzłem, a głównym elementem załadowanego dokumentu jest jeden dozwolony <xref:System.Xml.Linq.XElement> węzeł podrzędny <xref:System.Xml.Linq.XDocument> .</span><span class="sxs-lookup"><span data-stu-id="dfc3f-108">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="dfc3f-109">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]Osie działają względem węzła głównego.</span><span class="sxs-lookup"><span data-stu-id="dfc3f-109">The [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="dfc3f-110">Ten pierwszy przykład ładuje drzewo XML przy użyciu <xref:System.Xml.Linq.XElement.Load%2A> .</span><span class="sxs-lookup"><span data-stu-id="dfc3f-110">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="dfc3f-111">Następnie wykonuje zapytanie dotyczące elementów podrzędnych katalogu głównego drzewa.</span><span class="sxs-lookup"><span data-stu-id="dfc3f-111">It then queries for the child elements of the root of the tree.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="dfc3f-112">Zgodnie z oczekiwaniami ten przykład generuje następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="dfc3f-112">As expected, this example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="dfc3f-113">Poniższy przykład jest taki sam jak powyżej, z wyjątkiem tego, że drzewo XML jest załadowane do elementu <xref:System.Xml.Linq.XDocument> zamiast <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="dfc3f-113">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="dfc3f-114">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="dfc3f-114">This example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="dfc3f-115">Zwróć uwagę, że to samo zapytanie zwróciło jeden `Root` węzeł zamiast trzech węzłów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="dfc3f-115">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="dfc3f-116">Jednym z metod postępowania z tym jest użycie <xref:System.Xml.Linq.XDocument.Root%2A> Właściwości przed uzyskaniem dostępu do metody osi w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="dfc3f-116">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="dfc3f-117">To zapytanie jest teraz wykonywane w taki sam sposób, jak zapytanie w drzewie w katalogu głównym <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="dfc3f-117">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="dfc3f-118">Przykład generuje następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="dfc3f-118">The example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  