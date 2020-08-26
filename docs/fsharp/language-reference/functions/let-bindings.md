---
title: let — Powiązania
description: 'Dowiedz się, jak używać powiązania "let" języka F #, które kojarzy identyfikator z wartością lub funkcją.'
ms.date: 05/16/2016
ms.openlocfilehash: 6f2396f480c5e6c631d0022f4732419ee5b07db6
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812227"
---
# <a name="let-bindings"></a><span data-ttu-id="622aa-103">let — Powiązania</span><span class="sxs-lookup"><span data-stu-id="622aa-103">let Bindings</span></span>

<span data-ttu-id="622aa-104">*Powiązanie* kojarzy identyfikator z wartością lub funkcją.</span><span class="sxs-lookup"><span data-stu-id="622aa-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="622aa-105">Użyj `let` słowa kluczowego, aby powiązać nazwę z wartością lub funkcją.</span><span class="sxs-lookup"><span data-stu-id="622aa-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="622aa-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="622aa-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="622aa-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="622aa-107">Remarks</span></span>

<span data-ttu-id="622aa-108">`let`Słowo kluczowe jest używane w wyrażeniach wiązania do definiowania wartości lub wartości funkcji dla co najmniej jednej nazwy.</span><span class="sxs-lookup"><span data-stu-id="622aa-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="622aa-109">Najprostsza forma `let` wyrażenia wiąże nazwę z prostą wartością w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="622aa-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="622aa-110">Jeśli wyrażenie jest oddzielane od identyfikatora przy użyciu nowego wiersza, należy wciąć każdy wiersz wyrażenia, tak jak w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="622aa-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="622aa-111">Zamiast tylko nazwy, wzorzec zawierający nazwy można określić na przykład krotka, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="622aa-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="622aa-112">*Wyrażenie Body* jest wyrażeniem, w którym są używane nazwy.</span><span class="sxs-lookup"><span data-stu-id="622aa-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="622aa-113">Wyrażenie treści jest wyświetlane w osobnym wierszu, wcięcie w celu podzielenia dokładnie z pierwszym znakiem `let` słowa kluczowego:</span><span class="sxs-lookup"><span data-stu-id="622aa-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="622aa-114">`let`Powiązanie może być wyświetlane na poziomie modułu, w definicji typu klasy lub w lokalnych zakresach, takich jak w definicji funkcji.</span><span class="sxs-lookup"><span data-stu-id="622aa-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="622aa-115">`let`Powiązanie na najwyższym poziomie modułu lub w typie klasy nie musi mieć wyrażenia Body, ale na innych poziomach zakresu wyrażenie treści jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="622aa-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="622aa-116">Nazwy powiązane są użyteczne po punkcie definicji, ale nie w żadnym punkcie przed `let` wyświetleniem powiązania, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="622aa-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="622aa-117">Powiązania funkcji</span><span class="sxs-lookup"><span data-stu-id="622aa-117">Function Bindings</span></span>

<span data-ttu-id="622aa-118">Powiązania funkcji są zgodne z regułami dotyczącymi powiązań wartości, z tą różnicą, że powiązania funkcji zawierają nazwę funkcji i parametry, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="622aa-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="622aa-119">Ogólnie rzecz biorąc, parametry są wzorcami, takimi jak wzorzec krotki:</span><span class="sxs-lookup"><span data-stu-id="622aa-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="622aa-120">`let`Wyrażenie powiązania daje w wyniku wartość ostatniego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="622aa-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="622aa-121">W związku z tym, w poniższym przykładzie kodu, wartość `result` jest obliczana z `100 * function3 (1, 2)` , która daje w wyniku `300` .</span><span class="sxs-lookup"><span data-stu-id="622aa-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="622aa-122">Aby uzyskać więcej informacji, zobacz [Functions](index.md).</span><span class="sxs-lookup"><span data-stu-id="622aa-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="622aa-123">Adnotacje typu</span><span class="sxs-lookup"><span data-stu-id="622aa-123">Type Annotations</span></span>

<span data-ttu-id="622aa-124">Można określić typy parametrów, dołączając dwukropek (:) po którym następuje nazwa typu, wszystkie zawarte w nawiasach.</span><span class="sxs-lookup"><span data-stu-id="622aa-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="622aa-125">Można również określić typ wartości zwracanej przez dołączenie dwukropka i typu po ostatnim parametrze.</span><span class="sxs-lookup"><span data-stu-id="622aa-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="622aa-126">Pełne adnotacje typu dla `function1` , z liczbami całkowitymi jako typy parametrów, byłyby następujące.</span><span class="sxs-lookup"><span data-stu-id="622aa-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="622aa-127">Jeśli nie ma żadnych jawnych parametrów typu, wnioskowanie typu jest używane do określenia typów parametrów funkcji.</span><span class="sxs-lookup"><span data-stu-id="622aa-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="622aa-128">Może to obejmować automatyczne uogólnianie typu parametru, który ma być ogólny.</span><span class="sxs-lookup"><span data-stu-id="622aa-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="622aa-129">Aby uzyskać więcej informacji, zobacz [Automatyczne uogólnianie](../generics/automatic-generalization.md) i [wnioskowanie o typie](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="622aa-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="622aa-130">Powiązania let w klasach</span><span class="sxs-lookup"><span data-stu-id="622aa-130">let Bindings in Classes</span></span>

