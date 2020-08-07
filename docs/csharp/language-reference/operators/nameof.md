---
title: wyrażenie nameof — odwołanie w C#
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: b00c5f6f97d27290fb3773dcbb422bf9fb4c425b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916780"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="6368d-102">wyrażenie nameof (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="6368d-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="6368d-103">`nameof`Wyrażenie tworzy nazwę zmiennej, typu lub składowej jako stałą typu String:</span><span class="sxs-lookup"><span data-stu-id="6368d-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

<span data-ttu-id="6368d-104">Jak pokazano w powyższym przykładzie, w przypadku typu i przestrzeni nazw, wygenerowana nazwa zazwyczaj nie jest w [pełni kwalifikowana](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="6368d-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="6368d-105">W przypadku [identyfikatorów Verbatim](../tokens/verbatim.md) `@` znak nie jest częścią nazwy, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="6368d-105">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="6368d-106">`nameof`Wyrażenie jest oceniane w czasie kompilacji i nie ma wpływu na czas wykonywania.</span><span class="sxs-lookup"><span data-stu-id="6368d-106">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="6368d-107">Możesz użyć wyrażenia, `nameof` Aby zwiększyć łatwość obsługi kodu sprawdzania argumentów:</span><span class="sxs-lookup"><span data-stu-id="6368d-107">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="6368d-108">`nameof`Wyrażenie jest dostępne w języku C# 6 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="6368d-108">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6368d-109">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="6368d-109">C# language specification</span></span>

<span data-ttu-id="6368d-110">Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia nameof](~/_csharplang/spec/expressions.md#nameof-expressions) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="6368d-110">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6368d-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6368d-111">See also</span></span>

- [<span data-ttu-id="6368d-112">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="6368d-112">C# reference</span></span>](../index.md)
- [<span data-ttu-id="6368d-113">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="6368d-113">C# operators and expressions</span></span>](index.md)
