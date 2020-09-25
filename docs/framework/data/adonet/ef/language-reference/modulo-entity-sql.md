---
title: Operator (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: 25bd34db3a627fa708e1ab9a3f0e237426487bcb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175710"
---
# <a name="modulo-entity-sql"></a>Operator (Entity SQL)

Zwraca resztę jednego wyrażenia podzieloną przez inny.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
dividend % divisor  
```  
  
## <a name="arguments"></a>Argumenty  

 `dividend`  
 Wyrażenie liczbowe do podzielenia. `dividend` jest dowolnym prawidłowym wyrażeniem dowolnego typu danych liczbowych.  
  
 `divisor`  
 Wyrażenie liczbowe dzielące dywidendę przez. `divisor` jest dowolnym prawidłowym wyrażeniem dowolnego typu danych liczbowych.  
  
## <a name="result-types"></a>Typy wyników  

 Edm.Int32  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora arytmetycznego% do zwrócenia reszty jednego wyrażenia podzielonego przez inny. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#MODULO](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#modulo)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