<span data-ttu-id="622aa-131">`let`Powiązanie może pojawić się w typie klasy, ale nie w typie struktury lub rekordu.</span><span class="sxs-lookup"><span data-stu-id="622aa-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="622aa-132">Aby można było użyć powiązania let w typie klasy, Klasa musi mieć konstruktora podstawowego.</span><span class="sxs-lookup"><span data-stu-id="622aa-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="622aa-133">Parametry konstruktora muszą występować po nazwie typu w definicji klasy.</span><span class="sxs-lookup"><span data-stu-id="622aa-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="622aa-134">`let`Powiązanie w typie klasy definiuje prywatne pola i elementy członkowskie dla tego typu klasy oraz, wraz z `do` powiązaniami w typie, tworzy kod dla głównego konstruktora typu.</span><span class="sxs-lookup"><span data-stu-id="622aa-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="622aa-135">Poniższe przykłady kodu przedstawiają klasę `MyClass` z polami prywatnymi `field1` i `field2` .</span><span class="sxs-lookup"><span data-stu-id="622aa-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="622aa-136">Zakresy `field1` i `field2` są ograniczone do typu, w którym są zadeklarowane.</span><span class="sxs-lookup"><span data-stu-id="622aa-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="622aa-137">Aby uzyskać więcej informacji, zobacz [ `let` powiązania w klasach](../members/let-bindings-in-classes.md) i [klasach](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="622aa-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="622aa-138">Parametry typu w programie Let bindings</span><span class="sxs-lookup"><span data-stu-id="622aa-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="622aa-139">`let`Powiązanie na poziomie modułu, w typie lub w wyrażeniu obliczeniowym może mieć jawne parametry typu.</span><span class="sxs-lookup"><span data-stu-id="622aa-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="622aa-140">Powiązanie let w wyrażeniu, takie jak w definicji funkcji, nie może mieć parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="622aa-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="622aa-141">Aby uzyskać więcej informacji, zobacz [Ogólne](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="622aa-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="622aa-142">Atrybuty dla powiązań Let</span><span class="sxs-lookup"><span data-stu-id="622aa-142">Attributes on let Bindings</span></span>

<span data-ttu-id="622aa-143">Atrybuty mogą być stosowane do powiązań najwyższego poziomu `let` w module, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="622aa-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="622aa-144">Zakres i dostępność powiązań Let</span><span class="sxs-lookup"><span data-stu-id="622aa-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="622aa-145">Zakres jednostki zadeklarowanej za pomocą powiązania Let jest ograniczony do części zawierającego ją zakresu (na przykład funkcji, modułu, pliku lub klasy) po wyświetleniu powiązania.</span><span class="sxs-lookup"><span data-stu-id="622aa-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="622aa-146">W związku z tym może być uważany, że powiązanie Let wprowadza nazwę do zakresu.</span><span class="sxs-lookup"><span data-stu-id="622aa-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="622aa-147">W module, wartość lub funkcja, którą można powiązać, jest dostępna dla klientów modułu, o ile moduł jest dostępny, ponieważ powiązania let w module są kompilowane do funkcji publicznych modułu.</span><span class="sxs-lookup"><span data-stu-id="622aa-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="622aa-148">Z kolei należy zezwolić na powiązania w klasie z klasą.</span><span class="sxs-lookup"><span data-stu-id="622aa-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="622aa-149">Zwykle funkcje w modułach muszą być kwalifikowane według nazwy modułu, gdy są używane przez kod klienta.</span><span class="sxs-lookup"><span data-stu-id="622aa-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="622aa-150">Na przykład jeśli moduł `Module1` zawiera funkcję `function1` , użytkownicy mogą odwoływać się do `Module1.function1` funkcji.</span><span class="sxs-lookup"><span data-stu-id="622aa-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="622aa-151">Użytkownicy modułu mogą używać deklaracji importu, aby udostępnić funkcje w ramach tego modułu bez zakwalifikowania nazwy modułu.</span><span class="sxs-lookup"><span data-stu-id="622aa-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="622aa-152">W takim przykładzie użytkownicy modułu mogą w tym przypadku otworzyć moduł przy użyciu otwartej deklaracji import, `Module1` a następnie odwołać się bezpośrednio do niego `function1` .</span><span class="sxs-lookup"><span data-stu-id="622aa-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

<span data-ttu-id="622aa-153">Niektóre moduły mają atrybut [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html), co oznacza, że funkcje, które uwidaczniają, muszą być kwalifikowane przy użyciu nazwy modułu.</span><span class="sxs-lookup"><span data-stu-id="622aa-153">Some modules have the attribute [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="622aa-154">Na przykład moduł listy języka F # ma ten atrybut.</span><span class="sxs-lookup"><span data-stu-id="622aa-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="622aa-155">Aby uzyskać więcej informacji na temat modułów i kontroli dostępu, zobacz [moduły](../modules.md) i [Access Control](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="622aa-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="622aa-156">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="622aa-156">See also</span></span>

- [<span data-ttu-id="622aa-157">Funkcje</span><span class="sxs-lookup"><span data-stu-id="622aa-157">Functions</span></span>](index.md)
- [<span data-ttu-id="622aa-158">`let` Powiązania w klasach</span><span class="sxs-lookup"><span data-stu-id="622aa-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
