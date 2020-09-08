---
title: Jak zbadać LINQ to XML przy użyciu XPath-LINQ to XML
description: Poznaj metody rozszerzające, które umożliwiają badanie drzewa XML przy użyciu XPath.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: 8189bcdd38f9242a5890837633bbec4e7f2fc601
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553711"
---
# <a name="how-to-query-linq-to-xml-using-xpath-linq-to-xml"></a>Jak zbadać LINQ to XML przy użyciu XPath (LINQ to XML)

W tym artykule wprowadzono metody rozszerzające, które umożliwiają badanie drzewa XML przy użyciu XPath. Aby uzyskać szczegółowe informacje na temat korzystania z tych metod rozszerzających, zobacz <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType> .

> [!NOTE]
> Chyba że masz bardzo konkretny powód wykonywania zapytań przy użyciu XPath, na przykład w przypadku użycia starszego kodu, używanie XPath z LINQ to XML nie jest zalecane. Zapytania XPath nie będą działać oraz LINQ to XML zapytań.

## <a name="example"></a>Przykład

Poniższy przykład tworzy małe drzewo XML i używa <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> do wybierania zestawu elementów.

```csharp
XElement root = new XElement("Root",
    new XElement("Child1", 1),
    new XElement("Child1", 2),
    new XElement("Child1", 3),
    new XElement("Child2", 4),
    new XElement("Child2", 5),
    new XElement("Child2", 6)
);
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");
foreach (XElement el in list)
    Console.WriteLine(el);
```

```vb
Dim root As XElement = _
    <Root>
        <Child1>1</Child1>
        <Child1>2</Child1>
        <Child1>3</Child1>
        <Child2>4</Child2>
        <Child2>5</Child2>
        <Child2>6</Child2>
    </Root>

Dim list As IEnumerable(Of XElement) = root.XPathSelectElements("./Child2")
For Each el As XElement In list
    Console.WriteLine(el)
Next
```

Ten przykład generuje następujące wyniki:

```xml
<Child2>4</Child2>
<Child2>5</Child2>
<Child2>6</Child2>
```
