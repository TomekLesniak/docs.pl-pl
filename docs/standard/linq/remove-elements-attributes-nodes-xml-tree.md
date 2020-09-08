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
# <a name="remove-elements-attributes-and-nodes-from-an-xml-tree-linq-to-xml"></a>Usuwanie elementów, atrybutów i węzłów z drzewa XML (LINQ to XML)

Można modyfikować drzewo XML, usuwać elementy, atrybuty i inne typy węzłów.

Usuwanie pojedynczego elementu lub pojedynczego atrybutu z dokumentu XML jest proste. Jednak podczas usuwania kolekcji elementów lub atrybutów należy najpierw zmaterializowania kolekcję do listy, a następnie usunąć elementy lub atrybuty z listy. Najlepszym rozwiązaniem jest użycie <xref:System.Xml.Linq.Extensions.Remove%2A> metody rozszerzającej.

Głównym powodem korzystania z tego podejścia jest to, że większość kolekcji pobieranych z drzewa XML jest realizowana przy użyciu odroczonego wykonania. Jeśli nie musisz najpierw zmaterializowania ich do listy lub jeśli nie korzystasz z metod rozszerzających, może wystąpić pewna klasa usterek. Aby uzyskać więcej informacji, zobacz [mieszane błędy kodu deklaracyjnego/](mixed-declarative-imperative-code-bugs.md)bezwzględnego.

Poniższe metody usuwają węzły i atrybuty z drzewa XML.

|Metoda|Opis|
|------------|-----------------|
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|Usuń element <xref:System.Xml.Linq.XAttribute> z elementu nadrzędnego.|
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|Usuń węzły podrzędne z <xref:System.Xml.Linq.XContainer> .|
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|Usuń zawartość i atrybuty z <xref:System.Xml.Linq.XElement> .|
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Usuń atrybuty <xref:System.Xml.Linq.XElement> .|
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Usuń atrybut, Jeśli przekażesz wartość `null` .|
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Usuń element podrzędny, Jeśli przekażesz wartość `null` .|
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|Usuń element <xref:System.Xml.Linq.XNode> z elementu nadrzędnego.|
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|Usuń każdy atrybut lub element z kolekcji źródłowej z jego elementu nadrzędnego.|

## <a name="example-remove-a-single-element-and-remove-a-collection-of-elements-in-two-ways"></a>Przykład: Usuń pojedynczy element i Usuń kolekcję elementów na dwa sposoby.

Ten przykład ilustruje trzy podejścia do usuwania elementów. Najpierw usuwa pojedynczy element. Po drugie Pobiera kolekcję elementów, materializuje je przy użyciu <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> operatora, a następnie usuwa kolekcję. Na koniec Pobiera kolekcję elementów i usuwa je za pomocą <xref:System.Xml.Linq.Extensions.Remove%2A> metody rozszerzenia.

Aby uzyskać więcej informacji na temat <xref:System.Linq.Enumerable.ToList%2A> operatora, zobacz [konwertowanie typów danych (C#)](../../csharp/programming-guide/concepts/linq/converting-data-types.md) i [konwertowanie typów danych (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).

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

Ten przykład generuje następujące wyniki:

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

Pierwszy element grandchild został usunięty z `Child1` , a wszystkie elementy podrzędne zostały usunięte z `Child2` i z `Child3` .
