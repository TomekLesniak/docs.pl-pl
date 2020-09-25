---
title: Porównania wartości Null
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: 71b7c4d86debe8cf267b1b65e3d176cbc4704e6d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185109"
---
# <a name="null-comparisons"></a>Porównania wartości Null

`null`Wartość w źródle danych wskazuje, że wartość jest nieznana. W LINQ to Entities zapytaniach można sprawdzać wartości null, aby pewne obliczenia lub porównania były wykonywane tylko dla wierszy, które mają prawidłowe lub inne niż null dane. Semantyka języka CLR o wartości null może jednak różnić się od semantyki o wartości null źródła danych. Większość baz danych używa wersji logiki trójwarstwowej do obsługi porównań o wartości null. Oznacza to, że porównanie z wartością null nie jest wynikiem obliczenia do wartości `true` lub `false` `unknown` . Często jest to implementacja wartości null ANSI, ale nie zawsze jest to przypadek.  
  
 Domyślnie w SQL Server porównanie wartości null-Equals-NULL zwraca wartość null. W poniższym przykładzie wiersze, które `ShipDate` mają wartość null, są wykluczone z zestawu wyników, a instrukcja języka Transact-SQL zwróci 0 wierszy.  
  
```sql  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 Jest to bardzo różne od semantyki języka CLR o wartości null, gdzie porównanie NULL-Equals-NULL zwraca wartość true.  
  
 Poniższe zapytanie LINQ jest wyrażone w środowisku CLR, ale jest wykonywane w źródle danych. Ponieważ nie ma żadnej gwarancji, że semantyka środowiska CLR zostanie zastosowana w źródle danych, oczekiwane zachowanie jest nieokreślone.  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## <a name="key-selectors"></a>Selektory kluczy  

 *Selektor klucza* jest funkcją używaną w standardowych operatorach zapytań do wyodrębniania klucza z elementu. W funkcji selektora kluczy wyrażenie można porównać z stałą. Semantyka wartości null CLR jest zaprezentowania, jeśli wyrażenie jest porównywane ze stałą o wartości null lub dwie stałe wartości null są porównywane. Semantyka wartości null magazynu jest zastawiona, jeśli dwie kolumny zawierające wartości null w źródle danych są porównywane. Selektory kluczy są dostępne w wielu standardowych operatorów zapytań grupowania i porządkowania, takich jak <xref:System.Linq.Queryable.GroupBy%2A> , i służą do wybierania kluczy, według których mają być uporządkowane lub grupowane wyniki zapytania.  
  
## <a name="null-property-on-a-null-object"></a>Właściwość null dla obiektu o wartości null  

 W Entity Framework właściwości obiektu null mają wartość null. Podczas próby odwołania się do właściwości obiektu o wartości null w środowisku CLR zostanie wyświetlony komunikat <xref:System.NullReferenceException> . Gdy zapytanie LINQ obejmuje właściwość obiektu o wartości null, może to spowodować niespójne zachowanie.  
  
 Na przykład w poniższym zapytaniu rzutowanie `NewProduct` jest wykonywane w warstwie drzewa poleceń, co może spowodować, że `Introduced` Właściwość ma wartość null. Jeśli baza danych ma zdefiniowane porównania o wartości null w taki sposób, że wynikiem <xref:System.DateTime> porównania jest wartość true, wiersz zostanie uwzględniony.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>Przekazywanie kolekcji o wartości null do funkcji agregujących  

 W LINQ to Entities, gdy przekazujesz kolekcję, która obsługuje `IQueryable` funkcję agregującą, operacje agregacji są wykonywane w bazie danych. W wyniku zapytania, które zostało wykonane w pamięci, i zapytania, które zostało wykonane w bazie danych, mogą wystąpić różnice. W zapytaniu w pamięci, jeśli nie ma żadnych dopasowań, zapytanie zwróci wartość zero. W bazie danych ta sama kwerenda zwraca wartość `null` . Jeśli `null` wartość jest przenoszona do funkcji agregującej LINQ, zostanie zgłoszony wyjątek. Aby zaakceptować możliwe `null` wartości, należy rzutować typy i właściwości typów, które odbierają wyniki zapytania do typów wartości null.  
  
## <a name="see-also"></a>Zobacz też

- [Wyrażenia w zapytaniach składnika LINQ to Entities](expressions-in-linq-to-entities-queries.md)
