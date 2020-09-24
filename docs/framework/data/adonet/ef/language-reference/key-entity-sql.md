---
title: KLUCZ (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 07160467dcee60377e3ef448fdc66092da4e06e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161974"
---
# <a name="key-entity-sql"></a>KLUCZ (Entity SQL)

Wyodrębnia klucz odwołania lub wyrażenia jednostki.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a>Uwagi  

 Klucz jednostki zawiera wartości klucza w prawidłowej kolejności określonej jednostki lub odwołania do jednostki. Ponieważ wiele zestawów jednostek może opierać się na tym samym typie, ten sam klucz może pojawić się w każdym zestawie jednostek. Aby uzyskać unikatowe odwołanie, użyj `REF` . Zwracany typ operatora klucza jest typem wiersza, który zawiera jedno pole dla każdego klucza jednostki, w tej samej kolejności.  
  
 W poniższym przykładzie operator klucza jest przekazywać odwołanie do jednostki BadOrder i zwraca część klucza tego odwołania. W tym przypadku typ rekordu z dokładnie jednym polem odpowiadającym `Id` właściwości.  
  
```sql  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )
from LOB.Orders as o  
```  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora KEY do wyodrębnienia części klucza wyrażenia z odwołaniem do typu. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#KEY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#key)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
- [CREATEREF](createref-entity-sql.md)
- [UMIESZCZONE](ref-entity-sql.md)
- [DEREF](deref-entity-sql.md)
