---
title: Typy wskaźników — Przewodnik programowania w języku C#
description: Dowiedz się więcej o typach wskaźników. Zobacz przykłady różnych wskaźników, przykłady kodu i wyświetlanie dodatkowych dostępnych zasobów.
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 9c62a31f9a4a090fe56fb10ac45fe2f93f1b036e
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382038"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="b6a4d-104">Typy wskaźników (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="b6a4d-104">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="b6a4d-105">W kontekście słowa kluczowego „unsafe” typ może być typem wskaźnika, typem wartości lub typem referencyjnym.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-105">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="b6a4d-106">Deklaracja typu wskaźnika ma jedną z następujących form:</span><span class="sxs-lookup"><span data-stu-id="b6a4d-106">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="b6a4d-107">Typ określony przed typem `*` wskaźnika jest nazywany **typem referent**.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-107">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="b6a4d-108">Tylko [Typ niezarządzany](../../language-reference/builtin-types/unmanaged-types.md) może być typem referent.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-108">Only an [unmanaged type](../../language-reference/builtin-types/unmanaged-types.md) can be a referent type.</span></span>

<span data-ttu-id="b6a4d-109">Typy wskaźnika nie dziedziczą z [obiektu](../../language-reference/builtin-types/reference-types.md) i nie istnieją konwersje między typami wskaźnika i `object` .</span><span class="sxs-lookup"><span data-stu-id="b6a4d-109">Pointer types do not inherit from [object](../../language-reference/builtin-types/reference-types.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="b6a4d-110">Ponadto wskaźniki nie są obsługiwane w przypadku opakowywania i rozpakowywania.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-110">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="b6a4d-111">Można jednak wykonywać konwersje między różnymi typami wskaźnika oraz między typami wskaźnika a typami całkowitymi.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-111">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="b6a4d-112">W przypadku deklarowania wielu wskaźników w jednej deklaracji gwiazdka (\*) jest pisana razem tylko z typem podstawowym; nie jest używana jako prefiks każdej nazwy wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-112">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="b6a4d-113">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="b6a4d-113">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="b6a4d-114">Wskaźnik nie może wskazywać odwołania lub [struktury](../../language-reference/builtin-types/struct.md) , która zawiera odwołania, ponieważ odwołanie do obiektu może być odzyskiwane nawet wtedy, gdy wskaźnik wskazuje go.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-114">A pointer cannot point to a reference or to a [struct](../../language-reference/builtin-types/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="b6a4d-115">Moduł odśmiecania pamięci nie sprawdza, czy obiekt jest wskazywany przez jakiś wskaźnik.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-115">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="b6a4d-116">Wartość zmiennej wskaźnika typu `myType*` jest adresem zmiennej typu `myType` .</span><span class="sxs-lookup"><span data-stu-id="b6a4d-116">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="b6a4d-117">Poniżej przedstawiono przykłady deklaracji typów wskaźnika:</span><span class="sxs-lookup"><span data-stu-id="b6a4d-117">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="b6a4d-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="b6a4d-118">Example</span></span>|<span data-ttu-id="b6a4d-119">Opis</span><span class="sxs-lookup"><span data-stu-id="b6a4d-119">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="b6a4d-120">`p`jest wskaźnikiem do liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-120">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="b6a4d-121">`p`jest wskaźnikiem do wskaźnika do liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-121">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="b6a4d-122">`p`to Jednowymiarowa tablica wskaźników do liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-122">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="b6a4d-123">`p`jest wskaźnikiem do znaku.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-123">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="b6a4d-124">`p`jest wskaźnikiem do nieznanego typu.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-124">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="b6a4d-125">Operatora pośredniego wskaźnika \* można użyć w celu uzyskania dostępu do zawartości znajdującej się w lokalizacji wskazywanej przez zmienną wskaźnikową.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-125">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="b6a4d-126">Na przykład przeanalizujmy następującą deklarację:</span><span class="sxs-lookup"><span data-stu-id="b6a4d-126">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="b6a4d-127">Wyrażenie `*myVariable` oznacza `int` zmienną znalezioną w adresie zawartym w `myVariable` .</span><span class="sxs-lookup"><span data-stu-id="b6a4d-127">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="b6a4d-128">Kilka przykładów wskaźników znajduje się w tematach [stałych instrukcja](../../language-reference/keywords/fixed-statement.md) i [konwersje wskaźnika](./pointer-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="b6a4d-128">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](./pointer-conversions.md).</span></span> <span data-ttu-id="b6a4d-129">Poniższy przykład używa `unsafe` słowa kluczowego i `fixed` instrukcji oraz pokazuje, jak zwiększyć wewnętrzny wskaźnik.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-129">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="b6a4d-130">Ten kod można wkleić do funkcji Main aplikacji konsoli, aby go uruchomić.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-130">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="b6a4d-131">Te przykłady muszą zostać skompilowane przy użyciu [-niebezpiecznego](../../language-reference/compiler-options/unsafe-compiler-option.md) zestawu opcji kompilatora.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-131">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](snippets/FixedKeywordExamples.cs#5)]

<span data-ttu-id="b6a4d-132">Nie można zastosować operatora pośredni do wskaźnika typu `void*` .</span><span class="sxs-lookup"><span data-stu-id="b6a4d-132">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="b6a4d-133">Można jednak użyć rzutowania, aby przekonwertować wskaźnik typu void na wskaźnik dowolnego innego typu i odwrotnie.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-133">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="b6a4d-134">Wskaźnik może być `null` .</span><span class="sxs-lookup"><span data-stu-id="b6a4d-134">A pointer can be `null`.</span></span> <span data-ttu-id="b6a4d-135">Zastosowanie operatora pośredniego do wskaźnika o wartości null powoduje użycie zachowania zdefiniowanego w implementacji.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-135">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="b6a4d-136">Przekazywanie wskaźników między metodami może spowodować niezdefiniowane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-136">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="b6a4d-137">Rozważmy metodę, która zwraca wskaźnik do zmiennej lokalnej za pomocą `in` parametru, `out` , lub, `ref` jako wyniku funkcji.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-137">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="b6a4d-138">Jeśli wskaźnik został ustawiony w stałym bloku, wskazywana przez niego zmienna może już nie być stała.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-138">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="b6a4d-139">W poniższej tabeli wymieniono operatory i instrukcje, które mogą wykonywać operacje na wskaźnikach w kontekście słowa kluczowego „unsafe”:</span><span class="sxs-lookup"><span data-stu-id="b6a4d-139">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="b6a4d-140">Operator/instrukcja</span><span class="sxs-lookup"><span data-stu-id="b6a4d-140">Operator/Statement</span></span>|<span data-ttu-id="b6a4d-141">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="b6a4d-141">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="b6a4d-142">Wykonuje operację wskaźnika pośredniego.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-142">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="b6a4d-143">Uzyskuje dostęp do elementu członkowskiego struktury za pomocą wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-143">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="b6a4d-144">Indeksuje wskaźnik.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-144">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="b6a4d-145">Uzyskuje adres zmiennej.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-145">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="b6a4d-146">`++` i `--`</span><span class="sxs-lookup"><span data-stu-id="b6a4d-146">`++` and `--`</span></span>|<span data-ttu-id="b6a4d-147">Zwiększa i zmniejsza wartość wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-147">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="b6a4d-148">`+` i `-`</span><span class="sxs-lookup"><span data-stu-id="b6a4d-148">`+` and `-`</span></span>|<span data-ttu-id="b6a4d-149">Wykonuje operacje arytmetyczne na wskaźniku.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-149">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="b6a4d-150">`==`, `!=` , `<` , `>` , `<=` i`>=`</span><span class="sxs-lookup"><span data-stu-id="b6a4d-150">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="b6a4d-151">Porównuje wskaźniki.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-151">Compares pointers.</span></span>|
|[`stackalloc`](../../language-reference/operators/stackalloc.md)|<span data-ttu-id="b6a4d-152">Przydziela pamięć na stosie.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-152">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="b6a4d-153">`fixed`Merge</span><span class="sxs-lookup"><span data-stu-id="b6a4d-153">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="b6a4d-154">Tymczasowo ustala zmienną, dzięki czemu można znaleźć ten adres.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-154">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="b6a4d-155">Aby uzyskać więcej informacji na temat operatorów powiązanych ze wskaźnikiem, zobacz temat [Operatory powiązane z wskaźnikiem](../../language-reference/operators/pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="b6a4d-155">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b6a4d-156">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="b6a4d-156">C# language specification</span></span>

<span data-ttu-id="b6a4d-157">Aby uzyskać więcej informacji, zobacz sekcję [typy wskaźników](~/_csharplang/spec/unsafe-code.md#pointer-types) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b6a4d-157">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6a4d-158">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b6a4d-158">See also</span></span>

- [<span data-ttu-id="b6a4d-159">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="b6a4d-159">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b6a4d-160">Niebezpieczny kod i wskaźniki</span><span class="sxs-lookup"><span data-stu-id="b6a4d-160">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="b6a4d-161">Konwersje wskaźników</span><span class="sxs-lookup"><span data-stu-id="b6a4d-161">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="b6a4d-162">Typy odwołań</span><span class="sxs-lookup"><span data-stu-id="b6a4d-162">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="b6a4d-163">Typy wartości</span><span class="sxs-lookup"><span data-stu-id="b6a4d-163">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="b6a4d-164">niebezpieczne</span><span class="sxs-lookup"><span data-stu-id="b6a4d-164">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
