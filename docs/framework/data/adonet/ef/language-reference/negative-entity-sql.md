---
title: '- Poziomem (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 71749dab073fade854c2a494841e3f6b408ebd1d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204414"
---
# <a name="--negative-entity-sql"></a>-(Wartość ujemna) (Entity SQL)

Zwraca ujemną wartość wyrażenia liczbowego.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a>Argumenty  

 `expression`  
 Dowolne prawidłowe wyrażenie jednego z typów danych liczbowych.  
  
## <a name="result-types"></a>Typy wyników  

 Typ danych `expression` .  
  
## <a name="remarks"></a>Uwagi  

 Jeśli `expression` jest typem bez znaku, typ wyniku będzie typem ze znakiem, który najlepiej odnosi się do typu `expression` . Na przykład jeśli `expression` jest typu Byte, zostanie zwrócona wartość typu Int16.  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora-arytmetycznego, aby zwrócić ujemną wartość wyrażenia liczbowego. Zapytanie jest oparte na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
