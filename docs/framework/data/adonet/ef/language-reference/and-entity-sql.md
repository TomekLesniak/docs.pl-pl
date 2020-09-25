---
title: '&amp;&amp; LUB (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 86ff43f8ed20c5696d15e21284394c3cb63200e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198044"
---
# <a name="ampamp-and-entity-sql"></a>&amp;&amp; LUB (Entity SQL)

Zwraca `true` Jeśli oba wyrażenia są `true` ; w przeciwnym razie `false` lub `NULL` .  
  
## <a name="syntax"></a>Składnia  
  
```csharp  
boolean_expression AND boolean_expression
```

lub  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a>Argumenty  

 `boolean_expression`  
 Dowolne prawidłowe wyrażenie zwracające wartość logiczną.  
  
## <a name="remarks"></a>Uwagi  

 Podwójne znaki "i" (&&) mają takie same funkcje jak operator i.  
  
 W poniższej tabeli przedstawiono możliwe wartości wejściowe i typy zwracane.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|TRUE|FALSE|NULL|  
|`FALSE`|Fałsz|Fałsz|Fałsz|  
|`NULL`|NULL|FALSE|NULL|  
  
## <a name="example"></a>Przykład  

 W poniższym zapytaniu Entity SQL pokazano, jak używać operatora i. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
