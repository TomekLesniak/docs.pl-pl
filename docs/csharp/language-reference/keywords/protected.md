---
description: Protected — odwołanie w C#
title: Protected — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: af0c7ab5ebb6980bb0381e46fd38e9470f3a2152
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536759"
---
# <a name="protected-c-reference"></a><span data-ttu-id="1e772-103">protected (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="1e772-103">protected (C# Reference)</span></span>

<span data-ttu-id="1e772-104">`protected`Słowo kluczowe jest modyfikatorem dostępu składowej.</span><span class="sxs-lookup"><span data-stu-id="1e772-104">The `protected` keyword is a member access modifier.</span></span>

 > <span data-ttu-id="1e772-105">Ta strona dotyczy `protected` dostępu.</span><span class="sxs-lookup"><span data-stu-id="1e772-105">This page covers `protected` access.</span></span> <span data-ttu-id="1e772-106">`protected`Słowo kluczowe jest również częścią [`protected internal`](protected-internal.md) [`private protected`](private-protected.md) modyfikatorów i dostępu.</span><span class="sxs-lookup"><span data-stu-id="1e772-106">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="1e772-107">Chroniony element członkowski jest dostępny w jego klasie i wystąpieniach klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="1e772-107">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="1e772-108">Aby uzyskać porównanie `protected` z innymi modyfikatorami dostępu, zobacz [poziomy dostępności](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1e772-108">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="1e772-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="1e772-109">Example</span></span>

<span data-ttu-id="1e772-110">Chroniony element członkowski klasy bazowej jest dostępny w klasie pochodnej tylko wtedy, gdy dostęp odbywa się za pomocą typu klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="1e772-110">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="1e772-111">Rozważmy na przykład następujący segment kodu:</span><span class="sxs-lookup"><span data-stu-id="1e772-111">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="1e772-112">Instrukcja `a.x = 10` generuje błąd, ponieważ znajduje się w metodzie statycznej Main i nie jest wystąpieniem klasy B.</span><span class="sxs-lookup"><span data-stu-id="1e772-112">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="1e772-113">Elementy członkowskie struktury nie mogą być chronione, ponieważ struktura nie może być dziedziczona.</span><span class="sxs-lookup"><span data-stu-id="1e772-113">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="1e772-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="1e772-114">Example</span></span>

<span data-ttu-id="1e772-115">W tym przykładzie Klasa pochodzi `DerivedPoint` od `Point` .</span><span class="sxs-lookup"><span data-stu-id="1e772-115">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="1e772-116">W związku z tym można uzyskać dostęp do chronionych elementów członkowskich klasy bazowej bezpośrednio z klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="1e772-116">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="1e772-117">Jeśli zmienisz poziomy dostępu dla `x` i `y` na [prywatne](private.md), kompilator będzie wystawiał komunikaty o błędach:</span><span class="sxs-lookup"><span data-stu-id="1e772-117">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="1e772-118">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="1e772-118">C# language specification</span></span>  

<span data-ttu-id="1e772-119">Aby uzyskać więcej informacji, zobacz [zadeklarowane ułatwienia dostępu](~/_csharplang/spec/basic-concepts.md#declared-accessibility) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="1e772-119">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="1e772-120">Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="1e772-120">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e772-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1e772-121">See also</span></span>

- [<span data-ttu-id="1e772-122">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="1e772-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1e772-123">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="1e772-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1e772-124">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="1e772-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1e772-125">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="1e772-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="1e772-126">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="1e772-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="1e772-127">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="1e772-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="1e772-128">public</span><span class="sxs-lookup"><span data-stu-id="1e772-128">public</span></span>](public.md)
- [<span data-ttu-id="1e772-129">private</span><span class="sxs-lookup"><span data-stu-id="1e772-129">private</span></span>](private.md)
- [<span data-ttu-id="1e772-130">internal</span><span class="sxs-lookup"><span data-stu-id="1e772-130">internal</span></span>](internal.md)
- <span data-ttu-id="1e772-131">[Zagadnienia dotyczące zabezpieczeń wewnętrznych wirtualnych słów kluczowych](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1e772-131">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
