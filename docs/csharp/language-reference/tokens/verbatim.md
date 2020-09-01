---
description: Odwołanie do języka C#
title: Odwołanie do języka C#
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
ms.openlocfilehash: 7d78b28479ed6128321207073dc94976710f10b6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138907"
---
# <a name="-c-reference"></a><span data-ttu-id="a15e0-103">@ (Odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="a15e0-103">@ (C# Reference)</span></span>

<span data-ttu-id="a15e0-104">`@`Znak specjalny służy jako identyfikator Verbatim.</span><span class="sxs-lookup"><span data-stu-id="a15e0-104">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="a15e0-105">Może być używana w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="a15e0-105">It can be used in the following ways:</span></span>

1. <span data-ttu-id="a15e0-106">Aby włączyć używanie słów kluczowych języka C# jako identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="a15e0-106">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="a15e0-107">`@`Znak prefiksu elementu kodu, który kompilator ma interpretować jako identyfikator, a nie słowo kluczowe języka C#.</span><span class="sxs-lookup"><span data-stu-id="a15e0-107">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="a15e0-108">Poniższy przykład używa `@` znaku do definiowania identyfikatora o nazwie `for` , który używa w `for` pętli.</span><span class="sxs-lookup"><span data-stu-id="a15e0-108">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. <span data-ttu-id="a15e0-109">Aby wskazać, że literał ciągu ma być interpretowany Verbatim.</span><span class="sxs-lookup"><span data-stu-id="a15e0-109">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="a15e0-110">`@`Znak w tym wystąpieniu definiuje *literał ciągu Verbatim*.</span><span class="sxs-lookup"><span data-stu-id="a15e0-110">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="a15e0-111">Proste sekwencje ucieczki (takie jak `"\\"` dla ukośnika odwrotnego), szesnastkowe sekwencje ucieczki ( `"\x0041"` na przykład dla Wielkiej litery a) i sekwencje znaków Unicode ( `"\u0041"` na przykład dla Wielkiej litery a) są interpretowane dosłownie.</span><span class="sxs-lookup"><span data-stu-id="a15e0-111">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A), and Unicode escape sequences (such as `"\u0041"` for an uppercase A) are interpreted literally.</span></span> <span data-ttu-id="a15e0-112">Tylko sekwencja ucieczki oferty ( `""` ) nie jest interpretowana dosłownie; tworzy jeden podwójny cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="a15e0-112">Only a quote escape sequence (`""`) is not interpreted literally; it produces one double quotation mark.</span></span> <span data-ttu-id="a15e0-113">Ponadto w przypadku Verbatim [interpolowanego](interpolated.md) nawiasu klamrowego sekwencje ucieczki ( `{{` i `}}` ) nie są interpretowane dosłownie; tworzą one pojedyncze nawiasy klamrowe.</span><span class="sxs-lookup"><span data-stu-id="a15e0-113">Additionally, in case of a verbatim [interpolated string](interpolated.md) brace escape sequences (`{{` and `}}`) are not interpreted literally; they produce single brace characters.</span></span> <span data-ttu-id="a15e0-114">W poniższym przykładzie zdefiniowano dwie identyczne ścieżki plików, jeden przy użyciu zwykłego literału ciągu, a drugi przy użyciu literału ciągu Verbatim.</span><span class="sxs-lookup"><span data-stu-id="a15e0-114">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="a15e0-115">Jest to jeden z najczęściej używanych Verbatim literałów ciągów.</span><span class="sxs-lookup"><span data-stu-id="a15e0-115">This is one of the more common uses of verbatim string literals.</span></span>

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   <span data-ttu-id="a15e0-116">Poniższy przykład ilustruje efekt definiowania zwykłego literału ciągu i literału ciągu Verbatim, który zawiera identyczne sekwencje znaków.</span><span class="sxs-lookup"><span data-stu-id="a15e0-116">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. <span data-ttu-id="a15e0-117">Aby umożliwić kompilatorowi rozróżnienie atrybutów w przypadkach konfliktu nazw.</span><span class="sxs-lookup"><span data-stu-id="a15e0-117">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="a15e0-118">Atrybut jest klasą, która pochodzi od <xref:System.Attribute> .</span><span class="sxs-lookup"><span data-stu-id="a15e0-118">An attribute is a class that derives from <xref:System.Attribute>.</span></span> <span data-ttu-id="a15e0-119">Nazwa typu zwykle zawiera **atrybut**sufiksu, chociaż kompilator nie wymusza tej Konwencji.</span><span class="sxs-lookup"><span data-stu-id="a15e0-119">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="a15e0-120">Atrybut może następnie być przywoływany w kodzie według jego pełnej nazwy typu (na przykład `[InfoAttribute]` lub jego skróconej nazwy (na przykład `[Info]` ).</span><span class="sxs-lookup"><span data-stu-id="a15e0-120">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="a15e0-121">Jednak konflikt nazewnictwa występuje, jeśli dwa skrócone nazwy typów atrybutów są identyczne, a jedna nazwa typu zawiera sufiks **atrybutu** , ale drugi nie.</span><span class="sxs-lookup"><span data-stu-id="a15e0-121">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="a15e0-122">Na przykład następujący kod nie zostanie skompilowany, ponieważ kompilator nie może określić, czy `Info` atrybut lub `InfoAttribute` jest stosowany do `Example` klasy.</span><span class="sxs-lookup"><span data-stu-id="a15e0-122">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Example` class.</span></span> <span data-ttu-id="a15e0-123">Aby uzyskać więcej informacji, zobacz [CS1614](../compiler-messages/cs1614.md) .</span><span class="sxs-lookup"><span data-stu-id="a15e0-123">See [CS1614](../compiler-messages/cs1614.md) for more information.</span></span>

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim2.cs#1)]

## <a name="see-also"></a><span data-ttu-id="a15e0-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a15e0-124">See also</span></span>

- [<span data-ttu-id="a15e0-125">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="a15e0-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a15e0-126">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="a15e0-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a15e0-127">Znaki specjalne w języku C#</span><span class="sxs-lookup"><span data-stu-id="a15e0-127">C# Special Characters</span></span>](./index.md)
