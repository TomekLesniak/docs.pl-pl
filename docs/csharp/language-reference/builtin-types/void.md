---
title: odwołanie typu void-C#
ms.date: 02/11/2020
f1_keywords:
- void_CSharpKeyword
- void
- (void)
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: faf1cea4d02ba042cd9fee1cfa6d18168c49dd61
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854987"
---
# <a name="void-c-reference"></a><span data-ttu-id="d5fc9-102">void (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="d5fc9-102">void (C# reference)</span></span>

<span data-ttu-id="d5fc9-103">Używasz `void` jako zwracanego typu [metody](../../programming-guide/classes-and-structs/methods.md) (lub [funkcji lokalnej](../../programming-guide/classes-and-structs/local-functions.md)), aby określić, że metoda nie zwraca wartości.</span><span class="sxs-lookup"><span data-stu-id="d5fc9-103">You use `void` as the return type of a [method](../../programming-guide/classes-and-structs/methods.md) (or a [local function](../../programming-guide/classes-and-structs/local-functions.md)) to specify that the method doesn't return a value.</span></span>

[!code-csharp[void method](snippets/VoidType.cs#VoidExample)]

<span data-ttu-id="d5fc9-104">Można również użyć `void` jako typu referent, aby zadeklarować wskaźnik do nieznanego typu.</span><span class="sxs-lookup"><span data-stu-id="d5fc9-104">You can also use `void` as a referent type to declare a pointer to an unknown type.</span></span> <span data-ttu-id="d5fc9-105">Aby uzyskać więcej informacji, zobacz [typy wskaźnika](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="d5fc9-105">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="d5fc9-106">Nie można użyć `void` jako typu zmiennej.</span><span class="sxs-lookup"><span data-stu-id="d5fc9-106">You cannot use `void` as the type of a variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5fc9-107">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d5fc9-107">See also</span></span>

- [<span data-ttu-id="d5fc9-108">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="d5fc9-108">C# reference</span></span>](../index.md)
- <xref:System.Void?displayProperty=nameWithType>
