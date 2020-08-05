---
title: Operatory konwersji zdefiniowane przez użytkownika — odwołanie w C#
description: Dowiedz się, jak definiować niestandardowe niejawne i jawne konwersje typów w języku C#.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: ab3598b8158d0a789e8583403389df657ae01aed
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556283"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="9c45b-103">Operatory konwersji zdefiniowane przez użytkownika (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="9c45b-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="9c45b-104">Typ zdefiniowany przez użytkownika może definiować niestandardową lub niejawną konwersję z lub do innego typu.</span><span class="sxs-lookup"><span data-stu-id="9c45b-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="9c45b-105">Konwersje niejawne nie wymagają wywoływania specjalnej składni i mogą wystąpić w różnych sytuacjach, na przykład w przypisaniach i metodach wywołania.</span><span class="sxs-lookup"><span data-stu-id="9c45b-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="9c45b-106">Wstępnie zdefiniowane konwersje niejawne języka C# zawsze kończą się powodzeniem i nigdy nie generują wyjątku.</span><span class="sxs-lookup"><span data-stu-id="9c45b-106">Predefined C# implicit conversions always succeed and never throw an exception.</span></span> <span data-ttu-id="9c45b-107">Niejawne konwersje zdefiniowane przez użytkownika powinny również działać w ten sposób.</span><span class="sxs-lookup"><span data-stu-id="9c45b-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="9c45b-108">Jeśli niestandardowa konwersja może zgłosić wyjątek lub utracić informacje, zdefiniuj ją jako konwersję jawną.</span><span class="sxs-lookup"><span data-stu-id="9c45b-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="9c45b-109">Konwersje zdefiniowane przez użytkownika nie są uwzględniane przez operatory [is](type-testing-and-cast.md#is-operator) i [as](type-testing-and-cast.md#as-operator) .</span><span class="sxs-lookup"><span data-stu-id="9c45b-109">User-defined conversions are not considered by the [is](type-testing-and-cast.md#is-operator) and [as](type-testing-and-cast.md#as-operator) operators.</span></span> <span data-ttu-id="9c45b-110">Użyj [wyrażenia Cast](type-testing-and-cast.md#cast-expression) do wywołania jawnej konwersji zdefiniowanej przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9c45b-110">Use a [cast expression](type-testing-and-cast.md#cast-expression) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="9c45b-111">Użyj `operator` `implicit` `explicit` słów kluczowych i lub, aby zdefiniować odpowiednio niejawną lub jawną konwersję.</span><span class="sxs-lookup"><span data-stu-id="9c45b-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="9c45b-112">Typ, który definiuje konwersję, musi być typem źródłowym lub typem docelowym tej konwersji.</span><span class="sxs-lookup"><span data-stu-id="9c45b-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="9c45b-113">Konwersję między dwoma typami zdefiniowanymi przez użytkownika można zdefiniować w jeden z dwóch typów.</span><span class="sxs-lookup"><span data-stu-id="9c45b-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="9c45b-114">Poniższy przykład ilustruje sposób definiowania konwersji niejawnej i jawnej:</span><span class="sxs-lookup"><span data-stu-id="9c45b-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](snippets/UserDefinedConversions.cs)]

<span data-ttu-id="9c45b-115">Możesz również użyć `operator` słowa kluczowego do przeciążenia wstępnie zdefiniowanego operatora języka C#.</span><span class="sxs-lookup"><span data-stu-id="9c45b-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="9c45b-116">Aby uzyskać więcej informacji, zobacz [przeciążanie operatora](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="9c45b-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9c45b-117">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="9c45b-117">C# language specification</span></span>

<span data-ttu-id="9c45b-118">Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="9c45b-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="9c45b-119">Operatory konwersji</span><span class="sxs-lookup"><span data-stu-id="9c45b-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="9c45b-120">Konwersje zdefiniowane przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="9c45b-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="9c45b-121">Konwersje niejawne</span><span class="sxs-lookup"><span data-stu-id="9c45b-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="9c45b-122">Konwersje jawne</span><span class="sxs-lookup"><span data-stu-id="9c45b-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="9c45b-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9c45b-123">See also</span></span>

- [<span data-ttu-id="9c45b-124">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="9c45b-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9c45b-125">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="9c45b-125">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="9c45b-126">Przeładowanie operatora</span><span class="sxs-lookup"><span data-stu-id="9c45b-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="9c45b-127">Operatory testowania typu i rzutowania</span><span class="sxs-lookup"><span data-stu-id="9c45b-127">Type-testing and cast operators</span></span>](type-testing-and-cast.md)
- [<span data-ttu-id="9c45b-128">Rzutowanie i Konwersja typów</span><span class="sxs-lookup"><span data-stu-id="9c45b-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="9c45b-129">Wytyczne dotyczące projektowania — operatory konwersji</span><span class="sxs-lookup"><span data-stu-id="9c45b-129">Design guidelines - Conversion operators</span></span>](../../../standard/design-guidelines/operator-overloads.md#conversion-operators)
- [<span data-ttu-id="9c45b-130">Jawne konwersje zdefiniowane przez użytkownika w języku C #</span><span class="sxs-lookup"><span data-stu-id="9c45b-130">Chained user-defined explicit conversions in C#</span></span>](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)
