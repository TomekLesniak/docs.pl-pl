---
description: niebezpieczne słowo kluczowe — odwołanie w C#
title: niebezpieczne słowo kluczowe — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 2e047a4cff77877862c5cbbb5e49eb1a75b42499
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141962"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="2b41f-103">unsafe (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="2b41f-103">unsafe (C# Reference)</span></span>

<span data-ttu-id="2b41f-104">`unsafe`Słowo kluczowe oznacza niebezpieczny kontekst, który jest wymagany dla każdej operacji obejmującej wskaźniki.</span><span class="sxs-lookup"><span data-stu-id="2b41f-104">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="2b41f-105">Aby uzyskać więcej informacji, zobacz artykuł [niebezpieczny kod i wskaźniki](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="2b41f-105">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="2b41f-106">Można użyć `unsafe` modyfikatora w deklaracji typu lub elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="2b41f-106">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="2b41f-107">Cały tekstowy zakres typu lub elementu członkowskiego jest traktowany jako niebezpieczny kontekst.</span><span class="sxs-lookup"><span data-stu-id="2b41f-107">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="2b41f-108">Na przykład następująca metoda jest zadeklarowana z `unsafe` modyfikatorem:</span><span class="sxs-lookup"><span data-stu-id="2b41f-108">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="2b41f-109">Zakres niebezpiecznego kontekstu rozciąga się od listy parametrów na koniec metody, dlatego na liście parametrów można również używać wskaźników:</span><span class="sxs-lookup"><span data-stu-id="2b41f-109">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="2b41f-110">Można również użyć niebezpiecznego bloku, aby umożliwić użycie niebezpiecznego kodu wewnątrz tego bloku.</span><span class="sxs-lookup"><span data-stu-id="2b41f-110">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="2b41f-111">Przykład:</span><span class="sxs-lookup"><span data-stu-id="2b41f-111">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="2b41f-112">Aby skompilować niebezpieczny kod, należy określić [`-unsafe`](../compiler-options/unsafe-compiler-option.md) opcję kompilatora.</span><span class="sxs-lookup"><span data-stu-id="2b41f-112">To compile unsafe code, you must specify the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="2b41f-113">Kod niebezpieczny nie jest możliwy do zweryfikowania przez środowisko uruchomieniowe języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="2b41f-113">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="2b41f-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="2b41f-114">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="2b41f-115">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="2b41f-115">C# language specification</span></span>

<span data-ttu-id="2b41f-116">Aby uzyskać więcej informacji, zobacz artykuł [niebezpieczny kod](~/_csharplang/spec/unsafe-code.md) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="2b41f-116">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="2b41f-117">Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="2b41f-117">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b41f-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2b41f-118">See also</span></span>

- [<span data-ttu-id="2b41f-119">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="2b41f-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2b41f-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="2b41f-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2b41f-121">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="2b41f-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2b41f-122">fixed, instrukcja</span><span class="sxs-lookup"><span data-stu-id="2b41f-122">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="2b41f-123">Niebezpieczny kod i wskaźniki</span><span class="sxs-lookup"><span data-stu-id="2b41f-123">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="2b41f-124">Bufory o ustalonym rozmiarze</span><span class="sxs-lookup"><span data-stu-id="2b41f-124">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
