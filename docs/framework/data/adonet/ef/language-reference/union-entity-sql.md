---
title: Unia (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 9c4106d26fb73219d7b5f0c6763736aaf9163d4b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200982"
---
# <a name="union-entity-sql"></a>Unia (Entity SQL)

Łączy wyniki dwóch lub więcej zapytań w jedną kolekcję.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a>Argumenty  

 `expression`  
 Każde prawidłowe wyrażenie zapytania, które zwraca kolekcję w celu połączenia z kolekcją, wszystkie wyrażenia muszą być tego samego typu lub typu wspólnego lub pochodnego jako `expression` .  
  
 UNION  
 Określa, że wiele kolekcji ma być łączonych i zwracane jako pojedyncza kolekcja.  
  
 ALL  
 Określa, że wielokrotne kolekcje mają być połączone i zwracane jako pojedyncze kolekcje, w tym duplikaty. Jeśli nie zostanie określony, duplikaty są usuwane z kolekcji wyników.  
  
## <a name="return-value"></a>Wartość zwracana  

 Kolekcja tego samego typu lub typowego typu podstawowego lub pochodnego jako `expression` .  
  
## <a name="remarks"></a>Uwagi  

 Unia jest jednym z [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorów zestawu. Wszystkie [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Operatory zestawów są oceniane od lewej do prawej. Aby uzyskać informacje o pierwszeństwie dla [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorów zestawu, zobacz [except](except-entity-sql.md).  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora UNION ALL do łączenia wyników dwóch zapytań w jedną kolekcję. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#UNION](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#union)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
