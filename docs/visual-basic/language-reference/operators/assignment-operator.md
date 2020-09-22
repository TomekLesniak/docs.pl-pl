---
title: = — Operator
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: eccea0b43564a4980778c9d1a5b8f9a8c2a9207d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874821"
---
# <a name="-operator-visual-basic"></a>= — Operator (Visual Basic)

Przypisuje wartość do zmiennej lub właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a>Części  

 `variableorproperty`  
 Dowolna zapisywalna zmienna lub Każda właściwość.  
  
 `value`  
 Dowolny literał, stała lub wyrażenie.  
  
## <a name="remarks"></a>Uwagi  

 Element po lewej stronie znaku równości ( `=` ) może być prostą zmienną skalarną, właściwością lub elementem tablicy. Zmienna lub właściwość nie może być [tylko do odczytu](../modifiers/readonly.md). `=`Operator przypisuje wartość po prawej stronie do zmiennej lub właściwości po jej lewej stronie.  
  
> [!NOTE]
> `=`Operator jest również używany jako operator porównania. Aby uzyskać szczegółowe informacje, zobacz [Operatory porównania](comparison-operators.md).  
  
## <a name="overloading"></a>Przeciążenie  

 `=`Operator może być przeciążony tylko jako operator porównania relacyjnego, a nie jako operator przypisania. Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład demonstruje operator przypisania. Wartość po prawej stronie jest przypisana do zmiennej po lewej stronie.  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Zobacz też

- [&= — operator](and-assignment-operator.md)
- [Operator * =](multiplication-assignment-operator.md)
- [Operator + =](addition-assignment-operator.md)
- [-= — Operator (Visual Basic)](subtraction-assignment-operator.md)
- [Operator/= (Visual Basic)](floating-point-division-assignment-operator.md)
- [\\= — Operator](integer-division-assignment-operator.md)
- [^ = — Operator](exponentiation-assignment-operator.md)
- [Instrukcje](../../programming-guide/language-features/statements.md)
- [Operatory porównania](comparison-operators.md)
- [Trybie](../modifiers/readonly.md)
- [Wnioskowanie o typie lokalnym](../../programming-guide/language-features/variables/local-type-inference.md)
