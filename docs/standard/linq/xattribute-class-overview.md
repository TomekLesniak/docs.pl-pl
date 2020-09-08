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
# <a name="xattribute-class-overview"></a><span data-ttu-id="e7ba3-104">XAttribute, Klasa — Omówienie</span><span class="sxs-lookup"><span data-stu-id="e7ba3-104">XAttribute class overview</span></span>

<span data-ttu-id="e7ba3-105">Atrybuty są parami nazwa-wartość, które są skojarzone z elementem.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-105">Attributes are name-value pairs that are associated with an element.</span></span> <span data-ttu-id="e7ba3-106"><xref:System.Xml.Linq.XAttribute>Klasa reprezentuje atrybuty XML.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-106">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>

<span data-ttu-id="e7ba3-107">Praca z atrybutami w LINQ to XML jest podobna do pracy z elementami.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-107">Working with attributes in LINQ to XML is similar to working with elements.</span></span> <span data-ttu-id="e7ba3-108">Ich konstruktory są podobne.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-108">Their constructors are similar.</span></span> <span data-ttu-id="e7ba3-109">Metody używane do pobierania kolekcji są podobne.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-109">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="e7ba3-110">Wyrażenie zapytania LINQ dla kolekcji atrybutów wygląda podobnie do wyrażenia zapytania LINQ dla kolekcji elementów.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-110">A LINQ query expression for a collection of attributes looks similar to a LINQ query expression for a collection of elements.</span></span>

<span data-ttu-id="e7ba3-111">Kolejność, w jakiej atrybuty zostały dodane do elementu, jest zachowywana.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-111">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="e7ba3-112">Oznacza to, że podczas iteracji przez atrybuty są one widoczne w takiej samej kolejności, w jakiej zostały dodane.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-112">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>

## <a name="the-xattribute-constructor"></a><span data-ttu-id="e7ba3-113">Konstruktor XAttribute</span><span class="sxs-lookup"><span data-stu-id="e7ba3-113">The XAttribute constructor</span></span>

<span data-ttu-id="e7ba3-114">Następujący Konstruktor <xref:System.Xml.Linq.XAttribute> klasy jest tym, którego najczęściej używasz:</span><span class="sxs-lookup"><span data-stu-id="e7ba3-114">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you'll most commonly use:</span></span>

|<span data-ttu-id="e7ba3-115">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="e7ba3-115">Constructor</span></span>|<span data-ttu-id="e7ba3-116">Opis</span><span class="sxs-lookup"><span data-stu-id="e7ba3-116">Description</span></span>|
|-----------------|-----------------|
|`XAttribute(XName name, object content)`|<span data-ttu-id="e7ba3-117">Tworzy obiekt <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-117">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="e7ba3-118">`name`Argument określa nazwę atrybutu; `content` określa zawartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-118">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|

## <a name="example-create-an-element-with-an-attribute"></a><span data-ttu-id="e7ba3-119">Przykład: Utwórz element z atrybutem</span><span class="sxs-lookup"><span data-stu-id="e7ba3-119">Example: Create an element with an attribute</span></span>

<span data-ttu-id="e7ba3-120">Poniższy przykład przedstawia typowe zadanie tworzenia elementu, który zawiera atrybut.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-120">The following example shows the common task of creating an element that contains an attribute.</span></span>

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

<span data-ttu-id="e7ba3-121">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="e7ba3-121">This example produces the following output:</span></span>

```xml
<Phone Type="Home">555-555-5555</Phone>
```

## <a name="example-functional-construction-of-attributes"></a><span data-ttu-id="e7ba3-122">Przykład: funkcjonalne konstruowanie atrybutów</span><span class="sxs-lookup"><span data-stu-id="e7ba3-122">Example: Functional construction of attributes</span></span>

<span data-ttu-id="e7ba3-123">Można tworzyć <xref:System.Xml.Linq.XAttribute> obiekty w wierszu z konstrukcją <xref:System.Xml.Linq.XElement> obiektów, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="e7ba3-123">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as shown in the following example:</span></span>

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

<span data-ttu-id="e7ba3-124">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="e7ba3-124">This example produces the following output:</span></span>

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

## <a name="attributes-arent-nodes"></a><span data-ttu-id="e7ba3-125">Atrybuty nie są węzłami</span><span class="sxs-lookup"><span data-stu-id="e7ba3-125">Attributes aren't nodes</span></span>

<span data-ttu-id="e7ba3-126">Istnieją pewne różnice między atrybutami i elementami.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-126">There are some differences between attributes and elements.</span></span> <span data-ttu-id="e7ba3-127"><xref:System.Xml.Linq.XAttribute> obiekty nie są węzłami w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-127"><xref:System.Xml.Linq.XAttribute> objects aren't nodes in the XML tree.</span></span> <span data-ttu-id="e7ba3-128">Są to pary nazwa-wartość skojarzone z elementem XML.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-128">They're name-value pairs associated with an XML element.</span></span> <span data-ttu-id="e7ba3-129">W przeciwieństwie do Document Object Model (DOM), to dokładniej odzwierciedla strukturę XML.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-129">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="e7ba3-130">Chociaż <xref:System.Xml.Linq.XAttribute> obiekty nie są w rzeczywistości węzłami w drzewie XML, praca z <xref:System.Xml.Linq.XAttribute> obiektami jest podobna do pracy z <xref:System.Xml.Linq.XElement> obiektami.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-130">Although <xref:System.Xml.Linq.XAttribute> objects aren't actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>

<span data-ttu-id="e7ba3-131">Ta różnica jest głównie ważna tylko dla deweloperów, którzy piszą kod, który współpracuje z drzewami XML na poziomie węzła.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-131">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="e7ba3-132">Wielu deweloperów nie będą zainteresowani tym rozróżnieniem.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-132">Many developers won't be concerned with this distinction.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7ba3-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e7ba3-133">See also</span></span>

- [<span data-ttu-id="e7ba3-134">Przegląd LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="e7ba3-134">LINQ to XML overview</span></span>](linq-xml-overview.md)
