---
title: Funkcje bitowe Canonical
ms.date: 03/30/2017
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
ms.openlocfilehash: 67ae0302f6faf0fb7284bc0c4a53a90ba6d55e08
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185265"
---
# <a name="bitwise-canonical-functions"></a>Funkcje bitowe Canonical

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] zawiera bitowe funkcje kanoniczne.  
  
## <a name="remarks"></a>Uwagi  

 W poniższej tabeli przedstawiono bitowe [!INCLUDE[esql](../../../../../../includes/esql-md.md)] funkcje kanoniczne. Te funkcje będą zwracać, `Null` Jeśli `Null` dane wejściowe zostaną dostarczone. Zwracany typ funkcji jest taki sam jak typ argumentu (s). Argumenty muszą być tego samego typu, jeśli funkcja przyjmuje więcej niż jeden argument. Aby wykonywać operacje bitowe w różnych typach, należy jawnie rzutować na ten sam typ.  
  
|Funkcja|Opis|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,`  `value2` `)`|Zwraca koniunkcję bitową `value1` `value2` typu i `value1` `value2` .<br /><br /> **Argumenty**<br /><br /> A `Byte` , `Int16` , `Int32` , i `Int64` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (` `value` `)`|Zwraca bitową negację `value` .<br /><br /> **Argumenty**<br /><br /> A `Byte` , `Int16` , `Int32` , i `Int64` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,`  `value2` `)`|Zwraca bitowe rozłączenie `value1` i `value2` jako typ `value1` i `value2` .<br /><br /> **Argumenty**<br /><br /> A `Byte` , `Int16` `Int32` i `Int64` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,`  `value2` `)`|Zwraca bitowe, wyłączne rozłączenie `value1` i `value2` jako typ `value1` i `value2` .<br /><br /> **Argumenty**<br /><br /> A `Byte` , `Int16` `Int32` i `Int64` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>Zobacz też

- [Funkcje Canonical](canonical-functions.md)
