---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: c0c975ab5cf2761496db6efa1f88f409aa1b1abd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148220"
---
# <a name="deref-entity-sql"></a>DEREF (Entity SQL)

Odwołuje się do wartości odniesienia i tworzy wynik tego odwołania.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
SELECT DEREF ( o.expression ) FROM Table AS o;
```  
  
## <a name="arguments"></a>Argumenty  

 `expression`  
 Każde prawidłowe wyrażenie zapytania, które zwraca kolekcję.  
  
## <a name="return-value"></a>Wartość zwracana  

 Wartość obiektu, do którego istnieje odwołanie.  
  
## <a name="remarks"></a>Uwagi  

 Operator DEREF odwołuje się do wartości odniesienia i tworzy wynik tego odwołania. Na przykład, jeśli `r` jest odwołaniem typu ref \<T> , `Deref(r)` to wyrażenie typu `T` , które zwraca jednostkę, do której odwołuje się `r` . Jeśli wartość odwołania ma wartość null lub jest zawieszonego (oznacza to, że obiekt docelowy odwołania nie istnieje), wynik operatora DEREF ma wartość null.  
  
## <a name="example"></a>Przykład  

 Poniższe [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie używa operatora DEREF, aby usunąć odwołanie do wartości odniesienia i utworzyć wynik tego odwołania. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w [instrukcje: wykonywanie zapytania, które zwraca wyniki typu pierwotnego](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do metody ExecutePrimitiveTypeQuery:  
  
 [!code-sql[DP EntityServices Concepts#DEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#deref)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
- [UMIESZCZONE](ref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [GŁÓWNYCH](key-entity-sql.md)
- [Typy strukturalne dopuszczające wartości Null](nullable-structured-types-entity-sql.md)
