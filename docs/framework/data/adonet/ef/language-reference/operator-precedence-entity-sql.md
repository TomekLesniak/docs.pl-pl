---
title: Pierwszeństwo operatorów (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: f8aa0f213a24d6431d8910af849571a67fbd9f57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175645"
---
# <a name="operator-precedence-entity-sql"></a>Pierwszeństwo operatorów (Entity SQL)

Gdy [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie ma wiele operatorów, pierwszeństwo operatorów określa kolejność wykonywania operacji. Kolejność wykonywania może znacząco wpłynąć na wynik zapytania.  
  
 Operatory mają poziomy pierwszeństwa pokazane w poniższej tabeli. Operator o wyższym poziomie jest obliczany przed operatorem o niższym poziomie.  
  
|Poziom|Typ operacji|Operator|  
|-----------|--------------------|--------------|  
|1|Podstawowe|`. , [] ()`|  
|2|Jednoargumentowy|`! not`|  
|3|Mnożenie|`* / %`|  
|4|Dodawanie|`+ -`|  
|5|Zamawianie|`< > <= >=`|  
|6|Równość|`= != <>`|  
|7|AND warunkowe|`and &&`|  
|8|OR warunkowe|`or &#124;&#124;`|  
  
 Gdy dwa operatory w wyrażeniu mają ten sam poziom pierwszeństwa operatora, są oceniane od lewej do prawej na podstawie ich pozycji w zapytaniu. Na przykład, `x+y-z` jest oceniane jako `(x+y)-z` .  
  
 Możesz użyć nawiasów, aby przesłonić zdefiniowane pierwszeństwo operatorów w zapytaniu. Wszystkie elementy w nawiasach są oceniane jako pierwsze w celu uzyskania pojedynczego wyniku, zanim ten wynik może być używany przez dowolny operator poza nawiasami. Na przykład `x+y*z` mnoży `y` wartość przez, `z` a następnie dodaje `x` , ale `(x+y)*z` dodaje `x` do, `y` a następnie mnoży wynik przez `z` .  
  
## <a name="see-also"></a>Zobacz też

- [Omówienie jednostki SQL](entity-sql-overview.md)
