---
description: Dokumentacja Get-C#
title: Dokumentacja Get-C#
ms.date: 03/10/2017
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
ms.openlocfilehash: 7e13dc3ed6577717c64b4e36000a9e090f7b4751
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89139739"
---
# <a name="get-c-reference"></a><span data-ttu-id="8e164-103">get (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="8e164-103">get (C# Reference)</span></span>

<span data-ttu-id="8e164-104">`get`Słowo kluczowe definiuje metodę *dostępu* we właściwości lub indeksatora, która zwraca wartość właściwości lub element indeksatora.</span><span class="sxs-lookup"><span data-stu-id="8e164-104">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="8e164-105">Aby uzyskać więcej informacji, zobacz [Właściwości](../../programming-guide/classes-and-structs/properties.md), [zaimplementowane właściwości](../../programming-guide/classes-and-structs/auto-implemented-properties.md) i [indeksatory](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="8e164-105">For more information, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="8e164-106">W poniższym przykładzie zdefiniowano `get` `set` metodę dostępu a i dla właściwości o nazwie `Seconds` .</span><span class="sxs-lookup"><span data-stu-id="8e164-106">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="8e164-107">Używa pola prywatnego o nazwie `_seconds` do wstecz wartości właściwości.</span><span class="sxs-lookup"><span data-stu-id="8e164-107">It uses a private field named `_seconds` to back the property value.</span></span>  

 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
<span data-ttu-id="8e164-108">Często `get` metoda dostępu składa się z pojedynczej instrukcji, która zwraca wartość, tak jak w poprzednim przykładzie.</span><span class="sxs-lookup"><span data-stu-id="8e164-108">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="8e164-109">Począwszy od języka C# 7,0, można zaimplementować `get` metodę dostępu jako element członkowski będący w postaci wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="8e164-109">Starting with C# 7.0, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="8e164-110">W poniższym przykładzie zaimplementowane są `get` i `set` Akcesory jako elementy członkowskie z wyrażeniami.</span><span class="sxs-lookup"><span data-stu-id="8e164-110">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]

<span data-ttu-id="8e164-111">W przypadku prostych przypadków, w których właściwości `get` i metody `set` dostępu nie wykonują innej operacji niż ustawienie lub pobranie wartości w prywatnym polu zapasowym, można skorzystać z obsługi kompilatora języka C# dla właściwości, które są implementowane.</span><span class="sxs-lookup"><span data-stu-id="8e164-111">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="8e164-112">Poniższy przykład implementuje `Hours` jako właściwość, która jest implementowana.</span><span class="sxs-lookup"><span data-stu-id="8e164-112">The following example implements `Hours` as an auto-implemented property.</span></span>
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8e164-113">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="8e164-113">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e164-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8e164-114">See also</span></span>

- [<span data-ttu-id="8e164-115">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="8e164-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8e164-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="8e164-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8e164-117">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="8e164-117">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="8e164-118">Właściwości</span><span class="sxs-lookup"><span data-stu-id="8e164-118">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
