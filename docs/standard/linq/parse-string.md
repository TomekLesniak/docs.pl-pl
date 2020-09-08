---
title: Jak analizować ciąg LINQ to XML
description: Można przeanalizować ciąg za pomocą XElement. Parse, aby utworzyć drzewo XML w C# i Visual Basic, i można utworzyć drzewo XML z literałami XML w Visual Basic.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: f4bd22acbf3b11d801c791cc591d882810450fd4
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553077"
---
# <a name="how-to-parse-a-string-linq-to-xml"></a>Jak przeanalizować ciąg (LINQ to XML)

W tym artykule pokazano, jak przeanalizować ciąg w celu utworzenia drzewa XML w języku C# i w Visual Basic.

## <a name="example"></a>Przykład

Poniższy kod w języku C# pokazuje, jak analizować ciąg XML:

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

Można analizować ciąg w Visual Basic w podobny sposób. Jest to jednak bardziej wydajne w przypadku używania literałów XML, jak pokazano w poniższym kodzie, ponieważ literały XML nie cierpią od tych samych kar za wydajność, co analizowanie XML z ciągu.

Za pomocą literałów XML, można po prostu skopiować i wkleić kod XML do programu Visual Basic.

> [!NOTE]
> Analizowanie tekstu lub ładowanie dokumentu XML z pliku tekstowego jest mniej wydajne niż konstrukcja funkcjonalna. Jeśli inicjujesz drzewo XML od kodu, trwa mniej czasu procesora, aby użyć konstrukcji funkcjonalnej niż w celu przeanalizowania tekstu.

```vb
Dim contacts as XElement = _
    <Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type="home">206-555-0144</Phone>
            <Phone Type="work">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type="mobile">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>
```

Węzeł główny `Contacts` ma dwa `Contact` węzły. Aby uzyskać dostęp do określonych danych w analizowanym formacie XML, należy użyć metody [XElement. elementy ()](xref:System.Xml.Linq.XContainer.Elements) , która w tym przypadku zwraca elementy podrzędne `Contacts` węzła głównego. Poniższy przykład drukuje pierwszy `Contact` węzeł konsoli:

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

```vb
Dim contactNodes As List(Of XElement) = contacts.Elements("Contact").ToList()
Console.WriteLine(contactNodes(0))
```

## <a name="see-also"></a>Zobacz też

- [Sposób wyszukiwania elementu o określonym atrybucie](find-element-specific-attribute.md)
