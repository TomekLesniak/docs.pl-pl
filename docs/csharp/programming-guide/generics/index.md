---
title: Typy ogólne — Przewodnik programowania w języku C#
description: Dowiedz się więcej o typach ogólnych. Typy ogólne maksymalizują ponowne użycie kodu, bezpieczeństwo typów i wydajność oraz są często używane do tworzenia klas kolekcji.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: beef9c20e3ac62505bc7a4584b404637935de1dc
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299399"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="c9b05-104">Typy ogólne (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="c9b05-104">Generics (C# Programming Guide)</span></span>

<span data-ttu-id="c9b05-105">Typy ogólne wprowadzają koncepcję parametrów typu do platformy .NET, co pozwala na projektowanie klas i metod, które opóźniają specyfikację jednego lub więcej typów do momentu zadeklarowania klasy lub metody jako wystąpienia przez kod klienta.</span><span class="sxs-lookup"><span data-stu-id="c9b05-105">Generics introduce the concept of type parameters to .NET, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="c9b05-106">Na przykład przy użyciu parametru typu ogólnego można `T` napisać pojedynczą klasę, która może być używana przez inny kod klienta bez ponoszenia kosztów lub ryzyka rzutowania w czasie wykonywania lub operacji pakowania, jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="c9b05-106">For example, by using a generic type parameter `T`, you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>

[!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]

