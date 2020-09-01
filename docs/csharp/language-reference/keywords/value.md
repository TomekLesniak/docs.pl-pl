---
description: wartość kontekstowego słowa kluczowego — odwołanie w C#
title: wartość kontekstowego słowa kluczowego — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: f72e9f097880d9de725a85a0973001baaefd9a9c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141741"
---
# <a name="value-c-reference"></a><span data-ttu-id="a2329-103">value (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="a2329-103">value (C# Reference)</span></span>

<span data-ttu-id="a2329-104">Kontekstowe słowo kluczowe `value` jest używane w `set` metodzie dostępu w deklaracjach [Właściwości](../../programming-guide/classes-and-structs/properties.md) i [indeksatora](../../programming-guide/indexers/index.md) .</span><span class="sxs-lookup"><span data-stu-id="a2329-104">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="a2329-105">Jest podobny do parametru wejściowego metody.</span><span class="sxs-lookup"><span data-stu-id="a2329-105">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="a2329-106">Słowo `value` odwołuje się do wartości, którą kod klienta próbuje przypisać do właściwości lub indeksatora.</span><span class="sxs-lookup"><span data-stu-id="a2329-106">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="a2329-107">W poniższym przykładzie `MyDerivedClass` ma właściwość o nazwie, `Name` która używa `value` parametru do przypisywania nowego ciągu do pola zapasowego `name` .</span><span class="sxs-lookup"><span data-stu-id="a2329-107">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="a2329-108">Z punktu widzenia kodu klienta operacja jest zapisywana jako proste przypisanie.</span><span class="sxs-lookup"><span data-stu-id="a2329-108">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="a2329-109">Aby uzyskać więcej informacji, zobacz artykuły [Properties](../../programming-guide/classes-and-structs/properties.md) i [Indexeres](../../programming-guide/indexers/index.md) .</span><span class="sxs-lookup"><span data-stu-id="a2329-109">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexeres](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a2329-110">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a2329-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a2329-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a2329-111">See also</span></span>

- [<span data-ttu-id="a2329-112">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="a2329-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a2329-113">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="a2329-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a2329-114">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="a2329-114">C# Keywords</span></span>](index.md)
