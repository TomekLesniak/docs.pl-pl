---
title: Struktura „<structurename>" musi zawierać co najmniej jedną zmienną elementu członkowskiego lub co najmniej jedną deklarację wystąpienia zdarzenia, która nie jest oznaczona „Custom"
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: a350940cf052aa8fbee4a1e3c61cbeaa4e37408a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870587"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>Struktura „\<structurename>" musi zawierać co najmniej jedną zmienną elementu członkowskiego lub co najmniej jedną deklarację wystąpienia zdarzenia, która nie jest oznaczona „Custom"

Definicja struktury nie zawiera żadnych zmiennych nieudostępnionych lub nieudostępnianych zdarzeń nieniestandardowych.  
  
 Każda struktura musi mieć zmienną lub zdarzenie, które stosuje się do każdego określonego wystąpienia (nieudostępnione) zamiast do wszystkich wystąpień zbiorczo ([współużytkowane](../modifiers/shared.md)). Nieudostępnione stałe, właściwości i procedury nie spełniają tego wymagania. Ponadto, jeśli nie istnieją zmienne nieudostępnione i tylko jedno nieudostępnione zdarzenie, to zdarzenie nie może być `Custom` zdarzeniem.  
  
 **Identyfikator błędu:** BC30941  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Zdefiniuj co najmniej jedną zmienną lub zdarzenie, które nie jest `Shared` . Jeśli zdefiniujesz tylko jedno zdarzenie, musi ono być nieniestandardowe i nieudostępnione.  
  
## <a name="see-also"></a>Zobacz też

- [Struktury](../../programming-guide/language-features/data-types/structures.md)
- [Instrukcje: Deklarowanie struktury](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Structure — Instrukcja](../statements/structure-statement.md)
