---
title: Jak znaleźć element podrzędny (XPath-LINQ to XML) (C#)
description: Dowiedz się, jak znaleźć element podrzędny przez porównanie osi elementu podrzędnego XPath z metodą LINQ to XML elementu.
ms.date: 07/20/2015
ms.assetid: 4fa6182d-6196-4ed1-9c9e-82949ff89c71
ms.openlocfilehash: 57d1a4e636e3443512020129a76cc2de7bb3f244
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301739"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="9448c-103">Jak znaleźć element podrzędny (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9448c-103">How to find a child element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="9448c-104">W tym temacie porównano oś elementu podrzędnego XPath z [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> metodą.</span><span class="sxs-lookup"><span data-stu-id="9448c-104">This topic compares the XPath child element axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  
  
 <span data-ttu-id="9448c-105">Wyrażenie XPath ma wartość `DeliveryNotes` .</span><span class="sxs-lookup"><span data-stu-id="9448c-105">The XPath expression is `DeliveryNotes`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9448c-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="9448c-106">Example</span></span>  
 <span data-ttu-id="9448c-107">Ten przykład umożliwia znalezienie elementu podrzędnego `DeliveryNotes` .</span><span class="sxs-lookup"><span data-stu-id="9448c-107">This example finds the child element `DeliveryNotes`.</span></span>  
  
 <span data-ttu-id="9448c-108">W tym przykładzie zastosowano następujący dokument XML: [przykładowy plik XML: wiele zamówień zakupu (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9448c-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("PurchaseOrders.xml");  
XElement po = cpo.Root.Element("PurchaseOrder");  
  
// LINQ to XML query  
XElement el1 = po.Element("DeliveryNotes");  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("DeliveryNotes");  
// same as "child::DeliveryNotes"  
// same as "./DeliveryNotes"  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 <span data-ttu-id="9448c-109">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="9448c-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  