---
title: Jak utworzyć dokument z przestrzeniami nazw w języku C# — LINQ to XML
description: Użyj obiektu XNamespace w języku C#, aby utworzyć dokumenty, które mają domyślne przestrzenie nazw lub przestrzenie nazw z prefiksem.
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 3ec9624bcc599a73a6872e5c4c79504a1a4b4380
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553520"
---
# <a name="how-to-create-a-document-with-namespaces-in-c-linq-to-xml"></a><span data-ttu-id="19af1-103">Jak utworzyć dokument z przestrzeniami nazw w języku C# (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="19af1-103">How to create a document with namespaces in C# (LINQ to XML)</span></span>

<span data-ttu-id="19af1-104">W tym artykule pokazano, jak tworzyć dokumenty w języku C#, które mają przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-104">This article shows how to create documents in C# that have namespaces.</span></span>

## <a name="example-declare-and-initialize-a-default-namespace"></a><span data-ttu-id="19af1-105">Przykład: Zadeklaruj i zainicjuj domyślną przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="19af1-105">Example: Declare and initialize a default namespace</span></span>

<span data-ttu-id="19af1-106">Aby utworzyć element lub atrybut, który znajduje się w przestrzeni nazw, należy najpierw zadeklarować i zainicjować <xref:System.Xml.Linq.XNamespace> obiekt.</span><span class="sxs-lookup"><span data-stu-id="19af1-106">To create an element or an attribute that's in a namespace, you first declare and initialize an <xref:System.Xml.Linq.XNamespace> object.</span></span> <span data-ttu-id="19af1-107">Następnie należy użyć przeciążenia operatora dodawania, aby połączyć przestrzeń nazw z nazwą lokalną wyrażoną jako ciąg.</span><span class="sxs-lookup"><span data-stu-id="19af1-107">You then use the addition operator overload to combine the namespace with the local name, expressed as a string.</span></span>

<span data-ttu-id="19af1-108">Poniższy przykład tworzy dokument z jedną przestrzenią nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-108">The following example creates a document with one namespace.</span></span> <span data-ttu-id="19af1-109">Domyślnie LINQ to XML serializować tego dokumentu przy użyciu domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-109">By default, LINQ to XML serializes this document with a default namespace.</span></span>

```csharp
// Create an XML tree in a namespace.
XNamespace aw = "http://www.adventure-works.com";
XElement root = new XElement(aw + "Root",
    new XElement(aw + "Child", "child content")
);
Console.WriteLine(root);
```

<span data-ttu-id="19af1-110">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="19af1-110">This example produces the following output:</span></span>

```xml
<Root xmlns="http://www.adventure-works.com">
  <Child>child content</Child>
</Root>
```

## <a name="example-create-a-document-that-has-a-namespace-and-an-attribute"></a><span data-ttu-id="19af1-111">Przykład: Utwórz dokument z przestrzenią nazw i atrybutem</span><span class="sxs-lookup"><span data-stu-id="19af1-111">Example: Create a document that has a namespace and an attribute</span></span>

<span data-ttu-id="19af1-112">Poniższy przykład tworzy dokument z jedną przestrzenią nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-112">The following example creates a document with one namespace.</span></span> <span data-ttu-id="19af1-113">Tworzy również atrybut, który deklaruje przestrzeń nazw z prefiksem przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-113">It also creates an attribute that declares the namespace with a namespace prefix.</span></span> <span data-ttu-id="19af1-114">Aby utworzyć atrybut, który deklaruje przestrzeń nazw z prefiksem, utworzysz atrybut, w którym nazwa atrybutu jest prefiksem przestrzeni nazw, a ta nazwa znajduje się w <xref:System.Xml.Linq.XNamespace.Xmlns%2A> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-114">To create an attribute that declares a namespace with a prefix, you create an attribute where the name of the attribute is the namespace prefix, and this name is in the <xref:System.Xml.Linq.XNamespace.Xmlns%2A> namespace.</span></span> <span data-ttu-id="19af1-115">Wartość tego atrybutu jest identyfikatorem URI przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-115">The value of this attribute is the URI of the namespace.</span></span>

