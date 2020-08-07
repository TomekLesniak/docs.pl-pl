---
title: Operatory powiązane ze wskaźnikiem — odwołanie w C#
description: Dowiedz się więcej na temat operatorów języka C#, których można używać podczas pracy ze wskaźnikami.
ms.date: 05/20/2019
author: pkulikov
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- pointer related operators [C#]
- address-of operator [C#]
- '& operator [C#]'
- pointer indirection operator [C#]
- dereference operator [C#]
- '* operator [C#]'
- pointer member access operator [C#]
- -> operator [C#]
- pointer element access [C#]
- '[] operator [C#]'
- pointer arithmetic [C#]
- pointer increment [C#]
- pointer decrement [C#]
- pointer comparison [C#]
ms.openlocfilehash: 3728778b31a4b4adc51933e8fdc6287f28e03d83
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916715"
---
# <a name="pointer-related-operators-c-reference"></a><span data-ttu-id="0acb1-103">Operatory pokrewne wskaźnika (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="0acb1-103">Pointer related operators (C# reference)</span></span>

<span data-ttu-id="0acb1-104">Można użyć następujących operatorów do pracy ze wskaźnikami:</span><span class="sxs-lookup"><span data-stu-id="0acb1-104">You can use the following operators to work with pointers:</span></span>

- <span data-ttu-id="0acb1-105">Operator jednoargumentowy [ `&` (Address-of)](#address-of-operator-) : Aby uzyskać adres zmiennej</span><span class="sxs-lookup"><span data-stu-id="0acb1-105">Unary [`&` (address-of)](#address-of-operator-) operator: to get the address of a variable</span></span>
- <span data-ttu-id="0acb1-106">Operator jednoargumentowy [ `*` (pośredni wskaźnik)](#pointer-indirection-operator-) : Aby uzyskać zmienną wskazywaną przez wskaźnik</span><span class="sxs-lookup"><span data-stu-id="0acb1-106">Unary [`*` (pointer indirection)](#pointer-indirection-operator-) operator: to obtain the variable pointed by a pointer</span></span>
- <span data-ttu-id="0acb1-107">Operatory [ `->` (dostęp do elementów członkowskich)](#pointer-member-access-operator--) i [ `[]` (dostęp do elementów)](#pointer-element-access-operator-)</span><span class="sxs-lookup"><span data-stu-id="0acb1-107">The [`->` (member access)](#pointer-member-access-operator--) and [`[]` (element access)](#pointer-element-access-operator-) operators</span></span>
- <span data-ttu-id="0acb1-108">Operatory arytmetyczne [ `+` , `-` , `++` i `--` ](#pointer-arithmetic-operators)</span><span class="sxs-lookup"><span data-stu-id="0acb1-108">Arithmetic operators [`+`, `-`, `++`, and `--`](#pointer-arithmetic-operators)</span></span>
- <span data-ttu-id="0acb1-109">Operatory porównania,,,, [ `==` `!=` `<` `>` `<=` i `>=` ](#pointer-comparison-operators)</span><span class="sxs-lookup"><span data-stu-id="0acb1-109">Comparison operators [`==`, `!=`, `<`, `>`, `<=`, and `>=`](#pointer-comparison-operators)</span></span>

<span data-ttu-id="0acb1-110">Aby uzyskać informacje na temat typów wskaźnikowych, zobacz [typy wskaźnika](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="0acb1-110">For information about pointer types, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0acb1-111">Wszystkie operacje ze wskaźnikami wymagają [niebezpiecznego](../keywords/unsafe.md) kontekstu.</span><span class="sxs-lookup"><span data-stu-id="0acb1-111">Any operation with pointers requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="0acb1-112">Kod, który zawiera niebezpieczne bloki, musi być skompilowany przy użyciu [`-unsafe`](../compiler-options/unsafe-compiler-option.md) opcji kompilatora.</span><span class="sxs-lookup"><span data-stu-id="0acb1-112">The code that contains unsafe blocks must be compiled with the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

## <a name="address-of-operator-amp"></a><a name="address-of-operator-"></a><span data-ttu-id="0acb1-113">Operator address-of&amp;</span><span class="sxs-lookup"><span data-stu-id="0acb1-113">Address-of operator &amp;</span></span>

<span data-ttu-id="0acb1-114">Operator jednoargumentowy `&` zwraca adres tego operandu:</span><span class="sxs-lookup"><span data-stu-id="0acb1-114">The unary `&` operator returns the address of its operand:</span></span>

[!code-csharp[address of local](snippets/shared/PointerOperators.cs#AddressOf)]

<span data-ttu-id="0acb1-115">Operand `&` operatora musi być zmienną stałą.</span><span class="sxs-lookup"><span data-stu-id="0acb1-115">The operand of the `&` operator must be a fixed variable.</span></span> <span data-ttu-id="0acb1-116">Zmienne *stałe* są zmiennymi, które znajdują się w lokalizacjach magazynu, które nie mają wpływ na działanie [modułu wyrzucania elementów bezużytecznych](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="0acb1-116">*Fixed* variables are variables that reside in storage locations that are unaffected by operation of the [garbage collector](../../../standard/garbage-collection/index.md).</span></span> <span data-ttu-id="0acb1-117">W poprzednim przykładzie zmienna lokalna `number` to stała zmienna, ponieważ znajduje się ona na stosie.</span><span class="sxs-lookup"><span data-stu-id="0acb1-117">In the preceding example, the local variable `number` is a fixed variable, because it resides on the stack.</span></span> <span data-ttu-id="0acb1-118">Zmienne, które znajdują się w lokalizacjach magazynu, na które może mieć wpływ Moduł wyrzucania elementów bezużytecznych (na przykład rezlokalizowane), *są nazywane* zmiennymi zmiennych.</span><span class="sxs-lookup"><span data-stu-id="0acb1-118">Variables that reside in storage locations that can be affected by the garbage collector (for example, relocated) are called *movable* variables.</span></span> <span data-ttu-id="0acb1-119">Pola obiektów i elementy tablicy to przykłady ruchomych zmiennych.</span><span class="sxs-lookup"><span data-stu-id="0acb1-119">Object fields and array elements are examples of movable variables.</span></span> <span data-ttu-id="0acb1-120">Adres ruchomej zmiennej można pobrać, jeśli "Napraw" lub "PIN", za pomocą [ `fixed` instrukcji](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0acb1-120">You can get the address of a movable variable if you "fix", or "pin", it with a [`fixed` statement](../keywords/fixed-statement.md).</span></span> <span data-ttu-id="0acb1-121">Uzyskany adres jest prawidłowy tylko wewnątrz bloku `fixed` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="0acb1-121">The obtained address is valid only inside the block of a `fixed` statement.</span></span> <span data-ttu-id="0acb1-122">Poniższy przykład pokazuje, jak używać `fixed` instrukcji i `&` operatora:</span><span class="sxs-lookup"><span data-stu-id="0acb1-122">The following example shows how to use a `fixed` statement and the `&` operator:</span></span>

[!code-csharp[address of fixed](snippets/shared/PointerOperators.cs#AddressOfFixed)]

<span data-ttu-id="0acb1-123">Nie można uzyskać adresu stałej ani wartości.</span><span class="sxs-lookup"><span data-stu-id="0acb1-123">You can't get the address of a constant or a value.</span></span>

<span data-ttu-id="0acb1-124">Aby uzyskać więcej informacji na temat zmiennych stałych i przenośnych, zobacz sekcję [zmienne stałe i ruchome](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0acb1-124">For more information about fixed and movable variables, see the [Fixed and moveable variables](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="0acb1-125">Operator binarny `&` oblicza wartość [logiczną i](boolean-logical-operators.md#logical-and-operator-) jej operandy logiczne oraz [koniunkcję bitową i](bitwise-and-shift-operators.md#logical-and-operator-) jej całkowite argumenty operacji.</span><span class="sxs-lookup"><span data-stu-id="0acb1-125">The binary `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its Boolean operands or the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its integral operands.</span></span>

## <a name="pointer-indirection-operator-"></a><span data-ttu-id="0acb1-126">Operator pośredni wskaźnika \*</span><span class="sxs-lookup"><span data-stu-id="0acb1-126">Pointer indirection operator \*</span></span>

<span data-ttu-id="0acb1-127">Operator operatora bezoperatorowego pośredni `*` uzyskuje zmienną, do której odwołuje się argument operacji.</span><span class="sxs-lookup"><span data-stu-id="0acb1-127">The unary pointer indirection operator `*` obtains the variable to which its operand points.</span></span> <span data-ttu-id="0acb1-128">Jest on również znany jako operator dereferencji.</span><span class="sxs-lookup"><span data-stu-id="0acb1-128">It's also known as the dereference operator.</span></span> <span data-ttu-id="0acb1-129">Operand `*` operatora musi być typu wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="0acb1-129">The operand of the `*` operator must be of a pointer type.</span></span>

[!code-csharp[pointer indirection](snippets/shared/PointerOperators.cs#PointerIndirection)]

<span data-ttu-id="0acb1-130">Nie można zastosować `*` operatora do wyrażenia typu `void*` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-130">You cannot apply the `*` operator to an expression of type `void*`.</span></span>

<span data-ttu-id="0acb1-131">Operator binarny `*` oblicza [iloczyn](arithmetic-operators.md#multiplication-operator-) argumentów liczbowych.</span><span class="sxs-lookup"><span data-stu-id="0acb1-131">The binary `*` operator computes the [product](arithmetic-operators.md#multiplication-operator-) of its numeric operands.</span></span>

## <a name="pointer-member-access-operator--"></a><span data-ttu-id="0acb1-132">Operator dostępu do elementów członkowskich wskaźnika — ></span><span class="sxs-lookup"><span data-stu-id="0acb1-132">Pointer member access operator -></span></span>

<span data-ttu-id="0acb1-133">`->`Operator łączy [pośredni wskaźnik](#pointer-indirection-operator-) i [dostęp do elementów członkowskich](member-access-operators.md#member-access-expression-).</span><span class="sxs-lookup"><span data-stu-id="0acb1-133">The `->` operator combines [pointer indirection](#pointer-indirection-operator-) and [member access](member-access-operators.md#member-access-expression-).</span></span> <span data-ttu-id="0acb1-134">Oznacza to, że jeśli `x` jest wskaźnikiem typu `T*` i `y` jest dostępnym elementem członkowskim typu `T` , wyrażenie formularza</span><span class="sxs-lookup"><span data-stu-id="0acb1-134">That is, if `x` is a pointer of type `T*` and `y` is an accessible member of type `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="0acb1-135">jest równoważny</span><span class="sxs-lookup"><span data-stu-id="0acb1-135">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="0acb1-136">Poniższy przykład ilustruje użycie `->` operatora:</span><span class="sxs-lookup"><span data-stu-id="0acb1-136">The following example demonstrates the usage of the `->` operator:</span></span>

[!code-csharp[pointer member access](snippets/shared/PointerOperators.cs#MemberAccess)]

<span data-ttu-id="0acb1-137">Nie można zastosować `->` operatora do wyrażenia typu `void*` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-137">You cannot apply the `->` operator to an expression of type `void*`.</span></span>

## <a name="pointer-element-access-operator-"></a><span data-ttu-id="0acb1-138">Operator dostępu do elementów wskaźnika []</span><span class="sxs-lookup"><span data-stu-id="0acb1-138">Pointer element access operator []</span></span>

<span data-ttu-id="0acb1-139">Dla wyrażenia `p` typu wskaźnika dostęp do elementu wskaźnika `p[n]` jest oceniany jako `*(p + n)` , gdzie `n` musi być typem niejawnie konwertowanym na `int` , `uint` , `long` , lub `ulong` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-139">For an expression `p` of a pointer type, a pointer element access of the form `p[n]` is evaluated as `*(p + n)`, where `n` must be of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="0acb1-140">Aby uzyskać informacje o zachowaniu `+` operatora ze wskaźnikami, zobacz [Dodawanie lub odejmowanie wartości całkowitej do lub z sekcji wskaźnika](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) .</span><span class="sxs-lookup"><span data-stu-id="0acb1-140">For information about the behavior of the `+` operator with pointers, see the [Addition or subtraction of an integral value to or from a pointer](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) section.</span></span>

<span data-ttu-id="0acb1-141">W poniższym przykładzie pokazano, jak uzyskać dostęp do elementów tablicy za pomocą wskaźnika i `[]` operatora:</span><span class="sxs-lookup"><span data-stu-id="0acb1-141">The following example demonstrates how to access array elements with a pointer and the `[]` operator:</span></span>

[!code-csharp[pointer element access](snippets/shared/PointerOperators.cs#ElementAccess)]

<span data-ttu-id="0acb1-142">W poprzednim przykładzie [ `stackalloc` wyrażenie](stackalloc.md) przydziela blok pamięci na stosie.</span><span class="sxs-lookup"><span data-stu-id="0acb1-142">In the preceding example, a [`stackalloc` expression](stackalloc.md) allocates a block of memory on the stack.</span></span>

> [!NOTE]
> <span data-ttu-id="0acb1-143">Operator dostępu do elementów wskaźnika nie sprawdza występowania błędów poza granicami.</span><span class="sxs-lookup"><span data-stu-id="0acb1-143">The pointer element access operator doesn't check for out-of-bounds errors.</span></span>

<span data-ttu-id="0acb1-144">Nie można użyć `[]` do uzyskania dostępu do elementu wskaźnika z wyrażeniem typu `void*` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-144">You cannot use `[]` for pointer element access with an expression of type `void*`.</span></span>

<span data-ttu-id="0acb1-145">Można również użyć `[]` operatora dla [elementu tablicy lub dostępu indeksatora](member-access-operators.md#indexer-operator-).</span><span class="sxs-lookup"><span data-stu-id="0acb1-145">You can also use the `[]` operator for [array element or indexer access](member-access-operators.md#indexer-operator-).</span></span>

## <a name="pointer-arithmetic-operators"></a><span data-ttu-id="0acb1-146">Operatory arytmetyczne wskaźnika</span><span class="sxs-lookup"><span data-stu-id="0acb1-146">Pointer arithmetic operators</span></span>

<span data-ttu-id="0acb1-147">Za pomocą wskaźników można wykonywać następujące operacje arytmetyczne:</span><span class="sxs-lookup"><span data-stu-id="0acb1-147">You can perform the following arithmetic operations with pointers:</span></span>

- <span data-ttu-id="0acb1-148">Dodaj lub Odejmij wartość całkowitą do lub ze wskaźnika</span><span class="sxs-lookup"><span data-stu-id="0acb1-148">Add or subtract an integral value to or from a pointer</span></span>
- <span data-ttu-id="0acb1-149">Odejmij dwa wskaźniki</span><span class="sxs-lookup"><span data-stu-id="0acb1-149">Subtract two pointers</span></span>
- <span data-ttu-id="0acb1-150">Zwiększ lub Zmniejsz wskaźnik</span><span class="sxs-lookup"><span data-stu-id="0acb1-150">Increment or decrement a pointer</span></span>

<span data-ttu-id="0acb1-151">Nie można wykonać tych operacji ze wskaźnikami typu `void*` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-151">You cannot perform those operations with pointers of type `void*`.</span></span>

<span data-ttu-id="0acb1-152">Aby uzyskać informacje o obsługiwanych operacjach arytmetycznych o typach liczbowych, zobacz [Operatory arytmetyczne](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0acb1-152">For information about supported arithmetic operations with numeric types, see [Arithmetic operators](arithmetic-operators.md).</span></span>

### <a name="addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer"></a><span data-ttu-id="0acb1-153">Dodanie lub odjęcie wartości całkowitej do lub ze wskaźnika</span><span class="sxs-lookup"><span data-stu-id="0acb1-153">Addition or subtraction of an integral value to or from a pointer</span></span>

<span data-ttu-id="0acb1-154">Dla wskaźnika `p` typu `T*` i wyrażenia `n` typu niejawnie konwertowany na `int` , `uint` , `long` , lub `ulong` , Dodawanie i odejmowanie są zdefiniowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="0acb1-154">For a pointer `p` of type `T*` and an expression `n` of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`, addition and subtraction are defined as follows:</span></span>

- <span data-ttu-id="0acb1-155">Oba `p + n` i `n + p` wyrażenia tworzą wskaźnik typu `T*` , który wynika z dodania `n * sizeof(T)` do adresu podanego przez `p` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-155">Both `p + n` and `n + p` expressions produce a pointer of type `T*` that results from adding `n * sizeof(T)` to the address given by `p`.</span></span>
- <span data-ttu-id="0acb1-156">`p - n`Wyrażenie generuje wskaźnik typu `T*` , który wynika z odejmowania `n * sizeof(T)` od adresu podanych przez `p` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-156">The `p - n` expression produces a pointer of type `T*` that results from subtracting `n * sizeof(T)` from the address given by `p`.</span></span>

<span data-ttu-id="0acb1-157">[ `sizeof` Operator](sizeof.md) uzyskuje rozmiar typu w bajtach.</span><span class="sxs-lookup"><span data-stu-id="0acb1-157">The [`sizeof` operator](sizeof.md) obtains the size of a type in bytes.</span></span>

<span data-ttu-id="0acb1-158">Poniższy przykład ilustruje użycie `+` operatora ze wskaźnikiem:</span><span class="sxs-lookup"><span data-stu-id="0acb1-158">The following example demonstrates the usage of the `+` operator with a pointer:</span></span>

[!code-csharp[pointer addition](snippets/shared/PointerOperators.cs#AddNumber)]

### <a name="pointer-subtraction"></a><span data-ttu-id="0acb1-159">Odejmowanie wskaźnika</span><span class="sxs-lookup"><span data-stu-id="0acb1-159">Pointer subtraction</span></span>

<span data-ttu-id="0acb1-160">W przypadku dwóch wskaźników `p1` i `p2` typu `T*` wyrażenie `p1 - p2` tworzy różnicę między adresami podaną przez `p1` i `p2` podzieloną przez `sizeof(T)` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-160">For two pointers `p1` and `p2` of type `T*`, the expression `p1 - p2` produces the difference between the addresses given by `p1` and `p2` divided by `sizeof(T)`.</span></span> <span data-ttu-id="0acb1-161">Typ wyniku to `long` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-161">The type of the result is `long`.</span></span> <span data-ttu-id="0acb1-162">Oznacza to, że `p1 - p2` jest obliczana jako `((long)(p1) - (long)(p2)) / sizeof(T)` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-162">That is, `p1 - p2` is computed as `((long)(p1) - (long)(p2)) / sizeof(T)`.</span></span>

<span data-ttu-id="0acb1-163">Poniższy przykład ilustruje odejmowanie wskaźnika:</span><span class="sxs-lookup"><span data-stu-id="0acb1-163">The following example demonstrates the pointer subtraction:</span></span>

[!code-csharp[pointer subtraction](snippets/shared/PointerOperators.cs#SubtractPointers)]

### <a name="pointer-increment-and-decrement"></a><span data-ttu-id="0acb1-164">Zwiększenie i zmniejszenie wskaźnika</span><span class="sxs-lookup"><span data-stu-id="0acb1-164">Pointer increment and decrement</span></span>

<span data-ttu-id="0acb1-165">`++`Operator przyrostu [dodaje](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 do jego operandu wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="0acb1-165">The `++` increment operator [adds](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 to its pointer operand.</span></span> <span data-ttu-id="0acb1-166">`--`Operator zmniejszania [odejmuje](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 od jego operandu wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="0acb1-166">The `--` decrement operator [subtracts](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 from its pointer operand.</span></span>

<span data-ttu-id="0acb1-167">Oba operatory są obsługiwane w dwóch formach: przyrostka ( `p++` i `p--` ) oraz prefiks ( `++p` i `--p` ).</span><span class="sxs-lookup"><span data-stu-id="0acb1-167">Both operators are supported in two forms: postfix (`p++` and `p--`) and prefix (`++p` and `--p`).</span></span> <span data-ttu-id="0acb1-168">Wynik `p++` i `p--` jest wartością `p` *przed* operacją.</span><span class="sxs-lookup"><span data-stu-id="0acb1-168">The result of `p++` and `p--` is the value of `p` *before* the operation.</span></span> <span data-ttu-id="0acb1-169">Wynik `++p` i `--p` jest wartością `p` *po* operacji.</span><span class="sxs-lookup"><span data-stu-id="0acb1-169">The result of `++p` and `--p` is the value of `p` *after* the operation.</span></span>

<span data-ttu-id="0acb1-170">W poniższym przykładzie przedstawiono zachowanie operatorów przyrostu przyrostkowego i powiększania:</span><span class="sxs-lookup"><span data-stu-id="0acb1-170">The following example demonstrates the behavior of both postfix and prefix increment operators:</span></span>

[!code-csharp[pointer increment](snippets/shared/PointerOperators.cs#Increment)]

## <a name="pointer-comparison-operators"></a><span data-ttu-id="0acb1-171">Operatory porównania wskaźnika</span><span class="sxs-lookup"><span data-stu-id="0acb1-171">Pointer comparison operators</span></span>

<span data-ttu-id="0acb1-172">`==` `!=` Operatory,,,, i służą `<` `>` `<=` `>=` do porównywania operandów dowolnego typu wskaźnika, w tym `void*` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-172">You can use the `==`, `!=`, `<`, `>`, `<=`, and `>=` operators to compare operands of any pointer type, including `void*`.</span></span> <span data-ttu-id="0acb1-173">Te operatory porównują adresy podane przez dwa operandy, tak jakby były to liczby całkowite bez znaku.</span><span class="sxs-lookup"><span data-stu-id="0acb1-173">Those operators compare the addresses given by the two operands as if they were unsigned integers.</span></span>

<span data-ttu-id="0acb1-174">Aby uzyskać informacje o zachowaniu tych operatorów dla operandów innych typów, zobacz artykuły [Operatory równości](equality-operators.md) i [Operatory porównania](comparison-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="0acb1-174">For information about the behavior of those operators for operands of other types, see the [Equality operators](equality-operators.md) and [Comparison operators](comparison-operators.md) articles.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="0acb1-175">Pierwszeństwo operatorów</span><span class="sxs-lookup"><span data-stu-id="0acb1-175">Operator precedence</span></span>

<span data-ttu-id="0acb1-176">Poniższa lista kolejności pokrewnych operatorów, rozpoczynając od najwyższego priorytetu do najniższego:</span><span class="sxs-lookup"><span data-stu-id="0acb1-176">The following list orders pointer related operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="0acb1-177">Operatory przyrostka i zmniejszanie przyrostkowe oraz `x++` `x--` `->` `[]` Operatory i</span><span class="sxs-lookup"><span data-stu-id="0acb1-177">Postfix increment `x++` and decrement `x--` operators and the `->` and `[]` operators</span></span>
- <span data-ttu-id="0acb1-178">Operatory przyrostu `++x` i zmniejszania prefiksu oraz `--x` `&` `*` Operatory i</span><span class="sxs-lookup"><span data-stu-id="0acb1-178">Prefix increment `++x` and decrement `--x` operators and the `&` and `*` operators</span></span>
- <span data-ttu-id="0acb1-179">Dodatek `+` i `-` Operatory</span><span class="sxs-lookup"><span data-stu-id="0acb1-179">Additive `+` and `-` operators</span></span>
- <span data-ttu-id="0acb1-180">Porównanie `<` , `>` , `<=` i `>=` Operatory</span><span class="sxs-lookup"><span data-stu-id="0acb1-180">Comparison `<`, `>`, `<=`, and `>=` operators</span></span>
- <span data-ttu-id="0acb1-181">Równość `==` i `!=` Operatory</span><span class="sxs-lookup"><span data-stu-id="0acb1-181">Equality `==` and `!=` operators</span></span>

<span data-ttu-id="0acb1-182">Użyj nawiasów, `()` , aby zmienić kolejność oceny nałożona przez pierwszeństwo operatorów.</span><span class="sxs-lookup"><span data-stu-id="0acb1-182">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence.</span></span>

<span data-ttu-id="0acb1-183">Aby uzyskać pełną listę operatorów języka C# uporządkowanych według poziomu pierwszeństwa, zobacz sekcję [pierwszeństwo](index.md#operator-precedence) operatorów w artykule [operatory języka c#](index.md) .</span><span class="sxs-lookup"><span data-stu-id="0acb1-183">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0acb1-184">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="0acb1-184">Operator overloadability</span></span>

<span data-ttu-id="0acb1-185">Typ zdefiniowany przez użytkownika nie może przeciążać operatorów powiązanych ze wskaźnikiem, `&` `*` , `->` i `[]` .</span><span class="sxs-lookup"><span data-stu-id="0acb1-185">A user-defined type cannot overload the pointer related operators `&`, `*`, `->`, and `[]`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0acb1-186">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="0acb1-186">C# language specification</span></span>

<span data-ttu-id="0acb1-187">Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="0acb1-187">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="0acb1-188">Zmienne stałe i ruchome</span><span class="sxs-lookup"><span data-stu-id="0acb1-188">Fixed and moveable variables</span></span>](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)
- [<span data-ttu-id="0acb1-189">Operator address-of</span><span class="sxs-lookup"><span data-stu-id="0acb1-189">The address-of operator</span></span>](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)
- [<span data-ttu-id="0acb1-190">Pośredni wskaźnik</span><span class="sxs-lookup"><span data-stu-id="0acb1-190">Pointer indirection</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-indirection)
- [<span data-ttu-id="0acb1-191">Dostęp do elementu członkowskiego wskaźnika</span><span class="sxs-lookup"><span data-stu-id="0acb1-191">Pointer member access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-member-access)
- [<span data-ttu-id="0acb1-192">Dostęp do elementu wskaźnika</span><span class="sxs-lookup"><span data-stu-id="0acb1-192">Pointer element access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-element-access)
- [<span data-ttu-id="0acb1-193">Arytmetyczny wskaźnik</span><span class="sxs-lookup"><span data-stu-id="0acb1-193">Pointer arithmetic</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-arithmetic)
- [<span data-ttu-id="0acb1-194">Zwiększenie i zmniejszenie wskaźnika</span><span class="sxs-lookup"><span data-stu-id="0acb1-194">Pointer increment and decrement</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-increment-and-decrement)
- [<span data-ttu-id="0acb1-195">Porównanie wskaźników</span><span class="sxs-lookup"><span data-stu-id="0acb1-195">Pointer comparison</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-comparison)

## <a name="see-also"></a><span data-ttu-id="0acb1-196">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0acb1-196">See also</span></span>

- [<span data-ttu-id="0acb1-197">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="0acb1-197">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0acb1-198">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="0acb1-198">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="0acb1-199">Typy wskaźnika</span><span class="sxs-lookup"><span data-stu-id="0acb1-199">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="0acb1-200">unsafe — słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="0acb1-200">unsafe keyword</span></span>](../keywords/unsafe.md)
- [<span data-ttu-id="0acb1-201">FIXED — słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="0acb1-201">fixed keyword</span></span>](../keywords/fixed-statement.md)
- [<span data-ttu-id="0acb1-202">stackalloc</span><span class="sxs-lookup"><span data-stu-id="0acb1-202">stackalloc</span></span>](stackalloc.md)
- [<span data-ttu-id="0acb1-203">sizeof — Operator</span><span class="sxs-lookup"><span data-stu-id="0acb1-203">sizeof operator</span></span>](sizeof.md)
