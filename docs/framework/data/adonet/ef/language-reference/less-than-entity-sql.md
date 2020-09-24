---
title: < (mniejsze niż) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: 389c50a697c90dadb075369fe696f7382caf3cff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161922"
---
# <a name="-less-than-entity-sql"></a>\< (Mniejsze niż) (Entity SQL)

Porównuje dwa wyrażenia, aby określić, czy lewe wyrażenie ma wartość mniejszą niż prawo wyrażenie.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a>Argumenty  

 `expression`  
 Dowolne prawidłowe wyrażenie. Oba wyrażenia muszą mieć niejawnie wymienialne typy danych.  
  
## <a name="result-types"></a>Typy wyników  

 `true` Jeśli lewe wyrażenie ma wartość mniejszą niż prawe wyrażenie; w przeciwnym razie `false` .  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora porównania < do porównywania dwóch wyrażeń, aby określić, czy lewe wyrażenie ma wartość mniejszą niż prawe wyrażenie. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
