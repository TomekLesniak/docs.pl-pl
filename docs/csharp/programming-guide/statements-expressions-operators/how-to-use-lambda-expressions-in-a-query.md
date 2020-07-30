---
title: Jak używać wyrażeń lambda w przewodniku programowania w języku Query-C#
description: Dowiedz się, jak używać wyrażeń lambda w kwerendzie. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: 501e67011707e2d165a3b9c1ff9f206db7f55448
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381635"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>Jak używać wyrażeń lambda w kwerendzie (Przewodnik programowania w języku C#)
Wyrażenia lambda nie są używane bezpośrednio w składni zapytania, ale są używane w wywołaniach metod, a wyrażenia zapytań mogą zawierać wywołania metody. W rzeczywistości niektóre operacje zapytań można wyrazić tylko w składni metody. Aby uzyskać więcej informacji o różnicach między składnią zapytania i składnią metody, zobacz [składnia zapytań i składnia metod w LINQ](../concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład ilustruje sposób użycia wyrażenia lambda w kwerendzie opartej na metodzie przy użyciu <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> standardowego operatora zapytań. Należy zauważyć, że <xref:System.Linq.Enumerable.Where%2A> Metoda w tym przykładzie ma parametr wejściowy typu delegata <xref:System.Func%602> i że delegat przyjmuje liczbę całkowitą jako dane wejściowe i zwraca wartość logiczną. Wyrażenie lambda można przekonwertować na tego delegata. Jeśli było to [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] zapytanie, które używało <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> metody, typem parametru będzie, `Expression<Func<int,bool>>` ale wyrażenie lambda będzie wyglądać dokładnie tak samo. Aby uzyskać więcej informacji na temat typu wyrażenia, zobacz <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType> .  
  
 [!code-csharp[csProgGuideLINQ#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#1)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład ilustruje sposób użycia wyrażenia lambda w wywołaniu metody wyrażenia zapytania. Lambda jest konieczne, ponieważ <xref:System.Linq.Enumerable.Sum%2A> standardowego operatora zapytania nie można wywołać przy użyciu składni zapytania.  
  
 Zapytanie najpierw grupuje uczniów zgodnie z ich poziomem klasy, zgodnie z definicją w `GradeLevel` wyliczeniu. Następnie dla każdej grupy dodaje wszystkie wyniki dla każdego ucznia. Wymaga to dwóch `Sum` operacji. Wewnętrzna `Sum` oblicza łączny wynik dla każdego ucznia, a zewnętrzny `Sum` utrzymuje uruchomiony, łączny łącznie dla wszystkich uczniów w grupie.  
  
 [!code-csharp[csProgGuideLINQ#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#2)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Aby uruchomić ten kod, skopiuj i wklej metodę do `StudentClass` , która jest określona w [zapytaniu kolekcji obiektów](../../linq/query-a-collection-of-objects.md) i Wywołaj ją z `Main` metody.
  
## <a name="see-also"></a>Zobacz też

- [Wyrażenia lambda](./lambda-expressions.md)
- [Drzewa wyrażeń (C#)](../concepts/expression-trees/index.md)
