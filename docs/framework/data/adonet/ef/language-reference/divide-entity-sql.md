---
title: '- Mieszczon (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: d7d25d8c5b91850b21e36ba8f6f668af7a7d0045
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148164"
---
# <a name="-divide-entity-sql"></a>/(Dzielenie) (Entity SQL)

Dzieli jedną liczbę przez inną.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
dividend / divisor  
```  
  
## <a name="arguments"></a>Argumenty  

 `dividend`  
 Wyrażenie liczbowe do podzielenia. `dividend` jest dowolnym prawidłowym wyrażeniem dowolnego typu danych liczbowych.  
  
 `divisor`  
 Wyrażenie liczbowe dzielące dywidendę przez. `divisor` jest dowolnym prawidłowym wyrażeniem dowolnego typu danych liczbowych.  
  
## <a name="result-types"></a>Typy wyników  

 Typ danych, który wynika z promocji typu niejawnego dwóch argumentów. Aby uzyskać więcej informacji na temat niejawnego podwyższania poziomu, zobacz [typu System](type-system-entity-sql.md).  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora arytmetycznego w celu podzielenia jednej liczby przez inną. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#DIVIDE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#divide)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
