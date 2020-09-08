---
title: Pracuj z globalnymi przestrzeniami nazw w Visual Basic-LINQ to XML
description: Należy zadeklarować przestrzeń nazw w Visual Basic z instrukcją Imports, niezależnie od tego, czy przestrzeń nazw jest domyślną przestrzenią nazw, czy ma prefiks. W tym artykule omówiono instrukcje importu i inne aspekty pracy z przestrzeniami nazw.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
ms.openlocfilehash: f05fcab6788388e36e2b68a2d4f022ea63e74280
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553822"
---
# <a name="work-with-global-namespaces-in-visual-basic-linq-to-xml"></a><span data-ttu-id="86bfe-104">Pracuj z globalnymi przestrzeniami nazw w Visual Basic (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="86bfe-104">Work with global namespaces in Visual Basic (LINQ to XML)</span></span>

<span data-ttu-id="86bfe-105">Jedną z najważniejszych funkcji literałów XML w Visual Basic jest możliwość deklarowania przestrzeni nazw XML przy użyciu `Imports` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="86bfe-105">One of the key features of XML literals in Visual Basic is the capability to declare XML namespaces by using the `Imports` statement.</span></span> <span data-ttu-id="86bfe-106">Korzystając z tej funkcji, można zadeklarować przestrzeń nazw XML, która używa prefiksu lub można zadeklarować domyślną przestrzeń nazw XML.</span><span class="sxs-lookup"><span data-stu-id="86bfe-106">Using this feature, you can declare an XML namespace that uses a prefix, or you can declare a default XML namespace.</span></span>

<span data-ttu-id="86bfe-107">Ta funkcja jest przydatna w dwóch sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="86bfe-107">This capability is useful in two situations:</span></span>

- <span data-ttu-id="86bfe-108">Przestrzenie nazw zadeklarowane w literałach XML nie są przenoszone do wyrażeń osadzonych.</span><span class="sxs-lookup"><span data-stu-id="86bfe-108">Namespaces declared in XML literals don't carry over into embedded expressions.</span></span> <span data-ttu-id="86bfe-109">Deklarowanie globalnych przestrzeni nazw zmniejsza ilość pracy wymaganej do korzystania z osadzonych wyrażeń z przestrzeniami nazw.</span><span class="sxs-lookup"><span data-stu-id="86bfe-109">Declaring global namespaces reduces the amount of work needed to use embedded expressions with namespaces.</span></span>
- <span data-ttu-id="86bfe-110">Aby używać przestrzeni nazw z właściwościami XML, należy zadeklarować globalne przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="86bfe-110">You must declare global namespaces in order to use namespaces with XML properties.</span></span>

<span data-ttu-id="86bfe-111">Można zadeklarować globalne przestrzenie nazw na poziomie projektu.</span><span class="sxs-lookup"><span data-stu-id="86bfe-111">You can declare global namespaces at the project level.</span></span> <span data-ttu-id="86bfe-112">Można również zadeklarować globalne przestrzenie nazw na poziomie modułu, który zastępuje globalne przestrzenie nazw na poziomie projektu.</span><span class="sxs-lookup"><span data-stu-id="86bfe-112">You can also declare global namespaces at the module level, which overrides the project-level global namespaces.</span></span> <span data-ttu-id="86bfe-113">Na koniec można przesłonić globalne przestrzenie nazw w literale XML.</span><span class="sxs-lookup"><span data-stu-id="86bfe-113">Finally, you can override global namespaces in an XML literal.</span></span>

<span data-ttu-id="86bfe-114">W przypadku używania literałów XML lub właściwości XML, które znajdują się w globalnie zadeklarowanych przestrzeniach nazw, można zobaczyć rozwinięte nazwy literałów XML lub właściwości przez umieszczenie ich w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="86bfe-114">When using XML literals or XML properties that are in globally declared namespaces, you can see the expanded name of XML literals or properties by hovering over them in Visual Studio.</span></span> <span data-ttu-id="86bfe-115">Rozwinięta nazwa zostanie wyświetlona w etykietce narzędzia.</span><span class="sxs-lookup"><span data-stu-id="86bfe-115">You will see the expanded name in a tooltip.</span></span>

<span data-ttu-id="86bfe-116">Można uzyskać <xref:System.Xml.Linq.XNamespace> obiekt, który odnosi się do globalnej przestrzeni nazw za pomocą `GetXmlNamespace` metody.</span><span class="sxs-lookup"><span data-stu-id="86bfe-116">You can get an <xref:System.Xml.Linq.XNamespace> object that corresponds to a global namespace using the `GetXmlNamespace` method.</span></span>

