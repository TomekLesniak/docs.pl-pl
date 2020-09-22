---
title: 'Deklaracja operatora musi być jednym z: +,-, *,-,-, ^, &amp; , like, mod, and, or, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: c388b1b0762dd7475ca365a8a62228d0b5d59414
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873615"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a>Deklaracja operatora musi być jedną z: +,-, *, \, /, ^, &amp; , like, mod, and, or, XOR, not, \<\<, >>...

Można zadeklarować tylko operatora, który kwalifikuje się do przeciążenia. W poniższej tabeli wymieniono operatory, które można zadeklarować.  
  
|Typ|Operatory|  
|----------|---------------|  
|Jednoargumentowy|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binarne|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Konwersja (Jednoargumentowa)|`CType`|  
  
 Należy zauważyć, że `=` operator na liście Binary jest operatorem porównania, a nie operatorem przypisania.  
  
 **Identyfikator błędu:** BC33000  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Wybierz operator z zestawu operatorów z możliwością przeciążenia.  
  
2. Jeśli potrzebujesz funkcji przeciążania operatora, którego nie można przeciążyć bezpośrednio, Utwórz `Function` procedurę, która przyjmuje odpowiednie parametry i zwraca odpowiednią wartość.  
  
## <a name="see-also"></a>Zobacz też

- [Operator — Instrukcja](../statements/operator-statement.md)
- [Procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Instrukcje: definiowanie operatora](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Instrukcje: definiowanie operatora konwersji](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Function, instrukcja](../statements/function-statement.md)
