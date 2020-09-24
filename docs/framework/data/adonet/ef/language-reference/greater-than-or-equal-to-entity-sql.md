---
title: '>= (Większe lub równe) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: 02e03d6d2da321bd02ea2b14e45a910853d39c4d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158425"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a>>= (większe lub równe) (Entity SQL)

Porównuje dwa wyrażenia, aby określić, czy lewe wyrażenie ma wartość większą lub równą prawemu wyrażeniu.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
expression >= expression  
```  
  
## <a name="arguments"></a>Argumenty  

 `expression`  
 Dowolne prawidłowe wyrażenie. Oba wyrażenia muszą mieć niejawnie wymienialne typy danych.  
  
## <a name="result-types"></a>Typy wyników  

 `true` Jeśli wyrażenie po lewej stronie ma wartość większą lub równą prawemu wyrażeniu; w przeciwnym razie `false` .  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora porównania >= do porównywania dwóch wyrażeń, aby określić, czy lewe wyrażenie ma wartość większą lub równą prawemu wyrażeniu. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#GREATER_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater_or_equals)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
