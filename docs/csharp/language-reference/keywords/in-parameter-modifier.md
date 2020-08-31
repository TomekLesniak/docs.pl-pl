---
description: modyfikator parametru — odwołanie w C#
title: modyfikator parametru — odwołanie w C#
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 613be9248e6ce9b974bcab1b59abd30469e9e180
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118407"
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="3ab75-103">w modyfikatorze parametru (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="3ab75-103">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="3ab75-104">`in`Słowo kluczowe powoduje, że argumenty są przekazane przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="3ab75-104">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="3ab75-105">Sprawia, że parametr formalny jest aliasem dla argumentu, który musi być zmienną.</span><span class="sxs-lookup"><span data-stu-id="3ab75-105">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="3ab75-106">Innymi słowy, każda operacja na parametrze jest wykonywana na argumencie.</span><span class="sxs-lookup"><span data-stu-id="3ab75-106">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="3ab75-107">Przypomina słowa kluczowe [ref](ref.md) lub [out](out-parameter-modifier.md) , z wyjątkiem tego, że `in` argumenty nie mogą być modyfikowane przez wywołaną metodę.</span><span class="sxs-lookup"><span data-stu-id="3ab75-107">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method.</span></span> <span data-ttu-id="3ab75-108">`ref`Argumenty mogą być modyfikowane, `out` argumenty muszą być modyfikowane przez wywołana metoda i te modyfikacje są zauważalne w kontekście wywołującym.</span><span class="sxs-lookup"><span data-stu-id="3ab75-108">Whereas `ref` arguments may be modified, `out` arguments must be modified by the called method, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="3ab75-109">Powyższy przykład pokazuje, że `in` modyfikator zazwyczaj nie jest zbędny w miejscu wywołania.</span><span class="sxs-lookup"><span data-stu-id="3ab75-109">The preceding example demonstrates that the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="3ab75-110">Jest to wymagane tylko w deklaracji metody.</span><span class="sxs-lookup"><span data-stu-id="3ab75-110">It is only required in the method declaration.</span></span>

> [!NOTE]
> <span data-ttu-id="3ab75-111">`in`Słowo kluczowe może być również używane z parametrem typu ogólnego, aby określić, że parametr typu jest kontrawariantne, jako część `foreach` instrukcji lub jako część `join` klauzuli w zapytaniu LINQ.</span><span class="sxs-lookup"><span data-stu-id="3ab75-111">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="3ab75-112">Aby uzyskać więcej informacji na temat używania `in` słowa kluczowego w tych kontekstach, zobacz sekcję [w](in.md), która zawiera linki do wszystkich tych celów.</span><span class="sxs-lookup"><span data-stu-id="3ab75-112">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
<span data-ttu-id="3ab75-113">Zmienne przekazane jako `in` argumenty muszą być zainicjowane przed przekazywaniem w wywołaniu metody.</span><span class="sxs-lookup"><span data-stu-id="3ab75-113">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="3ab75-114">Jednak wywołana metoda nie może przypisywać wartości ani modyfikować argumentu.</span><span class="sxs-lookup"><span data-stu-id="3ab75-114">However, the called method may not assign a value or modify the argument.</span></span>  

<span data-ttu-id="3ab75-115">`in`Modyfikator parametru jest dostępny w języku C# 7,2 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="3ab75-115">The `in` parameter modifier is available in C# 7.2 and later.</span></span> <span data-ttu-id="3ab75-116">Poprzednie wersje generują błąd kompilatora `CS8107` ("funkcja ReadOnly References" nie jest dostępna w języku C# 7,0.</span><span class="sxs-lookup"><span data-stu-id="3ab75-116">Previous versions generate compiler error `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span></span> <span data-ttu-id="3ab75-117">Użyj języka w wersji 7,2 lub nowszej. ") Aby skonfigurować wersję języka kompilatora, zobacz [Wybieranie wersji języka C#](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="3ab75-117">Please use language version 7.2 or greater.") To configure the compiler language version, see [Select the C# language version](../configure-language-version.md).</span></span>

<span data-ttu-id="3ab75-118">`in` `ref` Słowa kluczowe, i `out` nie są uważane za część podpisu metody na potrzeby rozpoznawania przeciążenia.</span><span class="sxs-lookup"><span data-stu-id="3ab75-118">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="3ab75-119">W związku z tym metody nie mogą być przeciążone, jeśli jedyną różnicą jest to, że jedna metoda przyjmuje `ref` argument lub, `in` a druga przyjmuje `out` argument.</span><span class="sxs-lookup"><span data-stu-id="3ab75-119">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="3ab75-120">Poniższy kod, na przykład, nie zostanie skompilowany:</span><span class="sxs-lookup"><span data-stu-id="3ab75-120">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="3ab75-121">Przeciążanie na podstawie obecności `in` jest dozwolone:</span><span class="sxs-lookup"><span data-stu-id="3ab75-121">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="3ab75-122">Reguły rozpoznawania przeciążenia</span><span class="sxs-lookup"><span data-stu-id="3ab75-122">Overload resolution rules</span></span>

<span data-ttu-id="3ab75-123">Można zrozumieć reguły rozpoznawania przeciążeń dla metod za pomocą wartości przez wartość a `in` argumenty, opisując motywację `in` argumentów.</span><span class="sxs-lookup"><span data-stu-id="3ab75-123">You can understand the overload resolution rules for methods with by value vs. `in` arguments by understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="3ab75-124">Definiowanie metod przy użyciu `in` parametrów jest potencjalną optymalizacją wydajności.</span><span class="sxs-lookup"><span data-stu-id="3ab75-124">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="3ab75-125">Niektóre `struct` argumenty typu mogą być duże, a gdy metody są wywoływane przy użyciu ścisłych pętli lub ścieżek kodu krytycznego, koszt kopiowania tych struktur jest krytyczny.</span><span class="sxs-lookup"><span data-stu-id="3ab75-125">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="3ab75-126">Metody deklarują `in` Parametry, aby określić, że argumenty mogą być przekazane przez odwołanie bezpiecznie, ponieważ wywołana metoda nie modyfikuje stanu tego argumentu.</span><span class="sxs-lookup"><span data-stu-id="3ab75-126">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="3ab75-127">Przekazanie tych argumentów przez odwołanie pozwala uniknąć (potencjalnie) kosztownego kopiowania.</span><span class="sxs-lookup"><span data-stu-id="3ab75-127">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span>

<span data-ttu-id="3ab75-128">Określanie `in` dla argumentów w miejscu wywołania jest zwykle opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="3ab75-128">Specifying `in` for arguments at the call site is typically optional.</span></span> <span data-ttu-id="3ab75-129">Między przekazywaniem argumentów przez wartość i przekazaniem ich przez odwołanie za pomocą modyfikatora nie ma różnicy semantycznej `in` .</span><span class="sxs-lookup"><span data-stu-id="3ab75-129">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="3ab75-130">`in`Modyfikator w miejscu wywołania jest opcjonalny, ponieważ nie trzeba wskazywać, że wartość argumentu może zostać zmieniona.</span><span class="sxs-lookup"><span data-stu-id="3ab75-130">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="3ab75-131">Modyfikator można jawnie dodać `in` w miejscu wywołania, aby upewnić się, że argument jest przekazaniem przez odwołanie, a nie przez wartość.</span><span class="sxs-lookup"><span data-stu-id="3ab75-131">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="3ab75-132">Jawne użycie `in` ma dwa następujące efekty:</span><span class="sxs-lookup"><span data-stu-id="3ab75-132">Explicitly using `in` has the following two effects:</span></span>

<span data-ttu-id="3ab75-133">Po pierwsze, określenie `in` w witrynie wywołania wymusza, aby kompilator wybierał metodę zdefiniowaną za pomocą zgodnego `in` parametru.</span><span class="sxs-lookup"><span data-stu-id="3ab75-133">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="3ab75-134">W przeciwnym razie, gdy dwie metody różnią się tylko w obecności `in` , Przeciążenie przez wartość jest lepszym dopasowaniem.</span><span class="sxs-lookup"><span data-stu-id="3ab75-134">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="3ab75-135">Po drugie, określenie `in` deklaruje intencję przekazania argumentu przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="3ab75-135">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="3ab75-136">Argument używany z `in` musi reprezentować lokalizację, do której można bezpośrednio odwoływać się.</span><span class="sxs-lookup"><span data-stu-id="3ab75-136">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="3ab75-137">Te same reguły ogólne dla `out` i `ref` argumenty mają zastosowanie: nie można użyć stałych, zwykłych właściwości ani innych wyrażeń, które tworzą wartości.</span><span class="sxs-lookup"><span data-stu-id="3ab75-137">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="3ab75-138">W przeciwnym razie pomijanie `in` w witrynie wywołania informuje kompilator, że umożliwi to utworzenie zmiennej tymczasowej do przekazania przez odwołanie tylko do odczytu do metody.</span><span class="sxs-lookup"><span data-stu-id="3ab75-138">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="3ab75-139">Kompilator tworzy zmienną tymczasową, aby przezwyciężyć kilka ograniczeń z `in` argumentami:</span><span class="sxs-lookup"><span data-stu-id="3ab75-139">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="3ab75-140">Zmienna tymczasowa dopuszcza stałe w czasie kompilacji jako `in` parametry.</span><span class="sxs-lookup"><span data-stu-id="3ab75-140">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="3ab75-141">Zmienna tymczasowa pozwala na właściwości lub inne wyrażenia dla `in` parametrów.</span><span class="sxs-lookup"><span data-stu-id="3ab75-141">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="3ab75-142">Zmienna tymczasowa zezwala na argumenty, w których istnieje niejawna konwersja z typu argumentu na typ parametru.</span><span class="sxs-lookup"><span data-stu-id="3ab75-142">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="3ab75-143">We wszystkich poprzednich wystąpieniach kompilator tworzy zmienną tymczasową, która przechowuje wartość stałej, właściwości lub innego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="3ab75-143">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="3ab75-144">Poniższy kod ilustruje następujące reguły:</span><span class="sxs-lookup"><span data-stu-id="3ab75-144">The following code illustrates these rules:</span></span>

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="3ab75-145">Teraz Załóżmy, że jest dostępna inna metoda używająca argumentów wartości.</span><span class="sxs-lookup"><span data-stu-id="3ab75-145">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="3ab75-146">Wyniki są zmieniane, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="3ab75-146">The results change as shown in the following code:</span></span>

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="3ab75-147">Jedyne wywołanie metody, do którego argument jest przenoszona przez odwołanie jest ostatnim z nich.</span><span class="sxs-lookup"><span data-stu-id="3ab75-147">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="3ab75-148">Poprzedni kod używa `int` jako typu argumentu dla uproszczenia.</span><span class="sxs-lookup"><span data-stu-id="3ab75-148">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="3ab75-149">Ponieważ nie `int` jest większy niż odwołanie w większości nowoczesnych maszyn, nie ma zalet przekazywania jednego `int` jako odwołania tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="3ab75-149">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span>

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="3ab75-150">Ograniczenia dotyczące `in` parametrów</span><span class="sxs-lookup"><span data-stu-id="3ab75-150">Limitations on `in` parameters</span></span>

<span data-ttu-id="3ab75-151">Nie można używać `in` `ref` słów kluczowych, i `out` dla następujących rodzajów metod:</span><span class="sxs-lookup"><span data-stu-id="3ab75-151">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="3ab75-152">Metody asynchroniczne zdefiniowane za pomocą modyfikatora [Async](async.md) .</span><span class="sxs-lookup"><span data-stu-id="3ab75-152">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="3ab75-153">Metody iteratorów, które zawierają instrukcję [yield return](yield.md) lub `yield break` .</span><span class="sxs-lookup"><span data-stu-id="3ab75-153">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>
- <span data-ttu-id="3ab75-154">Pierwszy argument metody rozszerzenia nie może mieć `in` modyfikatora, chyba że ten argument jest strukturą.</span><span class="sxs-lookup"><span data-stu-id="3ab75-154">The first argument of an extension method cannot have the `in` modifier unless that argument is a struct.</span></span>
- <span data-ttu-id="3ab75-155">Pierwszy argument metody rozszerzenia, gdzie ten argument jest typem ogólnym (nawet wtedy, gdy ten typ jest ograniczony do struktury).</span><span class="sxs-lookup"><span data-stu-id="3ab75-155">The first argument of an extension method where that argument is a generic type (even when that type is constrained to be a struct.)</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3ab75-156">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="3ab75-156">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ab75-157">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3ab75-157">See also</span></span>

- [<span data-ttu-id="3ab75-158">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="3ab75-158">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3ab75-159">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="3ab75-159">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3ab75-160">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="3ab75-160">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3ab75-161">Parametry metody</span><span class="sxs-lookup"><span data-stu-id="3ab75-161">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="3ab75-162">Zapisz bezpieczny wydajny kod</span><span class="sxs-lookup"><span data-stu-id="3ab75-162">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
