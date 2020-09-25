---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: c2a57116f56abf4db3caabcfe3acd0d8afbcf4eb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201060"
---
# <a name="createref-entity-sql"></a>CREATEREF (Entity SQL)

W obiekcie EntitySet są przywoływane odwołania do jednostki.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a>Argumenty  

 `entityset_identifier`  
 Identyfikator obiektu EntitySet, a nie literału ciągu.  
  
 `row_typed_expression`  
 Wyrażenie z określonym wierszem, które odnosi się do właściwości klucza typu jednostki.  
  
## <a name="remarks"></a>Uwagi  

 `row_typed_expression` muszą być strukturalnie równoważne z typem klucza dla jednostki. Oznacza to, że musi mieć taką samą liczbę i typy pól w tej samej kolejności co klucze jednostek.  
  
 W poniższym przykładzie zamówienia i BadOrders są zarówno obiektem EntitySet typu Order, jak i przyjmuje się, że są one właściwością Single Key kolejności. W przykładzie pokazano, jak możemy utworzyć odwołanie do jednostki w BadOrders. Należy zauważyć, że odwołanie może być zawieszonego.  Oznacza to, że odwołanie może nie identyfikować określonej jednostki. W takich przypadkach `DEREF` operacja na tym odwołaniu zwraca wartość null.  
  
```sql  
SELECT CreateRef(LOB.BadOrders, row(o.Id))
FROM LOB.Orders AS o
```  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora CREATEREF do tworzenia odwołań do jednostki w zestawie jednostek. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#CREATEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#createref)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
- [DEREF](deref-entity-sql.md)
- [GŁÓWNYCH](key-entity-sql.md)
- [UMIESZCZONE](ref-entity-sql.md)
