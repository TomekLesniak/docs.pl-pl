---
description: Ustaw słowo kluczowe — odwołanie w C#
title: Ustaw słowo kluczowe — odwołanie w C#
ms.date: 03/10/2017
f1_keywords:
- set
- set_CSharpKeyword
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
ms.openlocfilehash: ff0c99e5d4d6271351783befd6650d9a77f39886
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136918"
---
# <a name="set-c-reference"></a><span data-ttu-id="73a24-103">set (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="73a24-103">set (C# Reference)</span></span>

<span data-ttu-id="73a24-104">`set`Słowo kluczowe definiuje metodę *dostępu* we właściwości lub indeksatora, która przypisuje wartość do właściwości lub elementu indeksatora.</span><span class="sxs-lookup"><span data-stu-id="73a24-104">The `set` keyword defines an *accessor* method in a property or indexer that assigns a value to the property or the indexer element.</span></span> <span data-ttu-id="73a24-105">Aby uzyskać więcej informacji i przykładów, zobacz [Właściwości](../../programming-guide/classes-and-structs/properties.md), [zaimplementowane właściwości](../../programming-guide/classes-and-structs/auto-implemented-properties.md), i [indeksatory](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="73a24-105">For more information and examples, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md), and [Indexers](../../programming-guide/indexers/index.md).</span></span>

<span data-ttu-id="73a24-106">W poniższym przykładzie zdefiniowano `get` `set` metodę dostępu a i dla właściwości o nazwie `Seconds` .</span><span class="sxs-lookup"><span data-stu-id="73a24-106">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="73a24-107">Używa pola prywatnego o nazwie `_seconds` do wstecz wartości właściwości.</span><span class="sxs-lookup"><span data-stu-id="73a24-107">It uses a private field named `_seconds` to back the property value.</span></span>

[!code-csharp[set#1](~/samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]

<span data-ttu-id="73a24-108">Często `set` metoda dostępu składa się z pojedynczej instrukcji, która przypisuje wartość, tak jak w poprzednim przykładzie.</span><span class="sxs-lookup"><span data-stu-id="73a24-108">Often, the `set` accessor consists of a single statement that assigns a value, as it did in the previous example.</span></span> <span data-ttu-id="73a24-109">Począwszy od języka C# 7,0, można zaimplementować `set` metodę dostępu jako element członkowski będący w postaci wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="73a24-109">Starting with C# 7.0, you can implement the `set` accessor as an expression-bodied member.</span></span> <span data-ttu-id="73a24-110">W poniższym przykładzie zaimplementowane są `get` i metody `set` dostępu jako elementy członkowskie, które są członkami wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="73a24-110">The following example implements both the `get` and the `set` accessors as expression-bodied members.</span></span>

[!code-csharp[set#3](~/samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]
  
<span data-ttu-id="73a24-111">W przypadku prostych przypadków, w których właściwości `get` i metody `set` dostępu nie wykonują innej operacji niż ustawienie lub pobranie wartości w prywatnym polu zapasowym, można skorzystać z obsługi kompilatora języka C# dla właściwości, które są implementowane.</span><span class="sxs-lookup"><span data-stu-id="73a24-111">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="73a24-112">Poniższy przykład implementuje `Hours` jako właściwość, która jest implementowana.</span><span class="sxs-lookup"><span data-stu-id="73a24-112">The following example implements `Hours` as an auto-implemented property.</span></span>

[!code-csharp[set#2](~/samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="73a24-113">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="73a24-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="73a24-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="73a24-114">See also</span></span>

- [<span data-ttu-id="73a24-115">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="73a24-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="73a24-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="73a24-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="73a24-117">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="73a24-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="73a24-118">Właściwości</span><span class="sxs-lookup"><span data-stu-id="73a24-118">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
