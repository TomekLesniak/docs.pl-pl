---
description: wyrażenie stackalloc — odwołanie w C#
title: wyrażenie stackalloc — odwołanie w C#
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 72d91cf9aa67957ed8e1cad5b2c4a1f3b6382c1f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136853"
---
# <a name="stackalloc-expression-c-reference"></a><span data-ttu-id="a4fda-103">wyrażenie stackalloc (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="a4fda-103">stackalloc expression (C# reference)</span></span>

<span data-ttu-id="a4fda-104">`stackalloc`Wyrażenie przydziela blok pamięci na stosie.</span><span class="sxs-lookup"><span data-stu-id="a4fda-104">A `stackalloc` expression allocates a block of memory on the stack.</span></span> <span data-ttu-id="a4fda-105">Blok pamięci przydzielony przez stos utworzony podczas wykonywania metody jest automatycznie usuwany, gdy ta metoda zwraca.</span><span class="sxs-lookup"><span data-stu-id="a4fda-105">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="a4fda-106">Nie można jawnie zwolnić pamięci przydzieloną z `stackalloc` .</span><span class="sxs-lookup"><span data-stu-id="a4fda-106">You cannot explicitly free the memory allocated with `stackalloc`.</span></span> <span data-ttu-id="a4fda-107">Przydzielony blok pamięci stosu nie podlega [wyrzucaniu elementów bezużytecznych](../../../standard/garbage-collection/index.md) i nie musi być przypięty za pomocą [ `fixed` instrukcji](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a4fda-107">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="a4fda-108">Wynik wyrażenia można przypisać `stackalloc` do zmiennej jednego z następujących typów:</span><span class="sxs-lookup"><span data-stu-id="a4fda-108">You can assign the result of a `stackalloc` expression to a variable of one of the following types:</span></span>

- <span data-ttu-id="a4fda-109">Począwszy od języka C# 7,2 <xref:System.Span%601?displayProperty=nameWithType> lub <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> , jak pokazano na poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a4fda-109">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](snippets/shared/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="a4fda-110">Nie trzeba używać [niebezpiecznego](../keywords/unsafe.md) kontekstu, gdy przypiszesz blok pamięci przydzielony przez stos do <xref:System.Span%601> <xref:System.ReadOnlySpan%601> zmiennej lub.</span><span class="sxs-lookup"><span data-stu-id="a4fda-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="a4fda-111">Podczas pracy z tymi typami można użyć `stackalloc` wyrażenia w wyrażeniach [warunkowych](conditional-operator.md) lub przypisywania, jak pokazano na poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a4fda-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](snippets/shared/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="a4fda-112">Począwszy od języka C# 8,0, można użyć `stackalloc` wyrażenia wewnątrz innych wyrażeń za każdym razem <xref:System.Span%601> <xref:System.ReadOnlySpan%601> , gdy zmienna lub jest dozwolona, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a4fda-112">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](snippets/shared/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="a4fda-113">Zalecamy używanie <xref:System.Span%601> lub <xref:System.ReadOnlySpan%601> typy do pracy z przydzieloną pamięcią stosu, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="a4fda-113">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="a4fda-114">[Typ wskaźnika](../../programming-guide/unsafe-code-pointers/pointer-types.md), jak pokazano na poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a4fda-114">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](snippets/shared/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="a4fda-115">Jak pokazano w powyższym przykładzie, należy użyć `unsafe` kontekstu podczas pracy z typami wskaźników.</span><span class="sxs-lookup"><span data-stu-id="a4fda-115">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="a4fda-116">W przypadku typów wskaźnika można użyć `stackalloc` wyrażenia tylko w deklaracji zmiennej lokalnej, aby zainicjować zmienną.</span><span class="sxs-lookup"><span data-stu-id="a4fda-116">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="a4fda-117">Ilość pamięci dostępnej na stosie jest ograniczona.</span><span class="sxs-lookup"><span data-stu-id="a4fda-117">The amount of memory available on the stack is limited.</span></span> <span data-ttu-id="a4fda-118">W przypadku przydzielenia zbyt dużej ilości pamięci na stosie <xref:System.StackOverflowException> jest zgłaszany.</span><span class="sxs-lookup"><span data-stu-id="a4fda-118">If you allocate too much memory on the stack, a <xref:System.StackOverflowException> is thrown.</span></span> <span data-ttu-id="a4fda-119">Aby tego uniknąć, postępuj zgodnie z poniższymi regułami:</span><span class="sxs-lookup"><span data-stu-id="a4fda-119">To avoid that, follow the rules below:</span></span>

- <span data-ttu-id="a4fda-120">Ogranicz ilość pamięci do przydzielenia `stackalloc` :</span><span class="sxs-lookup"><span data-stu-id="a4fda-120">Limit the amount of memory you allocate with `stackalloc`:</span></span>

  [!code-csharp[limit stackalloc](snippets/shared/StackallocOperator.cs#LimitStackalloc)]

  <span data-ttu-id="a4fda-121">Ponieważ ilość pamięci dostępnej na stosie zależy od środowiska, w którym wykonywany jest kod, należy ją wyrównać podczas definiowania rzeczywistej wartości limitu.</span><span class="sxs-lookup"><span data-stu-id="a4fda-121">Because the amount of memory available on the stack depends on the environment in which the code is executed, be conservative when you define the actual limit value.</span></span>

- <span data-ttu-id="a4fda-122">Unikaj używania `stackalloc` pętli wewnątrz.</span><span class="sxs-lookup"><span data-stu-id="a4fda-122">Avoid using `stackalloc` inside loops.</span></span> <span data-ttu-id="a4fda-123">Przydziel blok pamięci poza pętlą i ponownie Użyj go wewnątrz pętli.</span><span class="sxs-lookup"><span data-stu-id="a4fda-123">Allocate the memory block outside a loop and reuse it inside the loop.</span></span>

<span data-ttu-id="a4fda-124">Zawartość nowo przydzieloną pamięci jest niezdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="a4fda-124">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="a4fda-125">Należy ją zainicjować przed użyciem.</span><span class="sxs-lookup"><span data-stu-id="a4fda-125">You should initialize it before the use.</span></span> <span data-ttu-id="a4fda-126">Na przykład można użyć <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> metody, która ustawia wszystkie elementy na wartość domyślną typu `T` .</span><span class="sxs-lookup"><span data-stu-id="a4fda-126">For example, you can use the <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> method that sets all the items to the default value of type `T`.</span></span>

<span data-ttu-id="a4fda-127">Począwszy od języka C# 7,3, można użyć składni inicjatora tablicy do zdefiniowania zawartości nowo przydzieloną pamięć.</span><span class="sxs-lookup"><span data-stu-id="a4fda-127">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="a4fda-128">Poniższy przykład ilustruje różne sposoby, aby to zrobić:</span><span class="sxs-lookup"><span data-stu-id="a4fda-128">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](snippets/shared/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="a4fda-129">W wyrażeniu `stackalloc T[E]` `T` musi być [typem niezarządzanym](../builtin-types/unmanaged-types.md) i `E` musi być wynikiem obliczenia nieujemnej wartości [int](../builtin-types/integral-numeric-types.md) .</span><span class="sxs-lookup"><span data-stu-id="a4fda-129">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must evaluate to a non-negative [int](../builtin-types/integral-numeric-types.md) value.</span></span>

## <a name="security"></a><span data-ttu-id="a4fda-130">Zabezpieczenia</span><span class="sxs-lookup"><span data-stu-id="a4fda-130">Security</span></span>

<span data-ttu-id="a4fda-131">Korzystanie z programu `stackalloc` automatycznie włącza funkcje wykrywania przepełnienia buforu w środowisku uruchomieniowym języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="a4fda-131">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="a4fda-132">Jeśli wykryto przepełnienie buforu, proces zostaje zakończony jak najszybciej, aby zminimalizować prawdopodobieństwo wykonania złośliwego kodu.</span><span class="sxs-lookup"><span data-stu-id="a4fda-132">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a4fda-133">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a4fda-133">C# language specification</span></span>

<span data-ttu-id="a4fda-134">Aby uzyskać więcej informacji, zobacz sekcję [Alokacja stosu](~/_csharplang/spec/unsafe-code.md#stack-allocation) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md) i zapoznaj się z propozycją oferta funkcji [w przypadku `stackalloc` zagnieżdżonych kontekstów](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) .</span><span class="sxs-lookup"><span data-stu-id="a4fda-134">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4fda-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a4fda-135">See also</span></span>

- [<span data-ttu-id="a4fda-136">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a4fda-136">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a4fda-137">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="a4fda-137">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="a4fda-138">Operatory związane ze wskaźnikiem</span><span class="sxs-lookup"><span data-stu-id="a4fda-138">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="a4fda-139">Typy wskaźnika</span><span class="sxs-lookup"><span data-stu-id="a4fda-139">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="a4fda-140">Pamięć i typy związane z zakresem</span><span class="sxs-lookup"><span data-stu-id="a4fda-140">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="a4fda-141">DOS i stackalloc</span><span class="sxs-lookup"><span data-stu-id="a4fda-141">Dos and Don'ts of stackalloc</span></span>](https://vcsjones.dev/2020/02/24/stackalloc/)
