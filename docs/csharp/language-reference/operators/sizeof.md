---
description: operator sizeof — odwołanie w C#
title: operator sizeof — odwołanie w C#
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: f1358cbfb6cbc2942cef12e650f7bd362ba37a78
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136879"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="76ea9-103">sizeof — Operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="76ea9-103">sizeof operator (C# reference)</span></span>

<span data-ttu-id="76ea9-104">`sizeof`Operator zwraca liczbę bajtów zajmowanych przez zmienną danego typu.</span><span class="sxs-lookup"><span data-stu-id="76ea9-104">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="76ea9-105">Argument `sizeof` operatora musi być nazwą [typu niezarządzanego](../builtin-types/unmanaged-types.md) lub parametrem typu, który jest [ograniczony](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) do niezarządzanego typu.</span><span class="sxs-lookup"><span data-stu-id="76ea9-105">The argument to the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="76ea9-106">`sizeof`Operator wymaga [niebezpiecznego](../keywords/unsafe.md) kontekstu.</span><span class="sxs-lookup"><span data-stu-id="76ea9-106">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="76ea9-107">Jednak wyrażenia przedstawione w poniższej tabeli są oceniane w czasie kompilacji do odpowiednich wartości stałych i nie wymagają niebezpiecznego kontekstu:</span><span class="sxs-lookup"><span data-stu-id="76ea9-107">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="76ea9-108">Wyrażenie</span><span class="sxs-lookup"><span data-stu-id="76ea9-108">Expression</span></span>|<span data-ttu-id="76ea9-109">Stała wartość</span><span class="sxs-lookup"><span data-stu-id="76ea9-109">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="76ea9-110">1</span><span class="sxs-lookup"><span data-stu-id="76ea9-110">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="76ea9-111">1</span><span class="sxs-lookup"><span data-stu-id="76ea9-111">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="76ea9-112">2</span><span class="sxs-lookup"><span data-stu-id="76ea9-112">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="76ea9-113">2</span><span class="sxs-lookup"><span data-stu-id="76ea9-113">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="76ea9-114">4</span><span class="sxs-lookup"><span data-stu-id="76ea9-114">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="76ea9-115">4</span><span class="sxs-lookup"><span data-stu-id="76ea9-115">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="76ea9-116">8</span><span class="sxs-lookup"><span data-stu-id="76ea9-116">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="76ea9-117">8</span><span class="sxs-lookup"><span data-stu-id="76ea9-117">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="76ea9-118">2</span><span class="sxs-lookup"><span data-stu-id="76ea9-118">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="76ea9-119">4</span><span class="sxs-lookup"><span data-stu-id="76ea9-119">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="76ea9-120">8</span><span class="sxs-lookup"><span data-stu-id="76ea9-120">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="76ea9-121">16</span><span class="sxs-lookup"><span data-stu-id="76ea9-121">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="76ea9-122">1</span><span class="sxs-lookup"><span data-stu-id="76ea9-122">1</span></span>|

<span data-ttu-id="76ea9-123">Nie trzeba również używać niebezpiecznego kontekstu, gdy operand `sizeof` operatora jest nazwą typu [wyliczeniowego](../builtin-types/enum.md) .</span><span class="sxs-lookup"><span data-stu-id="76ea9-123">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../builtin-types/enum.md) type.</span></span>

<span data-ttu-id="76ea9-124">Poniższy przykład ilustruje użycie `sizeof` operatora:</span><span class="sxs-lookup"><span data-stu-id="76ea9-124">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](snippets/shared/SizeOfOperator.cs)]

<span data-ttu-id="76ea9-125">`sizeof`Operator zwraca liczbę bajtów, które zostałyby przydzielone przez środowisko uruchomieniowe języka wspólnego w pamięci zarządzanej.</span><span class="sxs-lookup"><span data-stu-id="76ea9-125">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="76ea9-126">W przypadku typów [struktur](../builtin-types/struct.md) ta wartość obejmuje wszelkie uzupełnienia, jak pokazano w powyższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="76ea9-126">For [struct](../builtin-types/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="76ea9-127">Wynik `sizeof` operatora może się różnić od wyniku <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> metody, która zwraca rozmiar typu w pamięci *niezarządzanej* .</span><span class="sxs-lookup"><span data-stu-id="76ea9-127">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="76ea9-128">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="76ea9-128">C# language specification</span></span>

<span data-ttu-id="76ea9-129">Aby uzyskać więcej informacji, zobacz sekcję [operator sizeof](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="76ea9-129">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="76ea9-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="76ea9-130">See also</span></span>

- [<span data-ttu-id="76ea9-131">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="76ea9-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="76ea9-132">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="76ea9-132">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="76ea9-133">Operatory związane ze wskaźnikiem</span><span class="sxs-lookup"><span data-stu-id="76ea9-133">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="76ea9-134">Typy wskaźnika</span><span class="sxs-lookup"><span data-stu-id="76ea9-134">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="76ea9-135">Pamięć i typy związane z zakresem</span><span class="sxs-lookup"><span data-stu-id="76ea9-135">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="76ea9-136">Typy ogólne w .NET</span><span class="sxs-lookup"><span data-stu-id="76ea9-136">Generics in .NET</span></span>](../../../standard/generics/index.md)
