---
title: Jak pisać zapytania ze złożonym filtrowaniem (C#)
description: Dowiedz się, jak pisać zapytania LINQ to XML przy użyciu złożonych filtrów. Zobacz przykłady kodu i wyświetlaj dodatkowe zasoby.
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 5d2c1aafc210b35d4d6b1f1b2d74b11966d90c80
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303429"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="04c60-104">Jak pisać zapytania ze złożonym filtrowaniem (C#)</span><span class="sxs-lookup"><span data-stu-id="04c60-104">How to write queries with complex filtering (C#)</span></span>
<span data-ttu-id="04c60-105">Czasami chcesz pisać zapytania LINQ to XML ze złożonymi filtrami.</span><span class="sxs-lookup"><span data-stu-id="04c60-105">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="04c60-106">Na przykład może być konieczne znalezienie wszystkich elementów, które mają element podrzędny o określonej nazwie i wartości.</span><span class="sxs-lookup"><span data-stu-id="04c60-106">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="04c60-107">Ten temat zawiera przykład tworzenia zapytania z skomplikowanym filtrowaniem.</span><span class="sxs-lookup"><span data-stu-id="04c60-107">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04c60-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="04c60-108">Example</span></span>  
 <span data-ttu-id="04c60-109">Ten przykład pokazuje, jak znaleźć wszystkie `PurchaseOrder` elementy, które mają `Address` element podrzędny, który ma `Type` atrybut równy "wysyłce" i `State` element podrzędny równy "NY".</span><span class="sxs-lookup"><span data-stu-id="04c60-109">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="04c60-110">Używa zapytania zagnieżdżonego w `Where` klauzuli i `Any` operator zwraca, `true` Jeśli kolekcja zawiera jakiekolwiek elementy.</span><span class="sxs-lookup"><span data-stu-id="04c60-110">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="04c60-111">Aby uzyskać informacje o używaniu składni zapytania opartej na metodzie, zobacz [składnia zapytań i składnia metod w LINQ](./query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="04c60-111">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="04c60-112">W tym przykładzie zastosowano następujący dokument XML: [przykładowy plik XML: wiele zamówień zakupu (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="04c60-112">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="04c60-113">Aby uzyskać więcej informacji na temat `Any` operatora, zobacz [Operacje kwantyfikatora (C#)](./quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="04c60-113">For more information about the `Any` operator, see [Quantifier Operations (C#)](./quantifier-operations.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="04c60-114">Ten kod spowoduje wygenerowanie następujących danych wyjściowych:</span><span class="sxs-lookup"><span data-stu-id="04c60-114">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="04c60-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="04c60-115">Example</span></span>  
 <span data-ttu-id="04c60-116">W poniższym przykładzie pokazano to samo zapytanie dla kodu XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="04c60-116">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="04c60-117">Aby uzyskać więcej informacji, zobacz temat [przestrzenie nazw — omówienie (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="04c60-117">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="04c60-118">W tym przykładzie zastosowano następujący dokument XML: [przykładowy plik XML: wiele zamówień zakupu w przestrzeni nazw](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="04c60-118">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="04c60-119">Ten kod spowoduje wygenerowanie następujących danych wyjściowych:</span><span class="sxs-lookup"><span data-stu-id="04c60-119">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="04c60-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="04c60-120">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="04c60-121">Operacje projekcji (C#)</span><span class="sxs-lookup"><span data-stu-id="04c60-121">Projection Operations (C#)</span></span>](./projection-operations.md)
- [<span data-ttu-id="04c60-122">Operacje kwantyfikatora (C#)</span><span class="sxs-lookup"><span data-stu-id="04c60-122">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)