## <a name="example-use-imports-to-declare-a-global-namespace"></a><span data-ttu-id="86bfe-117">Przykład: Użyj `Imports` , aby zadeklarować globalną przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="86bfe-117">Example: Use `Imports` to declare a global namespace</span></span>

<span data-ttu-id="86bfe-118">Poniższy przykład deklaruje domyślną globalną przestrzeń nazw z `Imports` instrukcją, a następnie inicjuje <xref:System.Xml.Linq.XElement> obiekt w tej przestrzeni nazw za pomocą literału XML:</span><span class="sxs-lookup"><span data-stu-id="86bfe-118">The following example declares a default global namespace with the `Imports` statement, and then initializes an <xref:System.Xml.Linq.XElement> object in that namespace with an XML literal:</span></span>

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = <Root/>
        Console.WriteLine(root)
    End Sub
End Module
```

<span data-ttu-id="86bfe-119">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="86bfe-119">This example produces the following output:</span></span>

```xml
<Root xmlns="http://www.adventure-works.com" />
```

## <a name="example-declare-a-global-namespace-that-has-a-prefix"></a><span data-ttu-id="86bfe-120">Przykład: Zadeklaruj globalną przestrzeń nazw, która ma prefiks</span><span class="sxs-lookup"><span data-stu-id="86bfe-120">Example: Declare a global namespace that has a prefix</span></span>

<span data-ttu-id="86bfe-121">Następny przykład deklaruje globalną przestrzeń nazw z prefiksem i inicjuje element z literałem XML:</span><span class="sxs-lookup"><span data-stu-id="86bfe-121">The next example declares a global namespace with a prefix, and initializes an element with an XML literal:</span></span>

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = <aw:Root/>
        Console.WriteLine(root)
    End Sub
End Module
```

<span data-ttu-id="86bfe-122">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="86bfe-122">This example produces the following output:</span></span>

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com" />
```

## <a name="example-declare-a-default-namespace-and-use-an-embedded-expression-for-the-child-element"></a><span data-ttu-id="86bfe-123">Przykład: Zadeklaruj domyślną przestrzeń nazw i użyj wyrażenia osadzonego dla `Child` elementu</span><span class="sxs-lookup"><span data-stu-id="86bfe-123">Example: Declare a default namespace and use an embedded expression for the `Child` element</span></span>

<span data-ttu-id="86bfe-124">Przestrzenie nazw, które są zadeklarowane w literałach XML, nie są przenoszone do wyrażeń osadzonych.</span><span class="sxs-lookup"><span data-stu-id="86bfe-124">Namespaces that are declared in XML literals don't carry over into embedded expressions.</span></span> <span data-ttu-id="86bfe-125">Poniższy przykład deklaruje domyślną przestrzeń nazw, a następnie używa osadzonego wyrażenia dla `Child` elementu.</span><span class="sxs-lookup"><span data-stu-id="86bfe-125">The following example declares a default namespace, and then uses an embedded expression for the `Child` element.</span></span>

```vb
Dim root As XElement = _
    <Root xmlns="http://www.adventure-works.com">
        <%= <Child/> %>
    </Root>
Console.WriteLine(root)
```

<span data-ttu-id="86bfe-126">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="86bfe-126">This example produces the following output:</span></span>

```xml
<Root xmlns="http://www.adventure-works.com">
  <Child xmlns="" />
</Root>
```

<span data-ttu-id="86bfe-127">Otrzymany kod XML zawiera deklarację domyślnej przestrzeni nazw, dzięki czemu `Child` element nie jest w żadnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="86bfe-127">The resulting XML includes a declaration of a default namespace so that the `Child` element is in no namespace.</span></span>

<span data-ttu-id="86bfe-128">Można zadeklarować inną przestrzeń nazw w wyrażeniu osadzonym w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="86bfe-128">You could declare a different namespace in the embedded expression, as follows:</span></span>

```vb
Dim root As XElement = _
    <Root xmlns="http://www.adventure-works.com">
        <%= <Child xmlns="http://www.adventure-works.com"/> %>
    </Root>
Console.WriteLine(root)
```

<span data-ttu-id="86bfe-129">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="86bfe-129">This example produces the following output:</span></span>

```xml
<Root xmlns="http://www.adventure-works.com">
  <Child xmlns="http://www.adventure-works.com" />
</Root>
```

<span data-ttu-id="86bfe-130">Jednak przy użyciu globalnej domyślnej przestrzeni nazw można używać literałów XML bez deklarowania przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="86bfe-130">However, with the global default namespace you can use XML literals without declaring namespaces.</span></span> <span data-ttu-id="86bfe-131">Otrzymany kod XML będzie w globalnie zadeklarowanej przestrzeni nazw, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="86bfe-131">The resulting XML will be in the globally-declared default namespace, as in this example:</span></span>

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = <Root>
                                   <%= <Child/> %>
                               </Root>
        Console.WriteLine(root)
    End Sub
End Module
```

