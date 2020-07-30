---
title: Jak znaleźć listę elementów podrzędnych (XPath-LINQ to XML) (C#)
description: Dowiedz się, jak znaleźć listę elementów podrzędnych przy użyciu wyrażenia XPath. Przejrzyj przykład kodu, który znajduje wszystkie elementy podrzędne określonego elementu.
ms.date: 07/20/2015
ms.assetid: 7c589dd8-f680-4cdb-9d6a-78d57e2555e8
ms.openlocfilehash: a3025aca7fb1055acd55e5ce98914d8359ebe4b7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301726"
---
# <a name="how-to-find-a-list-of-child-elements-xpath-linq-to-xml-c"></a>Jak znaleźć listę elementów podrzędnych (XPath-LINQ to XML) (C#)
W tym temacie porównano oś elementów podrzędnych XPath z [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> osią.  
  
 Wyrażenie XPath:`./*`  
  
## <a name="example"></a>Przykład  
 Ten przykład umożliwia znalezienie wszystkich elementów podrzędnych `Address` elementu.  
  
 W tym przykładzie zastosowano następujący dokument XML: [przykładowy plik XML: wiele zamówień zakupu (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```csharp  
XDocument cpo = XDocument.Load("PurchaseOrders.xml");  
XElement po = cpo.Root.Element("PurchaseOrder").Element("Address");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Elements();  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("./*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```output  
Results are identical  
<Name>Ellen Adams</Name>  
<Street>123 Maple Street</Street>  
<City>Mill Valley</City>  
<State>CA</State>  
<Zip>10999</Zip>  
<Country>USA</Country>  
```  
