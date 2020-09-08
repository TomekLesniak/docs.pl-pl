---
title: Przegląd — LINQ to XML
description: LINQ to XML udostępnia interfejs programowania XML w pamięci, który jest oparty na możliwościach platformy .NET i porównywalny z zaktualizowanym interfejsem API modelu DOM.
ms.date: 10/30/2018
dev_langs:
- csharp
- vb
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: f805d757c9059a07988c6cb16e41ffed017fe853
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553355"
---
# <a name="linq-to-xml-overview"></a>Przegląd LINQ to XML

LINQ to XML udostępnia interfejs programowania XML w pamięci, który wykorzystuje architekturę programu .NET Language-Integrated Query (LINQ). LINQ to XML używa możliwości platformy .NET i jest porównywalna z zaktualizowanym, przeprojektowanym Document Object Model (DOM) interfejsem programowania XML.

Język XML został szeroko przyjęty jako sposób formatowania danych w wielu kontekstach. Na przykład można znaleźć XML w sieci Web, w plikach konfiguracyjnych, w Microsoft Office pliki programu Word i w bazach danych.

LINQ to XML to aktualne, przeprojektowane podejście do programowania w języku XML. Zapewnia możliwości modyfikacji dokumentów w pamięci Document Object Model (DOM) i obsługuje wyrażenia zapytań LINQ. Mimo że te wyrażenia zapytania różnią się od składni XPath, zapewniają podobną funkcjonalność.

## <a name="linq-to-xml-developers"></a>LINQ to XML deweloperzy

LINQ to XML są przeznaczone dla wielu deweloperów. W przypadku przeciętnego dewelopera, który po prostu chce uzyskać coś gotowego, LINQ to XML ułatwia tworzenie kodu XML, zapewniając środowisko zapytania podobne do bazy danych SQL. Mając zaledwie kilka analiz, programiści mogą uczyć się pisać zwięzłe i zaawansowane zapytania w wybranym języku programowania.

Profesjonalni deweloperzy mogą korzystać z LINQ to XML, aby znacznie zwiększyć swoją produktywność. Dzięki LINQ to XML mogą pisać mniej kod, który jest bardziej wyraźny, bardziej kompaktowy i bardziej wydajny. Mogą używać wyrażeń zapytania z wielu domen danych w tym samym czasie.

## <a name="linq-to-xml-is-an-xml-programming-interface"></a>LINQ to XML to interfejs programowania XML

LINQ to XML to interfejs programowania XML obsługujący LINQ, który umożliwia współpracę z danymi XML z poziomu języków programowania .NET.

LINQ to XML przypomina Document Object Model (DOM) w tym, że dokument XML jest umieszczany w pamięci. Możesz wysyłać zapytania i modyfikować dokument, a po zmodyfikowaniu go można zapisać do pliku lub serializować go i wysłać za pośrednictwem Internetu. Jednak LINQ to XML różni się od modelu DOM:

- Udostępnia nowy model obiektów, który jest jaśniejszy i łatwiejszy do pracy z.
- Korzysta ona z funkcji języka w języku C# i Visual Basic.

Najważniejszym zaletą LINQ to XML jest integracja z funkcją LINQ (Language-Integrated Query). Ta Integracja umożliwia pisanie zapytań dotyczących dokumentu XML w pamięci w celu pobrania kolekcji elementów i atrybutów. Możliwość wykonywania zapytań w LINQ to XML jest porównywalna w funkcji (choć nie w składni) do XPath i XQuery. Integracja LINQ w języku C# i Visual Basic zapewnia lepsze wpisywanie, sprawdzanie czasu kompilowania i udoskonaloną obsługę debugera.

Kolejną zaletą LINQ to XML jest możliwość używania wyników zapytania jako parametrów do <xref:System.Xml.Linq.XElement> i <xref:System.Xml.Linq.XAttribute> konstruktorów obiektów umożliwia zaawansowane podejście do tworzenia drzew XML. Takie podejście, nazywane *konstrukcją funkcjonalną*, umożliwia deweloperom łatwe przekształcanie drzew XML z jednego kształtu do drugiego.

Można na przykład mieć typowe zamówienie zakupu XML, zgodnie z opisem w [przykładowym pliku XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md). Za pomocą LINQ to XML można uruchomić następujące zapytanie w celu uzyskania wartości atrybutu numer części dla każdego elementu elementu w zamówieniu zakupu:

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")
                               select (string) item.Attribute("PartNumber");
