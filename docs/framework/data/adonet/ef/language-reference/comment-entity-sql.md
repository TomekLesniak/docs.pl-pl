---
title: --(Komentarz) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 9ad6e38726d0802c3bc2090a4e6f11f008828ee5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197901"
---
# <a name="---comment-entity-sql"></a>--(Komentarz) (Entity SQL)

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytania mogą zawierać komentarze. Dwie kreski ( `--` ) — Zacznij od wiersza komentarza.  
  
## <a name="syntax"></a>Składnia  
  
```csharp  
-- text_of_comment  
```  
  
## <a name="arguments"></a>Argumenty  

 `text_of_comment`  
 Jest ciągiem znaków, który zawiera tekst komentarza.  
  
## <a name="example"></a>Przykład  

 W poniższym zapytaniu Entity SQL pokazano, jak używać komentarzy. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>Zobacz też

- [Omówienie jednostki SQL](entity-sql-overview.md)
- [Odwołanie do jednostki SQL](entity-sql-reference.md)
