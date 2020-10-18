---
title: Element <type1>„<typename>” musi implementować element „<methodname>” dla interfejsu „<interfacename>”
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 68c6f65e6be229cc74458fa56fe3d3aa889c18f7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161871"
---
# <a name="bc30149-type1typename-must-implement-methodname-for-interface-interfacename"></a>BC30149: \<type1> " \<typename> " musi implementować element " \<methodname> " dla interfejsu " \<interfacename> "

Klasa lub struktura oświadczenia do implementacji interfejsu, ale nie implementuje procedury zdefiniowanej przez interfejs. Każdy element członkowski interfejsu musi być zaimplementowany.

 **Identyfikator błędu:** BC30149

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Zadeklaruj procedurę o tej samej nazwie i podpisie, zgodnie z definicją w interfejsie. Pamiętaj, aby uwzględnić co najmniej `End Function` instrukcję or `End Sub` .

2. Dodaj `Implements` klauzulę do końca `Function` `Sub` instrukcji or. Na przykład:

    ```vb
    Public Sub DoSomething() Implements IBaseInterface.DoSomething
    ```

## <a name="see-also"></a>Zobacz też

- [Implements — Instrukcja](../statements/implements-statement.md)
- [Interfejsy](../../programming-guide/language-features/interfaces/index.md)
