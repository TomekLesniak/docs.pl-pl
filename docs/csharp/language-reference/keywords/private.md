---
description: Private — słowo kluczowe — odwołanie w C#
title: Private — słowo kluczowe — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: e6f40712fd2cca6d7b1f64760f1c6c5dd5c71370
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139401"
---
# <a name="private-c-reference"></a><span data-ttu-id="db39a-103">private (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="db39a-103">private (C# Reference)</span></span>

<span data-ttu-id="db39a-104">`private`Słowo kluczowe jest modyfikatorem dostępu składowej.</span><span class="sxs-lookup"><span data-stu-id="db39a-104">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="db39a-105">Ta strona dotyczy `private` dostępu.</span><span class="sxs-lookup"><span data-stu-id="db39a-105">This page covers `private` access.</span></span> <span data-ttu-id="db39a-106">`private`Słowo kluczowe jest również częścią [`private protected`](./private-protected.md) modyfikatora dostępu.</span><span class="sxs-lookup"><span data-stu-id="db39a-106">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="db39a-107">Dostęp prywatny to najmniejszy poziom dostępu.</span><span class="sxs-lookup"><span data-stu-id="db39a-107">Private access is the least permissive access level.</span></span> <span data-ttu-id="db39a-108">Prywatne elementy członkowskie są dostępne tylko w treści klasy lub struktury, w której są zadeklarowane, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="db39a-108">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="db39a-109">Typy zagnieżdżone w tej samej treści mogą również uzyskiwać dostęp do tych prywatnych członków.</span><span class="sxs-lookup"><span data-stu-id="db39a-109">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="db39a-110">Jest to błąd czasu kompilacji, który odwołuje się do prywatnego elementu członkowskiego spoza klasy lub struktury, w której jest zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="db39a-110">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="db39a-111">Aby uzyskać porównanie `private` z innymi modyfikatorami dostępu, zobacz [poziomy dostępności](accessibility-levels.md) i [Modyfikatory dostępu](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="db39a-111">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="db39a-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="db39a-112">Example</span></span>

<span data-ttu-id="db39a-113">W tym przykładzie `Employee` Klasa zawiera dwa prywatne elementy członkowskie danych `name` i `salary` .</span><span class="sxs-lookup"><span data-stu-id="db39a-113">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="db39a-114">Jako prywatne elementy członkowskie nie są dostępne z wyjątkiem metod składowych.</span><span class="sxs-lookup"><span data-stu-id="db39a-114">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="db39a-115">Metody publiczne o nazwie `GetName` i `Salary` są dodawane w celu umożliwienia kontrolowanego dostępu do prywatnych członków.</span><span class="sxs-lookup"><span data-stu-id="db39a-115">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="db39a-116">`name`Dostęp do elementu członkowskiego uzyskuje się za pomocą metody publicznej, a `salary` członek jest dostępny w postaci publicznej właściwości tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="db39a-116">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="db39a-117">(Zobacz [Właściwości](../../programming-guide/classes-and-structs/properties.md) , aby uzyskać więcej informacji).</span><span class="sxs-lookup"><span data-stu-id="db39a-117">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="db39a-118">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="db39a-118">C# language specification</span></span>  

<span data-ttu-id="db39a-119">Aby uzyskać więcej informacji, zobacz [zadeklarowane ułatwienia dostępu](~/_csharplang/spec/basic-concepts.md#declared-accessibility) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="db39a-119">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="db39a-120">Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="db39a-120">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="db39a-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="db39a-121">See also</span></span>

- [<span data-ttu-id="db39a-122">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="db39a-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="db39a-123">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="db39a-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="db39a-124">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="db39a-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="db39a-125">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="db39a-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="db39a-126">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="db39a-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="db39a-127">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="db39a-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="db39a-128">public</span><span class="sxs-lookup"><span data-stu-id="db39a-128">public</span></span>](public.md)
- [<span data-ttu-id="db39a-129">protected</span><span class="sxs-lookup"><span data-stu-id="db39a-129">protected</span></span>](protected.md)
- [<span data-ttu-id="db39a-130">internal</span><span class="sxs-lookup"><span data-stu-id="db39a-130">internal</span></span>](internal.md)
