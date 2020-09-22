---
title: Widening
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 14e0b026f4fc3b0bf202ea643a28d6f1a7df2b7c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867648"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)

Wskazuje, że Operator konwersji ( `CType` ) konwertuje klasę lub strukturę do typu, który może zawierać wszystkie możliwe wartości oryginalnej klasy lub struktury.  
  
## <a name="converting-with-the-widening-keyword"></a>Konwertowanie za pomocą słowa kluczowego rozszerzającego  

 Procedura konwersji musi być określona `Public Shared` poza `Widening` .  
  
 Rozszerzanie konwersji zawsze powiedzie się w czasie wykonywania i nigdy nie powiąże się z utratą danych. Przykłady to `Single` `Double` , `Char` do `String` i typ pochodny do jego typu podstawowego. Ta ostatnia konwersja jest rozszerzana, ponieważ typ pochodny zawiera wszystkie elementy członkowskie typu podstawowego i w związku z tym jest wystąpieniem typu podstawowego.  
  
 Kod zużywający nie musi być używany `CType` do rozszerzania konwersji, nawet jeśli `Option Strict` jest `On` .  
  
 `Widening`Słowo kluczowe może być używane w tym kontekście:  
  
 [Operator — Instrukcja](../statements/operator-statement.md)  
  
 Aby zapoznać się z przykładami definicji rozszerzania i zawężania operatorów konwersji, zobacz [How to: define Operator konwersji](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Zobacz też

- [Operator — Instrukcja](../statements/operator-statement.md)
- [Narrowing](narrowing.md)
- [Rozszerzanie i zwężanie konwersji](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Instrukcje: definiowanie operatora](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType — Funkcja](../functions/ctype-function.md)
- [Option Strict — Instrukcja](../statements/option-strict-statement.md)
- [Instrukcje: definiowanie operatora konwersji](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
