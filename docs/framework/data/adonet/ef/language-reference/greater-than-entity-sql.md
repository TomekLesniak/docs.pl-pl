---
title: '> (Większe niż) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: 52a9f9f645aa51402ceb8cb0a40d2040d1c0802c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147947"
---
# <a name="-greater-than-entity-sql"></a>> (większe niż) (Entity SQL)

Porównuje dwa wyrażenia, aby określić, czy lewe wyrażenie ma wartość większą niż prawo wyrażenie.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
expression > expression  
```  
  
## <a name="arguments"></a>Argumenty  

 `expression`  
 Dowolne prawidłowe wyrażenie. Oba wyrażenia muszą mieć niejawnie wymienialne typy danych.  
  
## <a name="result-types"></a>Typy wyników  

 `true` Jeśli lewe wyrażenie ma wartość większą niż wyrażenie Right; w przeciwnym razie `false` .  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora porównania > do porównywania dwóch wyrażeń, aby określić, czy lewe wyrażenie ma wartość większą niż prawe wyrażenie. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#GREATER](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
