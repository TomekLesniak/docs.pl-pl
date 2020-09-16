---
title: Funkcje zdefiniowane przez użytkownika (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: ab18c3ec785ca3bba9f8b67fbb82fb4bb8244f4f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540657"
---
# <a name="user-defined-functions-entity-sql"></a>Funkcje zdefiniowane przez użytkownika (Entity SQL)
Entity SQL obsługuje wywoływanie funkcji zdefiniowanych przez użytkownika w zapytaniu. Można zdefiniować te funkcje w postaci zastosowanej do zapytania (zobacz [How to: Called User-Defined Function](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) lub jako część modelu koncepcyjnego (zobacz [jak: Definiowanie funkcji niestandardowych w modelu koncepcyjnym](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))). Funkcje modelu koncepcyjnego są zdefiniowane jako polecenie Entity SQL w elemencie [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) elementu [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) w modelu koncepcyjnym.  
  
 Entity SQL umożliwia zdefiniowanie funkcji w samym poleceniu zapytania. Operator [funkcji](function-entity-sql.md) definiuje funkcje wbudowane. Można zdefiniować wiele funkcji w pojedynczym poleceniu, a funkcje te mogą mieć taką samą nazwę funkcji, o ile sygnatury funkcji są unikatowe. Aby uzyskać więcej informacji, zobacz [rozpoznawanie przeciążeń funkcji](function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Zobacz także

- [Funkcje](functions-entity-sql.md)
