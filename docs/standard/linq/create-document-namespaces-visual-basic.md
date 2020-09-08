---
title: Jak utworzyć dokument z przestrzeniami nazw w Visual Basic-LINQ to XML
description: Użyj literałów XML w Visual Basic, aby utworzyć dokumenty, które mają domyślne przestrzenie nazw lub przestrzenie nazw z prefiksem.
ms.date: 07/20/2015
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
ms.openlocfilehash: 48e2a1abf8f7a82df3db5cb2f580804d67776b15
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553507"
---
# <a name="how-to-create-a-document-with-namespaces-in-visual-basic-linq-to-xml"></a><span data-ttu-id="b52bc-103">Jak utworzyć dokument z przestrzeniami nazw w Visual Basic (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="b52bc-103">How to create a document with namespaces in Visual Basic (LINQ to XML)</span></span>

<span data-ttu-id="b52bc-104">W tym artykule przedstawiono sposób tworzenia dokumentu z przestrzeniami nazw w Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b52bc-104">This article shows how to create a document with namespaces in Visual Basic.</span></span>

<span data-ttu-id="b52bc-105">W przypadku używania literałów XML w Visual Basic użytkownicy mogą definiować jedną globalną domyślną przestrzeń nazw XML.</span><span class="sxs-lookup"><span data-stu-id="b52bc-105">When using XML literals in Visual Basic, users can define one global default XML namespace.</span></span> <span data-ttu-id="b52bc-106">Ta przestrzeń nazw jest domyślną przestrzenią nazw dla literałów XML i właściwości XML.</span><span class="sxs-lookup"><span data-stu-id="b52bc-106">This namespace is the default namespace for both XML literals and XML properties.</span></span> <span data-ttu-id="b52bc-107">Domyślną przestrzeń nazw XML można zdefiniować na poziomie projektu lub na poziomie pliku.</span><span class="sxs-lookup"><span data-stu-id="b52bc-107">The default XML namespace can be defined at either the project level or the file level.</span></span> <span data-ttu-id="b52bc-108">Jeśli jest on zdefiniowany na poziomie pliku, zastępuje domyślny obszar nazw na poziomie projektu.</span><span class="sxs-lookup"><span data-stu-id="b52bc-108">If it's defined at the file level, it overrides the default namespace at the project level.</span></span>

<span data-ttu-id="b52bc-109">Można również zdefiniować inne przestrzenie nazw i określić prefiksy przestrzeni nazw dla tych przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b52bc-109">You can also define other namespaces, and specify the namespace prefixes for those namespaces.</span></span> <span data-ttu-id="b52bc-110">Użyj `Imports` słowa kluczowego, aby zdefiniować oba typy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b52bc-110">You use the `Imports` keyword to define both types of namespace.</span></span>

<span data-ttu-id="b52bc-111">Aby uzyskać więcej informacji, zobacz [literały XML w Visual Basic](xml-literals.md).</span><span class="sxs-lookup"><span data-stu-id="b52bc-111">For more information, see [XML literals in Visual Basic](xml-literals.md).</span></span>

<span data-ttu-id="b52bc-112">Należy zauważyć, że domyślna przestrzeń nazw XML dotyczy tylko elementów i nie do atrybutów.</span><span class="sxs-lookup"><span data-stu-id="b52bc-112">Note that the default XML namespace only applies to elements and not to attributes.</span></span> <span data-ttu-id="b52bc-113">Atrybuty są domyślnie w domyślnym obszarze nazw.</span><span class="sxs-lookup"><span data-stu-id="b52bc-113">Attributes are by default in the default namespace.</span></span> <span data-ttu-id="b52bc-114">Można jednak użyć prefiksu przestrzeni nazw, aby umieścić atrybut w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b52bc-114">However, you can use a namespace prefix to put an attribute in a namespace.</span></span>

## <a name="example-create-a-document-that-has-a-namespace"></a><span data-ttu-id="b52bc-115">Przykład: Tworzenie dokumentu, który ma przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="b52bc-115">Example: Create a document that has a namespace</span></span>

<span data-ttu-id="b52bc-116">Ten przykład tworzy dokument zawierający przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="b52bc-116">This example creates a document that contains a namespace.</span></span>

```vb
Imports <xmlns:aw="http://www.adventure-works.com">
Module Module1
    Sub Main()
        Dim root As XElement = _
            <aw:Root>
                <aw:Child aw:Att="attvalue"/>
            </aw:Root>
        Console.WriteLine(root)
    End Sub
End Module
```

<span data-ttu-id="b52bc-117">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="b52bc-117">This example produces the following output:</span></span>

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Child aw:Att="attvalue" />
</aw:Root>
```

## <a name="example-create-a-document-that-has-two-namespaces-one-with-a-prefix"></a><span data-ttu-id="b52bc-118">Przykład: Utwórz dokument zawierający dwie przestrzenie nazw, jeden z prefiksem</span><span class="sxs-lookup"><span data-stu-id="b52bc-118">Example: Create a document that has two namespaces, one with a prefix</span></span>

<span data-ttu-id="b52bc-119">Ten przykład tworzy dokument zawierający dwie przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="b52bc-119">This example creates a document that contains two namespaces.</span></span> <span data-ttu-id="b52bc-120">Jedna jest domyślną przestrzenią nazw, druga ma prefiks.</span><span class="sxs-lookup"><span data-stu-id="b52bc-120">One is the default namespace, the other has a prefix.</span></span>

```vb
Imports <xmlns="http://www.adventure-works.com">
Imports <xmlns:fc="www.fourthcoffee.com">

Module Module1

    Sub Main()
        Dim root As XElement = _
            <Root>
                <Child Att="attvalue"/>
                <fc:Child2>child2 content</fc:Child2>
            </Root>
        Console.WriteLine(root)
    End Sub

End Module
```

<span data-ttu-id="b52bc-121">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="b52bc-121">This example produces the following output:</span></span>

```xml
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">
  <Child Att="attvalue" />
  <fc:Child2>child2 content</fc:Child2>
</Root>
```

## <a name="example-create-a-document-that-has-two-namespaces-both-with-prefixes"></a><span data-ttu-id="b52bc-122">Przykład: Utwórz dokument, który ma dwie przestrzenie nazw, zarówno z prefiksami</span><span class="sxs-lookup"><span data-stu-id="b52bc-122">Example: Create a document that has two namespaces, both with prefixes</span></span>

<span data-ttu-id="b52bc-123">Poniższy przykład tworzy dokument zawierający dwie przestrzenie nazw, które mają prefiksy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b52bc-123">The following example creates a document that contains two namespaces, both having namespace prefixes.</span></span>

<span data-ttu-id="b52bc-124">Podczas serializowania drzewa XML LINQ to XML emituje deklaracje przestrzeni nazw zgodnie z wymaganiami, aby każdy element był w wyznaczeniu przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b52bc-124">When serializing an XML tree, LINQ to XML emits namespace declarations as required so that each element is in its designated namespace.</span></span>

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

End Module
```

<span data-ttu-id="b52bc-125">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="b52bc-125">This example produces the following output:</span></span>

```xml
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">
  <fc:Child>
    <aw:DifferentChild>other content</aw:DifferentChild>
  </fc:Child>
  <aw:Child2>c2 content</aw:Child2>
  <fc:Child3>c3 content</fc:Child3>
</aw:Root>
```

## <a name="see-also"></a><span data-ttu-id="b52bc-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b52bc-126">See also</span></span>

- [<span data-ttu-id="b52bc-127">Przegląd przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="b52bc-127">Namespaces overview</span></span>](namespaces-overview.md)
