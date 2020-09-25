---
title: Pełnomocnicy — Przewodnik programowania w języku C#
description: Delegat w języku C# jest typem, który odwołuje się do metod z listą parametrów i zwracanym typem. Delegaty służą do przekazywania metod jako argumentów do innych metod.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: 7365cb89ad617148fb26d5a01c07f13a7888bbf8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178700"
---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="96d6e-104">Delegaty (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="96d6e-104">Delegates (C# Programming Guide)</span></span>

<span data-ttu-id="96d6e-105">[Delegat](../../language-reference/builtin-types/reference-types.md) jest typem, który reprezentuje odwołania do metod z określoną listą parametrów i zwracanym typem.</span><span class="sxs-lookup"><span data-stu-id="96d6e-105">A [delegate](../../language-reference/builtin-types/reference-types.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="96d6e-106">Podczas tworzenia wystąpienia delegata można skojarzyć jego wystąpienie z dowolną metodą mającą zgodny podpis i zwracany typ.</span><span class="sxs-lookup"><span data-stu-id="96d6e-106">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="96d6e-107">Za pośrednictwem wystąpienia delegata można wywołać metodę.</span><span class="sxs-lookup"><span data-stu-id="96d6e-107">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="96d6e-108">Delegaty służą do przekazywania metod jako argumentów do innych metod.</span><span class="sxs-lookup"><span data-stu-id="96d6e-108">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="96d6e-109">Programy obsługi zdarzeń to po prostu metody, które są wywoływane za pośrednictwem delegatów.</span><span class="sxs-lookup"><span data-stu-id="96d6e-109">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="96d6e-110">Użytkownik tworzy metodę niestandardową, a klasa, taka jak formant systemu Windows, może wywołać tę metodę, gdy wystąpi określone zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="96d6e-110">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="96d6e-111">W poniższym przykładzie pokazano deklarację delegata:</span><span class="sxs-lookup"><span data-stu-id="96d6e-111">The following example shows a delegate declaration:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#20)]  
  
 <span data-ttu-id="96d6e-112">Do delegata można przypisać każdą metodę z dowolnej dostępnej klasy lub struktury, która pasuje do typu delegata.</span><span class="sxs-lookup"><span data-stu-id="96d6e-112">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="96d6e-113">Może to być metoda statyczna lub metoda wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="96d6e-113">The method can be either static or an instance method.</span></span> <span data-ttu-id="96d6e-114">Umożliwia to programowe zmienianie wywołań metod, a także podłączanie nowego kodu do istniejących klas.</span><span class="sxs-lookup"><span data-stu-id="96d6e-114">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96d6e-115">W kontekście przeciążania metod podpis metody nie zawiera wartości zwracanej.</span><span class="sxs-lookup"><span data-stu-id="96d6e-115">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="96d6e-116">Jednak w kontekście delegatów podpis zawiera wartość zwracaną.</span><span class="sxs-lookup"><span data-stu-id="96d6e-116">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="96d6e-117">Innymi słowy metoda musi mieć taki sam zwracany typ jak delegat.</span><span class="sxs-lookup"><span data-stu-id="96d6e-117">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="96d6e-118">Ta możliwość odwoływania się do metody jak do parametru sprawia, że delegaty idealnie nadają się do definiowania metod wywoływania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="96d6e-118">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="96d6e-119">Na przykład odwołanie do metody, która porównuje dwa obiekty można przekazać jako argument do algorytmu sortowania.</span><span class="sxs-lookup"><span data-stu-id="96d6e-119">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="96d6e-120">Kod porównania znajduje się w osobnej procedurze, więc algorytm sortowania można napisać w bardziej ogólny sposób.</span><span class="sxs-lookup"><span data-stu-id="96d6e-120">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="96d6e-121">Omówienie delegatów</span><span class="sxs-lookup"><span data-stu-id="96d6e-121">Delegates Overview</span></span>  

 <span data-ttu-id="96d6e-122">Delegaty mają następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="96d6e-122">Delegates have the following properties:</span></span>  
  
- <span data-ttu-id="96d6e-123">Delegaty są podobne do wskaźników funkcji języka C++, ale Delegaty są w pełni zorientowane obiektowo i w przeciwieństwie do wskaźników języka C++ do funkcji składowych, Delegaty hermetyzują zarówno wystąpienie obiektu, jak i metodę.</span><span class="sxs-lookup"><span data-stu-id="96d6e-123">Delegates are similar to C++ function pointers, but delegates are fully object-oriented, and unlike C++ pointers to member functions, delegates encapsulate both an object instance and a method.</span></span>
  
- <span data-ttu-id="96d6e-124">Delegaty zezwalają na przekazywanie metod jako parametrów.</span><span class="sxs-lookup"><span data-stu-id="96d6e-124">Delegates allow methods to be passed as parameters.</span></span>  
  
- <span data-ttu-id="96d6e-125">Delegatów można używać do definiowania metod wywoływania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="96d6e-125">Delegates can be used to define callback methods.</span></span>  
  
- <span data-ttu-id="96d6e-126">Delegaty można łączyć w łańcuch; na przykład w jednym zdarzeniu można wywołać wiele metod.</span><span class="sxs-lookup"><span data-stu-id="96d6e-126">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
- <span data-ttu-id="96d6e-127">Metody nie muszą dokładnie pasować do typu delegata.</span><span class="sxs-lookup"><span data-stu-id="96d6e-127">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="96d6e-128">Aby uzyskać więcej informacji, zobacz [Korzystanie z wariancji w delegatach](../concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="96d6e-128">For more information, see [Using Variance in Delegates](../concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
- <span data-ttu-id="96d6e-129">W języku C# w wersji 2,0 wprowadzono koncepcję [metod anonimowych](../../language-reference/operators/delegate-operator.md), która umożliwia przekazywanie bloków kodu jako parametrów zamiast oddzielnie zdefiniowanej metody.</span><span class="sxs-lookup"><span data-stu-id="96d6e-129">C# version 2.0 introduced the concept of [anonymous methods](../../language-reference/operators/delegate-operator.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="96d6e-130">W języku C# 3.0 wprowadzono wyrażenia lambda, które stanową wygodniejszy sposób pisania bloków kodu w tekście.</span><span class="sxs-lookup"><span data-stu-id="96d6e-130">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="96d6e-131">Zarówno metody anonimowe, jak i wyrażenia lambda (w pewnych kontekstach) są kompilowane na typy delegatów.</span><span class="sxs-lookup"><span data-stu-id="96d6e-131">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="96d6e-132">Te funkcje są obecnie nazywane łącznie funkcjami anonimowymi.</span><span class="sxs-lookup"><span data-stu-id="96d6e-132">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="96d6e-133">Aby uzyskać więcej informacji na temat wyrażeń lambda, zobacz [lambda Expressions](../../language-reference/operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="96d6e-133">For more information about lambda expressions, see [Lambda expressions](../../language-reference/operators/lambda-expressions.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="96d6e-134">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="96d6e-134">In This Section</span></span>  
  
- [<span data-ttu-id="96d6e-135">Używanie delegatów</span><span class="sxs-lookup"><span data-stu-id="96d6e-135">Using Delegates</span></span>](./using-delegates.md)  
  
- <span data-ttu-id="96d6e-136">[Kiedy używać delegatów zamiast interfejsów (Przewodnik programowania w języku C#)](/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="96d6e-136">[When to Use Delegates Instead of Interfaces (C# Programming Guide)](/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))</span></span>  
  
- [<span data-ttu-id="96d6e-137">Delegaty z metodami nazwanymi lub Metody anonimowe</span><span class="sxs-lookup"><span data-stu-id="96d6e-137">Delegates with Named vs. Anonymous Methods</span></span>](./delegates-with-named-vs-anonymous-methods.md)  
  
- [<span data-ttu-id="96d6e-138">Korzystanie z wariancji w delegatach</span><span class="sxs-lookup"><span data-stu-id="96d6e-138">Using Variance in Delegates</span></span>](../concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
- [<span data-ttu-id="96d6e-139">Jak łączyć delegatów (delegatów multiemisji)</span><span class="sxs-lookup"><span data-stu-id="96d6e-139">How to combine delegates (Multicast Delegates)</span></span>](./how-to-combine-delegates-multicast-delegates.md)  
  
- [<span data-ttu-id="96d6e-140">Deklarowanie, tworzenie wystąpień i użycie delegowania</span><span class="sxs-lookup"><span data-stu-id="96d6e-140">How to declare, instantiate, and use a delegate</span></span>](./how-to-declare-instantiate-and-use-a-delegate.md)

## <a name="c-language-specification"></a><span data-ttu-id="96d6e-141">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="96d6e-141">C# Language Specification</span></span>  

<span data-ttu-id="96d6e-142">Aby uzyskać więcej informacji, zobacz [Delegaty](~/_csharplang/spec/delegates.md) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="96d6e-142">For more information, see [Delegates](~/_csharplang/spec/delegates.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="96d6e-143">Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="96d6e-143">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="96d6e-144">Polecane rozdziały książki</span><span class="sxs-lookup"><span data-stu-id="96d6e-144">Featured Book Chapters</span></span>  

 <span data-ttu-id="96d6e-145">[Delegaty, zdarzenia i wyrażenia lambda](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) w [języku c# 3,0 Cookbook, wydanie trzecie: więcej niż 250 rozwiązań dla programistów 3,0 c#](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="96d6e-145">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span></span>  
  
 <span data-ttu-id="96d6e-146">[Delegaty i zdarzenia](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) w [uczeniu C# 3,0: główne podstawy języka c# 3,0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="96d6e-146">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) in [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d6e-147">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96d6e-147">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="96d6e-148">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="96d6e-148">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="96d6e-149">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="96d6e-149">Events</span></span>](../events/index.md)