<span data-ttu-id="c9b05-107">Klasy generyczne i metody łączą użyteczność, bezpieczeństwo typów i wydajność w taki sposób, że ich nieogólnymi odpowiednikami nie jest.</span><span class="sxs-lookup"><span data-stu-id="c9b05-107">Generic classes and methods combine reusability, type safety, and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="c9b05-108">Typy ogólne są najczęściej używane z kolekcjami i metodami, które działają na nich.</span><span class="sxs-lookup"><span data-stu-id="c9b05-108">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="c9b05-109"><xref:System.Collections.Generic>Przestrzeń nazw zawiera kilka rodzajowych klas kolekcji.</span><span class="sxs-lookup"><span data-stu-id="c9b05-109">The <xref:System.Collections.Generic> namespace contains several generic-based collection classes.</span></span> <span data-ttu-id="c9b05-110">Kolekcje inne niż ogólne, takie jak <xref:System.Collections.ArrayList> nie są zalecane i są obsługiwane w celu zapewnienia zgodności.</span><span class="sxs-lookup"><span data-stu-id="c9b05-110">The non-generic collections, such as <xref:System.Collections.ArrayList> are not recommended and are maintained for compatibility purposes.</span></span> <span data-ttu-id="c9b05-111">Aby uzyskać więcej informacji, zobacz [typy ogólne w programie .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="c9b05-111">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>

<span data-ttu-id="c9b05-112">Oczywiście można również tworzyć niestandardowe typy ogólne i metody w celu udostępniania własnych uogólnionych rozwiązań i wzorców projektowych, które są bezpieczne i wydajne.</span><span class="sxs-lookup"><span data-stu-id="c9b05-112">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="c9b05-113">Poniższy przykład kodu pokazuje prostą ogólną klasę listy połączonej w celach demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="c9b05-113">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="c9b05-114">(W większości przypadków należy użyć <xref:System.Collections.Generic.List%601> klasy dostarczonej przez platformę .NET zamiast tworzenia własnych). Parametr typu `T` jest używany w kilku lokalizacjach, w których konkretny typ jest zwykle używany do wskazania typu elementu przechowywanego na liście.</span><span class="sxs-lookup"><span data-stu-id="c9b05-114">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by .NET instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="c9b05-115">Jest on używany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c9b05-115">It is used in the following ways:</span></span>

- <span data-ttu-id="c9b05-116">Jako typ parametru metody w `AddHead` metodzie.</span><span class="sxs-lookup"><span data-stu-id="c9b05-116">As the type of a method parameter in the `AddHead` method.</span></span>
- <span data-ttu-id="c9b05-117">Jako zwracany typ `Data` właściwości w klasie zagnieżdżonej `Node` .</span><span class="sxs-lookup"><span data-stu-id="c9b05-117">As the return type of the `Data` property in the nested `Node` class.</span></span>
- <span data-ttu-id="c9b05-118">Jako typ prywatnego elementu członkowskiego `data` w klasie zagnieżdżonej.</span><span class="sxs-lookup"><span data-stu-id="c9b05-118">As the type of the private member `data` in the nested class.</span></span>

 <span data-ttu-id="c9b05-119">Należy pamiętać, że `T` jest ona dostępna dla klasy zagnieżdżonej `Node` .</span><span class="sxs-lookup"><span data-stu-id="c9b05-119">Note that `T` is available to the nested `Node` class.</span></span> <span data-ttu-id="c9b05-120">Gdy `GenericList<T>` jest tworzona przy użyciu konkretnego typu, na przykład jako `GenericList<int>` , każde wystąpienie `T` zostanie zastąpione `int` .</span><span class="sxs-lookup"><span data-stu-id="c9b05-120">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>

[!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]

<span data-ttu-id="c9b05-121">Poniższy przykład kodu pokazuje, jak kod klienta używa klasy generycznej `GenericList<T>` do tworzenia listy liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="c9b05-121">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="c9b05-122">Po prostu poprzez zmianę argumentu typu można łatwo zmodyfikować następujący kod w celu utworzenia list ciągów lub dowolnego innego typu niestandardowego:</span><span class="sxs-lookup"><span data-stu-id="c9b05-122">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>

[!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]

## <a name="generics-overview"></a><span data-ttu-id="c9b05-123">Ogólne — przegląd</span><span class="sxs-lookup"><span data-stu-id="c9b05-123">Generics overview</span></span>

- <span data-ttu-id="c9b05-124">Używaj typów ogólnych do maksymalizowania ponownego użycia kodu, bezpieczeństwa typów i wydajności.</span><span class="sxs-lookup"><span data-stu-id="c9b05-124">Use generic types to maximize code reuse, type safety, and performance.</span></span>
- <span data-ttu-id="c9b05-125">Typowym zastosowaniem typów ogólnych jest utworzenie klas kolekcji.</span><span class="sxs-lookup"><span data-stu-id="c9b05-125">The most common use of generics is to create collection classes.</span></span>
- <span data-ttu-id="c9b05-126">Biblioteka klas .NET zawiera kilka ogólnych klas kolekcji w <xref:System.Collections.Generic> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="c9b05-126">The .NET class library contains several generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="c9b05-127">Powinny one być używane w miarę możliwości zamiast klas takich jak <xref:System.Collections.ArrayList> w <xref:System.Collections> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="c9b05-127">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>
- <span data-ttu-id="c9b05-128">Można tworzyć własne interfejsy, klasy, metody, zdarzenia i Delegaty.</span><span class="sxs-lookup"><span data-stu-id="c9b05-128">You can create your own generic interfaces, classes, methods, events, and delegates.</span></span>
- <span data-ttu-id="c9b05-129">Klasy generyczne mogą być ograniczone, aby umożliwić dostęp do metod dla konkretnych typów danych.</span><span class="sxs-lookup"><span data-stu-id="c9b05-129">Generic classes may be constrained to enable access to methods on particular data types.</span></span>
- <span data-ttu-id="c9b05-130">Informacje na temat typów, które są używane w ogólnym typie danych, można uzyskać w czasie wykonywania przy użyciu odbicia.</span><span class="sxs-lookup"><span data-stu-id="c9b05-130">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c9b05-131">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="c9b05-131">Related sections</span></span>

- [<span data-ttu-id="c9b05-132">Parametry typu ogólnego</span><span class="sxs-lookup"><span data-stu-id="c9b05-132">Generic Type Parameters</span></span>](generic-type-parameters.md)
- [<span data-ttu-id="c9b05-133">Ograniczenia dotyczące parametrów typu</span><span class="sxs-lookup"><span data-stu-id="c9b05-133">Constraints on Type Parameters</span></span>](constraints-on-type-parameters.md)
- [<span data-ttu-id="c9b05-134">Klasy ogólne</span><span class="sxs-lookup"><span data-stu-id="c9b05-134">Generic Classes</span></span>](generic-classes.md)
- [<span data-ttu-id="c9b05-135">Interfejsy ogólne</span><span class="sxs-lookup"><span data-stu-id="c9b05-135">Generic Interfaces</span></span>](generic-interfaces.md)
- [<span data-ttu-id="c9b05-136">Metody ogólne</span><span class="sxs-lookup"><span data-stu-id="c9b05-136">Generic Methods</span></span>](generic-methods.md)
- [<span data-ttu-id="c9b05-137">Delegaci ogólni</span><span class="sxs-lookup"><span data-stu-id="c9b05-137">Generic Delegates</span></span>](generic-delegates.md)
- [<span data-ttu-id="c9b05-138">Różnice między szablonami C++ i typami ogólnymi C#</span><span class="sxs-lookup"><span data-stu-id="c9b05-138">Differences Between C++ Templates and C# Generics</span></span>](differences-between-cpp-templates-and-csharp-generics.md)
- [<span data-ttu-id="c9b05-139">Typy ogólne i odbicie</span><span class="sxs-lookup"><span data-stu-id="c9b05-139">Generics and Reflection</span></span>](generics-and-reflection.md)
- [<span data-ttu-id="c9b05-140">Typy ogólne w środowisku uruchomieniowym</span><span class="sxs-lookup"><span data-stu-id="c9b05-140">Generics in the Run Time</span></span>](generics-in-the-run-time.md)

## <a name="c-language-specification"></a><span data-ttu-id="c9b05-141">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="c9b05-141">C# language specification</span></span>

<span data-ttu-id="c9b05-142">Aby uzyskać więcej informacji, zobacz [Specyfikacja języka C#](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="c9b05-142">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="c9b05-143">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c9b05-143">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="c9b05-144">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="c9b05-144">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c9b05-145">Typy</span><span class="sxs-lookup"><span data-stu-id="c9b05-145">Types</span></span>](../types/index.md)
- [\<typeparam>](../xmldoc/typeparam.md)
- [\<typeparamref>](../xmldoc/typeparamref.md)
- [<span data-ttu-id="c9b05-146">Typy ogólne w .NET</span><span class="sxs-lookup"><span data-stu-id="c9b05-146">Generics in .NET</span></span>](../../../standard/generics/index.md)