```

```vb
' Load the XML file from our project directory containing the purchase orders
Dim filename = "PurchaseOrder.xml"
Dim currentDirectory = Directory.GetCurrentDirectory()
Dim purchaseOrderFilepath = Path.Combine(currentDirectory, filename)

Dim purchaseOrder As XElement = XElement.Load(purchaseOrderFilepath)

Dim partNos = _
    From item In purchaseOrder...<Item> _
    Select item.@PartNumber
```

W języku C# można to napisać ponownie w postaci składni metody:

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

Innym przykładem może być lista, posortowana według numeru części, dla elementów o wartości większej niż $100. Aby uzyskać te informacje, można uruchomić następujące zapytanie:

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100
                                 orderby (string)item.Element("PartNumber")
                                 select item;
```

```vb
' Load the XML file from our project directory containing the purchase orders
Dim filename = "PurchaseOrder.xml"
Dim currentDirectory = Directory.GetCurrentDirectory()
Dim purchaseOrderFilepath = Path.Combine(currentDirectory, filename)

Dim purchaseOrder As XElement = XElement.Load(purchaseOrderFilepath)

Dim partNos = _
From item In purchaseOrder...<Item> _
Where (item.<Quantity>.Value * _
       item.<USPrice>.Value) > 100 _
Order By item.<PartNumber>.Value _
Select item
```

W języku C# można ponownie napisać w formie składni metody:

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

Oprócz tych możliwości LINQ LINQ to XML udostępnia udoskonalony interfejs programowania XML. Za pomocą LINQ to XML można:

- Załaduj plik XML z [plików](load-xml-file.md) lub [strumieni](stream-xml-fragments-xmlreader.md).
- Serializacja XML do plików lub strumieni.
- Utwórz plik XML od podstaw przy użyciu konstrukcji funkcjonalnej.
- Kwerenda XML przy użyciu osi podobnej do XPath.
- Manipulowanie drzewem XML w pamięci za pomocą metod takich jak <xref:System.Xml.Linq.XContainer.Add%2A> , <xref:System.Xml.Linq.XNode.Remove%2A> , <xref:System.Xml.Linq.XNode.ReplaceWith%2A> i <xref:System.Xml.Linq.XElement.SetValue%2A> .
- Sprawdzanie poprawności drzew XML przy użyciu XSD.
- Aby przekształcić drzewa XML z jednego kształtu na inny, należy użyć kombinacji tych funkcji.

## <a name="create-xml-trees"></a>Tworzenie drzew XML

Jedną z najbardziej znaczących zalet programowania przy użyciu LINQ to XML jest łatwość tworzenia drzew XML. Na przykład, aby utworzyć małe drzewo XML, można napisać kod w następujący sposób:

```csharp
XElement contacts =
new XElement("Contacts",
    new XElement("Contact",
        new XElement("Name", "Patrick Hines"),
        new XElement("Phone", "206-555-0144",
            new XAttribute("Type", "Home")),
        new XElement("phone", "425-555-0145",
            new XAttribute("Type", "Work")),
        new XElement("Address",
            new XElement("Street1", "123 Main St"),
            new XElement("City", "Mercer Island"),
            new XElement("State", "WA"),
            new XElement("Postal", "68042")
        )
    )
);
```

```vb
Dim contacts As XElement = _
    <Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone>206-555-0144</Phone>
            <Address>
                <Street1>123 Main St</Street1>
                <City>Mercer Island</City>
                <State>WA</State>
                <Postal>68042</Postal>
            </Address>
        </Contact>
    </Contacts>
```

> [!NOTE]
> W Visual Basic wersji tego przykładu są używane literały XML. Można również użyć <xref:System.Xml.Linq.XElement> w Visual Basic, jak w wersji języka C#.

Aby uzyskać więcej informacji, zobacz [drzewa XML](functional-construction.md).

## <a name="see-also"></a>Zobacz też

- [Odwołanie](reference.md)
- [LINQ to XML a DOM](linq-xml-vs-dom.md)
- [LINQ to XML a inne technologie XML](linq-xml-vs-xml-technologies.md)
- <xref:System.Xml.Linq>
