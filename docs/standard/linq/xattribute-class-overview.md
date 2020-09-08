---
title: XAttribute, Klasa — Omówienie
description: Klasa XAttribute reprezentuje atrybuty XML. Praca z atrybutami w LINQ to XML jest podobna do pracy z elementami.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
ms.openlocfilehash: deab6e8dd9695a442cd362401aec8b68cdbf218f
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552945"
---
# <a name="xattribute-class-overview"></a>XAttribute, Klasa — Omówienie

Atrybuty są parami nazwa-wartość, które są skojarzone z elementem. <xref:System.Xml.Linq.XAttribute>Klasa reprezentuje atrybuty XML.

Praca z atrybutami w LINQ to XML jest podobna do pracy z elementami. Ich konstruktory są podobne. Metody używane do pobierania kolekcji są podobne. Wyrażenie zapytania LINQ dla kolekcji atrybutów wygląda podobnie do wyrażenia zapytania LINQ dla kolekcji elementów.

Kolejność, w jakiej atrybuty zostały dodane do elementu, jest zachowywana. Oznacza to, że podczas iteracji przez atrybuty są one widoczne w takiej samej kolejności, w jakiej zostały dodane.

## <a name="the-xattribute-constructor"></a>Konstruktor XAttribute

Następujący Konstruktor <xref:System.Xml.Linq.XAttribute> klasy jest tym, którego najczęściej używasz:

|Konstruktor|Opis|
|-----------------|-----------------|
|`XAttribute(XName name, object content)`|Tworzy obiekt <xref:System.Xml.Linq.XAttribute>. `name`Argument określa nazwę atrybutu; `content` określa zawartość atrybutu.|

## <a name="example-create-an-element-with-an-attribute"></a>Przykład: Utwórz element z atrybutem

Poniższy przykład przedstawia typowe zadanie tworzenia elementu, który zawiera atrybut.

```csharp
XElement phone = new XElement("Phone",
    new XAttribute("Type", "Home"),
    "555-555-5555");
Console.WriteLine(phone);
```

```vb
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>
Console.WriteLine(phone)
```

Ten przykład generuje następujące wyniki:

```xml
<Phone Type="Home">555-555-5555</Phone>
```

## <a name="example-functional-construction-of-attributes"></a>Przykład: funkcjonalne konstruowanie atrybutów

Można tworzyć <xref:System.Xml.Linq.XAttribute> obiekty w wierszu z konstrukcją <xref:System.Xml.Linq.XElement> obiektów, jak pokazano w następującym przykładzie:

```csharp
XElement c = new XElement("Customers",
    new XElement("Customer",
        new XElement("Name", "John Doe"),
        new XElement("PhoneNumbers",
            new XElement("Phone",
                new XAttribute("type", "home"),
                "555-555-5555"),
            new XElement("Phone",
                new XAttribute("type", "work"),
                "666-666-6666")
        )
    )
);
Console.WriteLine(c);
```

```vb
Dim c As XElement = _
    <Customers>
        <Customer>
            <Name>John Doe</Name>
            <PhoneNumbers>
                <Phone type="home">555-555-5555</Phone>
                <Phone type="work">666-666-6666</Phone>
            </PhoneNumbers>
        </Customer>
    </Customers>
Console.WriteLine(c)
```

Ten przykład generuje następujące wyniki:

```xml
<Customers>
  <Customer>
    <Name>John Doe</Name>
    <PhoneNumbers>
      <Phone type="home">555-555-5555</Phone>
      <Phone type="work">666-666-6666</Phone>
    </PhoneNumbers>
  </Customer>
</Customers>
```

## <a name="attributes-arent-nodes"></a>Atrybuty nie są węzłami

Istnieją pewne różnice między atrybutami i elementami. <xref:System.Xml.Linq.XAttribute> obiekty nie są węzłami w drzewie XML. Są to pary nazwa-wartość skojarzone z elementem XML. W przeciwieństwie do Document Object Model (DOM), to dokładniej odzwierciedla strukturę XML. Chociaż <xref:System.Xml.Linq.XAttribute> obiekty nie są w rzeczywistości węzłami w drzewie XML, praca z <xref:System.Xml.Linq.XAttribute> obiektami jest podobna do pracy z <xref:System.Xml.Linq.XElement> obiektami.

Ta różnica jest głównie ważna tylko dla deweloperów, którzy piszą kod, który współpracuje z drzewami XML na poziomie węzła. Wielu deweloperów nie będą zainteresowani tym rozróżnieniem.

## <a name="see-also"></a>Zobacz też

- [Przegląd LINQ to XML](linq-xml-overview.md)
