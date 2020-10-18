---
title: Element „<classname>” jest niezgodny ze specyfikacją CLS, ponieważ interfejs „<interfacename>”, który implementuje, jest niezgodny ze specyfikacją CLS
ms.date: 07/20/2015
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
ms.openlocfilehash: 936bc78d87613a8492347df0f65688bbef6e2ca4
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163184"
---
# <a name="bc40029-classname-is-not-cls-compliant-because-the-interface-interfacename-it-implements-is-not-cls-compliant"></a>BC40029: element " \<classname> " nie jest zgodny ze specyfikacją CLS, ponieważ interfejs "", który \<interfacename> implementuje, jest niezgodny ze specyfikacją CLS

Klasa lub interfejs jest oznaczony jako, `<CLSCompliant(True)>` gdy pochodzi z lub implementuje typ, który jest oznaczony jako `<CLSCompliant(False)>` lub nie jest oznaczony.

 Aby Klasa lub interfejs były zgodne z [niezależnymi od języka i składnikami Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS), jego cała Hierarchia dziedziczenia musi być zgodna. Oznacza to, że każdy typ, z którego dziedziczy, bezpośrednio lub pośrednio, musi być zgodny. Podobnie, jeśli klasa implementuje jeden lub więcej interfejsów, muszą one być zgodne w całej hierarchii dziedziczenia.

 Po zastosowaniu <xref:System.CLSCompliantAttribute> do elementu programistycznego, należy ustawić `isCompliant` parametr atrybutu na wartość `True` lub `False` w celu wskazania zgodności lub niezgodności. Dla tego parametru nie ma wartości domyślnej i należy podać wartość.

 Jeśli nie zastosujesz <xref:System.CLSCompliantAttribute> do elementu, jest on uznawany za niezgodny.

 Domyślnie ten komunikat jest ostrzeżeniem. Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identyfikator błędu:** BC40029

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Jeśli wymagana jest zgodność ze specyfikacją CLS, należy zdefiniować ten typ w ramach innej hierarchii dziedziczenia lub schematu implementacji.

- Jeśli potrzebujesz, aby ten typ pozostał w bieżącej hierarchii dziedziczenia lub schemat implementacji, Usuń <xref:System.CLSCompliantAttribute> z jego definicji lub Oznacz jako `<CLSCompliant(False)>` .
