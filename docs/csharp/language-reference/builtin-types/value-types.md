---
description: 'Dowiedz się więcej na temat typów wartości, ich rodzajów i wbudowanych w języku C #'
title: Typy wartości — odwołanie w C#
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 7826e71fee235d32655ccfbc9060c3bbb48d76c5
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134773"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="261c0-103">Typy wartości (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="261c0-103">Value types (C# reference)</span></span>

<span data-ttu-id="261c0-104">*Typy wartości* i [typy referencyjne](../keywords/reference-types.md) to dwie główne kategorie typów języka C#.</span><span class="sxs-lookup"><span data-stu-id="261c0-104">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="261c0-105">Zmienna typu wartości zawiera wystąpienie typu.</span><span class="sxs-lookup"><span data-stu-id="261c0-105">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="261c0-106">Różni się to od zmiennej typu referencyjnego, która zawiera odwołanie do wystąpienia typu.</span><span class="sxs-lookup"><span data-stu-id="261c0-106">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="261c0-107">Domyślnie przy [przypisywaniu](../operators/assignment-operator.md)przekazywanie argumentu do metody i zwracanie wyniku metody powoduje skopiowanie wartości zmiennych.</span><span class="sxs-lookup"><span data-stu-id="261c0-107">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, and returning a method result, variable values are copied.</span></span> <span data-ttu-id="261c0-108">W przypadku zmiennych typu wartość są kopiowane odpowiednie wystąpienia typu.</span><span class="sxs-lookup"><span data-stu-id="261c0-108">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="261c0-109">Poniższy przykład ilustruje takie zachowanie:</span><span class="sxs-lookup"><span data-stu-id="261c0-109">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](snippets/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="261c0-110">Jak pokazano w powyższym przykładzie, operacje na zmiennej typu wartości wpływają tylko na to wystąpienie typu wartości przechowywane w zmiennej.</span><span class="sxs-lookup"><span data-stu-id="261c0-110">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="261c0-111">Jeśli typ wartości zawiera element członkowski danych typu referencyjnego, podczas kopiowania wystąpienia typu wartości jest kopiowane tylko odwołanie do wystąpienia typu referencyjnego.</span><span class="sxs-lookup"><span data-stu-id="261c0-111">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="261c0-112">Zarówno kopia, jak i oryginalne wystąpienie typu wartości mają dostęp do tego samego wystąpienia typu odwołania.</span><span class="sxs-lookup"><span data-stu-id="261c0-112">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="261c0-113">Poniższy przykład ilustruje takie zachowanie:</span><span class="sxs-lookup"><span data-stu-id="261c0-113">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](snippets/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="261c0-114">Aby kod był mniej podatny na błędy i bardziej niezawodny, definiować i korzystać z niezmiennego typu wartości.</span><span class="sxs-lookup"><span data-stu-id="261c0-114">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="261c0-115">W tym artykule są stosowane modyfikowalne typy wartości tylko w celach demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="261c0-115">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types"></a><span data-ttu-id="261c0-116">Rodzaje typów wartości</span><span class="sxs-lookup"><span data-stu-id="261c0-116">Kinds of value types</span></span>

<span data-ttu-id="261c0-117">Typ wartości może być jednym z dwóch następujących rodzajów:</span><span class="sxs-lookup"><span data-stu-id="261c0-117">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="261c0-118">[Typ struktury](struct.md), który hermetyzuje dane i powiązane funkcje</span><span class="sxs-lookup"><span data-stu-id="261c0-118">a [structure type](struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="261c0-119">[Typ wyliczeniowy](enum.md), który jest zdefiniowany przez zestaw nazwanych stałych i reprezentuje wybór lub kombinację opcji</span><span class="sxs-lookup"><span data-stu-id="261c0-119">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="261c0-120">[Typ wartości null](nullable-value-types.md) `T?` reprezentuje wszystkie wartości jego bazowego typu wartości `T` oraz dodatkową wartość [null](../keywords/null.md) .</span><span class="sxs-lookup"><span data-stu-id="261c0-120">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="261c0-121">Nie można przypisać `null` do zmiennej typu wartości, chyba że jest to typ wartości null.</span><span class="sxs-lookup"><span data-stu-id="261c0-121">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="261c0-122">Wbudowane typy wartości</span><span class="sxs-lookup"><span data-stu-id="261c0-122">Built-in value types</span></span>

<span data-ttu-id="261c0-123">Język C# udostępnia następujące wbudowane typy wartości, znane także jako *typy proste*:</span><span class="sxs-lookup"><span data-stu-id="261c0-123">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="261c0-124">Typy liczb całkowitych</span><span class="sxs-lookup"><span data-stu-id="261c0-124">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="261c0-125">Zmiennoprzecinkowe rodzaje wartości numerycznych</span><span class="sxs-lookup"><span data-stu-id="261c0-125">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="261c0-126">[bool](bool.md) reprezentujący wartość logiczną</span><span class="sxs-lookup"><span data-stu-id="261c0-126">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="261c0-127">[char](char.md) , który reprezentuje znak Unicode UTF-16</span><span class="sxs-lookup"><span data-stu-id="261c0-127">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="261c0-128">Wszystkie typy proste są typami struktury i różnią się od innych typów struktury w tym, że dopuszczają pewne dodatkowe operacje:</span><span class="sxs-lookup"><span data-stu-id="261c0-128">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="261c0-129">Można użyć literałów, aby podać wartość typu prostego.</span><span class="sxs-lookup"><span data-stu-id="261c0-129">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="261c0-130">Na przykład `'A'` jest literałem typu `char` i `2001` jest literałem typu `int` .</span><span class="sxs-lookup"><span data-stu-id="261c0-130">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="261c0-131">Stałe typów prostych można zadeklarować za pomocą słowa kluczowego [const](../keywords/const.md) .</span><span class="sxs-lookup"><span data-stu-id="261c0-131">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="261c0-132">Nie jest możliwe posiadanie stałych dla innych typów struktury.</span><span class="sxs-lookup"><span data-stu-id="261c0-132">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="261c0-133">Wyrażenia stałe, których operandy to wszystkie stałe typów prostych, są oceniane w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="261c0-133">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="261c0-134">Począwszy od języka C# 7,0, C# obsługuje [krotki wartości](value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="261c0-134">Beginning with C# 7.0, C# supports [value tuples](value-tuples.md).</span></span> <span data-ttu-id="261c0-135">Krotka wartości jest typem wartości, ale nie typem prostym.</span><span class="sxs-lookup"><span data-stu-id="261c0-135">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="261c0-136">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="261c0-136">C# language specification</span></span>

<span data-ttu-id="261c0-137">Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="261c0-137">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="261c0-138">Typy wartości</span><span class="sxs-lookup"><span data-stu-id="261c0-138">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="261c0-139">Typy proste</span><span class="sxs-lookup"><span data-stu-id="261c0-139">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="261c0-140">Zmienne</span><span class="sxs-lookup"><span data-stu-id="261c0-140">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="261c0-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="261c0-141">See also</span></span>

- [<span data-ttu-id="261c0-142">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="261c0-142">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="261c0-143">Typy odwołań</span><span class="sxs-lookup"><span data-stu-id="261c0-143">Reference types</span></span>](../keywords/reference-types.md)
