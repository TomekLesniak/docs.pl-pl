---
title: '|| ORAZ (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 89c0a92030f2f067d5e5d45b58d475414a224ce4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150807"
---
# <a name="-or-entity-sql"></a>|| ORAZ (Entity SQL)

Łączy dwa `Boolean` wyrażenia.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
boolean_expression OR boolean_expression  
-- or
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Argumenty  

 `boolean_expression`  
 Dowolne prawidłowe wyrażenie zwracające wartość `Boolean` .  
  
## <a name="return-value"></a>Wartość zwracana  

 `true` gdy jeden z warunków jest `true` ; w przeciwnym razie, `false` .  
  
## <a name="remarks"></a>Uwagi  

 OR jest [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorem logicznym. Służy do łączenia dwóch warunków. Gdy w instrukcji użyto więcej niż jednego operatora logicznego, operatory są oceniane po operatorze i. Można jednak zmienić kolejność obliczeń przy użyciu nawiasów.  
  
 Podwójne pionowe słupki (&#124;&#124;) mają takie same funkcje jak operator OR.  
  
 W poniższej tabeli przedstawiono możliwe wartości wejściowe i typy zwracane.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|Prawda|Prawda|Prawda|  
|`FALSE`|Prawda|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora OR do łączenia dwóch `Boolean` wyrażeń. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts 2#OR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#or)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
