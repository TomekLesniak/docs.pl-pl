---
title: Element „Is” wymaga argumentów operacji, które mają typ referencyjny, ale ten argument operacji ma typ wartości „<typename>”.
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 5c9f156272cd0c3cbaeadbc0e162129f41619cc6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163353"
---
# <a name="bc30020-is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a>BC30020: element "is" wymaga argumentów operacji, które mają typ referencyjny, ale ten argument operacji ma typ wartości " \<typename> "

`Is`Operator porównania określa, czy dwie zmienne obiektów odwołują się do tego samego wystąpienia. To porównanie nie jest zdefiniowane dla typów wartości.

 **Identyfikator błędu:** BC30020

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Użyj odpowiedniego operatora porównania arytmetycznego lub `Like` operatora, aby porównać dwa typy wartości.

## <a name="see-also"></a>Zobacz też

- [Is, operator](../operators/is-operator.md)
- [Like — Operator](../operators/like-operator.md)
- [Operatory porównania](../operators/comparison-operators.md)
