---
title: Typy wyliczeniowe — odwołanie w C#
description: Dowiedz się więcej na temat typów wyliczeniowych języka C#, które reprezentują wybór lub kombinację opcji
ms.date: 12/13/2019
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
- enum type [C#]
- enumeration type [C#]
- bit flags [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 930efdbdc6a20ea301331c1ce6fc664da43bfc5f
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471853"
---
# <a name="enumeration-types-c-reference"></a><span data-ttu-id="63b7a-103">Typy wyliczeniowe (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="63b7a-103">Enumeration types (C# reference)</span></span>

<span data-ttu-id="63b7a-104">*Typ wyliczenia* (lub *Typ wyliczeniowy*) jest [typem wartości](value-types.md) zdefiniowanym przez zestaw nazwanych stałych podstawowego typu [liczbowego](integral-numeric-types.md) .</span><span class="sxs-lookup"><span data-stu-id="63b7a-104">An *enumeration type* (or *enum type*) is a [value type](value-types.md) defined by a set of named constants of the underlying [integral numeric](integral-numeric-types.md) type.</span></span> <span data-ttu-id="63b7a-105">Aby zdefiniować typ wyliczeniowy, użyj `enum` słowa kluczowego i określ nazwy *elementów członkowskich wyliczenia*:</span><span class="sxs-lookup"><span data-stu-id="63b7a-105">To define an enumeration type, use the `enum` keyword and specify the names of *enum members*:</span></span>

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

<span data-ttu-id="63b7a-106">Domyślnie skojarzone wartości stałe elementów członkowskich wyliczenia są typu `int` ; zaczynają się od zera i zwiększają się o jeden po kolejności tekstu definicji.</span><span class="sxs-lookup"><span data-stu-id="63b7a-106">By default, the associated constant values of enum members are of type `int`; they start with zero and increase by one following the definition text order.</span></span> <span data-ttu-id="63b7a-107">Można jawnie określić dowolny inny typ [liczbowy całkowity](integral-numeric-types.md) jako typ podstawowy typu wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="63b7a-107">You can explicitly specify any other [integral numeric](integral-numeric-types.md) type as an underlying type of an enumeration type.</span></span> <span data-ttu-id="63b7a-108">Można również jawnie określić skojarzone wartości stałe, jak pokazano na poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="63b7a-108">You can also explicitly specify the associated constant values, as the following example shows:</span></span>

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

<span data-ttu-id="63b7a-109">Nie można zdefiniować metody wewnątrz definicji typu wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="63b7a-109">You cannot define a method inside the definition of an enumeration type.</span></span> <span data-ttu-id="63b7a-110">Aby dodać funkcjonalność do typu wyliczenia, Utwórz [metodę rozszerzenia](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="63b7a-110">To add functionality to an enumeration type, create an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="63b7a-111">Wartość domyślna typu wyliczeniowy `E` jest wartością wygenerowaną przez wyrażenie `(E)0` , nawet jeśli zero nie ma odpowiedniego elementu członkowskiego wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="63b7a-111">The default value of an enumeration type `E` is the value produced by expression `(E)0`, even if zero doesn't have the corresponding enum member.</span></span>

<span data-ttu-id="63b7a-112">Typ wyliczenia służy do reprezentowania wyboru z zestawu wzajemnie wykluczających się wartości lub kombinacji wyboru.</span><span class="sxs-lookup"><span data-stu-id="63b7a-112">You use an enumeration type to represent a choice from a set of mutually exclusive values or a combination of choices.</span></span> <span data-ttu-id="63b7a-113">Aby przedstawić kombinację opcji, zdefiniuj typ wyliczenia jako flagi bitowe.</span><span class="sxs-lookup"><span data-stu-id="63b7a-113">To represent a combination of choices, define an enumeration type as bit flags.</span></span>

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="63b7a-114">Typy wyliczeniowe jako flagi bitowe</span><span class="sxs-lookup"><span data-stu-id="63b7a-114">Enumeration types as bit flags</span></span>

<span data-ttu-id="63b7a-115">Jeśli chcesz, aby typ wyliczeniowy reprezentował kombinację opcji, Zdefiniuj elementy członkowskie wyliczenia dla tych opcji, tak że pojedynczy wybór jest polem bitowym.</span><span class="sxs-lookup"><span data-stu-id="63b7a-115">If you want an enumeration type to represent a combination of choices, define enum members for those choices such that an individual choice is a bit field.</span></span> <span data-ttu-id="63b7a-116">Oznacza to, że skojarzone wartości tych elementów członkowskich wyliczenia powinny być potęgami dwóch.</span><span class="sxs-lookup"><span data-stu-id="63b7a-116">That is, the associated values of those enum members should be the powers of two.</span></span> <span data-ttu-id="63b7a-117">Następnie można użyć [bitowe operatory logiczne `|` lub `&` ](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) do łączenia opcji lub przecinających się kombinacji opcji.</span><span class="sxs-lookup"><span data-stu-id="63b7a-117">Then, you can use the [bitwise logical operators `|` or `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) to combine choices or intersect combinations of choices, respectively.</span></span> <span data-ttu-id="63b7a-118">Aby wskazać, że typ wyliczeniowy deklaruje pola bitowe, Zastosuj do niego atrybut [flags](xref:System.FlagsAttribute) .</span><span class="sxs-lookup"><span data-stu-id="63b7a-118">To indicate that an enumeration type declares bit fields, apply the [Flags](xref:System.FlagsAttribute) attribute to it.</span></span> <span data-ttu-id="63b7a-119">Jak pokazano na poniższym przykładzie, można także uwzględnić niektóre typowe kombinacje w definicji typu wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="63b7a-119">As the following example shows, you can also include some typical combinations in the definition of an enumeration type.</span></span>

[!code-csharp[enum flags](snippets/shared/EnumType.cs#Flags)]

<span data-ttu-id="63b7a-120">Aby uzyskać więcej informacji i przykładów, zobacz <xref:System.FlagsAttribute?displayProperty=nameWithType> stronę referencyjną interfejsu API i [niewyłączne elementy członkowskie oraz atrybuty flag](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) na <xref:System.Enum?displayProperty=nameWithType> stronie odwołania interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="63b7a-120">For more information and examples, see the <xref:System.FlagsAttribute?displayProperty=nameWithType> API reference page and the [Non-exclusive members and the Flags attribute](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) section of the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

## <a name="the-systemenum-type-and-enum-constraint"></a><span data-ttu-id="63b7a-121">Typ System. Enum i ograniczenie wyliczenia</span><span class="sxs-lookup"><span data-stu-id="63b7a-121">The System.Enum type and enum constraint</span></span>

<span data-ttu-id="63b7a-122"><xref:System.Enum?displayProperty=nameWithType>Typ jest abstrakcyjną klasą bazową wszystkich typów wyliczeniowych.</span><span class="sxs-lookup"><span data-stu-id="63b7a-122">The <xref:System.Enum?displayProperty=nameWithType> type is the abstract base class of all enumeration types.</span></span> <span data-ttu-id="63b7a-123">Zawiera kilka metod uzyskiwania informacji na temat typu wyliczenia i jego wartości.</span><span class="sxs-lookup"><span data-stu-id="63b7a-123">It provides a number of methods to get information about an enumeration type and its values.</span></span> <span data-ttu-id="63b7a-124">Aby uzyskać więcej informacji i przykładów, zobacz <xref:System.Enum?displayProperty=nameWithType> stronę referencyjną interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="63b7a-124">For more information and examples, see the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

<span data-ttu-id="63b7a-125">Począwszy od języka C# 7,3, można użyć `System.Enum` w ramach ograniczenia klasy bazowej (zwanego [ograniczeniem wyliczenia](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)), aby określić, że parametr typu jest typem wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="63b7a-125">Beginning with C# 7.3, you can use `System.Enum` in a base class constraint (that is known as the [enum constraint](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) to specify that a type parameter is an enumeration type.</span></span>

## <a name="conversions"></a><span data-ttu-id="63b7a-126">Konwersje</span><span class="sxs-lookup"><span data-stu-id="63b7a-126">Conversions</span></span>

<span data-ttu-id="63b7a-127">Dla dowolnego typu wyliczenia istnieją jawne konwersje między typem wyliczenia i jego podstawowym typem całkowitym.</span><span class="sxs-lookup"><span data-stu-id="63b7a-127">For any enumeration type, there exist explicit conversions between the enumeration type and its underlying integral type.</span></span> <span data-ttu-id="63b7a-128">W przypadku [rzutowania](../operators/type-testing-and-cast.md#cast-expression) wartości wyliczenia na jej typ podstawowy wynik jest skojarzoną wartością całkowitą elementu członkowskiego wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="63b7a-128">If you [cast](../operators/type-testing-and-cast.md#cast-expression) an enum value to its underlying type, the result is the associated integral value of an enum member.</span></span>

[!code-csharp[enum conversions](snippets/shared/EnumType.cs#Conversions)]

<span data-ttu-id="63b7a-129">Użyj <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> metody, aby określić, czy typ wyliczeniowy zawiera element członkowski wyliczenia z określoną wartością skojarzoną.</span><span class="sxs-lookup"><span data-stu-id="63b7a-129">Use the <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> method to determine whether an enumeration type contains an enum member with the certain associated value.</span></span>

<span data-ttu-id="63b7a-130">Dla dowolnego typu wyliczenia istnieją konwersje pakowania [i](../../programming-guide/types/boxing-and-unboxing.md) rozpakowywania do i z <xref:System.Enum?displayProperty=nameWithType> typu, odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="63b7a-130">For any enumeration type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.Enum?displayProperty=nameWithType> type, respectively.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="63b7a-131">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="63b7a-131">C# language specification</span></span>

<span data-ttu-id="63b7a-132">Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="63b7a-132">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="63b7a-133">Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="63b7a-133">Enums</span></span>](~/_csharplang/spec/enums.md)
- [<span data-ttu-id="63b7a-134">Wartości wyliczeniowe i operacje</span><span class="sxs-lookup"><span data-stu-id="63b7a-134">Enum values and operations</span></span>](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [<span data-ttu-id="63b7a-135">Wyliczanie operatorów logicznych</span><span class="sxs-lookup"><span data-stu-id="63b7a-135">Enumeration logical operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [<span data-ttu-id="63b7a-136">Operatory porównania wyliczenia</span><span class="sxs-lookup"><span data-stu-id="63b7a-136">Enumeration comparison operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [<span data-ttu-id="63b7a-137">Jawne konwersje wyliczenia</span><span class="sxs-lookup"><span data-stu-id="63b7a-137">Explicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [<span data-ttu-id="63b7a-138">Niejawne konwersje wyliczenia</span><span class="sxs-lookup"><span data-stu-id="63b7a-138">Implicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a><span data-ttu-id="63b7a-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="63b7a-139">See also</span></span>

- [<span data-ttu-id="63b7a-140">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="63b7a-140">C# reference</span></span>](../index.md)
- [<span data-ttu-id="63b7a-141">Wyliczanie ciągów formatujących</span><span class="sxs-lookup"><span data-stu-id="63b7a-141">Enumeration format strings</span></span>](../../../standard/base-types/enumeration-format-strings.md)
- [<span data-ttu-id="63b7a-142">Wskazówki dotyczące projektowania — projekt enum</span><span class="sxs-lookup"><span data-stu-id="63b7a-142">Design guidelines - Enum design</span></span>](../../../standard/design-guidelines/enum.md)
- [<span data-ttu-id="63b7a-143">Wytyczne dotyczące projektowania — wyliczanie konwencji nazewnictwa</span><span class="sxs-lookup"><span data-stu-id="63b7a-143">Design guidelines - Enum naming conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [<span data-ttu-id="63b7a-144">switch, instrukcja</span><span class="sxs-lookup"><span data-stu-id="63b7a-144">switch statement</span></span>](../keywords/switch.md)
