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
# <a name="generics-and-arrays-c-programming-guide"></a>Typy ogólne i tablice (Przewodnik programowania w języku C#)

W języku C# 2,0 i nowszych tablic jednowymiarowych, które mają dolną granicę zero, są implementowane automatycznie <xref:System.Collections.Generic.IList%601> . Dzięki temu można tworzyć metody ogólne, które mogą używać tego samego kodu do iterowania za pomocą tablic i innych typów kolekcji. Ta technika jest szczególnie przydatna w przypadku odczytywania danych w kolekcjach. <xref:System.Collections.Generic.IList%601>Nie można użyć interfejsu do dodawania lub usuwania elementów z tablicy. Wyjątek zostanie wygenerowany w przypadku próby wywołania <xref:System.Collections.Generic.IList%601> metody, takiej jak <xref:System.Collections.Generic.IList%601.RemoveAt%2A> w przypadku tablicy w tym kontekście.  
  
 Poniższy przykład kodu demonstruje, jak pojedyncza Metoda ogólna pobierająca <xref:System.Collections.Generic.IList%601> parametr wejściowy może wykonywać iterację zarówno na liście, jak i w tablicy, w tym przypadku tablicą liczb całkowitych.  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Collections.Generic>
- [Przewodnik programowania w języku C#](../index.md)
- [Typy ogólne](./index.md)
- [Tablice](../arrays/index.md)
- [Typy ogólne](../../../standard/generics/index.md)
