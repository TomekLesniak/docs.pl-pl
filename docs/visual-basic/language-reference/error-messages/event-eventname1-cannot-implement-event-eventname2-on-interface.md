---
title: Zdarzenie „<eventname1>” nie może implementować zdarzenia „<eventname2>” w interfejsie „<interface>”, ponieważ ich typy delegowane „<delegate1>” i „<delegate2>” są niezgodne
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: d0b2b095ed355b420b28e87ed0b9d6a31f049ebf
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162027"
---
# <a name="bc31423-event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a>BC31423: zdarzenie " \<eventname1> " nie może implementować zdarzenia " \<eventname2> " w interfejsie " \<interface> ", ponieważ ich typy delegatów " \<delegate1> " i " \<delegate2> " nie pasują do siebie

Visual Basic nie może zaimplementować zdarzenia, ponieważ typ delegata zdarzenia nie jest zgodny z typem delegata zdarzenia w interfejsie. Ten błąd może wystąpić, gdy zdefiniujesz wiele zdarzeń w interfejsie, a następnie spróbujesz zaimplementować je razem z tym samym zdarzeniem. Zdarzenie może zaimplementować dwa lub więcej zdarzeń tylko wtedy, gdy wszystkie zaimplementowane zdarzenia są deklarowane przy użyciu `As` składni i określają ten sam typ delegata.

 **Identyfikator błędu:** BC31423

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Zaimplementuj zdarzenia oddzielnie.

     —lub—

- Zdefiniuj zdarzenia w interfejsie przy użyciu `As` składni i określ ten sam typ delegata.

## <a name="see-also"></a>Zobacz też

- [Event — Instrukcja](../statements/event-statement.md)
- [Delegate — Instrukcja](../statements/delegate-statement.md)
- [Zdarzenia](../../programming-guide/language-features/events/index.md)
