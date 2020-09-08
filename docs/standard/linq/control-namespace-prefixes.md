---
title: Jak kontrolować prefiksy przestrzeni nazw — LINQ to XML
description: Prefiksy przestrzeni nazw można kontrolować podczas serializowania drzewa XML w C# i Visual Basic. W tym celu należy wstawić atrybuty, które deklarują przestrzenie nazw.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: 07efc23c11cd0dc0d281968911cf24d6ecbc76a2
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553020"
---
# <a name="how-to-control-namespace-prefixes-linq-to-xml"></a>Sposób kontrolowania prefiksów przestrzeni nazw (LINQ to XML)

W tym artykule opisano sposób kontrolowania prefiksów przestrzeni nazw podczas serializowania drzewa XML w języku C# i Visual Basic.

W wielu sytuacjach nie trzeba kontrolować prefiksów przestrzeni nazw. Jednak niektóre narzędzia programowania XML wymagają tego. Na przykład może to być manipulowanie arkuszem stylów XSLT lub dokumentem XAML zawierającym osadzone wyrażenia XPath odwołujące się do określonych prefiksów przestrzeni nazw. W takim przypadku ważne jest, aby dokument był serializowany z tymi prefiksami. Jest to typowa przyczyna kontrolowania prefiksów przestrzeni nazw.

Kolejną przyczyną jest to, że użytkownicy będą mogli ręcznie edytować dokument XML i utworzyć prefiksy przestrzeni nazw, które są wygodne dla użytkownika. Na przykład może być generowany dokument XSD. Konwencje dla schematów sugerują użycie albo `xs` `xsd` jako prefiksu przestrzeni nazw schematu.

Aby kontrolować prefiksy przestrzeni nazw, należy wstawić atrybuty, które deklarują przestrzenie nazw. Jeśli zadeklarujesz przestrzenie nazw z określonymi prefiksami, LINQ to XML podejmie próbę zahonorowania prefiksów przestrzeni nazw podczas serializacji.

Aby utworzyć atrybut, który deklaruje przestrzeń nazw z prefiksem, utworzysz atrybut, w którym przestrzeń nazw atrybutu jest <xref:System.Xml.Linq.XNamespace.Xmlns%2A> , a nazwa atrybutu jest prefiksem przestrzeni nazw. Wartość atrybutu jest identyfikatorem URI przestrzeni nazw.

## <a name="example-create-two-namespaces-that-have-prefixes"></a>Przykład: Utwórz dwie przestrzenie nazw, które mają prefiksy

Ten przykład deklaruje dwie przestrzenie nazw. Określa prefiks `aw` `http://www.adventure-works.com` przestrzeni nazw oraz prefiks `fc` `www.fourthcoffee.com` przestrzeni nazw.

```csharp
XNamespace aw = "http://www.adventure-works.com";
XNamespace fc = "www.fourthcoffee.com";
XElement root = new XElement(aw + "Root",
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),
    new XElement(fc + "Child",
        new XElement(aw + "DifferentChild", "other content")
    ),
    new XElement(aw + "Child2", "c2 content"),
    new XElement(fc + "Child3", "c3 content")
);
Console.WriteLine(root);
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">
Imports <xmlns:fc="www.fourthcoffee.com">

Module Module1

    Sub Main()
        Dim root As XElement = _
            <aw:Root>
                <fc:Child>
                    <aw:DifferentChild>other content</aw:DifferentChild>
                </fc:Child>
                <aw:Child2>c2 content</aw:Child2>
                <fc:Child3>c3 content</fc:Child3>
            </aw:Root>
        Console.WriteLine(root)
    End Sub

This example produces the following output:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">
  <fc:Child>
    <aw:DifferentChild>other content</aw:DifferentChild>
  </fc:Child>
  <aw:Child2>c2 content</aw:Child2>
  <fc:Child3>c3 content</fc:Child3>
</aw:Root>
```

## <a name="see-also"></a>Zobacz też

- [Przegląd przestrzeni nazw](namespaces-overview.md)
