---
title: Struktura „<structurename>" musi zawierać co najmniej jedną zmienną elementu członkowskiego lub co najmniej jedną deklarację wystąpienia zdarzenia, która nie jest oznaczona „Custom"
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 4e7ef82659c43be08ee444eaf3f4df663f7aaa53
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159654"
---
# <a name="bc30941-structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>BC30941: struktura " \<structurename> " musi zawierać co najmniej jedną zmienną elementu członkowskiego wystąpienia lub co najmniej jedną deklarację zdarzenia wystąpienia, która nie jest oznaczona jako "Custom"

Definicja struktury nie zawiera żadnych zmiennych nieudostępnionych lub nieudostępnianych zdarzeń nieniestandardowych.

 Każda struktura musi mieć zmienną lub zdarzenie, które stosuje się do każdego określonego wystąpienia (nieudostępnione) zamiast do wszystkich wystąpień zbiorczo ([współużytkowane](../modifiers/shared.md)). Nieudostępnione stałe, właściwości i procedury nie spełniają tego wymagania. Ponadto, jeśli nie istnieją zmienne nieudostępnione i tylko jedno nieudostępnione zdarzenie, to zdarzenie nie może być `Custom` zdarzeniem.

 **Identyfikator błędu:** BC30941

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Zdefiniuj co najmniej jedną zmienną lub zdarzenie, które nie jest `Shared` . Jeśli zdefiniujesz tylko jedno zdarzenie, musi ono być nieniestandardowe i nieudostępnione.

## <a name="see-also"></a>Zobacz też

- [Struktury](../../programming-guide/language-features/data-types/structures.md)
- [Instrukcje: Deklarowanie struktury](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Structure — Instrukcja](../statements/structure-statement.md)