```csharp
// Create an XML tree in a namespace, with a specified prefix
XNamespace aw = "http://www.adventure-works.com";
XElement root = new XElement(aw + "Root",
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),
    new XElement(aw + "Child", "child content")
);
Console.WriteLine(root);
```

<span data-ttu-id="19af1-116">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="19af1-116">This example produces the following output:</span></span>

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Child>child content</aw:Child>
</aw:Root>
```

## <a name="example-create-a-document-that-has-two-namespaces-one-with-a-prefix"></a><span data-ttu-id="19af1-117">Przykład: Utwórz dokument zawierający dwie przestrzenie nazw, jeden z prefiksem</span><span class="sxs-lookup"><span data-stu-id="19af1-117">Example: Create a document that has two namespaces, one with a prefix</span></span>

<span data-ttu-id="19af1-118">Poniższy przykład pokazuje, jak utworzyć dokument zawierający dwie przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-118">The following example shows the creation of a document that contains two namespaces.</span></span> <span data-ttu-id="19af1-119">Jedną z nich jest domyślna przestrzeń nazw, druga jest przestrzenią nazw z prefiksem.</span><span class="sxs-lookup"><span data-stu-id="19af1-119">One is the default namespace, the other is a namespace with a prefix.</span></span>

<span data-ttu-id="19af1-120">Uwzględniając atrybuty przestrzeni nazw w elemencie głównym, przestrzenie nazw są serializowane, więc `http://www.adventure-works.com` jest to domyślna przestrzeń nazw i `www.fourthcoffee.com` jest serializowany z prefiksem `fc` .</span><span class="sxs-lookup"><span data-stu-id="19af1-120">By including namespace attributes in the root element, the namespaces are serialized so that `http://www.adventure-works.com` is the default namespace, and `www.fourthcoffee.com` is serialized with a prefix of `fc`.</span></span> <span data-ttu-id="19af1-121">Aby utworzyć atrybut, który deklaruje domyślną przestrzeń nazw, należy utworzyć atrybut o nazwie `xmlns` bez przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-121">To create an attribute that declares a default namespace, you create an attribute with the name `xmlns`, without a namespace.</span></span> <span data-ttu-id="19af1-122">Wartość atrybutu jest domyślnym identyfikatorem URI przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-122">The value of the attribute is the default namespace URI.</span></span>

```csharp
// The http://www.adventure-works.com namespace is forced to be the default namespace.
XNamespace aw = "http://www.adventure-works.com";
XNamespace fc = "www.fourthcoffee.com";
XElement root = new XElement(aw + "Root",
    new XAttribute("xmlns", "http://www.adventure-works.com"),
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),
    new XElement(fc + "Child",
        new XElement(aw + "DifferentChild", "other content")
    ),
    new XElement(aw + "Child2", "c2 content"),
    new XElement(fc + "Child3", "c3 content")
);
Console.WriteLine(root);
```

<span data-ttu-id="19af1-123">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="19af1-123">This example produces the following output:</span></span>

```xml
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">
  <fc:Child>
    <DifferentChild>other content</DifferentChild>
  </fc:Child>
  <Child2>c2 content</Child2>
  <fc:Child3>c3 content</fc:Child3>
</Root>
```

## <a name="example-create-a-document-that-has-two-namespaces-both-with-prefixes"></a><span data-ttu-id="19af1-124">Przykład: Utwórz dokument, który ma dwie przestrzenie nazw, zarówno z prefiksami</span><span class="sxs-lookup"><span data-stu-id="19af1-124">Example: Create a document that has two namespaces, both with prefixes</span></span>

