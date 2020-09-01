---
description: Public — słowo kluczowe — odwołanie w C#
title: Public — słowo kluczowe — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 26edaf7538d11d082a4b8863228213c3ebc46937
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122345"
---
# <a name="public-c-reference"></a><span data-ttu-id="a5576-103">public (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="a5576-103">public (C# Reference)</span></span>

<span data-ttu-id="a5576-104">`public`Słowo kluczowe jest modyfikatorem dostępu dla typów i elementów członkowskich typu.</span><span class="sxs-lookup"><span data-stu-id="a5576-104">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="a5576-105">Dostęp publiczny to najwyższy poziom dostępu.</span><span class="sxs-lookup"><span data-stu-id="a5576-105">Public access is the most permissive access level.</span></span> <span data-ttu-id="a5576-106">Nie ma żadnych ograniczeń dotyczących uzyskiwania dostępu do publicznych członków, jak w tym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a5576-106">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="a5576-107">Aby uzyskać więcej informacji, zobacz [Modyfikatory dostępu](../../programming-guide/classes-and-structs/access-modifiers.md) i [poziomy dostępności](accessibility-levels.md) .</span><span class="sxs-lookup"><span data-stu-id="a5576-107">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="a5576-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="a5576-108">Example</span></span>

<span data-ttu-id="a5576-109">W poniższym przykładzie zadeklarowane są dwie klasy `PointTest` i `MainClass` .</span><span class="sxs-lookup"><span data-stu-id="a5576-109">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="a5576-110">Publiczne elementy członkowskie `x` i `y` `PointTest` są dostępne bezpośrednio z programu `MainClass` .</span><span class="sxs-lookup"><span data-stu-id="a5576-110">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="a5576-111">W przypadku zmiany `public` poziomu dostępu na [prywatny](private.md) lub [chroniony](protected.md)zostanie wyświetlony komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="a5576-111">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="a5576-112">Element "PointTest. y" jest niedostępny z powodu swojego poziomu ochrony.</span><span class="sxs-lookup"><span data-stu-id="a5576-112">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a5576-113">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a5576-113">C# language specification</span></span>  

<span data-ttu-id="a5576-114">Aby uzyskać więcej informacji, zobacz [zadeklarowane ułatwienia dostępu](~/_csharplang/spec/basic-concepts.md#declared-accessibility) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="a5576-114">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="a5576-115">Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="a5576-115">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5576-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a5576-116">See also</span></span>

- [<span data-ttu-id="a5576-117">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="a5576-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a5576-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="a5576-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a5576-119">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="a5576-119">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="a5576-120">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="a5576-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a5576-121">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="a5576-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="a5576-122">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="a5576-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="a5576-123">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="a5576-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="a5576-124">private</span><span class="sxs-lookup"><span data-stu-id="a5576-124">private</span></span>](private.md)
- [<span data-ttu-id="a5576-125">protected</span><span class="sxs-lookup"><span data-stu-id="a5576-125">protected</span></span>](protected.md)
- [<span data-ttu-id="a5576-126">internal</span><span class="sxs-lookup"><span data-stu-id="a5576-126">internal</span></span>](internal.md)
