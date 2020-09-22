---
title: Stałe muszą być typu wewnętrznego lub wyliczeniowego, a nie typu klasy, struktury, parametru typu lub tablicy
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: a9bbf27615233f4282e481710a0234b2fa589f63
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874559"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>Stałe muszą być typu wewnętrznego lub wyliczeniowego, a nie typu klasy, struktury, parametru typu lub tablicy

Próbowano zadeklarować stałą jako klasę, strukturę lub typ tablicy albo jako parametr typu zdefiniowany przez zawierający typ ogólny.  
  
 Stałe muszą być typu wewnętrznego (,,,,,,,,,, `Boolean` `Byte` ,,,, `Date` `Decimal` `Double` `Integer` `Long` `Object` `SByte` `Short` `Single` `String` `UInteger` `ULong` lub `UShort` ) lub `Enum` typu na podstawie jednego z typów całkowitych.  
  
 **Identyfikator błędu:** BC30424  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Zadeklaruj stałą jako wewnętrzną lub `Enum` Typ.  
  
2. Stała może być również specjalną wartością, taką jak `True` , `False` , lub `Nothing` . Kompilator uważa, że te wstępnie zdefiniowane wartości mają być odpowiednim typem wewnętrznym.  
  
## <a name="see-also"></a>Zobacz też

- [Stałe i wyliczenia](../constants-and-enumerations.md)
- [Typy danych](../../programming-guide/language-features/data-types/index.md)
- [Typy danych](../data-types/index.md)
