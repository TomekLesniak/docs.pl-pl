---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 3360ad4ca7306a8cc1b7d6948204f825ff9a93c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203621"
---
# <a name="isnull-entity-sql"></a>ISNULL (Entity SQL)

Określa, czy wyrażenie zapytania ma wartość null.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a>Argumenty  

 `expression`  
 Dowolne prawidłowe wyrażenie zapytania. Nie może być kolekcją, mieć składowe kolekcji lub typem rekordu z właściwościami typu kolekcji.  
  
 NOT  
 Negacja modelu EDM. Wynik wartości logicznej jest równy NULL.  
  
## <a name="return-value"></a>Wartość zwracana  

 `true` Jeśli `expression` zwraca wartość null; w przeciwnym razie `false` .  
  
## <a name="remarks"></a>Uwagi  

 Użyj `IS NULL` , aby określić, czy element sprzężenia zewnętrznego ma wartość null:  
  
```sql  
select c
      from LOB.Customers as c left outer join LOB.Orders as o
                              on c.ID = o.CustomerID
      where o is not null and o.OrderQuantity = @x  
```  
  
 Użyj `IS NULL` , aby określić, czy element członkowski ma rzeczywistą wartość:  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 W poniższej tabeli przedstawiono zachowanie `IS NULL` niektórych wzorców. Wszystkie wyjątki są zgłaszane po stronie klienta przed wywołaniem dostawcy:  
  
|Wzorce|Zachowanie|  
|-------------|--------------|  
|wartość zerowa ma wartość NULL|Zwraca wartość `true`.|  
|TRAKTOWANIe (null jako EntityType) ma wartość NULL|Zwraca wartość `true`.|  
|TRAKTOWANIe (null jako ComplexType) ma wartość NULL|Zgłasza błąd.|  
|TRAKTOWANIe (null AS RowType) ma wartość NULL|Zgłasza błąd.|  
|Obiekt EntityType ma wartość NULL|Zwraca `true` lub `false` .|  
|ComplexType ma wartość NULL|Zgłasza błąd.|  
|RowType ma wartość NULL|Zgłasza błąd.|  
  
## <a name="example"></a>Przykład  

 Następujące [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie używa operatora is not null, aby określić, czy wyrażenie zapytania nie ma wartości null. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
