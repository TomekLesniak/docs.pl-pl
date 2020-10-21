---
title: Struktury
description: 'Dowiedz się więcej o strukturze języka F #, typ obiektu kompaktowego jest często bardziej wydajny niż Klasa dla typów z małą ilością danych i prostym zachowaniem.'
ms.date: 05/16/2016
ms.openlocfilehash: 1e9652cc4776e4d1d52eb20e41b6dd87a6c5ba05
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223825"
---
# <a name="structures"></a><span data-ttu-id="4b697-103">Struktury</span><span class="sxs-lookup"><span data-stu-id="4b697-103">Structures</span></span>

<span data-ttu-id="4b697-104">*Struktura* jest typem obiektu kompaktowego, który może być bardziej wydajny niż Klasa dla typów, które mają niewielką ilość danych i proste zachowanie.</span><span class="sxs-lookup"><span data-stu-id="4b697-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b697-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="4b697-105">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a><span data-ttu-id="4b697-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4b697-106">Remarks</span></span>

<span data-ttu-id="4b697-107">Struktury są *typami wartości*, co oznacza, że są przechowywane bezpośrednio na stosie lub, gdy są używane jako pola lub elementy tablicy, wbudowane w typie nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="4b697-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="4b697-108">W przeciwieństwie do klas i rekordów struktury mają semantykę typu pass-by-Value.</span><span class="sxs-lookup"><span data-stu-id="4b697-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="4b697-109">Oznacza to, że są one przydatne głównie w przypadku małych zagregowanych danych, do których często uzyskuje się dostęp i które są kopiowane.</span><span class="sxs-lookup"><span data-stu-id="4b697-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="4b697-110">W poprzedniej składni są wyświetlane dwa formularze.</span><span class="sxs-lookup"><span data-stu-id="4b697-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="4b697-111">Pierwsza nie jest prostą składnią, ale jest Niemniej często używana, ponieważ przy użyciu `struct` `end` słów kluczowych i można pominąć ten `StructAttribute` atrybut, który pojawia się w drugim formularzu.</span><span class="sxs-lookup"><span data-stu-id="4b697-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="4b697-112">Można skrócić `StructAttribute` do samego `Struct` .</span><span class="sxs-lookup"><span data-stu-id="4b697-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="4b697-113">*Definicja typu-elementy-i-Members* w poprzedniej składni reprezentuje deklaracje i definicje składowych.</span><span class="sxs-lookup"><span data-stu-id="4b697-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="4b697-114">Struktury mogą mieć konstruktory i modyfikowalne i niezmienne pola oraz mogą deklarować elementy członkowskie i implementacje interfejsów.</span><span class="sxs-lookup"><span data-stu-id="4b697-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="4b697-115">Aby uzyskać więcej informacji, zobacz [Członkowie](./members/index.md).</span><span class="sxs-lookup"><span data-stu-id="4b697-115">For more information, see [Members](./members/index.md).</span></span>

