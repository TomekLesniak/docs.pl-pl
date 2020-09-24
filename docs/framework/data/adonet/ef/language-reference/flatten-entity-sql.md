---
title: SPŁASZCZ (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 36ae2b2b1264150bc66d09366ee33723ed7b28a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166709"
---
# <a name="flatten-entity-sql"></a>SPŁASZCZ (Entity SQL)

Konwertuje kolekcję kolekcji na spłaszczoną kolekcję. Nowa kolekcja zawiera wszystkie te same elementy co stara kolekcja, ale bez zagnieżdżonej struktury.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a>Argumenty  

 `collection`  
 Dowolne prawidłowe wyrażenie zwracające kolekcję kolekcji wartości do spłaszczenia do pojedynczej kolekcji.  
  
## <a name="remarks"></a>Uwagi  

 `FLATTEN` jest jednym z [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorów zestawu. Wszystkie [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Operatory zestawów są oceniane od lewej do prawej. Zobacz [z wyjątkiem](except-entity-sql.md) informacji o priorytecie dla [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorów zestawu.  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa `FLATTEN` operatora do konwertowania kolekcji kolekcji na spłaszczoną kolekcję. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
