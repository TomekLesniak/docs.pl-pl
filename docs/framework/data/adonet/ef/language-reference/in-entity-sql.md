---
title: W (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 582a3b988247f1484197c0905fecf7f4407f88b0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203673"
---
# <a name="in-entity-sql"></a>W (Entity SQL)

Określa, czy wartość jest zgodna z dowolną wartością w kolekcji.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>Argumenty  

 `value`  
 Dowolne prawidłowe wyrażenie zwracające wartość do dopasowania.  
  
 NIEMOŻLIWE  
 Określa, że `Boolean` wynik jest negacji.  
  
 `expression`  
 Dowolne prawidłowe wyrażenie zwracające kolekcję do przetestowania w celu dopasowania. Wszystkie wyrażenia muszą być tego samego typu lub według wspólnego typu podstawowego lub pochodnego `value` .  
  
## <a name="return-value"></a>Wartość zwracana  

 `true` Jeśli wartość zostanie znaleziona w kolekcji; wartość null, jeśli wartość jest równa null lub kolekcja ma wartość null; w przeciwnym razie `false` . Użycie nie jest w wyniku negacji wyników w.  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora IN, aby określić, czy wartość pasuje do dowolnej wartości w kolekcji. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
