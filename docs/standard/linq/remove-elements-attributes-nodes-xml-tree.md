---
title: Usuwanie elementów, atrybutów i węzłów z drzewa XML — LINQ to XML
description: Dowiedz się, jak usunąć elementy, atrybuty i inne typy węzłów z drzewa XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 07dd06d6-1117-4077-bf98-9120cf51176e
ms.openlocfilehash: 1a7c10892ccf1baaab7dde700266a134abe727de
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553693"
---
# <a name="remove-elements-attributes-and-nodes-from-an-xml-tree-linq-to-xml"></a><span data-ttu-id="1ea8b-103">Usuwanie elementów, atrybutów i węzłów z drzewa XML (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1ea8b-103">Remove elements, attributes, and nodes from an XML tree (LINQ to XML)</span></span>

<span data-ttu-id="1ea8b-104">Można modyfikować drzewo XML, usuwać elementy, atrybuty i inne typy węzłów.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-104">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>

<span data-ttu-id="1ea8b-105">Usuwanie pojedynczego elementu lub pojedynczego atrybutu z dokumentu XML jest proste.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-105">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="1ea8b-106">Jednak podczas usuwania kolekcji elementów lub atrybutów należy najpierw zmaterializowania kolekcję do listy, a następnie usunąć elementy lub atrybuty z listy.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-106">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="1ea8b-107">Najlepszym rozwiązaniem jest użycie <xref:System.Xml.Linq.Extensions.Remove%2A> metody rozszerzającej.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-107">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method to do this.</span></span>

<span data-ttu-id="1ea8b-108">Głównym powodem korzystania z tego podejścia jest to, że większość kolekcji pobieranych z drzewa XML jest realizowana przy użyciu odroczonego wykonania.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-108">The main reason to use this approach is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="1ea8b-109">Jeśli nie musisz najpierw zmaterializowania ich do listy lub jeśli nie korzystasz z metod rozszerzających, może wystąpić pewna klasa usterek.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-109">If you don't first materialize them into a list, or if you don't use the extension methods, you may encounter a certain class of bugs.</span></span> <span data-ttu-id="1ea8b-110">Aby uzyskać więcej informacji, zobacz [mieszane błędy kodu deklaracyjnego/](mixed-declarative-imperative-code-bugs.md)bezwzględnego.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-110">For more information, see [Mixed declarative/imperative code bugs](mixed-declarative-imperative-code-bugs.md).</span></span>

<span data-ttu-id="1ea8b-111">Poniższe metody usuwają węzły i atrybuty z drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-111">The following methods remove nodes and attributes from an XML tree.</span></span>

|<span data-ttu-id="1ea8b-112">Metoda</span><span class="sxs-lookup"><span data-stu-id="1ea8b-112">Method</span></span>|<span data-ttu-id="1ea8b-113">Opis</span><span class="sxs-lookup"><span data-stu-id="1ea8b-113">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="1ea8b-114">Usuń element <xref:System.Xml.Linq.XAttribute> z elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-114">Remove an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="1ea8b-115">Usuń węzły podrzędne z <xref:System.Xml.Linq.XContainer> .</span><span class="sxs-lookup"><span data-stu-id="1ea8b-115">Remove the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="1ea8b-116">Usuń zawartość i atrybuty z <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="1ea8b-116">Remove content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="1ea8b-117">Usuń atrybuty <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="1ea8b-117">Remove the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="1ea8b-118">Usuń atrybut, Jeśli przekażesz wartość `null` .</span><span class="sxs-lookup"><span data-stu-id="1ea8b-118">Remove the attribute if you pass the value `null`.</span></span>|
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="1ea8b-119">Usuń element podrzędny, Jeśli przekażesz wartość `null` .</span><span class="sxs-lookup"><span data-stu-id="1ea8b-119">Remove the child element if you pass the value `null`.</span></span>|
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="1ea8b-120">Usuń element <xref:System.Xml.Linq.XNode> z elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-120">Remove an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="1ea8b-121">Usuń każdy atrybut lub element z kolekcji źródłowej z jego elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-121">Remove every attribute or element in the source collection from its parent element.</span></span>|

## <a name="example-remove-a-single-element-and-remove-a-collection-of-elements-in-two-ways"></a><span data-ttu-id="1ea8b-122">Przykład: Usuń pojedynczy element i Usuń kolekcję elementów na dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-122">Example: Remove a single element, and remove a collection of elements in two ways</span></span>

<span data-ttu-id="1ea8b-123">Ten przykład ilustruje trzy podejścia do usuwania elementów.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-123">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="1ea8b-124">Najpierw usuwa pojedynczy element.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-124">First, it removes a single element.</span></span> <span data-ttu-id="1ea8b-125">Po drugie Pobiera kolekcję elementów, materializuje je przy użyciu <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> operatora, a następnie usuwa kolekcję.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-125">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> operator, and then removes the collection.</span></span> <span data-ttu-id="1ea8b-126">Na koniec Pobiera kolekcję elementów i usuwa je za pomocą <xref:System.Xml.Linq.Extensions.Remove%2A> metody rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="1ea8b-126">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>

<span data-ttu-id="1ea8b-127">Aby uzyskać więcej informacji na temat <xref:System.Linq.Enumerable.ToList%2A> operatora, zobacz [konwertowanie typów danych (C#)](../../csharp/programming-guide/concepts/linq/converting-data-types.md) i [konwertowanie typów danych (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1ea8b-127">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (C#)](../../csharp/programming-guide/concepts/linq/converting-data-types.md) and [Converting Data Types (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</span></span>

```csharp
XElement root = XElement.Parse(@"<Root>
    <Child1>
        <GrandChild1/>
        <GrandChild2/>
        <GrandChild3/>
    </Child1>
    <Child2>
        <GrandChild4/>
        <GrandChild5/>
        <GrandChild6/>
    </Child2>
    <Child3>
        <GrandChild7/>
        <GrandChild8/>
        <GrandChild9/>
    </Child3>
</Root>");
root.Element("Child1").Element("GrandChild1").Remove();
root.Element("Child2").Elements().ToList().Remove();
root.Element("Child3").Elements().Remove();
Console.WriteLine(root);
```

```vb
Dim root As XElement = _
    <Root>
        <Child1>
            <GrandChild1/>
            <GrandChild2/>
            <GrandChild3/>
        </Child1>
        <Child2>
            <GrandChild4/>
            <GrandChild5/>
            <GrandChild6/>
        </Child2>
        <Child3>
            <GrandChild7/>
            <GrandChild8/>
            <GrandChild9/>
        </Child3>
    </Root>
root.<Child1>.<GrandChild1>.Remove()
root.<Child2>.Elements().ToList().Remove()
root.<Child3>.Elements().Remove()
Console.WriteLine(root)
```

<span data-ttu-id="1ea8b-128">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1ea8b-128">This example produces the following output:</span></span>

```xml
<Root>
  <Child1>
    <GrandChild2 />
    <GrandChild3 />
  </Child1>
  <Child2 />
  <Child3 />
</Root>
```

<span data-ttu-id="1ea8b-129">Pierwszy element grandchild został usunięty z `Child1` , a wszystkie elementy podrzędne zostały usunięte z `Child2` i z `Child3` .</span><span class="sxs-lookup"><span data-stu-id="1ea8b-129">The first grandchild element was removed from `Child1`, and all grandchildren elements were removed from `Child2` and from `Child3`.</span></span>