<span data-ttu-id="4b697-116">Struktury nie mogą uczestniczyć w dziedziczeniu, nie mogą zawierać `let` ani `do` powiązań ani rekursywnie zawierać pól własnego typu (chociaż mogą zawierać komórki odniesienia odwołujące się do własnego typu).</span><span class="sxs-lookup"><span data-stu-id="4b697-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="4b697-117">Ponieważ struktury nie zezwalają na `let` powiązania, należy zadeklarować pola w strukturach za pomocą `val` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="4b697-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="4b697-118">`val`Słowo kluczowe definiuje pole i jego typ, ale nie zezwala na inicjalizację.</span><span class="sxs-lookup"><span data-stu-id="4b697-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="4b697-119">Zamiast tego `val` deklaracje są inicjowane do zera lub wartości null.</span><span class="sxs-lookup"><span data-stu-id="4b697-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="4b697-120">Z tego powodu struktury, które mają niejawny Konstruktor (czyli parametry, które są nadawane bezpośrednio po nazwie struktury w deklaracji), wymagają, aby `val` deklaracje miały adnotację z `DefaultValue` atrybutem.</span><span class="sxs-lookup"><span data-stu-id="4b697-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="4b697-121">Struktury, które mają zdefiniowany Konstruktor nadal obsługują inicjowanie zerowe.</span><span class="sxs-lookup"><span data-stu-id="4b697-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="4b697-122">W związku z tym `DefaultValue` atrybut jest deklaracją, że ta wartość zerowa jest prawidłowa dla pola.</span><span class="sxs-lookup"><span data-stu-id="4b697-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="4b697-123">Niejawne konstruktory struktur nie wykonują żadnych akcji, ponieważ nie `let` `do` są dozwolone powiązania z typem, ale niejawne wartości parametrów konstruktora są dostępne jako pola prywatne.</span><span class="sxs-lookup"><span data-stu-id="4b697-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="4b697-124">Jawne konstruktory mogą polegać na inicjacji wartości pól.</span><span class="sxs-lookup"><span data-stu-id="4b697-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="4b697-125">Jeśli masz strukturę, która ma jawny Konstruktor, nadal obsługuje inicjowanie zerujące; nie należy jednak używać `DefaultValue` atrybutu w `val` deklaracjach, ponieważ powoduje on konflikt z konstruktorem jawnym.</span><span class="sxs-lookup"><span data-stu-id="4b697-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="4b697-126">Aby uzyskać więcej informacji na temat `val` deklaracji, zobacz [jawne pola: `val` słowo kluczowe](./members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="4b697-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="4b697-127">Atrybuty i Modyfikatory dostępności są dozwolone w strukturach i są zgodne z tymi samymi regułami dla innych typów.</span><span class="sxs-lookup"><span data-stu-id="4b697-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="4b697-128">Aby uzyskać więcej informacji, zobacz [atrybuty](attributes.md) i [Access Control](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="4b697-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="4b697-129">Poniższe przykłady kodu ilustrują definicje struktury.</span><span class="sxs-lookup"><span data-stu-id="4b697-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="4b697-130">Struktury ByRefLike</span><span class="sxs-lookup"><span data-stu-id="4b697-130">ByRefLike structs</span></span>

<span data-ttu-id="4b697-131">Można definiować własne struktury, które mogą przestrzegać `byref` podobnej semantyki: Aby uzyskać więcej informacji, zobacz [ByRef](byrefs.md) .</span><span class="sxs-lookup"><span data-stu-id="4b697-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="4b697-132">Jest to realizowane z <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> atrybutem:</span><span class="sxs-lookup"><span data-stu-id="4b697-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="4b697-133">`IsByRefLike` nie oznacza `Struct` .</span><span class="sxs-lookup"><span data-stu-id="4b697-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="4b697-134">Oba muszą być obecne w typie.</span><span class="sxs-lookup"><span data-stu-id="4b697-134">Both must be present on the type.</span></span>

<span data-ttu-id="4b697-135">Struktura " `byref` like" w języku F # jest typem wartości powiązanej ze stosem.</span><span class="sxs-lookup"><span data-stu-id="4b697-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="4b697-136">Nigdy nie jest przydzielany na zarządzanym stosie.</span><span class="sxs-lookup"><span data-stu-id="4b697-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="4b697-137">`byref`Struktura przypominająca podobne rozwiązanie jest przydatna w programowaniu o wysokiej wydajności, ponieważ jest wymuszana z zestawem silnych sprawdzeń i bez przechwycenia.</span><span class="sxs-lookup"><span data-stu-id="4b697-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="4b697-138">Reguły są następujące:</span><span class="sxs-lookup"><span data-stu-id="4b697-138">The rules are:</span></span>

- <span data-ttu-id="4b697-139">Mogą one być używane jako parametry funkcji, parametry metody, zmienne lokalne, Metoda Return.</span><span class="sxs-lookup"><span data-stu-id="4b697-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
- <span data-ttu-id="4b697-140">Nie mogą być statyczne ani składowe wystąpień klasy ani normalnej struktury.</span><span class="sxs-lookup"><span data-stu-id="4b697-140">They cannot be static or instance members of a class or normal struct.</span></span>
- <span data-ttu-id="4b697-141">Nie mogą być przechwytywane przez żadną konstrukcję zamknięcia ( `async` metody lub wyrażenia lambda).</span><span class="sxs-lookup"><span data-stu-id="4b697-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
- <span data-ttu-id="4b697-142">Nie mogą być używane jako parametr generyczny.</span><span class="sxs-lookup"><span data-stu-id="4b697-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="4b697-143">Chociaż te reguły bardzo zdecydowanie ograniczają użycie, robią to w celu zapewnienia bezpieczeństwa obliczeń o wysokiej wydajności w bezpieczny sposób.</span><span class="sxs-lookup"><span data-stu-id="4b697-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="4b697-144">Struktury tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4b697-144">ReadOnly structs</span></span>

<span data-ttu-id="4b697-145">Można dodawać adnotacje do struktur przy użyciu <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="4b697-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="4b697-146">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="4b697-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="4b697-147">`IsReadOnly` nie oznacza `Struct` .</span><span class="sxs-lookup"><span data-stu-id="4b697-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="4b697-148">Musisz dodać oba, aby mieć `IsReadOnly` strukturę.</span><span class="sxs-lookup"><span data-stu-id="4b697-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="4b697-149">Użycie tego atrybutu emituje metadane, dzięki czemu F # i C# wiedzą, że odpowiednio traktuje ją jako `inref<'T>` i `in ref` .</span><span class="sxs-lookup"><span data-stu-id="4b697-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="4b697-150">Zdefiniowanie wartości modyfikowalnej wewnątrz struktury tylko do odczytu powoduje wystąpienie błędu.</span><span class="sxs-lookup"><span data-stu-id="4b697-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="4b697-151">Rekordy struktury i związki rozłącznych</span><span class="sxs-lookup"><span data-stu-id="4b697-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="4b697-152">[Rekordy](records.md) i [związki rozłącznych](discriminated-unions.md) można reprezentować jako struktury z `[<Struct>]` atrybutem.</span><span class="sxs-lookup"><span data-stu-id="4b697-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="4b697-153">Aby dowiedzieć się więcej, zobacz każdy artykuł.</span><span class="sxs-lookup"><span data-stu-id="4b697-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b697-154">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4b697-154">See also</span></span>

- [<span data-ttu-id="4b697-155">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="4b697-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="4b697-156">Klasy</span><span class="sxs-lookup"><span data-stu-id="4b697-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="4b697-157">Rekordy</span><span class="sxs-lookup"><span data-stu-id="4b697-157">Records</span></span>](records.md)
- [<span data-ttu-id="4b697-158">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="4b697-158">Members</span></span>](./members/index.md)
