---
title: XAttribute — przegląd klas (C#)
description: Atrybuty są parami nazw/wartości skojarzonych z elementem. XAttribute reprezentuje atrybuty XML. Dowiedz się więcej na temat pracy z atrybutami w LINQ to XML w języku C#.
ms.date: 07/20/2015
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
ms.openlocfilehash: 8a19de601041bbb20241c959e909483b97bcf797
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302233"
---
# <a name="xattribute-class-overview-c"></a><span data-ttu-id="65e8b-105">XAttribute — przegląd klas (C#)</span><span class="sxs-lookup"><span data-stu-id="65e8b-105">XAttribute Class Overview (C#)</span></span>
<span data-ttu-id="65e8b-106">Atrybuty są parami nazw/wartości, które są skojarzone z elementem.</span><span class="sxs-lookup"><span data-stu-id="65e8b-106">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="65e8b-107"><xref:System.Xml.Linq.XAttribute>Klasa reprezentuje atrybuty XML.</span><span class="sxs-lookup"><span data-stu-id="65e8b-107">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="65e8b-108">Omówienie</span><span class="sxs-lookup"><span data-stu-id="65e8b-108">Overview</span></span>  
 <span data-ttu-id="65e8b-109">Praca z atrybutami w [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] jest podobna do pracy z elementami.</span><span class="sxs-lookup"><span data-stu-id="65e8b-109">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="65e8b-110">Ich konstruktory są podobne.</span><span class="sxs-lookup"><span data-stu-id="65e8b-110">Their constructors are similar.</span></span> <span data-ttu-id="65e8b-111">Metody używane do pobierania kolekcji są podobne.</span><span class="sxs-lookup"><span data-stu-id="65e8b-111">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="65e8b-112">Wyrażenie zapytania LINQ dla kolekcji atrybutów wygląda bardzo podobnie do wyrażenia zapytania LINQ dla kolekcji elementów.</span><span class="sxs-lookup"><span data-stu-id="65e8b-112">A LINQ query expression for a collection of attributes looks very similar to a LINQ query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="65e8b-113">Kolejność, w jakiej atrybuty zostały dodane do elementu, jest zachowywana.</span><span class="sxs-lookup"><span data-stu-id="65e8b-113">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="65e8b-114">Oznacza to, że podczas iteracji przez atrybuty są one widoczne w takiej samej kolejności, w jakiej zostały dodane.</span><span class="sxs-lookup"><span data-stu-id="65e8b-114">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="65e8b-115">Konstruktor XAttribute</span><span class="sxs-lookup"><span data-stu-id="65e8b-115">The XAttribute Constructor</span></span>  
 <span data-ttu-id="65e8b-116">Następujący Konstruktor <xref:System.Xml.Linq.XAttribute> klasy jest najczęściej używanym:</span><span class="sxs-lookup"><span data-stu-id="65e8b-116">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="65e8b-117">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="65e8b-117">Constructor</span></span>|<span data-ttu-id="65e8b-118">Opis</span><span class="sxs-lookup"><span data-stu-id="65e8b-118">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="65e8b-119">Tworzy obiekt <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="65e8b-119">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="65e8b-120">`name`Argument określa nazwę atrybutu; `content` określa zawartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="65e8b-120">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="65e8b-121">Tworzenie elementu z atrybutem</span><span class="sxs-lookup"><span data-stu-id="65e8b-121">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="65e8b-122">Poniższy kod przedstawia typowe zadanie tworzenia elementu, który zawiera atrybut:</span><span class="sxs-lookup"><span data-stu-id="65e8b-122">The following code shows the common task of creating an element that contains an attribute:</span></span>  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 <span data-ttu-id="65e8b-123">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="65e8b-123">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="65e8b-124">Funkcjonalne konstruowanie atrybutów</span><span class="sxs-lookup"><span data-stu-id="65e8b-124">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="65e8b-125">Można tworzyć <xref:System.Xml.Linq.XAttribute> obiekty w wierszu z konstrukcją <xref:System.Xml.Linq.XElement> obiektów w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="65e8b-125">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
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
  
 <span data-ttu-id="65e8b-126">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="65e8b-126">This example produces the following output:</span></span>  
  
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
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="65e8b-127">Atrybuty nie są węzłami</span><span class="sxs-lookup"><span data-stu-id="65e8b-127">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="65e8b-128">Istnieją pewne różnice między atrybutami i elementami.</span><span class="sxs-lookup"><span data-stu-id="65e8b-128">There are some differences between attributes and elements.</span></span> <span data-ttu-id="65e8b-129"><xref:System.Xml.Linq.XAttribute>obiekty nie są węzłami w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="65e8b-129"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="65e8b-130">Są to pary nazw/wartości skojarzone z elementem XML.</span><span class="sxs-lookup"><span data-stu-id="65e8b-130">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="65e8b-131">W przeciwieństwie do Document Object Model (DOM), to dokładniej odzwierciedla strukturę XML.</span><span class="sxs-lookup"><span data-stu-id="65e8b-131">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="65e8b-132">Chociaż <xref:System.Xml.Linq.XAttribute> obiekty nie są w rzeczywistości węzłami w drzewie XML, praca z <xref:System.Xml.Linq.XAttribute> obiektami jest bardzo podobna do pracy z <xref:System.Xml.Linq.XElement> obiektami.</span><span class="sxs-lookup"><span data-stu-id="65e8b-132">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="65e8b-133">Ta różnica jest głównie ważna tylko dla deweloperów, którzy piszą kod, który współpracuje z drzewami XML na poziomie węzła.</span><span class="sxs-lookup"><span data-stu-id="65e8b-133">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="65e8b-134">Wielu deweloperów nie będą zainteresowani tym rozróżnieniem.</span><span class="sxs-lookup"><span data-stu-id="65e8b-134">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65e8b-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="65e8b-135">See also</span></span>

- [<span data-ttu-id="65e8b-136">Omówienie programowania LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="65e8b-136">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
