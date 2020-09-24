---
title: Parametry (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 759452902461e1a460b69774bb33f92bbd532ed0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177521"
---
# <a name="parameters-entity-sql"></a>Parametry (Entity SQL)

Parametry są zmiennymi, które są zdefiniowane poza [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , zwykle za pomocą powiązania interfejsu API, który jest używany przez język hosta. Każdy parametr ma nazwę i typ. Nazwy parametrów są zdefiniowane w wyrażeniach zapytania z symbolem at (@) jako prefiksem. Pozwala to odróżnić je od nazw właściwości lub innych nazw zdefiniowanych w zapytaniu.  
  
 Interfejs API powiązania języka hosta udostępnia interfejsy API dla parametrów powiązań.  
  
## <a name="example"></a>Przykład  
  
```sql  
SELECT c
      FROM LOB.Customers AS c
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
- [Omówienie jednostki SQL](entity-sql-overview.md)
