---
title: Obsługa par nazwa-wartość-LINQ to XML
description: Dowiedz się, jak używać metod LINQ to XML do obsługi zestawu par nazwa-wartość.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
ms.openlocfilehash: 681df91d42f8bdb403dcf6f735104301c4a0c9ba
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553280"
---
# <a name="maintain-name-value-pairs-linq-to-xml"></a><span data-ttu-id="5b97d-103">Obsługa par nazwa-wartość (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="5b97d-103">Maintain name-value pairs (LINQ to XML)</span></span>

<span data-ttu-id="5b97d-104">Wiele aplikacji musi utrzymywać informacje, które najlepiej są przechowywane jako pary nazwa-wartość.</span><span class="sxs-lookup"><span data-stu-id="5b97d-104">Many applications have to maintain information that is best kept as name-value pairs.</span></span> <span data-ttu-id="5b97d-105">Te informacje mogą dotyczyć informacji konfiguracyjnych lub ustawień globalnych.</span><span class="sxs-lookup"><span data-stu-id="5b97d-105">This information might be configuration information or global settings.</span></span> <span data-ttu-id="5b97d-106">LINQ to XML zawiera metody, które ułatwiają przechowywanie zestawu par nazwa-wartość.</span><span class="sxs-lookup"><span data-stu-id="5b97d-106">LINQ to XML contains methods that make it easy to maintain a set of name-value pairs.</span></span> <span data-ttu-id="5b97d-107">Możesz zachować informacje jako atrybuty lub jako zestaw elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="5b97d-107">You can either keep the information as attributes or as a set of child elements.</span></span>

<span data-ttu-id="5b97d-108">Jedną z różnic między przechowywaniem informacji jako atrybuty lub jako elementami podrzędnymi jest to, że atrybuty mogą mieć tylko jeden atrybut z określoną nazwą dla elementu.</span><span class="sxs-lookup"><span data-stu-id="5b97d-108">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="5b97d-109">To ograniczenie nie ma zastosowania do elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="5b97d-109">This limitation doesn't apply to child elements.</span></span>

## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="5b97d-110">SetAttributeValue i SetElementValue</span><span class="sxs-lookup"><span data-stu-id="5b97d-110">SetAttributeValue and SetElementValue</span></span>

<span data-ttu-id="5b97d-111">Dwie metody, które ułatwiają utrzymywanie par nazwa-wartość <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> i <xref:System.Xml.Linq.XElement.SetElementValue%2A> .</span><span class="sxs-lookup"><span data-stu-id="5b97d-111">The two methods that facilitate keeping name-value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="5b97d-112">Te dwie metody mają podobną semantykę.</span><span class="sxs-lookup"><span data-stu-id="5b97d-112">These two methods have similar semantics.</span></span>

<span data-ttu-id="5b97d-113"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> może dodawać, modyfikować i usuwać atrybuty elementu.</span><span class="sxs-lookup"><span data-stu-id="5b97d-113"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, and remove attributes of an element.</span></span>

- <span data-ttu-id="5b97d-114">W przypadku wywołania <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> z nazwą atrybutu, który nie istnieje, metoda tworzy nowy atrybut i dodaje go do określonego elementu.</span><span class="sxs-lookup"><span data-stu-id="5b97d-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that doesn't exist, the method creates a new attribute and adds it to the specified element.</span></span>
- <span data-ttu-id="5b97d-115">Jeśli wywołasz <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> nazwę istniejącego atrybutu i z określoną zawartością, zawartość atrybutu zostanie zastąpiona określoną zawartością.</span><span class="sxs-lookup"><span data-stu-id="5b97d-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>
- <span data-ttu-id="5b97d-116">Jeśli wywołasz <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> nazwę istniejącego atrybutu i określisz `null` dla zawartości, atrybut zostanie usunięty z jego elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="5b97d-116">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify `null` for the content, the attribute is removed from its parent.</span></span>

<span data-ttu-id="5b97d-117"><xref:System.Xml.Linq.XElement.SetElementValue%2A> może dodawać, modyfikować i usuwać elementy podrzędne elementu.</span><span class="sxs-lookup"><span data-stu-id="5b97d-117"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, and remove child elements of an element.</span></span>

- <span data-ttu-id="5b97d-118">W przypadku wywołania <xref:System.Xml.Linq.XElement.SetElementValue%2A> z nazwą elementu podrzędnego, który nie istnieje, metoda tworzy nowy element i dodaje go do określonego elementu.</span><span class="sxs-lookup"><span data-stu-id="5b97d-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that doesn't exist, the method creates a new element and adds it to the specified element.</span></span>
- <span data-ttu-id="5b97d-119">Jeśli wywołasz <xref:System.Xml.Linq.XElement.SetElementValue%2A> nazwę istniejącego elementu i z określoną zawartością, zawartość elementu zostanie zastąpiona określoną zawartością.</span><span class="sxs-lookup"><span data-stu-id="5b97d-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>
- <span data-ttu-id="5b97d-120">Jeśli wywołasz <xref:System.Xml.Linq.XElement.SetElementValue%2A> nazwę istniejącego elementu i określisz `null` dla zawartości, element zostanie usunięty z jego elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="5b97d-120">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify `null` for the content, the element is removed from its parent.</span></span>

