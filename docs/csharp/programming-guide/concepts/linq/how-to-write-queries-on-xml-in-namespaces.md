---
title: Jak pisać zapytania dotyczące kodu XML w przestrzeniach nazw (C#)
description: Dowiedz się, jak pisać zapytania dotyczące kodu XML w przestrzeniach nazw. Dla tych zapytań należy użyć obiektów XName, które mają prawidłową przestrzeń nazw.
ms.date: 07/20/2015
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: 64eb9df1cde3b434a11e2e5410aab96993dc0fa1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303182"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a><span data-ttu-id="dfdeb-104">Jak pisać zapytania dotyczące kodu XML w przestrzeniach nazw (C#)</span><span class="sxs-lookup"><span data-stu-id="dfdeb-104">How to write queries on XML in namespaces (C#)</span></span>
<span data-ttu-id="dfdeb-105">Aby napisać zapytanie dotyczące kodu XML, który znajduje się w przestrzeni nazw, należy użyć <xref:System.Xml.Linq.XName> obiektów, które mają prawidłową przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="dfdeb-105">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="dfdeb-106">W przypadku języka C# najbardziej typowym podejściem jest zainicjowanie <xref:System.Xml.Linq.XNamespace> przy użyciu ciągu, który zawiera identyfikator URI, a następnie użycie przeciążenia operatora dodawania, aby połączyć przestrzeń nazw z nazwą lokalną.</span><span class="sxs-lookup"><span data-stu-id="dfdeb-106">For C#, the most common approach is to initialize an <xref:System.Xml.Linq.XNamespace> using a string that contains the URI, then use the addition operator overload to combine the namespace with the local name.</span></span>  
  
 <span data-ttu-id="dfdeb-107">Pierwszy zestaw przykładów w tym temacie przedstawia sposób tworzenia drzewa XML w domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="dfdeb-107">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="dfdeb-108">Drugi zestaw pokazuje, jak utworzyć drzewo XML w przestrzeni nazw z prefiksem.</span><span class="sxs-lookup"><span data-stu-id="dfdeb-108">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfdeb-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="dfdeb-109">Example</span></span>  
 <span data-ttu-id="dfdeb-110">Poniższy przykład tworzy drzewo XML, który znajduje się w domyślnym obszarze nazw.</span><span class="sxs-lookup"><span data-stu-id="dfdeb-110">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="dfdeb-111">Następnie pobiera kolekcję elementów.</span><span class="sxs-lookup"><span data-stu-id="dfdeb-111">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="dfdeb-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="dfdeb-112">This example produces the following output:</span></span>  
  
```output  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="dfdeb-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="dfdeb-113">Example</span></span>  
 <span data-ttu-id="dfdeb-114">W języku C# zapytania są pisane w taki sam sposób, niezależnie od tego, czy piszesz zapytania w drzewie XML, który używa przestrzeni nazw z prefiksem lub w drzewie XML z domyślną przestrzenią nazw.</span><span class="sxs-lookup"><span data-stu-id="dfdeb-114">In C#, you write queries in the same way regardless of whether you are writing queries on an XML tree that uses a namespace with a prefix or on an XML tree with a default namespace.</span></span>  
  
 <span data-ttu-id="dfdeb-115">Poniższy przykład tworzy drzewo XML, który znajduje się w przestrzeni nazw z prefiksem.</span><span class="sxs-lookup"><span data-stu-id="dfdeb-115">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="dfdeb-116">Następnie pobiera kolekcję elementów.</span><span class="sxs-lookup"><span data-stu-id="dfdeb-116">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="dfdeb-117">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="dfdeb-117">This example produces the following output:</span></span>  
  
```output  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfdeb-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dfdeb-118">See also</span></span>

- [<span data-ttu-id="dfdeb-119">Przegląd przestrzeni nazw (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="dfdeb-119">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
