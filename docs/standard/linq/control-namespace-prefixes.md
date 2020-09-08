---
title: Jak kontrolować prefiksy przestrzeni nazw — LINQ to XML
description: Prefiksy przestrzeni nazw można kontrolować podczas serializowania drzewa XML w C# i Visual Basic. W tym celu należy wstawić atrybuty, które deklarują przestrzenie nazw.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: 07efc23c11cd0dc0d281968911cf24d6ecbc76a2
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553020"
---
# <a name="how-to-control-namespace-prefixes-linq-to-xml"></a><span data-ttu-id="643d2-104">Sposób kontrolowania prefiksów przestrzeni nazw (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="643d2-104">How to control namespace prefixes (LINQ to XML)</span></span>

<span data-ttu-id="643d2-105">W tym artykule opisano sposób kontrolowania prefiksów przestrzeni nazw podczas serializowania drzewa XML w języku C# i Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="643d2-105">This article describes how to control namespace prefixes when serializing an XML tree in C# and Visual Basic.</span></span>

<span data-ttu-id="643d2-106">W wielu sytuacjach nie trzeba kontrolować prefiksów przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="643d2-106">In many situations, it's not necessary to control namespace prefixes.</span></span> <span data-ttu-id="643d2-107">Jednak niektóre narzędzia programowania XML wymagają tego.</span><span class="sxs-lookup"><span data-stu-id="643d2-107">However, certain XML programming tools require it.</span></span> <span data-ttu-id="643d2-108">Na przykład może to być manipulowanie arkuszem stylów XSLT lub dokumentem XAML zawierającym osadzone wyrażenia XPath odwołujące się do określonych prefiksów przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="643d2-108">For example, you might be manipulating an XSLT style sheet or a XAML document that contains embedded XPath expressions that refer to specific namespace prefixes.</span></span> <span data-ttu-id="643d2-109">W takim przypadku ważne jest, aby dokument był serializowany z tymi prefiksami.</span><span class="sxs-lookup"><span data-stu-id="643d2-109">In such a case, it's important that the document be serialized with those prefixes.</span></span> <span data-ttu-id="643d2-110">Jest to typowa przyczyna kontrolowania prefiksów przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="643d2-110">This is a common reason for controlling namespace prefixes.</span></span>

<span data-ttu-id="643d2-111">Kolejną przyczyną jest to, że użytkownicy będą mogli ręcznie edytować dokument XML i utworzyć prefiksy przestrzeni nazw, które są wygodne dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="643d2-111">Another reason is that you want users to edit the XML document manually, and you want to create namespace prefixes that are convenient for the user to type.</span></span> <span data-ttu-id="643d2-112">Na przykład może być generowany dokument XSD.</span><span class="sxs-lookup"><span data-stu-id="643d2-112">For example, you might be generating an XSD document.</span></span> <span data-ttu-id="643d2-113">Konwencje dla schematów sugerują użycie albo `xs` `xsd` jako prefiksu przestrzeni nazw schematu.</span><span class="sxs-lookup"><span data-stu-id="643d2-113">Conventions for schemas suggest that you use either `xs` or `xsd` as the prefix for the schema namespace.</span></span>

<span data-ttu-id="643d2-114">Aby kontrolować prefiksy przestrzeni nazw, należy wstawić atrybuty, które deklarują przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="643d2-114">To control namespace prefixes, you insert attributes that declare namespaces.</span></span> <span data-ttu-id="643d2-115">Jeśli zadeklarujesz przestrzenie nazw z określonymi prefiksami, LINQ to XML podejmie próbę zahonorowania prefiksów przestrzeni nazw podczas serializacji.</span><span class="sxs-lookup"><span data-stu-id="643d2-115">If you declare the namespaces with specific prefixes, LINQ to XML will attempt to honor the namespace prefixes when serializing.</span></span>

<span data-ttu-id="643d2-116">Aby utworzyć atrybut, który deklaruje przestrzeń nazw z prefiksem, utworzysz atrybut, w którym przestrzeń nazw atrybutu jest <xref:System.Xml.Linq.XNamespace.Xmlns%2A> , a nazwa atrybutu jest prefiksem przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="643d2-116">To create an attribute that declares a namespace with a prefix, you create an attribute where the namespace of the name of the attribute is <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, and the name of the attribute is the namespace prefix.</span></span> <span data-ttu-id="643d2-117">Wartość atrybutu jest identyfikatorem URI przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="643d2-117">The value of the attribute is the URI of the namespace.</span></span>

## <a name="example-create-two-namespaces-that-have-prefixes"></a><span data-ttu-id="643d2-118">Przykład: Utwórz dwie przestrzenie nazw, które mają prefiksy</span><span class="sxs-lookup"><span data-stu-id="643d2-118">Example: Create two namespaces that have prefixes</span></span>

<span data-ttu-id="643d2-119">Ten przykład deklaruje dwie przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="643d2-119">This example declares two namespaces.</span></span> <span data-ttu-id="643d2-120">Określa prefiks `aw` `http://www.adventure-works.com` przestrzeni nazw oraz prefiks `fc` `www.fourthcoffee.com` przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="643d2-120">It specifies the prefix `aw` for the `http://www.adventure-works.com` namespace, and the prefix `fc` for the `www.fourthcoffee.com` namespace.</span></span>

```csharp
XNamespace aw = "http://www.adventure-works.com";
XNamespace fc = "www.fourthcoffee.com";
XElement root = new XElement(aw + "Root",
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),
    new XElement(fc + "Child",
        new XElement(aw + "DifferentChild", "other content")
    ),
    new XElement(aw + "Child2", "c2 content"),
    new XElement(fc + "Child3", "c3 content")
);
Console.WriteLine(root);
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">
Imports <xmlns:fc="www.fourthcoffee.com">

Module Module1

    Sub Main()
        Dim root As XElement = _
            <aw:Root>
                <fc:Child>
                    <aw:DifferentChild>other content</aw:DifferentChild>
                </fc:Child>
                <aw:Child2>c2 content</aw:Child2>
                <fc:Child3>c3 content</fc:Child3>
            </aw:Root>
        Console.WriteLine(root)
    End Sub

This example produces the following output:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">
  <fc:Child>
    <aw:DifferentChild>other content</aw:DifferentChild>
  </fc:Child>
  <aw:Child2>c2 content</aw:Child2>
  <fc:Child3>c3 content</fc:Child3>
</aw:Root>
```

## <a name="see-also"></a><span data-ttu-id="643d2-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="643d2-121">See also</span></span>

- [<span data-ttu-id="643d2-122">Przegląd przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="643d2-122">Namespaces overview</span></span>](namespaces-overview.md)
