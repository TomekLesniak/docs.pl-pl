---
description: 'Informacje o typach niezarządzanych w języku C #'
title: Typy niezarządzane — odwołanie w C#
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: b5a689ca3ade36ef77da958549894f76e074986e
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89143535"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="65b1d-103">Typy niezarządzane (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="65b1d-103">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="65b1d-104">Typ jest **typem niezarządzanym** , jeśli jest dowolnego z następujących typów:</span><span class="sxs-lookup"><span data-stu-id="65b1d-104">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="65b1d-105">`sbyte`,,,,, `byte` `short` ,,,, `ushort` `int` `uint` `long` `ulong` `char` `float` , `double` , `decimal` lub `bool`</span><span class="sxs-lookup"><span data-stu-id="65b1d-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="65b1d-106">Dowolny typ [wyliczeniowy](enum.md)</span><span class="sxs-lookup"><span data-stu-id="65b1d-106">Any [enum](enum.md) type</span></span>
- <span data-ttu-id="65b1d-107">Dowolny typ [wskaźnika](../../programming-guide/unsafe-code-pointers/pointer-types.md)</span><span class="sxs-lookup"><span data-stu-id="65b1d-107">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="65b1d-108">Dowolny zdefiniowany przez użytkownika typ [struktury](struct.md) , który zawiera pola tylko typy niezarządzane i, w języku C# 7,3 i wcześniejszych, nie jest typem skonstruowanym (typ, który zawiera co najmniej jeden argument typu)</span><span class="sxs-lookup"><span data-stu-id="65b1d-108">Any user-defined [struct](struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="65b1d-109">Począwszy od języka C# 7,3, można użyć [ `unmanaged` ograniczenia](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) , aby określić, że parametr typu jest niewskaźnikiem typu niebędącego typem niedopuszczający wartości null.</span><span class="sxs-lookup"><span data-stu-id="65b1d-109">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="65b1d-110">Począwszy od języka C# 8,0, *skonstruowany* typ struktury, który zawiera pola typów niezarządzanych, również jest niezarządzany, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="65b1d-110">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](snippets/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="65b1d-111">Struktura generyczna może być źródłem zarówno typów niezarządzanych, jak i niezarządzanych.</span><span class="sxs-lookup"><span data-stu-id="65b1d-111">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="65b1d-112">W poprzednim przykładzie zdefiniowano strukturę generyczną `Coords<T>` i przedstawiono przykłady niezarządzanych typów skonstruowanych.</span><span class="sxs-lookup"><span data-stu-id="65b1d-112">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="65b1d-113">Przykładem niezarządzanego typu jest `Coords<object>` .</span><span class="sxs-lookup"><span data-stu-id="65b1d-113">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="65b1d-114">Nie jest ona zarządzana, ponieważ zawiera pola `object` typu, które nie są zarządzane.</span><span class="sxs-lookup"><span data-stu-id="65b1d-114">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="65b1d-115">Jeśli chcesz, aby *wszystkie* skonstruowane typy były typami niezarządzanymi, użyj `unmanaged` ograniczenia w definicji generycznej struktury:</span><span class="sxs-lookup"><span data-stu-id="65b1d-115">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](snippets/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="65b1d-116">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="65b1d-116">C# language specification</span></span>

<span data-ttu-id="65b1d-117">Aby uzyskać więcej informacji, zobacz sekcję [typy wskaźników](~/_csharplang/spec/unsafe-code.md#pointer-types) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="65b1d-117">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="65b1d-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="65b1d-118">See also</span></span>

- [<span data-ttu-id="65b1d-119">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="65b1d-119">C# reference</span></span>](../index.md)
- [<span data-ttu-id="65b1d-120">Typy wskaźnika</span><span class="sxs-lookup"><span data-stu-id="65b1d-120">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="65b1d-121">Pamięć i typy związane z zakresem</span><span class="sxs-lookup"><span data-stu-id="65b1d-121">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="65b1d-122">sizeof — Operator</span><span class="sxs-lookup"><span data-stu-id="65b1d-122">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="65b1d-123">stackalloc</span><span class="sxs-lookup"><span data-stu-id="65b1d-123">stackalloc</span></span>](../operators/stackalloc.md)