<span data-ttu-id="86bfe-132">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="86bfe-132">This example produces the following output:</span></span>

```xml
<Root xmlns="http://www.adventure-works.com">
  <Child />
</Root>
```

## <a name="example-use-namespaces-with-xml-properties"></a><span data-ttu-id="86bfe-133">Przykład: Użyj przestrzeni nazw z właściwościami XML</span><span class="sxs-lookup"><span data-stu-id="86bfe-133">Example: Use namespaces with XML properties</span></span>

<span data-ttu-id="86bfe-134">Jeśli pracujesz z drzewem XML, który znajduje się w przestrzeni nazw, i używasz właściwości XML, należy użyć globalnej przestrzeni nazw, aby właściwości XML również znajdować się w poprawnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="86bfe-134">If you're working with an XML tree that's in a namespace, and you use XML properties, then you must use a global namespace so that the XML properties will also be in the correct namespace.</span></span> <span data-ttu-id="86bfe-135">Poniższy przykład deklaruje drzewo XML w przestrzeni nazw, a następnie drukuje liczbę `Child` elementów.</span><span class="sxs-lookup"><span data-stu-id="86bfe-135">The following example declares an XML tree in a namespace, and then prints the count of `Child` elements.</span></span>

```vb
Dim root As XElement = _
    <Root xmlns="http://www.adventure-works.com">
        <Child>content</Child>
    </Root>
Console.WriteLine(root.<Child>.Count())
```

<span data-ttu-id="86bfe-136">Ten przykład wskazuje, że nie ma żadnych `Child` elementów.</span><span class="sxs-lookup"><span data-stu-id="86bfe-136">This example indicates that there are no `Child` elements.</span></span> <span data-ttu-id="86bfe-137">Wytwarza następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="86bfe-137">It produces this output:</span></span>

```output
0
```

<span data-ttu-id="86bfe-138">Jeśli jednak zostanie zadeklarowana Domyślna globalna przestrzeń nazw, wówczas zarówno literał XML, jak i Właściwość XML znajdują się w domyślnej globalnej przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="86bfe-138">If, however, you declare a default global namespace, then both the XML literal and the XML property are in the default global namespace:</span></span>

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root>
                <Child>content</Child>
            </Root>
        Console.WriteLine(root.<Child>.Count())
    End Sub
End Module
```

<span data-ttu-id="86bfe-139">Ten przykład wskazuje, że istnieje jeden `Child` element.</span><span class="sxs-lookup"><span data-stu-id="86bfe-139">This example indicates that there is one `Child` element.</span></span> <span data-ttu-id="86bfe-140">Wytwarza następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="86bfe-140">It produces this output:</span></span>

```output
1
```

<span data-ttu-id="86bfe-141">Jeśli zadeklarujesz globalną przestrzeń nazw, która ma prefiks, można użyć prefiksu dla obu literałów XML i właściwości XML:</span><span class="sxs-lookup"><span data-stu-id="86bfe-141">If you declare a global namespace that has a prefix, you can use the prefix for both XML literals and XML properties:</span></span>

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <aw:Root>
                <aw:Child>content</aw:Child>
            </aw:Root>
        Console.WriteLine(root.<aw:Child>.Count())
    End Sub
End Module
```

## <a name="example-use-getxmlnamespace-to-get-an-xnamespace"></a><span data-ttu-id="86bfe-142">Przykład: Użyj `GetXmlNamespace` , aby uzyskać `XNamespace`</span><span class="sxs-lookup"><span data-stu-id="86bfe-142">Example: Use `GetXmlNamespace` to get an `XNamespace`</span></span>

<span data-ttu-id="86bfe-143">Można uzyskać <xref:System.Xml.Linq.XNamespace> obiekt za pomocą `GetXmlNamespace` metody:</span><span class="sxs-lookup"><span data-stu-id="86bfe-143">You can obtain an <xref:System.Xml.Linq.XNamespace> object by using the `GetXmlNamespace` method:</span></span>

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = <aw:Root/>
        Dim xn As XNamespace = GetXmlNamespace(aw)
        Console.WriteLine(xn)
    End Sub
End Module
```

<span data-ttu-id="86bfe-144">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="86bfe-144">This example produces the following output:</span></span>

```output
http://www.adventure-works.com
```

## <a name="see-also"></a><span data-ttu-id="86bfe-145">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="86bfe-145">See also</span></span>

- [<span data-ttu-id="86bfe-146">Przegląd przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="86bfe-146">Namespaces overview</span></span>](namespaces-overview.md)
