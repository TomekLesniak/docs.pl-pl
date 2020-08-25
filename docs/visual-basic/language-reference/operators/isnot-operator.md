---
title: Operator IsNot
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ea978f8874cee20fb3a005189fd846f7564da777
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811044"
---
# <a name="isnot-operator-visual-basic"></a>IsNot — Operator (Visual Basic)

Porównuje dwie zmienne odwołań do obiektów.

## <a name="syntax"></a>Składnia

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Części

- `result`

  Wymagany. `Boolean`Wartość.

- `object1`

  Wymagany. Dowolna `Object` zmienna lub wyrażenie.

- `object2`

  Wymagany. Dowolna `Object` zmienna lub wyrażenie.

## <a name="remarks"></a>Uwagi

`IsNot`Operator określa, czy dwa odwołania do obiektów odwołują się do różnych obiektów. Jednak nie wykonuje porównania wartości. Jeśli `object1` i `object2` oba odnoszą się do dokładnie tego samego wystąpienia obiektu, `result` to `False` ; Jeśli nie, `result` to `True` .

`IsNot` jest przeciwieństwem `Is` operatora. Zaletą `IsNot` jest to, że można uniknąć niewygodna składni z `Not` i `Is` , co może być trudne do odczytania.

 Operatory i służą `Is` `IsNot` do testowania zarówno obiektów wczesnych, jak i z późnym wiązaniem.

## <a name="example"></a>Przykład

Poniższy przykład kodu używa `Is` operatora i `IsNot` operatora, aby wykonać to samo porównanie.

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a>Użycie operatora TypeOf z operatorem IsNot

Rozpoczynając od Visual Basic 14, można użyć `TypeOf` operatora z `IsNot` operatorem, aby sprawdzić, czy obiekt *nie* jest zgodny z typem danych. Na przykład:

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a>Zobacz też

- [Is, operator](is-operator.md)
- [TypeOf — Operator](typeof-operator.md)
- [Kolejność wykonywania działań (Visual Basic)](operator-precedence.md)
- [Porady: testowanie, czy dwa obiekty są takie same](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
