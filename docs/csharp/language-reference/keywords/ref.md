---
description: ref — słowo kluczowe — odwołanie w C#
title: ref — słowo kluczowe — odwołanie w C#
ms.date: 04/21/2020
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 58a4ce30e11ca023b50e5e53b1f1554a30d44390
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137087"
---
# <a name="ref-c-reference"></a><span data-ttu-id="da2e1-103">ref (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="da2e1-103">ref (C# Reference)</span></span>

<span data-ttu-id="da2e1-104">`ref`Słowo kluczowe wskazuje wartość, która jest przenoszona przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-104">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="da2e1-105">Jest on używany w czterech różnych kontekstach:</span><span class="sxs-lookup"><span data-stu-id="da2e1-105">It is used in four different contexts:</span></span>

- <span data-ttu-id="da2e1-106">W sygnaturze metody i w wywołaniu metody, aby przekazać argument do metody przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-106">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="da2e1-107">Aby uzyskać więcej informacji, zobacz [przekazywanie argumentu przez odwołanie](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="da2e1-107">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="da2e1-108">W podpisie metody, aby zwrócić wartość do obiektu wywołującego przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-108">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="da2e1-109">Aby uzyskać więcej informacji, zobacz [odwołania do zwracanych wartości](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="da2e1-109">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="da2e1-110">W treści elementu członkowskiego, aby wskazać, że wartość zwracana przez odwołanie jest przechowywana lokalnie jako odwołanie, które obiekt wywołujący zamierza zmodyfikować lub ogólnie rzecz biorąc, zmienna lokalna uzyskuje dostęp do innej wartości przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-110">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="da2e1-111">Aby uzyskać więcej informacji, zobacz [odwołania lokalne](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="da2e1-111">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="da2e1-112">W `struct` deklaracji do deklarowania `ref struct` lub `readonly ref struct` .</span><span class="sxs-lookup"><span data-stu-id="da2e1-112">In a `struct` declaration to declare a `ref struct` or a `readonly ref struct`.</span></span> <span data-ttu-id="da2e1-113">Aby uzyskać więcej informacji, zobacz sekcję [ `ref` struktury](../builtin-types/struct.md#ref-struct) w artykule [typy struktury](../builtin-types/struct.md) .</span><span class="sxs-lookup"><span data-stu-id="da2e1-113">For more information, see the [`ref` struct](../builtin-types/struct.md#ref-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="da2e1-114">Przekazywanie argumentu przez odwołanie</span><span class="sxs-lookup"><span data-stu-id="da2e1-114">Passing an argument by reference</span></span>

<span data-ttu-id="da2e1-115">W przypadku użycia na liście parametrów metody `ref` słowo kluczowe wskazuje, że argument jest przenoszona przez odwołanie, a nie przez wartość.</span><span class="sxs-lookup"><span data-stu-id="da2e1-115">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="da2e1-116">`ref`Słowo kluczowe powoduje, że parametr formalny jest aliasem dla argumentu, który musi być zmienną.</span><span class="sxs-lookup"><span data-stu-id="da2e1-116">The `ref` keyword makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="da2e1-117">Innymi słowy, każda operacja na parametrze jest wykonywana na argumencie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-117">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="da2e1-118">Na przykład, jeśli obiekt wywołujący przekazuje wyrażenie zmiennej lokalnej lub wyrażenie dostępu do elementu tablicy, a wywoływana metoda zastępuje obiekt, do którego odwołuje się parametr ref, wówczas zmienna lokalna obiektu wywołującego lub element array odwołuje się teraz do nowego obiektu, gdy metoda zwraca.</span><span class="sxs-lookup"><span data-stu-id="da2e1-118">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller's local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="da2e1-119">Nie należy mylić koncepcji przekazywania przez odwołanie z koncepcją typów referencyjnych.</span><span class="sxs-lookup"><span data-stu-id="da2e1-119">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="da2e1-120">Te dwa koncepcje nie są takie same.</span><span class="sxs-lookup"><span data-stu-id="da2e1-120">The two concepts are not the same.</span></span> <span data-ttu-id="da2e1-121">Parametr metody można zmodyfikować, `ref` niezależnie od tego, czy jest to typ wartości, czy też typ referencyjny.</span><span class="sxs-lookup"><span data-stu-id="da2e1-121">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="da2e1-122">Nie istnieje opakowanie typu wartości, gdy jest ono przesyłane przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-122">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="da2e1-123">Aby użyć `ref` parametru, zarówno definicja metody, jak i Metoda wywołująca muszą jawnie użyć `ref` słowa kluczowego, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-123">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="da2e1-124">Argument, który jest przesyłany do `ref` `in` parametru lub musi zostać zainicjowany przed jego przekazaniem.</span><span class="sxs-lookup"><span data-stu-id="da2e1-124">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="da2e1-125">Różni się to od parametrów [out](out-parameter-modifier.md) , których argumenty nie muszą być jawnie inicjowane przed ich przekazaniem.</span><span class="sxs-lookup"><span data-stu-id="da2e1-125">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="da2e1-126">Elementy członkowskie klasy nie mogą mieć sygnatur, które różnią się tylko przez `ref` , `in` lub `out` .</span><span class="sxs-lookup"><span data-stu-id="da2e1-126">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="da2e1-127">Błąd kompilatora występuje, jeśli jedyną różnicą między dwoma elementami członkowskimi tego typu jest, że jeden z nich ma `ref` parametr, a drugi ma `out` parametr, lub `in` .</span><span class="sxs-lookup"><span data-stu-id="da2e1-127">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="da2e1-128">Poniższy kod, na przykład, nie kompiluje.</span><span class="sxs-lookup"><span data-stu-id="da2e1-128">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="da2e1-129">Jednakże metody mogą być przeciążone, gdy jedna metoda ma parametr `ref` , `in` , lub, `out` a drugi ma parametr value, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-129">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="da2e1-130">W innych sytuacjach, które wymagają dopasowania podpisu, takich jak ukrywanie lub zastępowanie, `in` , `ref` , i `out` są częścią podpisu i nie pasują do siebie nawzajem.</span><span class="sxs-lookup"><span data-stu-id="da2e1-130">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="da2e1-131">Właściwości nie są zmiennymi.</span><span class="sxs-lookup"><span data-stu-id="da2e1-131">Properties are not variables.</span></span> <span data-ttu-id="da2e1-132">Są to metody i nie można ich przekazywać do `ref` parametrów.</span><span class="sxs-lookup"><span data-stu-id="da2e1-132">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="da2e1-133">Nie można używać `ref` `in` słów kluczowych, i `out` dla następujących rodzajów metod:</span><span class="sxs-lookup"><span data-stu-id="da2e1-133">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="da2e1-134">Metody asynchroniczne zdefiniowane za pomocą modyfikatora [Async](async.md) .</span><span class="sxs-lookup"><span data-stu-id="da2e1-134">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="da2e1-135">Metody iteratorów, które zawierają instrukcję [yield return](yield.md) lub `yield break` .</span><span class="sxs-lookup"><span data-stu-id="da2e1-135">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>

<span data-ttu-id="da2e1-136">Ponadto [metody rozszerzające](../../programming-guide/classes-and-structs/extension-methods.md) mają następujące ograniczenia:</span><span class="sxs-lookup"><span data-stu-id="da2e1-136">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="da2e1-137">`out`Nie można użyć słowa kluczowego dla pierwszego argumentu metody rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="da2e1-137">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="da2e1-138">`ref`Nie można użyć słowa kluczowego dla pierwszego argumentu metody rozszerzenia, jeśli argument nie jest strukturą lub typ ogólny nie jest ograniczony do struktury.</span><span class="sxs-lookup"><span data-stu-id="da2e1-138">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="da2e1-139">`in`Nie można użyć słowa kluczowego, chyba że pierwszy argument jest strukturą.</span><span class="sxs-lookup"><span data-stu-id="da2e1-139">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="da2e1-140">`in`Nie można użyć słowa kluczowego w żadnym typie ogólnym, nawet jeśli jest to struktura.</span><span class="sxs-lookup"><span data-stu-id="da2e1-140">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="da2e1-141">Przekazywanie argumentu przez odwołanie: przykład</span><span class="sxs-lookup"><span data-stu-id="da2e1-141">Passing an argument by reference: An example</span></span>

<span data-ttu-id="da2e1-142">Poprzednie przykłady przechodzą typy wartości według odwołania.</span><span class="sxs-lookup"><span data-stu-id="da2e1-142">The previous examples pass value types by reference.</span></span> <span data-ttu-id="da2e1-143">Możesz również użyć `ref` słowa kluczowego, aby przekazać typy odwołań przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-143">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="da2e1-144">Przekazywanie typu referencyjnego przez odwołanie włącza wywoływaną metodę, aby zastąpić obiekt, do którego odwołuje się parametr Reference w wywołującym.</span><span class="sxs-lookup"><span data-stu-id="da2e1-144">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="da2e1-145">Lokalizacja przechowywania obiektu jest przenoszona do metody jako wartość parametru Reference.</span><span class="sxs-lookup"><span data-stu-id="da2e1-145">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="da2e1-146">Jeśli zmienisz wartość w lokalizacji magazynu parametru (w celu wskazywania nowego obiektu), zmienisz również lokalizację magazynu, do którego odwołuje się obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="da2e1-146">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="da2e1-147">Poniższy przykład przekazuje wystąpienie typu odwołania jako `ref` parametr.</span><span class="sxs-lookup"><span data-stu-id="da2e1-147">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="da2e1-148">Aby uzyskać więcej informacji na temat przekazywania typów odwołań według wartości i według odwołania, zobacz [przekazywanie parametrów typu odwołania](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="da2e1-148">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="da2e1-149">Odwoływanie się do zwracanych wartości</span><span class="sxs-lookup"><span data-stu-id="da2e1-149">Reference return values</span></span>

<span data-ttu-id="da2e1-150">Wartości zwracane przez odwołanie (lub zwroty odwołań) to wartości, które Metoda zwraca przez odwołanie do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="da2e1-150">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="da2e1-151">Oznacza to, że obiekt wywołujący może zmodyfikować wartość zwróconą przez metodę, a ta zmiana jest odzwierciedlona w stanie obiektu w metodzie wywołującej.</span><span class="sxs-lookup"><span data-stu-id="da2e1-151">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object in the calling method.</span></span>

<span data-ttu-id="da2e1-152">Wartość zwracana przez odwołanie jest definiowana za pomocą `ref` słowa kluczowego:</span><span class="sxs-lookup"><span data-stu-id="da2e1-152">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="da2e1-153">W podpisie metody.</span><span class="sxs-lookup"><span data-stu-id="da2e1-153">In the method signature.</span></span> <span data-ttu-id="da2e1-154">Na przykład następująca sygnatura metody wskazuje, że `GetCurrentPrice` Metoda zwraca <xref:System.Decimal> wartość przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-154">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="da2e1-155">Między `return` tokenem i zmienną zwróconą w `return` instrukcji w metodzie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-155">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="da2e1-156">Przykład:</span><span class="sxs-lookup"><span data-stu-id="da2e1-156">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="da2e1-157">Aby obiekt wywołujący zmodyfikował stan obiektu, wartość zwracana odwołania musi być przechowywana w zmiennej, która jest jawnie zdefiniowana jako [lokalna jako ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="da2e1-157">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="da2e1-158">Poniżej znajduje się bardziej kompletny przykład powrotu odwołania, pokazujący zarówno podpis metody, jak i treść metody.</span><span class="sxs-lookup"><span data-stu-id="da2e1-158">Here is a more complete ref return example, showing both the method signature and method body.</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="da2e1-159">Wywołana metoda może również deklarować wartość zwracaną jako `ref readonly` zwracającą wartość przez odwołanie i wymusić, że wywoływany kod nie może zmodyfikować zwracanej wartości.</span><span class="sxs-lookup"><span data-stu-id="da2e1-159">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="da2e1-160">Metoda wywołująca może uniknąć kopiowania zwracanej wartości przez zapisanie wartości w lokalnej zmiennej [ref ReadOnly](#ref-readonly-locals) .</span><span class="sxs-lookup"><span data-stu-id="da2e1-160">The calling method can avoid copying the returned valued by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="da2e1-161">Aby zapoznać się z przykładem, zobacz [przykład ref Returns i ref locales](#a-ref-returns-and-ref-locals-example).</span><span class="sxs-lookup"><span data-stu-id="da2e1-161">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="da2e1-162">Odwołania lokalne</span><span class="sxs-lookup"><span data-stu-id="da2e1-162">Ref locals</span></span>

<span data-ttu-id="da2e1-163">Referencyjna zmienna lokalna służy do odwoływania się do wartości zwracanych przy użyciu `return ref` .</span><span class="sxs-lookup"><span data-stu-id="da2e1-163">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="da2e1-164">Nie można zainicjować zmiennej lokalnej ref do wartości zwracanej niebędącej odwołaniem.</span><span class="sxs-lookup"><span data-stu-id="da2e1-164">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="da2e1-165">Innymi słowy, prawa strona inicjowania musi być odwołaniem.</span><span class="sxs-lookup"><span data-stu-id="da2e1-165">In other words, the right-hand side of the initialization must be a reference.</span></span> <span data-ttu-id="da2e1-166">Wszelkie modyfikacje wartości lokalnego elementu ref są odzwierciedlane w stanie obiektu, którego Metoda zwróciła wartość przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-166">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="da2e1-167">Można zdefiniować odwołanie lokalne przy użyciu `ref` słowa kluczowego przed deklaracją zmiennej, a także bezpośrednio przed wywołaniem metody, która zwraca wartość przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-167">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="da2e1-168">Na przykład poniższa instrukcja definiuje wartość lokalną ref zwracaną przez metodę o nazwie `GetEstimatedValue` :</span><span class="sxs-lookup"><span data-stu-id="da2e1-168">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="da2e1-169">Możesz uzyskać dostęp do wartości przez odwołanie w ten sam sposób.</span><span class="sxs-lookup"><span data-stu-id="da2e1-169">You can access a value by reference in the same way.</span></span> <span data-ttu-id="da2e1-170">W niektórych przypadkach uzyskanie dostępu do wartości przez odwołanie zwiększa wydajność poprzez uniknięcie potencjalnie kosztownej operacji kopiowania.</span><span class="sxs-lookup"><span data-stu-id="da2e1-170">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="da2e1-171">Na przykład poniższa instrukcja pokazuje, jak jedna z nich może definiować wartość lokalna ref, która jest używana do odwoływania się do wartości.</span><span class="sxs-lookup"><span data-stu-id="da2e1-171">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="da2e1-172">W obu przykładach `ref` słowo kluczowe musi być używane w obu miejscach lub kompilator generuje błąd CS8172, "nie można zainicjować zmiennej przez odwołanie za pomocą wartości".</span><span class="sxs-lookup"><span data-stu-id="da2e1-172">In both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="da2e1-173">Począwszy od języka C# 7,3, Zmienna iteracji `foreach` instrukcji może być lokalna lokalną lub ref tylko do odczytu zmienna lokalna.</span><span class="sxs-lookup"><span data-stu-id="da2e1-173">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="da2e1-174">Aby uzyskać więcej informacji, zobacz artykuł [instrukcji foreach](foreach-in.md) .</span><span class="sxs-lookup"><span data-stu-id="da2e1-174">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

<span data-ttu-id="da2e1-175">Zaczynając od języka C# 7,3, można ponownie przypisać lokalną zmienną lokalną lub ref ReadOnly do odczytu za pomocą [operatora przypisania ref](../operators/assignment-operator.md#ref-assignment-operator).</span><span class="sxs-lookup"><span data-stu-id="da2e1-175">Also beginning with C# 7.3, you can reassign a ref local or ref readonly local variable with the [ref assignment operator](../operators/assignment-operator.md#ref-assignment-operator).</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="da2e1-176">Odwołania do elementów lokalnych ReadOnly</span><span class="sxs-lookup"><span data-stu-id="da2e1-176">Ref readonly locals</span></span>

<span data-ttu-id="da2e1-177">Wartość Ref Local ReadOnly jest używana do odwoływania się do wartości zwracanych przez metodę lub właściwość, która ma `ref readonly` w jej podpisie i używa `return ref` .</span><span class="sxs-lookup"><span data-stu-id="da2e1-177">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="da2e1-178">`ref readonly`Zmienna łączy właściwości `ref` zmiennej lokalnej ze `readonly` zmienną: jest to alias do magazynu, do którego jest przypisany, i nie może być modyfikowany.</span><span class="sxs-lookup"><span data-stu-id="da2e1-178">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="da2e1-179">Przykład odwołania ref i lokalne odwołania ref</span><span class="sxs-lookup"><span data-stu-id="da2e1-179">A ref returns and ref locals example</span></span>

<span data-ttu-id="da2e1-180">W poniższym przykładzie zdefiniowano `Book` klasę, która ma dwa <xref:System.String> pola `Title` i `Author` .</span><span class="sxs-lookup"><span data-stu-id="da2e1-180">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="da2e1-181">Definiuje również `BookCollection` klasę, która zawiera prywatną tablicę `Book` obiektów.</span><span class="sxs-lookup"><span data-stu-id="da2e1-181">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="da2e1-182">Poszczególne obiekty książek są zwracane przez odwołanie poprzez wywołanie `GetBookByTitle` metody.</span><span class="sxs-lookup"><span data-stu-id="da2e1-182">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="da2e1-183">Gdy obiekt wywołujący przechowuje wartość zwróconą przez `GetBookByTitle` metodę jako odwołanie lokalne, zmiany, które obiekt wywołujący wprowadza do wartości zwracanej, są odzwierciedlone w `BookCollection` obiekcie, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="da2e1-183">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="da2e1-184">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="da2e1-184">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da2e1-185">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="da2e1-185">See also</span></span>

- [<span data-ttu-id="da2e1-186">Zapisz bezpieczny wydajny kod</span><span class="sxs-lookup"><span data-stu-id="da2e1-186">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
- [<span data-ttu-id="da2e1-187">Wartości zwracane ref i zmienne lokalne ref</span><span class="sxs-lookup"><span data-stu-id="da2e1-187">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="da2e1-188">Wyrażenie warunkowe ref</span><span class="sxs-lookup"><span data-stu-id="da2e1-188">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="da2e1-189">Przekazywanie parametrów</span><span class="sxs-lookup"><span data-stu-id="da2e1-189">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)
- [<span data-ttu-id="da2e1-190">Parametry metody</span><span class="sxs-lookup"><span data-stu-id="da2e1-190">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="da2e1-191">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="da2e1-191">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="da2e1-192">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="da2e1-192">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="da2e1-193">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="da2e1-193">C# Keywords</span></span>](index.md)
