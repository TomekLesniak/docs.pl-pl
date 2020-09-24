---
title: Typy ogólne i tablice — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat typów ogólnych i tablic w programowaniu języka C#. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: 808e9ddafea9806a74ccd105c8850e7b77b563be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151457"
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="77b27-104">Typy ogólne i tablice (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="77b27-104">Generics and Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="77b27-105">W języku C# 2,0 i nowszych tablic jednowymiarowych, które mają dolną granicę zero, są implementowane automatycznie <xref:System.Collections.Generic.IList%601> .</span><span class="sxs-lookup"><span data-stu-id="77b27-105">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="77b27-106">Dzięki temu można tworzyć metody ogólne, które mogą używać tego samego kodu do iterowania za pomocą tablic i innych typów kolekcji.</span><span class="sxs-lookup"><span data-stu-id="77b27-106">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="77b27-107">Ta technika jest szczególnie przydatna w przypadku odczytywania danych w kolekcjach.</span><span class="sxs-lookup"><span data-stu-id="77b27-107">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="77b27-108"><xref:System.Collections.Generic.IList%601>Nie można użyć interfejsu do dodawania lub usuwania elementów z tablicy.</span><span class="sxs-lookup"><span data-stu-id="77b27-108">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="77b27-109">Wyjątek zostanie wygenerowany w przypadku próby wywołania <xref:System.Collections.Generic.IList%601> metody, takiej jak <xref:System.Collections.Generic.IList%601.RemoveAt%2A> w przypadku tablicy w tym kontekście.</span><span class="sxs-lookup"><span data-stu-id="77b27-109">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="77b27-110">Poniższy przykład kodu demonstruje, jak pojedyncza Metoda ogólna pobierająca <xref:System.Collections.Generic.IList%601> parametr wejściowy może wykonywać iterację zarówno na liście, jak i w tablicy, w tym przypadku tablicą liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="77b27-110">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a><span data-ttu-id="77b27-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="77b27-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="77b27-112">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="77b27-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="77b27-113">Typy ogólne</span><span class="sxs-lookup"><span data-stu-id="77b27-113">Generics</span></span>](./index.md)
- [<span data-ttu-id="77b27-114">Tablice</span><span class="sxs-lookup"><span data-stu-id="77b27-114">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="77b27-115">Typy ogólne</span><span class="sxs-lookup"><span data-stu-id="77b27-115">Generics</span></span>](../../../standard/generics/index.md)
