---
title: Typ „<typename>” jest typem delegowanym
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: dcb52188c53b38ac14de0002b5212bb33c9f7203
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161780"
---
# <a name="bc32008-typename-is-a-delegate-type"></a>BC32008: " \<typename> " jest typem delegata

\<typename>Typ "" jest typem delegowanym. Konstrukcja delegata zezwala tylko na pojedyncze wyrażenie AddressOf jako listę argumentów. Często wyrażenie AddressOf może być używane zamiast konstrukcji delegata.

 `New`Klauzula tworząca wystąpienie klasy delegata dostarcza do konstruktora delegata nieprawidłową listę argumentów.

 `AddressOf`Podczas tworzenia nowego wystąpienia delegata można podać tylko jedno wyrażenie.

 Ten błąd może wystąpić, jeśli nie przekażesz żadnych argumentów do konstruktora delegata, Jeśli przekażesz więcej niż jeden argument lub przekażesz pojedynczy argument, który nie jest prawidłowym `AddressOf` wyrażeniem.

 **Identyfikator błędu:** BC32008

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Użyj jednego `AddressOf` wyrażenia na liście argumentów dla klasy delegata w `New` klauzuli.

## <a name="see-also"></a>Zobacz też

- [Operator new](../operators/new-operator.md)
- [AddressOf, operator](../operators/addressof-operator.md)
- [Delegaci](../../programming-guide/language-features/delegates/index.md)
- [Instrukcje: wywoływanie metody delegata](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
