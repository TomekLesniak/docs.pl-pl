---
title: Konstrukcja funkcjonalna — LINQ to XML
description: LINQ to XML zapewnia konstrukcję funkcjonalną, która umożliwia tworzenie drzewa XML w pojedynczej instrukcji.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 57a82bcf-de03-4f1c-a0c8-9a76e989d542
ms.openlocfilehash: bcdc153d7f60cfb165dcb741d62b6af5c07a148a
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553098"
---
# <a name="functional-construction-linq-to-xml"></a><span data-ttu-id="29160-103">Konstrukcja funkcjonalna (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="29160-103">Functional construction (LINQ to XML)</span></span>

<span data-ttu-id="29160-104">LINQ to XML zapewnia zaawansowany sposób tworzenia elementów XML o nazwie *konstrukcja funkcjonalna*.</span><span class="sxs-lookup"><span data-stu-id="29160-104">LINQ to XML provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="29160-105">Konstrukcja funkcjonalna umożliwia utworzenie drzewa XML w pojedynczej instrukcji.</span><span class="sxs-lookup"><span data-stu-id="29160-105">Functional construction enables you to create an XML tree in a single statement.</span></span>

<span data-ttu-id="29160-106">Kilka najważniejszych funkcji interfejsu programowania LINQ to XML są używane w konstrukcji funkcjonalnej:</span><span class="sxs-lookup"><span data-stu-id="29160-106">Several key features of the LINQ to XML programming interface are used in functional construction:</span></span>

- <span data-ttu-id="29160-107"><xref:System.Xml.Linq.XElement>Konstruktor ma różne typy argumentów dla zawartości.</span><span class="sxs-lookup"><span data-stu-id="29160-107">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="29160-108">Na przykład można przekazać inny <xref:System.Xml.Linq.XElement> obiekt, który stanie się elementem podrzędnym.</span><span class="sxs-lookup"><span data-stu-id="29160-108">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="29160-109">Można przekazać <xref:System.Xml.Linq.XAttribute> obiekt, który stanie się atrybutem elementu.</span><span class="sxs-lookup"><span data-stu-id="29160-109">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="29160-110">Lub można przekazać każdy inny typ obiektu, który jest konwertowany na ciąg i stanie się zawartością tekstową elementu.</span><span class="sxs-lookup"><span data-stu-id="29160-110">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>
- <span data-ttu-id="29160-111"><xref:System.Xml.Linq.XElement>Konstruktor pobiera `params` tablicę typu <xref:System.Object> , dzięki czemu można przekazać dowolną liczbę obiektów do konstruktora.</span><span class="sxs-lookup"><span data-stu-id="29160-111">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="29160-112">Dzięki temu można utworzyć element, który ma złożoną zawartość.</span><span class="sxs-lookup"><span data-stu-id="29160-112">This enables you to create an element that has complex content.</span></span>
- <span data-ttu-id="29160-113">Jeśli obiekt implementuje <xref:System.Collections.Generic.IEnumerable%601> , kolekcja w obiekcie jest wyliczana i dodawane są wszystkie elementy w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="29160-113">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="29160-114">Jeśli kolekcja zawiera <xref:System.Xml.Linq.XElement> obiekty lub <xref:System.Xml.Linq.XAttribute> , każdy element w kolekcji zostanie dodany osobno.</span><span class="sxs-lookup"><span data-stu-id="29160-114">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="29160-115">Jest to ważne, ponieważ umożliwia przekazywanie wyników zapytania LINQ do konstruktora.</span><span class="sxs-lookup"><span data-stu-id="29160-115">This is important because it lets you pass the results of a LINQ query to the constructor.</span></span>

## <a name="example-create-an-xml-tree"></a><span data-ttu-id="29160-116">Przykład: Tworzenie drzewa XML</span><span class="sxs-lookup"><span data-stu-id="29160-116">Example: Create an XML tree</span></span>

<span data-ttu-id="29160-117">Można użyć konstrukcji funkcjonalnej, aby napisać kod w celu utworzenia drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="29160-117">You can use functional construction to write code to create an XML tree.</span></span> <span data-ttu-id="29160-118">Poniżej przedstawiono przykład:</span><span class="sxs-lookup"><span data-stu-id="29160-118">The following is an example:</span></span>

```csharp
XElement contacts =
    new XElement("Contacts",
        new XElement("Contact",
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),
            new XElement("Address",
                new XElement("Street1", "123 Main St"),
                new XElement("City", "Mercer Island"),
                new XElement("State", "WA"),
                new XElement("Postal", "68042")
            )
        )
    );
```

## <a name="example-create-an-xml-tree-using-linq-query-results"></a><span data-ttu-id="29160-119">Przykład: Tworzenie drzewa XML przy użyciu wyników zapytania LINQ</span><span class="sxs-lookup"><span data-stu-id="29160-119">Example: Create an XML tree using LINQ query results</span></span>

<span data-ttu-id="29160-120">Te funkcje umożliwiają również pisanie kodu, który używa wyników zapytań LINQ podczas tworzenia drzewa XML, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="29160-120">These features also enable you to write code that uses the results of LINQ queries when you create an XML tree, as in the following example:</span></span>

```csharp
XElement srcTree = new XElement("Root",
    new XElement("Element", 1),
    new XElement("Element", 2),
    new XElement("Element", 3),
    new XElement("Element", 4),
    new XElement("Element", 5)
);
XElement xmlTree = new XElement("Root",
    new XElement("Child", 1),
    new XElement("Child", 2),
    from el in srcTree.Elements()
    where (int)el > 2
    select el
);
Console.WriteLine(xmlTree);
```

<span data-ttu-id="29160-121">W Visual Basic ten sam element jest realizowany za pomocą literałów XML:</span><span class="sxs-lookup"><span data-stu-id="29160-121">In Visual Basic, the same thing is accomplished with XML literals:</span></span>

```vb
Dim srcTree As XElement = _
    <Root>
        <Element>1</Element>
        <Element>2</Element>
        <Element>3</Element>
        <Element>4</Element>
        <Element>5</Element>
    </Root>
Dim xmlTree As XElement = _
    <Root>
        <Child>1</Child>
        <Child>2</Child>
        <%= From el In srcTree.Elements() _
            Where CInt(el) > 2 _
            Select el %>
    </Root>
Console.WriteLine(xmlTree)
```

<span data-ttu-id="29160-122">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="29160-122">This example produces the following output:</span></span>

```xml
<Root>
  <Child>1</Child>
  <Child>2</Child>
  <Element>3</Element>
  <Element>4</Element>
  <Element>5</Element>
</Root>
```

## <a name="see-also"></a><span data-ttu-id="29160-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="29160-123">See also</span></span>

- [<span data-ttu-id="29160-124">Tworzenie drzew XML w języku C #</span><span class="sxs-lookup"><span data-stu-id="29160-124">Create XML Trees in C#</span></span>](create-xml-trees.md)
- [<span data-ttu-id="29160-125">Literały XML w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="29160-125">XML literals in Visual Basic</span></span>](xml-literals.md)
