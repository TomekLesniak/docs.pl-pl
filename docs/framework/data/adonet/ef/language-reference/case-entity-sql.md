---
title: PRZYPADEK (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: 65efedd36401db402a32748afaebff0f2af9f2a7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185226"
---
# <a name="case-entity-sql"></a>PRZYPADEK (Entity SQL)

Oblicza zestaw `Boolean` wyrażeń, aby określić wynik.  
  
## <a name="syntax"></a>Składnia  
  
```csharp  
CASE  
     WHEN Boolean_expression THEN result_expression
    [ ...n ]
     [
    ELSE else_result_expression
     ]
END  
```  
  
## <a name="arguments"></a>Argumenty  

 `n`  
 Jest symbolem zastępczym, który wskazuje, że `Boolean_expression` `result_expression` można użyć wielu klauzule then.  
  
 NASTĘPNIE `result_expression`  
 Jest wyrażeniem zwracanym podczas `Boolean_expression` obliczania `true` . `result expression` jest dowolnym prawidłowym wyrażeniem.  
  
 PRZEJMI `else_result_expression`  
 Jest wyrażeniem zwracanym, jeśli nie zostanie obliczona żadna operacja porównania `true` . Jeśli ten argument zostanie pominięty i żadna operacja porównania nie zostanie obliczona do `true` , przypadek zwraca wartość null. `else_result_expression` jest dowolnym prawidłowym wyrażeniem. Typy danych `else_result_expression` i any `result_expression` muszą być takie same lub muszą być niejawną konwersją.  
  
 CZASIE `Boolean_expression`  
 Jest `Boolean` wyrażeniem obliczanym, gdy jest używany przeszukiwany format wielkości liter. `Boolean_expression` jest dowolnym prawidłowym `Boolean` wyrażeniem.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca typ najwyższego pierwszeństwa z zestawu typów w `result_expression` i opcjonalne `else_result_expression` .  
  
## <a name="remarks"></a>Uwagi  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]Wyrażenie CASE przypomina wyrażenie CASE języka Transact-SQL. Wyrażenie CASE służy do tworzenia serii testów warunkowych, aby określić, które wyrażenie zwróci odpowiedni wynik. Ta forma wyrażenia case ma zastosowanie do serii co najmniej jednego `Boolean` wyrażenia, aby określić poprawne wyrażenie wyniku.  
  
 Funkcja CASE oblicza `Boolean_expression` dla każdej klauzuli when w określonej kolejności i zwraca `result_expression` pierwszy `Boolean_expression` , który jest obliczany `true` . Pozostałe wyrażenia nie są oceniane. Jeśli żaden z nich nie jest `Boolean_expression` wynikiem `true` , aparat bazy danych zwraca wartość, `else_result_expression` Jeśli określono klauzulę else lub wartość null, jeśli nie określono klauzuli else.  
  
 Instrukcja CASE nie może zwracać zestawu wielokrotnego.  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa wyrażenia CASE do obliczenia zestawu `Boolean` wyrażeń w celu określenia wyniku. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w [instrukcje: wykonywanie zapytania, które zwraca wyniki typu pierwotnego](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecutePrimitiveTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Zobacz też

- [NASTĘPNIE](then-entity-sql.md)
- [ZAZNACZENIA](select-entity-sql.md)
- [Odwołanie do jednostki SQL](entity-sql-reference.md)
