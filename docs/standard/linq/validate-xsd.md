---
title: Jak przeprowadzić walidację przy użyciu LINQ to XML XSD
description: Można użyć metod rozszerzających z System.Xml. Przestrzeń nazw schematu do walidacji drzewa XML względem pliku języka definicji schematu XML (XSD).
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 6a7f83a9-2d74-4c2b-8417-0a8595879516
ms.openlocfilehash: 275a49658ddf2524530949929a7a5f04515a8493
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553762"
---
# <a name="how-to-validate-using-xsd-linq-to-xml"></a>Weryfikowanie przy użyciu XSD (LINQ to XML)

<xref:System.Xml.Schema>Przestrzeń nazw zawiera metody rozszerzające, które ułatwiają Weryfikowanie drzewa XML względem pliku języka definicji schematu XML (XSD). Aby uzyskać więcej informacji, zobacz <xref:System.Xml.Schema.Extensions.Validate%2A> dokumentację metody.

## <a name="example-validate-xdocument-objects-against-an-xmlschemaset"></a>Przykład: weryfikowanie obiektów klasy XDocument względem elementu XmlSchemaSet

Poniższy przykład tworzy <xref:System.Xml.Schema.XmlSchemaSet> , a następnie weryfikuje dwa <xref:System.Xml.Linq.XDocument> obiekty względem zestawu schematów. Jeden z dokumentów jest prawidłowy, druga nie jest.

```csharp
string xsdMarkup =
    @"<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>
       <xsd:element name='Root'>
        <xsd:complexType>
         <xsd:sequence>
          <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>
          <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>
         </xsd:sequence>
        </xsd:complexType>
       </xsd:element>
      </xsd:schema>";
XmlSchemaSet schemas = new XmlSchemaSet();
schemas.Add("", XmlReader.Create(new StringReader(xsdMarkup)));

XDocument doc1 = new XDocument(
    new XElement("Root",
        new XElement("Child1", "content1"),
        new XElement("Child2", "content1")
    )
);

XDocument doc2 = new XDocument(
    new XElement("Root",
        new XElement("Child1", "content1"),
        new XElement("Child3", "content1")
    )
);

Console.WriteLine("Validating doc1");
bool errors = false;
doc1.Validate(schemas, (o, e) =>
                     {
                         Console.WriteLine("{0}", e.Message);
                         errors = true;
                     });
Console.WriteLine("doc1 {0}", errors ? "did not validate" : "validated");

Console.WriteLine();
Console.WriteLine("Validating doc2");
errors = false;
doc2.Validate(schemas, (o, e) =>
                     {
                         Console.WriteLine("{0}", e.Message);
                         errors = true;
                     });
Console.WriteLine("doc2 {0}", errors ? "did not validate" : "validated");
```

```vb
Dim errors As Boolean = False

Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)
    Console.WriteLine("{0}", e.Message)
    errors = True
End Sub

Sub Main()
    Dim xsdMarkup As XElement = _
        <xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>
            <xsd:element name='Root'>
                <xsd:complexType>
                    <xsd:sequence>
                        <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>
                        <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>
                    </xsd:sequence>
                </xsd:complexType>
            </xsd:element>
        </xsd:schema>
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()
    schemas.Add("", xsdMarkup.CreateReader)

    Dim doc1 As XDocument = _
        <?xml version='1.0'?>
        <Root>
            <Child1>content1</Child1>
            <Child2>content1</Child2>
        </Root>

    Dim doc2 As XDocument = _
        <?xml version='1.0'?>
        <Root>
            <Child1>content1</Child1>
            <Child3>content1</Child3>
        </Root>

    Console.WriteLine("Validating doc1")
    errors = False
    doc1.Validate(schemas, AddressOf XSDErrors)
    Console.WriteLine("doc1 {0}", IIf(errors = True, "did not validate", "validated"))

    Console.WriteLine()
    Console.WriteLine("Validating doc2")
    errors = False
    doc2.Validate(schemas, AddressOf XSDErrors)
    Console.WriteLine("doc2 {0}", IIf(errors = True, "did not validate", "validated"))
End Sub
```

Ten przykład generuje następujące wyniki:

```output
Validating doc1
doc1 validated

Validating doc2
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.
doc2 did not validate
```

## <a name="example-validate-an-xml-document-from-a-file-against-a-schema-from-a-file"></a>Przykład: sprawdzanie poprawności dokumentu XML z pliku na schemat z pliku

Poniższy przykład sprawdza, czy dokument XML z [przykładowego pliku XML: klienci i zamówienia](sample-xml-file-customers-orders.md) są prawidłowe dla schematu z [przykładowego pliku XSD: klienci i zamówienia](sample-xsd-file-customers-orders.md). Następnie modyfikuje źródłowy dokument XML. Zmienia `CustomerID` atrybut pierwszego klienta. Po zmianie zamówienia będą odwoływać się do klienta, który nie istnieje, więc dokument XML nie zostanie już zweryfikowany.

```csharp
XmlSchemaSet schemas = new XmlSchemaSet();
schemas.Add("", "CustomersOrders.xsd");

Console.WriteLine("Attempting to validate");
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");
bool errors = false;
custOrdDoc.Validate(schemas, (o, e) =>
                     {
                         Console.WriteLine("{0}", e.Message);
                         errors = true;
                     });
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");

Console.WriteLine();
// Modify the source document so that it won't validate.
custOrdDoc.Root.Element("Orders").Element("Order").Element("CustomerID").Value = "AAAAA";
Console.WriteLine("Attempting to validate after modification");
errors = false;
custOrdDoc.Validate(schemas, (o, e) =>
                     {
                         Console.WriteLine("{0}", e.Message);
                         errors = true;
                     });
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");
```

```vb
Dim errors As Boolean = False

Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)
    Console.WriteLine("{0}", e.Message)
    errors = True
End Sub

Sub Main()
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()
    schemas.Add("", "CustomersOrders.xsd")

    Console.WriteLine("Attempting to validate")
    Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")
    errors = False
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))

    Console.WriteLine()
    ' Modify the source document so that it won't validate.
    custOrdDoc.<Root>.<Orders>.<Order>.<CustomerID>(0).Value = "AAAAA"
    Console.WriteLine("Attempting to validate after modification")
    errors = False
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))
End Sub
```

Ten przykład generuje następujące wyniki:

```output
Attempting to validate
custOrdDoc validated

Attempting to validate after modification
The key sequence 'AAAAA' in Keyref fails to refer to some key.
custOrdDoc did not validate
```

## <a name="see-also"></a>Zobacz też

- <xref:System.Xml.Schema.Extensions.Validate%2A?displayProperty=nameWithType>
- [Drzewa XML](functional-construction.md)
