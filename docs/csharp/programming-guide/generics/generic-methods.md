---
title: Metody ogólne — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat metod zadeklarowanych za pomocą parametrów typu, znanych jako metody ogólne. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
ms.openlocfilehash: 195e3f11c73a17931fa6331750e2ae4ee8fd6f10
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151470"
---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="e762b-104">Metody ogólne (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="e762b-104">Generic Methods (C# Programming Guide)</span></span>

<span data-ttu-id="e762b-105">Metoda generyczna jest metodą zadeklarowaną z parametrami typu w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="e762b-105">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#22)]  
  
 <span data-ttu-id="e762b-106">Poniższy przykład kodu pokazuje jeden ze sposobów wywoływania metody przy użyciu `int` dla argumentu typu:</span><span class="sxs-lookup"><span data-stu-id="e762b-106">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#23)]  
  
 <span data-ttu-id="e762b-107">Można również pominąć argument typu i kompilator wywnioskuje go.</span><span class="sxs-lookup"><span data-stu-id="e762b-107">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="e762b-108">Następujące wywołanie `Swap` jest równoważne z poprzednim wywołaniem:</span><span class="sxs-lookup"><span data-stu-id="e762b-108">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#24)]  
  
 <span data-ttu-id="e762b-109">Te same reguły wnioskowania o typie mają zastosowanie do metod statycznych i metod wystąpień.</span><span class="sxs-lookup"><span data-stu-id="e762b-109">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="e762b-110">Kompilator może wywnioskować parametry typu na podstawie argumentów metody, które są przekazywane; nie można wywnioskować parametrów typu tylko z ograniczenia lub wartości zwracanej.</span><span class="sxs-lookup"><span data-stu-id="e762b-110">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="e762b-111">W związku z tym, wnioskowanie typu nie działa z metodami, które nie mają parametrów.</span><span class="sxs-lookup"><span data-stu-id="e762b-111">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="e762b-112">Wnioskowanie o typie występuje w czasie kompilacji, zanim kompilator próbuje rozpoznać przeciążone sygnatury metod.</span><span class="sxs-lookup"><span data-stu-id="e762b-112">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="e762b-113">Kompilator stosuje logikę wnioskowania typu do wszystkich metod ogólnych, które mają taką samą nazwę.</span><span class="sxs-lookup"><span data-stu-id="e762b-113">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="e762b-114">W kroku rozwiązywanie przeciążenia kompilator zawiera tylko te metody ogólne, dla których wnioskowanie typu zostało zakończone powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="e762b-114">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="e762b-115">W ramach klasy generycznej metody niegeneryczne mogą uzyskać dostęp do parametrów typu poziomu klasy w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="e762b-115">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#25)]  
  
 <span data-ttu-id="e762b-116">W przypadku zdefiniowania metody ogólnej, która przyjmuje takie same parametry typu jak Klasa zawierająca, kompilator generuje ostrzeżenie [CS0693](../../misc/cs0693.md) , ponieważ w zakresie metody argument dostarczony dla elementu wewnętrznego `T` ukrywa argument podany dla elementu zewnętrznego `T` .</span><span class="sxs-lookup"><span data-stu-id="e762b-116">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning [CS0693](../../misc/cs0693.md) because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="e762b-117">Jeśli wymagana jest elastyczność wywoływania metody klasy generycznej z argumentami typu innym niż podane podczas tworzenia wystąpienia klasy, należy rozważyć dostarczenie innego identyfikatora dla parametru typu metody, jak pokazano w `GenericList2<T>` poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="e762b-117">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#26)]  
  
 <span data-ttu-id="e762b-118">Użyj ograniczeń, aby włączyć bardziej wyspecjalizowane operacje dotyczące parametrów typu w metodach.</span><span class="sxs-lookup"><span data-stu-id="e762b-118">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="e762b-119">Ta wersja programu o `Swap<T>` nazwie `SwapIfGreater<T>` może być używana tylko z argumentami typu, które implementują <xref:System.IComparable%601> .</span><span class="sxs-lookup"><span data-stu-id="e762b-119">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#27)]  
  
 <span data-ttu-id="e762b-120">Metody generyczne mogą być przeciążone dla kilku parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="e762b-120">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="e762b-121">Na przykład następujące metody mogą znajdować się w tej samej klasie:</span><span class="sxs-lookup"><span data-stu-id="e762b-121">For example, the following methods can all be located in the same class:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#28)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e762b-122">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="e762b-122">C# Language Specification</span></span>  

 <span data-ttu-id="e762b-123">Aby uzyskać więcej informacji, zobacz [Specyfikacja języka C#](~/_csharplang/spec/classes.md#methods).</span><span class="sxs-lookup"><span data-stu-id="e762b-123">For more information, see the [C# Language Specification](~/_csharplang/spec/classes.md#methods).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e762b-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e762b-124">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="e762b-125">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="e762b-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e762b-126">Wprowadzenie do typów ogólnych</span><span class="sxs-lookup"><span data-stu-id="e762b-126">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="e762b-127">Metody</span><span class="sxs-lookup"><span data-stu-id="e762b-127">Methods</span></span>](../classes-and-structs/methods.md)
