---
title: 'Przykładowy plik XSD: klienci i zamówienia — LINQ to XML'
description: 'Ten plik XSD, który jest używany w przykładach — zawiera definicję schematu dla "przykładowego pliku XML: Customers i Orders".'
ms.date: 07/20/2015
ms.assetid: ef9911a3-7ac4-44fd-b36e-a0c0ad0a157d
ms.openlocfilehash: 660d1dae764882199c8f2516057f8fc07ad0a9af
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553816"
---
# <a name="sample-xsd-file-customers-and-orders-linq-to-xml"></a><span data-ttu-id="a1d1f-103">Przykładowy plik XSD: klienci i zamówienia (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="a1d1f-103">Sample XSD file: Customers and orders (LINQ to XML)</span></span>

<span data-ttu-id="a1d1f-104">Następujący plik XSD jest używany w różnych przykładach w dokumentacji LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="a1d1f-104">The following XSD file is used in various examples in the LINQ to XML documentation.</span></span> <span data-ttu-id="a1d1f-105">Ten plik zawiera definicję schematu dla [przykładowego pliku XML: klienci i zamówienia](sample-xml-file-customers-orders.md).</span><span class="sxs-lookup"><span data-stu-id="a1d1f-105">This file contains a schema definition for the [Sample XML file: Customers and orders](sample-xml-file-customers-orders.md).</span></span> <span data-ttu-id="a1d1f-106">Schemat używa `xs:key` i `xs:keyref` funkcji XSD, aby określić, że `CustomerID` atrybut `Customer` elementu jest kluczem i aby ustanowić relację między `CustomerID` elementem w każdym `Order` elemencie a `CustomerID` atrybutem w każdym `Customer` elemencie.</span><span class="sxs-lookup"><span data-stu-id="a1d1f-106">The schema uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>

<span data-ttu-id="a1d1f-107">Przykład pisania zapytań LINQ, które wykorzystują tę relację przy użyciu `Join` klauzuli, można znaleźć w temacie [jak sprzęgać dwie kolekcje](join-two-collections.md).</span><span class="sxs-lookup"><span data-stu-id="a1d1f-107">For an example of writing LINQ queries that take advantage of this relationship using the `Join` clause, see [How to join two collections](join-two-collections.md).</span></span>

## <a name="customersordersxsd"></a><span data-ttu-id="a1d1f-108">CustomersOrders. xsd</span><span class="sxs-lookup"><span data-stu-id="a1d1f-108">CustomersOrders.xsd</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name='Root'>
    <xs:complexType>
      <xs:sequence>
        <xs:element name='Customers'>
          <xs:complexType>
            <xs:sequence>
              <xs:element name='Customer' type='CustomerType' minOccurs='0' maxOccurs='unbounded' />
            </xs:sequence>
          </xs:complexType>
        </xs:element>
        <xs:element name='Orders'>
          <xs:complexType>
            <xs:sequence>
              <xs:element name='Order' type='OrderType' minOccurs='0' maxOccurs='unbounded' />
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:sequence>
    </xs:complexType>
    <xs:key name='CustomerIDKey'>
      <xs:selector xpath='Customers/Customer'/>
      <xs:field xpath='@CustomerID'/>
    </xs:key>
    <xs:keyref name='CustomerIDKeyRef' refer='CustomerIDKey'>
      <xs:selector xpath='Orders/Order'/>
      <xs:field xpath='CustomerID'/>
    </xs:keyref>
  </xs:element>
  <xs:complexType name='CustomerType'>
    <xs:sequence>
      <xs:element name='CompanyName' type='xs:string'/>
      <xs:element name='ContactName' type='xs:string'/>
      <xs:element name='ContactTitle' type='xs:string'/>
      <xs:element name='Phone' type='xs:string'/>
      <xs:element name='Fax' minOccurs='0' type='xs:string'/>
      <xs:element name='FullAddress' type='AddressType'/>
    </xs:sequence>
    <xs:attribute name='CustomerID' type='xs:token'/>
  </xs:complexType>
  <xs:complexType name='AddressType'>
    <xs:sequence>
      <xs:element name='Address' type='xs:string'/>
      <xs:element name='City' type='xs:string'/>
      <xs:element name='Region' type='xs:string'/>
      <xs:element name='PostalCode' type='xs:string' />
      <xs:element name='Country' type='xs:string'/>
    </xs:sequence>
    <xs:attribute name='CustomerID' type='xs:token'/>
  </xs:complexType>
  <xs:complexType name='OrderType'>
    <xs:sequence>
      <xs:element name='CustomerID' type='xs:token'/>
      <xs:element name='EmployeeID' type='xs:token'/>
      <xs:element name='OrderDate' type='xs:dateTime'/>
      <xs:element name='RequiredDate' type='xs:dateTime'/>
      <xs:element name='ShipInfo' type='ShipInfoType'/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name='ShipInfoType'>
    <xs:sequence>
      <xs:element name='ShipVia' type='xs:integer'/>
      <xs:element name='Freight' type='xs:decimal'/>
      <xs:element name='ShipName' type='xs:string'/>
      <xs:element name='ShipAddress' type='xs:string'/>
      <xs:element name='ShipCity' type='xs:string'/>
      <xs:element name='ShipRegion' type='xs:string'/>
      <xs:element name='ShipPostalCode' type='xs:string'/>
      <xs:element name='ShipCountry' type='xs:string'/>
    </xs:sequence>
    <xs:attribute name='ShippedDate' type='xs:dateTime'/>
  </xs:complexType>
</xs:schema>
```