<span data-ttu-id="19af1-125">Poniższy przykład tworzy dokument zawierający dwie przestrzenie nazw, zarówno z prefiksami przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="19af1-125">The following example creates a document that contains two namespaces, both with namespace prefixes.</span></span>

```csharp
XNamespace aw = "http://www.adventure-works.com";
XNamespace fc = "www.fourthcoffee.com";
XElement root = new XElement(aw + "Root",
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),
    new XElement(fc + "Child",
        new XElement(aw + "DifferentChild", "other content")
    ),
    new XElement(aw + "Child2", "c2 content"),
    new XElement(fc + "Child3", "c3 content")
);
Console.WriteLine(root);
```

<span data-ttu-id="19af1-126">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="19af1-126">This example produces the following output:</span></span>

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">
  <fc:Child>
    <aw:DifferentChild>other content</aw:DifferentChild>
  </fc:Child>
  <aw:Child2>c2 content</aw:Child2>
  <fc:Child3>c3 content</fc:Child3>
</aw:Root>
```

## <a name="example-create-a-namespace-using-expanded-names"></a><span data-ttu-id="19af1-127">Przykład: tworzenie przestrzeni nazw przy użyciu rozwiniętych nazw</span><span class="sxs-lookup"><span data-stu-id="19af1-127">Example: Create a namespace using expanded names</span></span>

<span data-ttu-id="19af1-128">Innym sposobem osiągnięcia tego samego wyniku jest użycie rozwiniętych nazw zamiast deklarowania i tworzenia <xref:System.Xml.Linq.XNamespace> obiektu.</span><span class="sxs-lookup"><span data-stu-id="19af1-128">Another way to accomplish the same result is to use expanded names instead of declaring and creating an <xref:System.Xml.Linq.XNamespace> object.</span></span>

<span data-ttu-id="19af1-129">Takie podejście ma wpływ na wydajność.</span><span class="sxs-lookup"><span data-stu-id="19af1-129">This approach has performance implications.</span></span> <span data-ttu-id="19af1-130">Za każdym razem, gdy przekazujesz ciąg zawierający rozwiniętą nazwę do LINQ to XML, LINQ to XML musi przeanalizować nazwę, znaleźć wykorzystaną przestrzeń nazw i znaleźć nazwę atomową.</span><span class="sxs-lookup"><span data-stu-id="19af1-130">Each time you pass a string that contains an expanded name to LINQ to XML, LINQ to XML must parse the name, find the atomized namespace, and find the atomized name.</span></span> <span data-ttu-id="19af1-131">Ten proces pobiera czas procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="19af1-131">This process takes CPU time.</span></span> <span data-ttu-id="19af1-132">Jeśli wydajność jest ważna, warto zadeklarować obiekt i używać go <xref:System.Xml.Linq.XNamespace> jawnie.</span><span class="sxs-lookup"><span data-stu-id="19af1-132">If performance is important, you might want to declare and use an <xref:System.Xml.Linq.XNamespace> object explicitly.</span></span>

<span data-ttu-id="19af1-133">Jeśli wydajność jest ważnym problemem, zobacz [pre-rozproszenie of XName Objects](pre-atomization-xname-objects.md) , aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="19af1-133">If performance is an important issue, see [Pre-Atomization of XName Objects](pre-atomization-xname-objects.md) for more information.</span></span>

```csharp
// Create an XML tree in a namespace, with a specified prefix
XElement root = new XElement("{http://www.adventure-works.com}Root",
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),
    new XElement("{http://www.adventure-works.com}Child", "child content")
);
Console.WriteLine(root);
```

<span data-ttu-id="19af1-134">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="19af1-134">This example produces the following output:</span></span>

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Child>child content</aw:Child>
</aw:Root>
```

## <a name="see-also"></a><span data-ttu-id="19af1-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="19af1-135">See also</span></span>

- [<span data-ttu-id="19af1-136">Przegląd przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="19af1-136">Namespaces overview</span></span>](namespaces-overview.md)
