---
title: 'Przykładowy plik XML: wiele zamówień zakupu w przestrzeni nazw — LINQ to XML'
description: Ten plik XML — który jest używany w przykładach — zawiera dane w przestrzeni nazw dotyczące zamówień zakupu.
ms.date: 07/20/2015
ms.assetid: 595024f2-374a-4615-acb5-64fa1600f377
ms.openlocfilehash: 17c416ad2a6fb75a5f019160b5935f1eb4b853c3
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553600"
---
# <a name="sample-xml-file-multiple-purchase-orders-in-a-namespace-linq-to-xml"></a><span data-ttu-id="9ac01-103">Przykładowy plik XML: wiele zamówień zakupu w przestrzeni nazw (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="9ac01-103">Sample XML file: Multiple purchase orders in a namespace (LINQ to XML)</span></span>

<span data-ttu-id="9ac01-104">Poniższy plik XML jest używany w różnych przykładach w dokumentacji LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="9ac01-104">The following XML file is used in various examples in the LINQ to XML documentation.</span></span> <span data-ttu-id="9ac01-105">Ten plik zawiera kilka zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="9ac01-105">This file contains several purchase orders.</span></span> <span data-ttu-id="9ac01-106">KOD XML znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9ac01-106">The XML is in a namespace.</span></span>

## <a name="purchaseordersinnamespacexml"></a><span data-ttu-id="9ac01-107">PurchaseOrdersInNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="9ac01-107">PurchaseOrdersInNamespace.xml</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<aw:PurchaseOrders xmlns:aw="http://www.adventure-works.com">
  <aw:PurchaseOrder aw:PurchaseOrderNumber="99503" aw:OrderDate="1999-10-20">
    <aw:Address aw:Type="Shipping">
      <aw:Name>Ellen Adams</aw:Name>
      <aw:Street>123 Maple Street</aw:Street>
      <aw:City>Mill Valley</aw:City>
      <aw:State>CA</aw:State>
      <aw:Zip>10999</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:Address>
    <aw:Address aw:Type="Billing">
      <aw:Name>Tai Yee</aw:Name>
      <aw:Street>8 Oak Avenue</aw:Street>
      <aw:City>Old Town</aw:City>
      <aw:State>PA</aw:State>
      <aw:Zip>95819</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:Address>
    <aw:DeliveryNotes>Please leave packages in shed by driveway.</aw:DeliveryNotes>
    <aw:Items>
      <aw:Item aw:PartNumber="872-AA">
        <aw:ProductName>Lawnmower</aw:ProductName>
        <aw:Quantity>1</aw:Quantity>
        <aw:USPrice>148.95</aw:USPrice>
        <aw:Comment>Confirm this is electric</aw:Comment>
      </aw:Item>
      <aw:Item aw:PartNumber="926-AA">
        <aw:ProductName>Baby Monitor</aw:ProductName>
        <aw:Quantity>2</aw:Quantity>
        <aw:USPrice>39.98</aw:USPrice>
        <aw:ShipDate>1999-05-21</aw:ShipDate>
      </aw:Item>
    </aw:Items>
  </aw:PurchaseOrder>
  <aw:PurchaseOrder aw:PurchaseOrderNumber="99505" aw:OrderDate="1999-10-22">
    <aw:Address aw:Type="Shipping">
      <aw:Name>Cristian Osorio</aw:Name>
      <aw:Street>456 Main Street</aw:Street>
      <aw:City>Buffalo</aw:City>
      <aw:State>NY</aw:State>
      <aw:Zip>98112</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:Address>
    <aw:Address aw:Type="Billing">
      <aw:Name>Cristian Osorio</aw:Name>
      <aw:Street>456 Main Street</aw:Street>
      <aw:City>Buffalo</aw:City>
      <aw:State>NY</aw:State>
      <aw:Zip>98112</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:Address>
    <aw:DeliveryNotes>Please notify me before shipping.</aw:DeliveryNotes>
    <aw:Items>
      <aw:Item aw:PartNumber="456-NM">
        <aw:ProductName>Power Supply</aw:ProductName>
        <aw:Quantity>1</aw:Quantity>
        <aw:USPrice>45.99</aw:USPrice>
      </aw:Item>
    </aw:Items>
  </aw:PurchaseOrder>
  <aw:PurchaseOrder aw:PurchaseOrderNumber="99504" aw:OrderDate="1999-10-22">
    <aw:Address aw:Type="Shipping">
      <aw:Name>Jessica Arnold</aw:Name>
      <aw:Street>4055 Madison Ave</aw:Street>
      <aw:City>Seattle</aw:City>
      <aw:State>WA</aw:State>
      <aw:Zip>98112</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:Address>
    <aw:Address aw:Type="Billing">
      <aw:Name>Jessica Arnold</aw:Name>
      <aw:Street>4055 Madison Ave</aw:Street>
      <aw:City>Buffalo</aw:City>
      <aw:State>NY</aw:State>
      <aw:Zip>98112</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:Address>
    <aw:Items>
      <aw:Item aw:PartNumber="898-AZ">
        <aw:ProductName>Computer Keyboard</aw:ProductName>
        <aw:Quantity>1</aw:Quantity>
        <aw:USPrice>29.99</aw:USPrice>
      </aw:Item>
      <aw:Item aw:PartNumber="898-AM">
        <aw:ProductName>Wireless Mouse</aw:ProductName>
        <aw:Quantity>1</aw:Quantity>
        <aw:USPrice>14.99</aw:USPrice>
      </aw:Item>
    </aw:Items>
  </aw:PurchaseOrder>
</aw:PurchaseOrders>
```
