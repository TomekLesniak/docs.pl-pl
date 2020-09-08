---
title: Atomowe obiekty XName i XNamespace — LINQ to XML
description: Dowiedz się, jak obiekty XName i XNamespace o tej samej nazwie współużytkują wystąpienie.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: a5b21433-b49d-415c-b00e-bcbfb0d267d7
ms.openlocfilehash: bc2be4d408385936598d94d34f9b452d950516d3
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553544"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml"></a><span data-ttu-id="bf242-103">Atomowe obiekty XName i XNamespace (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="bf242-103">Atomized XName and XNamespace objects (LINQ to XML)</span></span>

<span data-ttu-id="bf242-104"><xref:System.Xml.Linq.XName> i <xref:System.Xml.Linq.XNamespace> obiekty są *atomowe*; oznacza to, że jeśli zawierają one taką samą kwalifikowaną nazwę, odwołują się do tego samego obiektu.</span><span class="sxs-lookup"><span data-stu-id="bf242-104"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="bf242-105">Zapewnia to korzyści z wydajności dla zapytań: w przypadku porównania dwóch nazw atomowych dla równości, podstawowy język pośredni musi określić, czy te dwa odwołania wskazują na ten sam obiekt.</span><span class="sxs-lookup"><span data-stu-id="bf242-105">This yields performance benefits for queries: when you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="bf242-106">Kod źródłowy nie musi wykonywać porównań ciągów, co może potrwać dłużej.</span><span class="sxs-lookup"><span data-stu-id="bf242-106">The underlying code doesn't have to do string comparisons, which would take longer.</span></span>

## <a name="atomization-semantics"></a><span data-ttu-id="bf242-107">Semantyka rozproszenie</span><span class="sxs-lookup"><span data-stu-id="bf242-107">Atomization semantics</span></span>

<span data-ttu-id="bf242-108">Rozproszenie oznacza, że jeśli dwa <xref:System.Xml.Linq.XName> obiekty mają tę samą nazwę lokalną i znajdują się w tej samej przestrzeni nazw, współużytkują to samo wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="bf242-108">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they're in the same namespace, they share the same instance.</span></span> <span data-ttu-id="bf242-109">W taki sam sposób, jeśli dwa <xref:System.Xml.Linq.XNamespace> obiekty mają ten sam identyfikator URI przestrzeni nazw, współużytkują to samo wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="bf242-109">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>

<span data-ttu-id="bf242-110">Aby można było włączyć obiekt Atoms, Konstruktor dla klasy musi być prywatny, a nie publiczny.</span><span class="sxs-lookup"><span data-stu-id="bf242-110">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="bf242-111">Wynika to z faktu, że jeśli Konstruktor był publiczny, można utworzyć obiekt niebędący atomem.</span><span class="sxs-lookup"><span data-stu-id="bf242-111">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="bf242-112"><xref:System.Xml.Linq.XName>Klasy i <xref:System.Xml.Linq.XNamespace> implementują Operator niejawnej konwersji w celu przekonwertowania ciągu na <xref:System.Xml.Linq.XName> lub <xref:System.Xml.Linq.XNamespace> .</span><span class="sxs-lookup"><span data-stu-id="bf242-112">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="bf242-113">W ten sposób można uzyskać wystąpienie tych obiektów.</span><span class="sxs-lookup"><span data-stu-id="bf242-113">This is how you get an instance of these objects.</span></span> <span data-ttu-id="bf242-114">Nie można uzyskać wystąpienia przy użyciu konstruktora, ponieważ Konstruktor jest niedostępny.</span><span class="sxs-lookup"><span data-stu-id="bf242-114">You can't get an instance by using a constructor, because the constructor is inaccessible.</span></span>

<span data-ttu-id="bf242-115"><xref:System.Xml.Linq.XName> a <xref:System.Xml.Linq.XNamespace> także zaimplementować operatory równości i nierówności, które określają, czy dwa porównywane obiekty są odwołaniami do tego samego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="bf242-115"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, which determine whether the two objects being compared are references to the same instance.</span></span>

## <a name="example-create-objects-and-show-that-identical-names-share-an-instance"></a><span data-ttu-id="bf242-116">Przykład: Tworzenie obiektów i pokazuje, że identyczne nazwy współużytkują wystąpienie</span><span class="sxs-lookup"><span data-stu-id="bf242-116">Example: Create objects and show that identical names share an instance</span></span>

<span data-ttu-id="bf242-117">Poniższy kod tworzy niektóre <xref:System.Xml.Linq.XElement> obiekty i pokazuje, że identyczne nazwy współużytkują to samo wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="bf242-117">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>

```csharp
XElement r1 = new XElement("Root", "data1");
XElement r2 = XElement.Parse("<Root>data2</Root>");

if ((object)r1.Name == (object)r2.Name)
    Console.WriteLine("r1 and r2 have names that refer to the same instance.");
else
    Console.WriteLine("Different");

XName n = "Root";

if ((object)n == (object)r1.Name)
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.");
else
    Console.WriteLine("Different");
```

```vb
Dim r1 As New XElement("Root", "data1")
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")

If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")
Else
    Console.WriteLine("Different")
End If

Dim n As XName = "Root"

If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")
Else
    Console.WriteLine("Different")
End If
```

<span data-ttu-id="bf242-118">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="bf242-118">This example produces the following output:</span></span>

```output
r1 and r2 have names that refer to the same instance.
The name of r1 and the name in 'n' refer to the same instance.
```

<span data-ttu-id="bf242-119">Jak wspomniano wcześniej, zaletą obiektów atomowych jest użycie jednej z metod osi, która przyjmuje <xref:System.Xml.Linq.XName> jako parametr, metoda osi ma tylko określić, że dwie nazwy odwołują się do tego samego wystąpienia w celu wybrania żądanych elementów.</span><span class="sxs-lookup"><span data-stu-id="bf242-119">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>

<span data-ttu-id="bf242-120">Poniższy przykład przekazuje <xref:System.Xml.Linq.XName> <xref:System.Xml.Linq.XContainer.Descendants%2A> wywołanie metody, które następnie ma lepszą wydajność ze względu na wzorzec rozproszenie.</span><span class="sxs-lookup"><span data-stu-id="bf242-120">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>

```csharp
XElement root = new XElement("Root",
    new XElement("C1", 1),
    new XElement("Z1",
        new XElement("C1", 2),
        new XElement("C1", 1)
    )
);

var query = from e in root.Descendants("C1")
            where (int)e == 1
            select e;

foreach (var z in query)
    Console.WriteLine(z);
```

```vb
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))

Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e

For Each z As var In query
    Console.WriteLine(z)
Next
```

<span data-ttu-id="bf242-121">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="bf242-121">This example produces the following output:</span></span>

```xml
<C1>1</C1>
<C1>1</C1>
```
