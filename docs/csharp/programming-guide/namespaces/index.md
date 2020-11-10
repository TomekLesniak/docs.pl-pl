---
title: Przestrzenie nazw — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat przestrzeni nazw w programowaniu języka C#. Zobacz Omówienie właściwości przestrzeni nazw i Wyświetl dodatkowe zasoby.
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 41a666fd5f368e6990e08a36700e18f648939213
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440344"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="5948f-104">Przestrzenie nazw (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="5948f-104">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="5948f-105">Przestrzenie nazw są intensywnie używane w programowaniu języka C# na dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="5948f-105">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="5948f-106">Najpierw platforma .NET używa przestrzeni nazw do organizowania jej wielu klas w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="5948f-106">First, .NET uses namespaces to organize its many classes, as follows:</span></span>  

[!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]

<span data-ttu-id="5948f-107"><xref:System> jest przestrzenią nazw i <xref:System.Console> jest klasą w tej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="5948f-107"><xref:System> is a namespace and <xref:System.Console> is a class in that namespace.</span></span> <span data-ttu-id="5948f-108">`using`Można użyć słowa kluczowego, tak aby pełna nazwa nie była wymagana, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="5948f-108">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="5948f-109">Aby uzyskać więcej informacji, zobacz [dyrektywa using](../../language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="5948f-109">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>

<span data-ttu-id="5948f-110">Po drugie, zadeklarowanie własnych przestrzeni nazw może pomóc w kontroli zakresu nazw klas i metod w większych projektach programistycznych.</span><span class="sxs-lookup"><span data-stu-id="5948f-110">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="5948f-111">Użyj słowa kluczowego [Namespace](../../language-reference/keywords/namespace.md) , aby zadeklarować przestrzeń nazw, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="5948f-111">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>

[!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="5948f-112">Nazwa przestrzeni nazw musi być prawidłową [nazwą identyfikatora](../inside-a-program/identifier-names.md)języka C#.</span><span class="sxs-lookup"><span data-stu-id="5948f-112">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="5948f-113">Przestrzenie nazw — przegląd</span><span class="sxs-lookup"><span data-stu-id="5948f-113">Namespaces overview</span></span>

<span data-ttu-id="5948f-114">Przestrzenie nazw mają następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="5948f-114">Namespaces have the following properties:</span></span>

- <span data-ttu-id="5948f-115">Organizują one duże projekty kodu.</span><span class="sxs-lookup"><span data-stu-id="5948f-115">They organize large code projects.</span></span>
- <span data-ttu-id="5948f-116">Są one rozdzielane za pomocą `.` operatora.</span><span class="sxs-lookup"><span data-stu-id="5948f-116">They are delimited by using the `.` operator.</span></span>
- <span data-ttu-id="5948f-117">`using`Dyrektywa eliminuje konieczność określenia nazwy przestrzeni nazw dla każdej klasy.</span><span class="sxs-lookup"><span data-stu-id="5948f-117">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>
- <span data-ttu-id="5948f-118">`global`Przestrzeń nazw jest przestrzenią nazw "root": `global::System` zawsze odwołuje się do <xref:System> przestrzeni nazw platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="5948f-118">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5948f-119">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="5948f-119">C# language specification</span></span>

<span data-ttu-id="5948f-120">Aby uzyskać więcej informacji, zobacz sekcję [przestrzenie nazw](~/_csharplang/spec/namespaces.md) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5948f-120">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5948f-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5948f-121">See also</span></span>

- [<span data-ttu-id="5948f-122">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="5948f-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5948f-123">Używanie przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="5948f-123">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="5948f-124">Korzystanie z przestrzeni nazw typu My</span><span class="sxs-lookup"><span data-stu-id="5948f-124">How to use the My namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="5948f-125">Nazwy identyfikatorów</span><span class="sxs-lookup"><span data-stu-id="5948f-125">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="5948f-126">using — Dyrektywa</span><span class="sxs-lookup"><span data-stu-id="5948f-126">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="5948f-127">:: Operator</span><span class="sxs-lookup"><span data-stu-id="5948f-127">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
