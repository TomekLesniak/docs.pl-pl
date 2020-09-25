---
title: Rozwiązanie przeciążenia funkcji (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
ms.openlocfilehash: d37cd9342d1fb3b60d5a2c05d373fb7e71f54b1f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189399"
---
# <a name="function-overload-resolution-entity-sql"></a>Rozwiązanie przeciążenia funkcji (Entity SQL)

W tym temacie opisano sposób [!INCLUDE[esql](../../../../../../includes/esql-md.md)] rozwiązywania funkcji.  
  
 Można zdefiniować więcej niż jedną funkcję o tej samej nazwie, o ile funkcje mają unikatowe podpisy.  
  
 W takim przypadku należy zastosować następujące kryteria, aby określić, która funkcja jest przywoływana przez dane wyrażenie. Te kryteria są stosowane w kolejności. Pierwsze kryterium stosowane tylko do pojedynczej funkcji jest funkcją rozpoznaną.  
  
1. **Numer parametru**. Funkcja ma taką samą liczbę parametrów, jak określono w wyrażeniu.  
  
2. **Dokładne dopasowanie typu**. Każdy typ argumentu funkcji dokładnie pasuje do typu parametru lub jest literałem o wartości null.  
  
3. **Dopasowanie dla podtypu**. Każdy typ argumentu funkcji dokładnie pasuje lub jest podtypem typu parametru lub argument jest literałem null. W przypadku, gdy kilka funkcji różni się tylko w liczbie wymaganych konwersji podtypów, funkcja o najmniejszej liczbie podtypów konwersji jest rozpoznawaną funkcją.  
  
4. **Dopasowanie do podtypu lub podwyższania poziomu**. Każdy typ argumentu funkcji dokładnie pasuje, jest podtypem lub można podwyższyć poziom do typu parametru lub argument jest literałem o wartości null. Ponownie w przypadku, gdy kilka funkcji różni się tylko w przypadku konwersji typu podrzędnego i promocji, funkcja o najmniejszej liczbie podtypów konwersji i promocji jest funkcją rozpoznaną.  
  
 Jeśli żaden z tych kryteriów nie powoduje wybrania pojedynczej funkcji, wyrażenie wywołania funkcji jest niejednoznaczne.  
  
 Nawet jeśli jedna funkcja może zostać wyodrębniona przy użyciu tych reguł, argumenty nadal mogą być niezgodne z parametrami. W tym przypadku zostanie zgłoszony błąd.  
  
 W przypadku funkcji zdefiniowanych przez użytkownika definicja wbudowanej funkcji zapytania ma pierwszeństwo, nawet gdy istnieje funkcja zdefiniowana przez model z podpisem, który jest lepszym dopasowaniem dla funkcji zdefiniowanej przez użytkownika.  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie do jednostki SQL](entity-sql-reference.md)
- [Omówienie jednostki SQL](entity-sql-overview.md)
- [Funkcje](functions-entity-sql.md)
