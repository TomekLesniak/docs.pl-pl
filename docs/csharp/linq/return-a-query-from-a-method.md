---
title: Zwracanie zapytania z metody
description: Jak zwrócić zapytanie.
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 646e771d637aa242231e3fe216d4a856bb156649
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203335"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a>Jak zwrócić zapytanie z metody (Przewodnik programowania w języku C#)

Ten przykład przedstawia sposób zwrócenia zapytania z metody jako wartości zwracanej i jako `out` parametru.  
  
 Obiekty zapytań są możliwe do redagowania, co oznacza, że można zwrócić zapytanie z metody. Obiekty reprezentujące zapytania nie przechowują wynikowej kolekcji, ale zamiast kroków w celu wygenerowania wyników w razie potrzeby. Zaletą zwracania obiektów zapytań z metod jest, że mogą one być bardziej złożone lub zmodyfikowane. W związku z tym wszystkie wartości zwracane lub `out` Parametry metody, która zwraca zapytanie, muszą również mieć ten typ. Jeśli metoda materializuje zapytanie w konkretną <xref:System.Collections.Generic.List%601> lub <xref:System.Array> typu, jest uważane za zwracające wyniki zapytania zamiast samego zapytania. Zmienna zapytania, która jest zwracana z metody, może być w dalszym ciągu złożona lub zmodyfikowana.  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie pierwsza metoda zwraca zapytanie jako wartość zwracaną, a druga metoda zwraca zapytanie jako `out` parametr. Należy zauważyć, że w obu przypadkach jest to zapytanie, które jest zwracane, a nie wyniki zapytania.  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a>Zobacz też

- [Language Integrated Query (LINQ)](index.md)
