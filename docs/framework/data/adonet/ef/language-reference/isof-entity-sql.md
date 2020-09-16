---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: a0294f425552df3329d158d69a6d503b2f008780
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542336"
---
# <a name="isof-entity-sql"></a>ISOF (Entity SQL)
Określa, czy typ wyrażenia jest określonego typu czy jednego z jego podtypów.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a>Argumenty  
 `expression`  
 Dowolne prawidłowe wyrażenie zapytania, aby określić typ.  
  
 NOT  
 Negacja modelu EDM. Wynik wartości logicznej wynosi.  
  
 JEDYN  
 Określa, że jest zwraca `true` tylko wtedy, gdy `expression` jest typu `type` , a nie dowolnego jednego z jego podtypów.  
  
 `type`  
 Typ do przetestowania `expression` . Typ musi być kwalifikowaną przestrzenią nazw.  
  
## <a name="return-value"></a>Wartość zwracana  
 `true` Jeśli `expression` parametr jest typu T i T jest typem podstawowym lub typem pochodnym `type` ; null, jeśli `expression` ma wartość null w czasie wykonywania; w przeciwnym razie `false` .  
  
## <a name="remarks"></a>Uwagi  
 Wyrażenia `expression IS NOT OF (type)` i `expression IS NOT OF (ONLY type)` są syntaktycznie równoważne z `NOT (expression IS OF (type))` i `NOT (expression IS OF (ONLY type))` , odpowiednio.  
  
 W poniższej tabeli przedstawiono zachowanie `IS OF` operatora w przypadku niektórych wzorców typowych i narożnych. Wszystkie wyjątki są zgłaszane po stronie klienta przed wywołaniem dostawcy:  
  
|Wzorce|Zachowanie|  
|-------------|--------------|  
|wartość zerowa jest typu (EntityType)|Generuje|  
|wartość zerowa jest równa (ComplexType)|Generuje|  
|wartość zerowa jest równa (RowType)|Generuje|  
|Traktuj (wartość null jako element EntityType) to (EntityType)|Zwraca wartość DBNull|  
|Traktuj (wartość null jako ComplexType) to (ComplexType)|Generuje|  
|Traktuj (wartość null AS RowType) to (RowType)|Generuje|  
|Typ EntityType to (EntityType)|Zwraca wartość PRAWDA/FAŁSZ|  
|ComplexType jest typu (ComplexType)|Generuje|  
|RowType jest (RowType)|Generuje|  
  
## <a name="example"></a>Przykład  
 Następujące [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie używa operatora is, aby określić typ wyrażenia zapytania, a następnie używa operatora Traktuj do konwersji obiektu typu kursu do kolekcji obiektów typu OnsiteCourse. Zapytanie jest oparte na [modelu szkoły](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).  
  
 [! code-SQL [DP EntityServices koncepcje # TREAT_ISOF] ~/Samples/Snippets/TSQL/VS_Snippets_Data/DP EntityServices koncepcje/TSQL/EntitySql. SQL # treat_isof)]  
  
## <a name="see-also"></a>Zobacz także

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
