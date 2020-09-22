---
title: NotOverridable
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 8eec54a12c7fb748df46e8c48a8b07eab983cc72
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867866"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)

Określa, że właściwość lub procedura nie może zostać zastąpiona w klasie pochodnej.  
  
## <a name="remarks"></a>Uwagi  

 `NotOverridable`Modyfikator uniemożliwia przesłanianie właściwości lub metody w klasie pochodnej.  Modyfikator [, który umożliwia](overridable.md) zastąpienie właściwości lub metody w klasie klasy pochodnej. Aby uzyskać więcej informacji, zobacz podstawowe informacje o [dziedziczeniu](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Jeśli `Overridable` modyfikator or `NotOverridable` nie jest określony, ustawienie domyślne zależy od tego, czy właściwość lub metoda przesłania właściwość lub metodę klasy bazowej. Jeśli właściwość lub metoda przesłania właściwość lub metodę klasy bazowej, ustawienie domyślne to `Overridable` ; w przeciwnym razie jest `NotOverridable` .  
  
 Element, który nie może zostać zastąpiony, jest czasami nazywany *zapieczętowanym* elementem.  
  
 Można użyć `NotOverridable` tylko w instrukcji deklaracji właściwości lub procedury. Można określić `NotOverridable` tylko dla właściwości lub procedury, która zastępuje inną właściwość lub procedurę, czyli tylko w połączeniu z `Overrides` .  
  
## <a name="combined-modifiers"></a>Połączone Modyfikatory  

 Nie można określić `Overridable` lub `NotOverridable` dla `Private` metody.  
  
 Nie można określić `NotOverridable` razem z `MustOverride` , `Overridable` , lub `Shared` w tej samej deklaracji.  
  
## <a name="usage"></a>Użycie  

 `NotOverridable`Modyfikator może być używany w tych kontekstach:  
  
 [Function, instrukcja](../statements/function-statement.md)  
  
 [Property — Instrukcja](../statements/property-statement.md)  
  
 [Sub, instrukcja](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Zobacz też

- [Modyfikatory](index.md)
- [Podstawowe informacje o dziedziczeniu](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [Overridable](overridable.md)
- [Przesłonięcia](overrides.md)
- [Słowa kluczowe](../keywords/index.md)
- [Przesłanianie w Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
