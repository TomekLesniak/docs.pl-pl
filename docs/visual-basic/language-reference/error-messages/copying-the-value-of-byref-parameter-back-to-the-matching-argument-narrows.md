---
title: Kopiowanie wartości parametru „ByRef” <parametername>” z powrotem do pasującego argumentu powoduje zawężenie typu „<typename1>” do typu „<typename2>”.
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: b9a38d3eb4e25d5c9ac765adf47df72e45fd082a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160935"
---
# <a name="bc32053-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a>BC32053: kopiowanie wartości parametru "ByRef" "" z \<parametername> powrotem do pasującego argumentu powoduje zawężenie z typu " \<typename1> " do typu " \<typename2> "

Procedura jest wywoływana z argumentem, który jest poszerzany do odpowiedniego typu parametru, a konwersja z parametru do argumentu jest zawężana.

 Podczas definiowania klasy lub struktury można zdefiniować jeden lub więcej operatorów konwersji, aby przekonwertować tę klasę lub typ struktury na inne typy. Można również zdefiniować operatory konwersji odwrotnej, aby przekonwertować te inne typy z powrotem na klasę lub typ struktury. Jeśli używasz klasy lub typu struktury w wywołaniu procedury, Visual Basic może użyć tych operatorów konwersji do przekonwertowania typu argumentu na typ odpowiadającego mu parametru.

 W przypadku przekazania argumentu [ByRef](../modifiers/byref.md), Visual Basic czasami kopiuje wartość argumentu do zmiennej lokalnej w procedurze, zamiast przekazywać odwołanie. W takim przypadku, gdy procedura zwraca, Visual Basic należy skopiować wartość zmiennej lokalnej z powrotem do argumentu w kodzie wywołującym.

 Jeśli `ByRef` wartość argumentu jest kopiowana do procedury, a argument i parametr są tego samego typu, konwersja nie jest konieczna. Ale jeśli typy są różne, Visual Basic muszą być konwertowane w obu kierunkach. Jeśli jeden z typów jest klasą lub typem struktury, Visual Basic musi przekonwertować go zarówno do, jak i z innego typu. Jeśli jedno z tych konwersji jest rozszerzane, konwersja odwrotna może ulec zawężaniu.

 **Identyfikator błędu:** BC32053

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Jeśli to możliwe, użyj argumentu wywołującego tego samego typu co parametr procedury, więc Visual Basic nie musi wykonywać żadnej konwersji.

- Jeśli musisz wywołać procedurę z typem argumentu innym niż typ parametru, ale nie musisz zwracać wartości do argumentu wywołującego, zdefiniuj parametr jako [ByVal](../modifiers/byval.md) zamiast `ByRef` .

- Jeśli musisz zwrócić wartość do argumentu wywołującego, zdefiniuj Operator konwersji odwrotnej jako [rozszerzający](../modifiers/widening.md), jeśli to możliwe.

## <a name="see-also"></a>Zobacz też

- [Procedury](../../programming-guide/language-features/procedures/index.md)
- [Parametry i argumenty procedur](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Przekazywanie argumentów według wartości i według odwołania](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Operator — Instrukcja](../statements/operator-statement.md)
- [Instrukcje: definiowanie operatora](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Instrukcje: definiowanie operatora konwersji](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Konwersje plików w Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Rozszerzanie i zwężanie konwersji](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
