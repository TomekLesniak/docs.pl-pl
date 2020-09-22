---
title: '>>= — Operator'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: a1c2331791644155504183d3cf5767470a3bf17b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873355"
---
# <a name="-operator-visual-basic"></a>>>= — operator (Visual Basic)

Wykonuje arytmetyczne przesunięcie w prawo wartości zmiennej lub właściwości i przypisuje wynik z powrotem do zmiennej lub właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Części  

 `variableorproperty`  
 Wymagany. Zmienna lub właściwość typu całkowitego ( `SByte` , `Byte` ,,, `Short` , `UShort` `Integer` `UInteger` , `Long` lub `ULong` ).  
  
 `amount`  
 Wymagany. Wyrażenie liczbowe typu danych, które jest poszerzane do `Integer` .  
  
## <a name="remarks"></a>Uwagi  

 Element po lewej stronie `>>=` operatora może być prostą zmienną skalarną, właściwością lub elementem tablicy. Zmienna lub właściwość nie może być [tylko do odczytu](../modifiers/readonly.md).  
  
 `>>=`Operator najpierw wykonuje arytmetyczne przesunięcie w prawo wartości zmiennej lub właściwości. Następnie operator przypisuje wynik tej operacji z powrotem do zmiennej lub właściwości.  
  
 Przesunięcia arytmetyczne nie są cykliczne, co oznacza, że bity przesunięte poza jeden koniec wyniku nie są ponownie wprowadzane na drugim końcu. W wyniku przesunięcia w prawo arytmetyczne bity przesunięte poza skrajną prawą pozycję bitu są odrzucane, a bit z lewej strony jest propagowany do pozycji bitowych opuszczone w lewo. Oznacza to, że jeśli `variableorproperty` ma wartość ujemną, pozycje opuszczone są ustawione na jeden. Jeśli `variableorproperty` jest wartością dodatnią lub jeśli jej typ danych jest typem bez znaku, pozycje opuszczone są ustawione na wartość zero.  
  
## <a name="overloading"></a>Przeciążenie  

 [Operator>> ](right-shift-operator.md) może być *przeciążony*, co oznacza, że Klasa lub struktura może przedefiniować jej zachowanie, gdy operand ma typ tej klasy lub struktury. Przeciążanie `>>` operatora ma wpływ na zachowanie `>>=` operatora. Jeśli kod korzysta z `>>=` klasy lub struktury, która przeciążania `>>` , należy poznać jej ponownie zdefiniowane zachowanie. Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa operatora, `>>=` Aby przesunąć wzorzec bitowy `Integer` zmiennej bezpośrednio o określoną wartość i przypisać wynik do zmiennej.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Zobacz też

- [ Operator>> ](right-shift-operator.md)
- [Operatory przypisania](assignment-operators.md)
- [Operatory Bit Shift](bit-shift-operators.md)
- [Kolejność wykonywania działań (Visual Basic)](operator-precedence.md)
- [Operatory według funkcji](operators-listed-by-functionality.md)
- [Instrukcje](../../programming-guide/language-features/statements.md)