## <a name="example-use-setattributevalue-to-create-and-maintain-a-list-of-name-value-pairs"></a><span data-ttu-id="5b97d-121">Przykład: Użyj, `SetAttributeValue` Aby utworzyć i zachować listę par nazwa-wartość</span><span class="sxs-lookup"><span data-stu-id="5b97d-121">Example: Use `SetAttributeValue` to create and maintain a list of name-value pairs</span></span>

<span data-ttu-id="5b97d-122">Poniższy przykład tworzy element bez atrybutów.</span><span class="sxs-lookup"><span data-stu-id="5b97d-122">The following example creates an element with no attributes.</span></span> <span data-ttu-id="5b97d-123">Następnie używa metody, <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> Aby utworzyć i zachować listę par nazwa-wartość.</span><span class="sxs-lookup"><span data-stu-id="5b97d-123">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name-value pairs.</span></span>

```csharp
// Create an element with no content.
XElement root = new XElement("Root");

// Add a number of name-value pairs as attributes.
root.SetAttributeValue("Top", 22);
root.SetAttributeValue("Left", 20);
root.SetAttributeValue("Bottom", 122);
root.SetAttributeValue("Right", 300);
root.SetAttributeValue("DefaultColor", "Color.Red");
Console.WriteLine(root);

// Replace the value of Top.
root.SetAttributeValue("Top", 10);
Console.WriteLine(root);

// Remove DefaultColor.
root.SetAttributeValue("DefaultColor", null);
Console.WriteLine(root);
```

```vb
' Create an element with no content.
Dim root As XElement = <Root/>

' Add a number of name-value pairs as attributes.
root.SetAttributeValue("Top", 22)
root.SetAttributeValue("Left", 20)
root.SetAttributeValue("Bottom", 122)
root.SetAttributeValue("Right", 300)
root.SetAttributeValue("DefaultColor", "Color.Red")
Console.WriteLine(root)

' Replace the value of Top.
root.SetAttributeValue("Top", 10)
Console.WriteLine(root)

' Remove DefaultColor.
root.SetAttributeValue("DefaultColor", Nothing)
Console.WriteLine(root)
```

<span data-ttu-id="5b97d-124">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="5b97d-124">This example produces the following output:</span></span>

```xml
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />
<Root Top="10" Left="20" Bottom="122" Right="300" />
```

## <a name="example-use-setelementvalue-to-create-and-maintain-a-list-of-name-value-pairs"></a><span data-ttu-id="5b97d-125">Przykład: Użyj, `SetElementValue` Aby utworzyć i zachować listę par nazwa-wartość</span><span class="sxs-lookup"><span data-stu-id="5b97d-125">Example: Use `SetElementValue` to create and maintain a list of name-value pairs</span></span>

<span data-ttu-id="5b97d-126">Poniższy przykład tworzy element bez elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="5b97d-126">The following example creates an element with no child elements.</span></span> <span data-ttu-id="5b97d-127">Następnie używa metody, <xref:System.Xml.Linq.XElement.SetElementValue%2A> Aby utworzyć i zachować listę par nazwa-wartość.</span><span class="sxs-lookup"><span data-stu-id="5b97d-127">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name-value pairs.</span></span>

```csharp
// Create an element with no content.
XElement root = new XElement("Root");

// Add a number of name-value pairs as elements.
root.SetElementValue("Top", 22);
root.SetElementValue("Left", 20);
root.SetElementValue("Bottom", 122);
root.SetElementValue("Right", 300);
root.SetElementValue("DefaultColor", "Color.Red");
Console.WriteLine(root);
Console.WriteLine("----");

// Replace the value of Top.
root.SetElementValue("Top", 10);
Console.WriteLine(root);
Console.WriteLine("----");

// Remove DefaultColor.
root.SetElementValue("DefaultColor", null);
Console.WriteLine(root);
```

```vb
' Create an element with no content.
Dim root As XElement = <Root/>

' Add a number of name-value pairs as elements.
root.SetElementValue("Top", 22)
root.SetElementValue("Left", 20)
root.SetElementValue("Bottom", 122)
root.SetElementValue("Right", 300)
root.SetElementValue("DefaultColor", "Color.Red")
Console.WriteLine(root)
Console.WriteLine("----")

' Replace the value of Top.
root.SetElementValue("Top", 10)
Console.WriteLine(root)
Console.WriteLine("----")

' Remove DefaultColor.
root.SetElementValue("DefaultColor", Nothing)
Console.WriteLine(root)
```

<span data-ttu-id="5b97d-128">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="5b97d-128">This example produces the following output:</span></span>

```xml
<Root>
  <Top>22</Top>
  <Left>20</Left>
  <Bottom>122</Bottom>
  <Right>300</Right>
  <DefaultColor>Color.Red</DefaultColor>
</Root>
----
<Root>
  <Top>10</Top>
  <Left>20</Left>
  <Bottom>122</Bottom>
  <Right>300</Right>
  <DefaultColor>Color.Red</DefaultColor>
</Root>
----
<Root>
  <Top>10</Top>
  <Left>20</Left>
  <Bottom>122</Bottom>
  <Right>300</Right>
</Root>
```

## <a name="see-also"></a><span data-ttu-id="5b97d-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5b97d-129">See also</span></span>

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
