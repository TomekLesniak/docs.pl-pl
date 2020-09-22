---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 59f1c1666ce38923a2861244fb377007cd0fa992
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874980"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)

Określa, że co najmniej jeden zadeklarowany element programistyczny jest dostępny tylko w obrębie ich kontekstu deklaracji, łącznie z zawartymi w zawartych typach.  
  
## <a name="remarks"></a>Uwagi  

 Jeśli element programistyczny reprezentuje funkcje własnościowe lub zawiera dane poufne, zazwyczaj trzeba ograniczyć dostęp do niego tak samo jak to możliwe. Maksymalne ograniczenie można osiągnąć, zezwalając tylko na moduł, klasę lub strukturę, która je definiuje, aby uzyskać do niej dostęp. Aby ograniczyć dostęp do elementu w ten sposób, można go zadeklarować za pomocą `Private` .  

> [!NOTE]
> Można również użyć modyfikatora [Private Protected](private-protected.md) Access, który umożliwia członkom dostęp z tej klasy i z klas pochodnych znajdujących się w jego zestawie zawierającym.

## <a name="rules"></a>Reguły  

- **Kontekst deklaracji.** Można używać `Private` tylko na poziomie modułu. Oznacza to, że kontekst deklaracji dla `Private` elementu musi być modułem, klasą lub strukturą i nie może być plikiem źródłowym, przestrzenią nazw, interfejsem ani procedurą.  
  
## <a name="behavior"></a>Zachowanie  
  
- **Poziom dostępu.** Cały kod w kontekście deklaracji może uzyskać dostęp do jego `Private` elementów. Obejmuje to kod w obrębie zawartego typu, taki jak Klasa zagnieżdżona lub wyrażenie przypisania w wyliczeniu. Żaden kod spoza kontekstu deklaracji nie może uzyskać dostępu do jego `Private` elementów.  
  
- **Modyfikatory dostępu.** Słowa kluczowe określające poziom dostępu są nazywane *modyfikatorami dostępu*. Aby porównać Modyfikatory dostępu, zobacz [poziomy dostępu w Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 `Private`Modyfikator może być używany w tych kontekstach:  
  
 [Class, instrukcja](../statements/class-statement.md)  
  
 [Const, instrukcja](../statements/const-statement.md)  
  
 [Declare — Instrukcja](../statements/declare-statement.md)  
  
 [Delegate — Instrukcja](../statements/delegate-statement.md)  
  
 [Dim, instrukcja](../statements/dim-statement.md)  
  
 [Enum, instrukcja](../statements/enum-statement.md)  
  
 [Event — Instrukcja](../statements/event-statement.md)  
  
 [Function, instrukcja](../statements/function-statement.md)  
  
 [Interface, instrukcja](../statements/interface-statement.md)  
  
 [Property — Instrukcja](../statements/property-statement.md)  
  
 [Structure — Instrukcja](../statements/structure-statement.md)  
  
 [Sub, instrukcja](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Zobacz też

- [Publiczne](public.md)
- [Chronione](protected.md)
- [Friend](friend.md)
- [Prywatne chronione](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Poziomy dostępu w Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedury](../../programming-guide/language-features/procedures/index.md)
- [Struktury](../../programming-guide/language-features/data-types/structures.md)
- [Obiekty i klasy](../../programming-guide/language-features/objects-and-classes/index.md)
