---
title: Jak utworzyć dokument z przestrzeniami nazw w języku C# — LINQ to XML
description: Użyj obiektu XNamespace w języku C#, aby utworzyć dokumenty, które mają domyślne przestrzenie nazw lub przestrzenie nazw z prefiksem.
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 3ec9624bcc599a73a6872e5c4c79504a1a4b4380
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553520"
---
# <a name="how-to-create-a-document-with-namespaces-in-c-linq-to-xml"></a>Jak utworzyć dokument z przestrzeniami nazw w języku C# (LINQ to XML)

W tym artykule pokazano, jak tworzyć dokumenty w języku C#, które mają przestrzenie nazw.

## <a name="example-declare-and-initialize-a-default-namespace"></a>Przykład: Zadeklaruj i zainicjuj domyślną przestrzeń nazw

Aby utworzyć element lub atrybut, który znajduje się w przestrzeni nazw, należy najpierw zadeklarować i zainicjować <xref:System.Xml.Linq.XNamespace> obiekt. Następnie należy użyć przeciążenia operatora dodawania, aby połączyć przestrzeń nazw z nazwą lokalną wyrażoną jako ciąg.

Poniższy przykład tworzy dokument z jedną przestrzenią nazw. Domyślnie LINQ to XML serializować tego dokumentu przy użyciu domyślnej przestrzeni nazw.

```csharp
// Create an XML tree in a namespace.
XNamespace aw = "http://www.adventure-works.com";
XElement root = new XElement(aw + "Root",
    new XElement(aw + "Child", "child content")
);
Console.WriteLine(root);
```

Ten przykład generuje następujące wyniki:

```xml
<Root xmlns="http://www.adventure-works.com">
  <Child>child content</Child>
</Root>
```

## <a name="example-create-a-document-that-has-a-namespace-and-an-attribute"></a>Przykład: Utwórz dokument z przestrzenią nazw i atrybutem

Poniższy przykład tworzy dokument z jedną przestrzenią nazw. Tworzy również atrybut, który deklaruje przestrzeń nazw z prefiksem przestrzeni nazw. Aby utworzyć atrybut, który deklaruje przestrzeń nazw z prefiksem, utworzysz atrybut, w którym nazwa atrybutu jest prefiksem przestrzeni nazw, a ta nazwa znajduje się w <xref:System.Xml.Linq.XNamespace.Xmlns%2A> przestrzeni nazw. Wartość tego atrybutu jest identyfikatorem URI przestrzeni nazw.

```csharp
// Create an XML tree in a namespace, with a specified prefix
XNamespace aw = "http://www.adventure-works.com";
XElement root = new XElement(aw + "Root",
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),
    new XElement(aw + "Child", "child content")
);
Console.WriteLine(root);
```

Ten przykład generuje następujące wyniki:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Child>child content</aw:Child>
</aw:Root>
```

## <a name="example-create-a-document-that-has-two-namespaces-one-with-a-prefix"></a>Przykład: Utwórz dokument zawierający dwie przestrzenie nazw, jeden z prefiksem

Poniższy przykład pokazuje, jak utworzyć dokument zawierający dwie przestrzenie nazw. Jedną z nich jest domyślna przestrzeń nazw, druga jest przestrzenią nazw z prefiksem.

Uwzględniając atrybuty przestrzeni nazw w elemencie głównym, przestrzenie nazw są serializowane, więc `http://www.adventure-works.com` jest to domyślna przestrzeń nazw i `www.fourthcoffee.com` jest serializowany z prefiksem `fc` . Aby utworzyć atrybut, który deklaruje domyślną przestrzeń nazw, należy utworzyć atrybut o nazwie `xmlns` bez przestrzeni nazw. Wartość atrybutu jest domyślnym identyfikatorem URI przestrzeni nazw.

```csharp
// The http://www.adventure-works.com namespace is forced to be the default namespace.
XNamespace aw = "http://www.adventure-works.com";
XNamespace fc = "www.fourthcoffee.com";
XElement root = new XElement(aw + "Root",
    new XAttribute("xmlns", "http://www.adventure-works.com"),
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),
    new XElement(fc + "Child",
        new XElement(aw + "DifferentChild", "other content")
    ),
    new XElement(aw + "Child2", "c2 content"),
    new XElement(fc + "Child3", "c3 content")
);
Console.WriteLine(root);
```

Ten przykład generuje następujące wyniki:

```xml
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">
  <fc:Child>
    <DifferentChild>other content</DifferentChild>
  </fc:Child>
  <Child2>c2 content</Child2>
  <fc:Child3>c3 content</fc:Child3>
</Root>
```

## <a name="example-create-a-document-that-has-two-namespaces-both-with-prefixes"></a>Przykład: Utwórz dokument, który ma dwie przestrzenie nazw, zarówno z prefiksami

Poniższy przykład tworzy dokument zawierający dwie przestrzenie nazw, zarówno z prefiksami przestrzeni nazw.

```csharp
XNamespace aw = "http://www.adventure-works.com";
XNamespace fc = "www.fourthcoffee.com";
XElement root = new XElement(aw + "Root",
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),
    new XElement(fc + "Child",
        new XElement(aw + "DifferentChild", "other content")
    ),
    new XElement(aw + "Child2", "c2 content"),
    new XElement(fc + "Child3", "c3 content")
);
Console.WriteLine(root);
```

Ten przykład generuje następujące wyniki:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">
  <fc:Child>
    <aw:DifferentChild>other content</aw:DifferentChild>
  </fc:Child>
  <aw:Child2>c2 content</aw:Child2>
  <fc:Child3>c3 content</fc:Child3>
</aw:Root>
```

## <a name="example-create-a-namespace-using-expanded-names"></a>Przykład: tworzenie przestrzeni nazw przy użyciu rozwiniętych nazw

Innym sposobem osiągnięcia tego samego wyniku jest użycie rozwiniętych nazw zamiast deklarowania i tworzenia <xref:System.Xml.Linq.XNamespace> obiektu.

Takie podejście ma wpływ na wydajność. Za każdym razem, gdy przekazujesz ciąg zawierający rozwiniętą nazwę do LINQ to XML, LINQ to XML musi przeanalizować nazwę, znaleźć wykorzystaną przestrzeń nazw i znaleźć nazwę atomową. Ten proces pobiera czas procesora CPU. Jeśli wydajność jest ważna, warto zadeklarować obiekt i używać go <xref:System.Xml.Linq.XNamespace> jawnie.

Jeśli wydajność jest ważnym problemem, zobacz [pre-rozproszenie of XName Objects](pre-atomization-xname-objects.md) , aby uzyskać więcej informacji.

```csharp
// Create an XML tree in a namespace, with a specified prefix
XElement root = new XElement("{http://www.adventure-works.com}Root",
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),
    new XElement("{http://www.adventure-works.com}Child", "child content")
);
Console.WriteLine(root);
```

Ten przykład generuje następujące wyniki:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Child>child content</aw:Child>
</aw:Root>
```

## <a name="see-also"></a>Zobacz też

- [Przegląd przestrzeni nazw](namespaces-overview.md)
