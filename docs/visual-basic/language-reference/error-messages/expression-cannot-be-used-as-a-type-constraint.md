---
title: Elementu „<expression>” nie można użyć jako ograniczenia typu
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 6e55bfdc175f285b335512e64f4c2407bdb0e8c7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163093"
---
# <a name="bc32061-expression-cannot-be-used-as-a-type-constraint"></a>BC32061: element " \<expression> " nie może być używany jako ograniczenie typu

Lista ograniczeń zawiera wyrażenie, które nie reprezentuje prawidłowego ograniczenia w parametrze typu.

 Lista ograniczeń nakłada wymagania dotyczące argumentu typu przekazaną do parametru typu. W dowolnej kombinacji można określić następujące wymagania:

- Argument typu musi implementować jeden lub więcej interfejsów

- Argument typu musi dziedziczyć z co najwyżej jednej klasy

- Argument typu musi ujawniać Konstruktor bez parametrów, który może uzyskać dostęp do kodu (Uwzględnij `New` ograniczenie)

 Jeśli na liście ograniczeń nie dołączysz żadnej konkretnej klasy lub interfejsu, możesz wprowadzić bardziej ogólne wymagania, określając jedną z następujących opcji:

- Argument typu musi być typem wartości (Uwzględnij `Structure` ograniczenie)

- Argument typu musi być typem referencyjnym (Uwzględnij `Class` ograniczenie)

 Nie można określić jednocześnie `Structure` i `Class` dla tego samego parametru typu. nie można określić jednego więcej niż raz.

 **Identyfikator błędu:** BC32061

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Sprawdź, czy wyrażenie i jego elementy są poprawnie napisane.

- Jeśli wyrażenie nie kwalifikuje się do powyższej listy wymagań, usuń je z listy ograniczeń.

- Jeśli wyrażenie odwołuje się do interfejsu lub klasy, należy sprawdzić, czy kompilator ma dostęp do tego interfejsu lub klasy. Może być konieczne zakwalifikowanie nazwy i może być konieczne dodanie odwołania do projektu. Aby uzyskać więcej informacji, zobacz "odwołania do projektów" w [odwołaniach do zadeklarowanych elementów](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

## <a name="see-also"></a>Zobacz też

- [Typy ogólne w Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Typy wartości i odwołań](../../programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Odwołania do elementów zadeklarowanych](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
