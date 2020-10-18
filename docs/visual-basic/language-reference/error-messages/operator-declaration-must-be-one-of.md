---
title: 'Deklaracja operatora musi być jednym z: +,-, *,-,-, ^, &amp; , like, mod, and, or, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: a94e62e33427987a302a6244b2b8ce8d295e4f11
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159901"
---
# <a name="bc33000-operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a>BC33000: Deklaracja operatora musi być jedną z: +,-, *, \, /, ^, &amp; , like, mod, and, or, XOR, not, \<\<, >>...

Można zadeklarować tylko operatora, który kwalifikuje się do przeciążenia. W poniższej tabeli wymieniono operatory, które można zadeklarować.

|Typ|Operatory|
|----------|---------------|
|Jednoargumentowy|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|Binarne|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|Konwersja (Jednoargumentowa)|`CType`|

 Należy zauważyć, że `=` operator na liście Binary jest operatorem porównania, a nie operatorem przypisania.

 **Identyfikator błędu:** BC33000

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Wybierz operator z zestawu operatorów z możliwością przeciążenia.

- Jeśli potrzebujesz funkcji przeciążania operatora, którego nie można przeciążyć bezpośrednio, Utwórz `Function` procedurę, która przyjmuje odpowiednie parametry i zwraca odpowiednią wartość.

## <a name="see-also"></a>Zobacz też

- [Operator — Instrukcja](../statements/operator-statement.md)
- [Procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Instrukcje: definiowanie operatora](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Instrukcje: definiowanie operatora konwersji](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Function, instrukcja](../statements/function-statement.md)
