---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: e060956545ca924fa6fedb80b2f53ff312f307a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201203"
---
# <a name="anyelement-entity-sql"></a>ANYELEMENT (Entity SQL)

Wyodrębnia element z kolekcji wielowartościowej.  
  
## <a name="syntax"></a>Składnia  
  
```csharp
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a>Argumenty  

 `expression`  
 Każde prawidłowe wyrażenie zapytania, które zwraca kolekcję w celu wyodrębnienia elementu z.  
  
## <a name="return-value"></a>Wartość zwracana  

 Pojedynczy element w kolekcji lub dowolny element, jeśli kolekcja zawiera więcej niż jeden; Jeśli kolekcja jest pusta, zwraca `null` . Jeśli `collection` jest kolekcją typu `Collection<T>` , `ANYELEMENT(collection)` jest prawidłowym wyrażeniem, które zwraca wystąpienie typu `T` .  
  
## <a name="remarks"></a>Uwagi  

 ANYELEMENT wyodrębnia dowolny element z kolekcji wielowartościowej. Na przykład poniższy przykład próbuje wyodrębnić element singleton z zestawu `Customers` .  
  
```csharp
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a>Przykład  

 Następujące [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie używa operatora AnyElement do wyodrębnienia elementu z kolekcji wielowartościowej. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
- [Typy strukturalne dopuszczające wartości Null](nullable-structured-types-entity-sql.md)
