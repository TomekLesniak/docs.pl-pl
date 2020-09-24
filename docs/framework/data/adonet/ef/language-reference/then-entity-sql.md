---
title: NASTĘPNIE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: f038f242bc0873df3d72700aa05fca2f76f777ff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161675"
---
# <a name="then-entity-sql"></a>NASTĘPNIE (Entity SQL)

Wynik klauzuli WHEN, gdy jest obliczany `true` .  
  
## <a name="syntax"></a>Składnia  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>Argumenty  

 `when_expression`  
 Dowolne prawidłowe wyrażenie logiczne.  
  
 `then_expression`  
 Każde prawidłowe wyrażenie zapytania, które zwraca kolekcję.  
  
## <a name="remarks"></a>Uwagi  

 Jeśli `when_expression` zwraca wartość `true` , wynik jest odpowiedni `then-expression` . Jeśli żaden z warunków nie zostanie spełniony, `else-expression` zostanie obliczona wartość. Jeśli jednak nie ma `else-expression` , wynik ma wartość null.  
  
 Aby zapoznać się z przykładem, zobacz [wielkość liter](case-entity-sql.md).  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa wyrażenia CASE do obliczenia zestawu `Boolean` wyrażeń. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w [instrukcje: wykonywanie zapytania, które zwraca wyniki typu pierwotnego](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecutePrimitiveTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a>Zobacz też

- [SPRAW](case-entity-sql.md)
- [Odwołanie do jednostki SQL](entity-sql-reference.md)
