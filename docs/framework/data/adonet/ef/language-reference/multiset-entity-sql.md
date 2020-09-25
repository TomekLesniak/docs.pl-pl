---
title: Zestaw WIELOKROTNy (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: a81787da9ee1af084a903dcb50b024f3d26d18fc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175697"
---
# <a name="multiset-entity-sql"></a>Zestaw WIELOKROTNy (Entity SQL)

Tworzy wystąpienie zestawu wielokrotnego z listy wartości. Wszystkie wartości w konstruktorze zestawów wielokrotnych muszą być zgodne z typem `T` . Puste konstruktory wielu zestawów są niedozwolone.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
MULTISET ( expression [{, expression }] )  
-- or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a>Argumenty  

 `expression`  
 Dowolna prawidłowa lista wartości.  
  
## <a name="return-value"></a>Wartość zwracana  

 Kolekcja zestawu WIELOKROTNego \<T> .  
  
## <a name="remarks"></a>Uwagi  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] oferuje trzy rodzaje konstruktorów: konstruktory wierszy, konstruktory obiektów i konstruktory wielokrotnego (lub kolekcji). Aby uzyskać więcej informacji, zobacz [konstruowanie typów](constructing-types-entity-sql.md).  
  
 Konstruktor zestawów wielokrotnych tworzy wystąpienie zestawu wielokrotnego z listy wartości. Wszystkie wartości w konstruktorze muszą być zgodnego typu.  
  
 Na przykład następujące wyrażenie tworzy zestaw wielokrotny dla liczb całkowitych.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
> Zagnieżdżone literały zestawu wielokrotnego są obsługiwane tylko wtedy, gdy zestaw wielokrotny zawijania zawiera pojedynczy element wielokrotnego zestawu. na przykład `{{1, 2, 3}}` . Gdy zestaw wielokrotny zawijania ma wiele elementów wielokrotnych (na przykład `{{1, 2}, {3, 4}}` ), zagnieżdżone literały zestawów wielokrotnych nie są obsługiwane.  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora WIELOKROTNego tworzenia wystąpienia zestawu wielokrotnego na podstawie listy wartości. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#MULTISET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiset)]  
  
## <a name="see-also"></a>Zobacz też

- [Konstruowanie typów](constructing-types-entity-sql.md)
- [Odwołanie do jednostki SQL](entity-sql-reference.md)
