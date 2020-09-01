---
description: const — słowo kluczowe — odwołanie w C#
title: const — słowo kluczowe — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: 312725c3a231f0ca766d5b99bf7d9308ddd634c4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142092"
---
# <a name="const-c-reference"></a><span data-ttu-id="0a5c3-103">const (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="0a5c3-103">const (C# Reference)</span></span>

<span data-ttu-id="0a5c3-104">Użyj `const` słowa kluczowego, aby zadeklarować pole stałe lub stałą lokalną.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-104">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="0a5c3-105">Pola stałe i zmienne lokalne nie są zmiennymi i nie mogą być modyfikowane.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-105">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="0a5c3-106">Stałe mogą być liczbami, wartościami logicznymi, ciągami lub odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-106">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="0a5c3-107">Nie należy tworzyć stałej do reprezentowania informacji, które można zmienić w dowolnym momencie.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-107">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="0a5c3-108">Na przykład nie należy używać pola stałego do przechowywania ceny usługi, numeru wersji produktu ani nazwy marki firmy.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-108">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="0a5c3-109">Te wartości mogą ulec zmianie z upływem czasu, a ponieważ kompilatory propagują stałe, inne kod skompilowane z bibliotekami będzie musiały zostać ponownie skompilowane w celu wyświetlenia zmian.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-109">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="0a5c3-110">Zobacz również słowo kluczowe [ReadOnly](./readonly.md) .</span><span class="sxs-lookup"><span data-stu-id="0a5c3-110">See also the [readonly](./readonly.md) keyword.</span></span> <span data-ttu-id="0a5c3-111">Przykład:</span><span class="sxs-lookup"><span data-stu-id="0a5c3-111">For example:</span></span>

```csharp
const int X = 0;
public const double GravitationalConstant = 6.673e-11;
private const string ProductName = "Visual C#";
```

## <a name="remarks"></a><span data-ttu-id="0a5c3-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0a5c3-112">Remarks</span></span>

<span data-ttu-id="0a5c3-113">Typ deklaracji stałej określa typ elementów członkowskich, które wprowadza deklaracja.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-113">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="0a5c3-114">Inicjator stałego lokalnego lub stałego pola musi być wyrażeniem stałym, które może być niejawnie konwertowane na typ docelowy.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-114">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>

<span data-ttu-id="0a5c3-115">Wyrażenie stałe jest wyrażeniem, które może być w pełni oceniane w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-115">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="0a5c3-116">W związku z tym jedynymi możliwymi wartościami dla stałych typów odwołań są `string` i odwołania o wartości null.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-116">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>

<span data-ttu-id="0a5c3-117">Deklaracja stałej może deklarować wiele stałych, takich jak:</span><span class="sxs-lookup"><span data-stu-id="0a5c3-117">The constant declaration can declare multiple constants, such as:</span></span>

```csharp
public const double X = 1.0, Y = 2.0, Z = 3.0;
```

<span data-ttu-id="0a5c3-118">`static`Modyfikator nie jest dozwolony w deklaracji stałej.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-118">The `static` modifier is not allowed in a constant declaration.</span></span>

<span data-ttu-id="0a5c3-119">Stała może uczestniczyć w wyrażeniu stałym w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="0a5c3-119">A constant can participate in a constant expression, as follows:</span></span>

```csharp
public const int C1 = 5;
public const int C2 = C1 + 100;
```

> [!NOTE]
> <span data-ttu-id="0a5c3-120">Słowo kluczowe [ReadOnly](./readonly.md) różni się od `const` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-120">The [readonly](./readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="0a5c3-121">`const`Pole może być inicjowane tylko w deklaracji pola.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-121">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="0a5c3-122">`readonly`Pole może być inicjowane w deklaracji lub w konstruktorze.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-122">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="0a5c3-123">W związku z tym `readonly` pola mogą mieć różne wartości w zależności od użytego konstruktora.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-123">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="0a5c3-124">Ponadto mimo że `const` pole jest stałą czasu kompilacji, `readonly` pole może być używane dla stałych czasu wykonywania, jak w tym wierszu: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="0a5c3-124">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>

## <a name="example"></a><span data-ttu-id="0a5c3-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="0a5c3-125">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a><span data-ttu-id="0a5c3-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="0a5c3-126">Example</span></span>

<span data-ttu-id="0a5c3-127">W tym przykładzie pokazano, jak używać stałych jako zmiennych lokalnych.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-127">This example demonstrates how to use constants as local variables.</span></span>

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="0a5c3-128">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="0a5c3-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0a5c3-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0a5c3-129">See also</span></span>

- [<span data-ttu-id="0a5c3-130">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="0a5c3-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0a5c3-131">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="0a5c3-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0a5c3-132">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="0a5c3-132">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="0a5c3-133">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="0a5c3-133">Modifiers</span></span>](index.md)
- [<span data-ttu-id="0a5c3-134">readonly</span><span class="sxs-lookup"><span data-stu-id="0a5c3-134">readonly</span></span>](./readonly.md)
