---
title: Element „<keyword>” jest prawidłowy tylko wewnątrz metody wystąpienia
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: ad39ade294b362b20f2dfb93455445bf41d056cd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163327"
---
# <a name="bc30043-keyword-is-valid-only-within-an-instance-method"></a>BC30043: element " \<keyword> " jest prawidłowy tylko wewnątrz metody wystąpienia

`Me` `MyClass` Słowa kluczowe, i `MyBase` odwołują się do określonych wystąpień klasy. Nie można ich używać wewnątrz wspólnej `Function` procedury lub `Sub` .

*Identyfikator błędu:** BC30043

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Usuń słowo kluczowe z procedury lub Usuń `Shared` słowo kluczowe z deklaracji procedury.

## <a name="see-also"></a>Zobacz też

- [Przypisanie zmiennej obiektu](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase i MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Podstawowe informacje o dziedziczeniu](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
