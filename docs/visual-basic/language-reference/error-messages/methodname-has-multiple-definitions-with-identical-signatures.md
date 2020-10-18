---
title: „<methodname>” ma wiele definicji o identycznych podpisach
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 663b22421d1a0e401cfb3c135c99bd097163a78b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160369"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a>BC30269: " \<methodname> " ma wiele definicji z identycznymi sygnaturami

`Function` `Sub` Deklaracja procedury lub używa identycznej nazwy procedury i listy argumentów jako poprzedniej deklaracji. Jedną z możliwych przyczyn jest próba przeciążenia oryginalnej procedury. Przeciążone procedury muszą mieć różne listy argumentów.

 **Identyfikator błędu:** BC30269

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Zmień nazwę procedury lub listę argumentów lub Usuń zduplikowaną deklarację.

## <a name="see-also"></a>Zobacz też

- [Odwołania do elementów zadeklarowanych](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Zagadnienia dotyczące przeciążania procedur](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
