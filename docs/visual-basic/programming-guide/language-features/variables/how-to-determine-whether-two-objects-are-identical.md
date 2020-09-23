---
title: 'Porady: określanie, czy dwa obiekty są jednakowe'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 1bbc8083fcfb6f5ff0f4328c32b83a2e7218ecd6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072278"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Porady: określanie, czy dwa obiekty są jednakowe (Visual Basic)

W Visual Basic, dwa odwołania do zmiennych są uważane za identyczne, jeśli ich wskaźniki są takie same, czyli jeśli obie zmienne wskazują na to samo wystąpienie klasy w pamięci. Na przykład w aplikacji Windows Forms można przeprowadzić porównanie, aby określić, czy bieżące wystąpienie ( `Me` ) jest takie samo jak określone wystąpienie, takie jak `Form2` .  
  
 Visual Basic udostępnia dwa operatory do porównywania wskaźników. [Operator is](../../../language-reference/operators/is-operator.md) zwraca `True` , jeśli obiekty są identyczne, a [operator IsNot](../../../language-reference/operators/isnot-operator.md) zwraca, `True` Jeśli nie są.  
  
## <a name="determining-if-two-objects-are-identical"></a>Określanie, czy dwa obiekty są identyczne  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Aby określić, czy dwa obiekty są identyczne  
  
1. Skonfiguruj `Boolean` wyrażenie, aby przetestować dwa obiekty.  
  
2. W wyrażeniu testowym Użyj `Is` operatora z dwoma obiektami jako operandami.  
  
     `Is` zwraca `True` Jeśli obiekty wskazują to samo wystąpienie klasy.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Określanie, czy dwa obiekty nie są identyczne  

 Czasami chcesz wykonać akcję, jeśli dwa obiekty nie są identyczne i mogą być niewygodna do łączenia `Not` i `Is` , na przykład `If Not obj1 Is obj2` . W takim przypadku można użyć `IsNot` operatora.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Aby określić, czy dwa obiekty nie są identyczne  
  
1. Skonfiguruj `Boolean` wyrażenie, aby przetestować dwa obiekty.  
  
2. W wyrażeniu testowym Użyj `IsNot` operatora z dwoma obiektami jako operandami.  
  
     `IsNot` zwraca `True` czy obiekty nie wskazują tego samego wystąpienia klasy.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład sprawdza pary `Object` zmiennych, aby sprawdzić, czy wskazują one na to samo wystąpienie klasy.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 W poprzednim przykładzie przedstawiono następujące dane wyjściowe.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Zobacz także

- [Object — typ danych](../../../language-reference/data-types/object-data-type.md)
- [Zmienne obiektów](object-variables.md)
- [Wartości zmiennej obiektu](object-variable-values.md)
- [Is, operator](../../../language-reference/operators/is-operator.md)
- [IsNot, operator](../../../language-reference/operators/isnot-operator.md)
- [Porady: określanie, czy dwa obiekty są powiązane](how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase i MyClass](../../program-structure/me-my-mybase-and-myclass.md)
