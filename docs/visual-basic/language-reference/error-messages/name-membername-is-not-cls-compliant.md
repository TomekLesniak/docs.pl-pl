---
title: Nazwa <membername> jest niezgodna ze specyfikacją CLS
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 43fff3f12295f3837148b0a349887e8405126819
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160239"
---
# <a name="bc40031-name-membername-is-not-cls-compliant"></a>BC40031: nazwa \<membername> jest niezgodna ze specyfikacją CLS

Zestaw jest oznaczony jako, `<CLSCompliant(True)>` ale uwidacznia element członkowski o nazwie rozpoczynającej się od znaku podkreślenia ( `_` ).

 Element programowania może zawierać jeden lub więcej podkreśleń, ale w celu uzyskania zgodności z [niezależnymi od języka i składnikami Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS) nie może zaczynać się od znaku podkreślenia. Zobacz [zadeklarowane nazwy elementów](../../programming-guide/language-features/declared-elements/declared-element-names.md).

 Po zastosowaniu <xref:System.CLSCompliantAttribute> do elementu programistycznego, należy ustawić `isCompliant` parametr atrybutu na wartość `True` lub `False` w celu wskazania zgodności lub niezgodności. Dla tego parametru nie ma wartości domyślnej i należy podać wartość.

 Jeśli nie zastosujesz <xref:System.CLSCompliantAttribute> do elementu, jest on uznawany za niezgodny.

 Domyślnie ten komunikat jest ostrzeżeniem. Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identyfikator błędu:** BC40031

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Jeśli masz kontrolę nad kodem źródłowym, Zmień nazwę elementu członkowskiego tak, aby nie zaczynała się od znaku podkreślenia.

- Jeśli wymagasz, aby nazwa elementu członkowskiego pozostała niezmieniona, Usuń <xref:System.CLSCompliantAttribute> z jej definicji lub oznacz ją jako `<CLSCompliant(False)>` . Można nadal oznaczyć zestaw jako `<CLSCompliant(True)>` .

## <a name="see-also"></a>Zobacz też

- [Nazwy zadeklarowanych elementów](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Visual Basic — Konwencje nazewnictwa](../../programming-guide/program-structure/naming-conventions.md)
