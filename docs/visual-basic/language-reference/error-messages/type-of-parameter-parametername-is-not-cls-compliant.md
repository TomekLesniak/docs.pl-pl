---
title: Typ parametru „<parametername>” jest niezgodny ze specyfikacją CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: 7043138f770264b73eeac79cd262104b88cd8516
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161234"
---
# <a name="bc40028-type-of-parameter-parametername-is-not-cls-compliant"></a>BC40028: typ parametru " \<parametername> " jest niezgodny ze specyfikacją CLS

Procedura jest oznaczona jako `<CLSCompliant(True)>` , ale deklaruje parametr z typem, który jest oznaczony jako `<CLSCompliant(False)>` , nie jest oznaczona lub nie kwalifikuje się, ponieważ jest typem niezgodnym.

 Aby procedura była zgodna z [niezależnością od języka i składnikami Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS), musi używać tylko typów zgodnych ze specyfikacją CLS. Dotyczy to typów parametrów, typu zwracanego i typów wszystkich zmiennych lokalnych.

 Następujące Visual Basic typy danych nie są zgodne ze specyfikacją CLS:

- [SByte, typ danych](../data-types/sbyte-data-type.md)

- [UInteger, typ danych](../data-types/uinteger-data-type.md)

- [ULong, typ danych](../data-types/ulong-data-type.md)

- [UShort, typ danych](../data-types/ushort-data-type.md)

 Po zastosowaniu <xref:System.CLSCompliantAttribute> do elementu programistycznego, należy ustawić `isCompliant` parametr atrybutu na wartość `True` lub `False` w celu wskazania zgodności lub niezgodności. Dla tego parametru nie ma wartości domyślnej i należy podać wartość.

 Jeśli nie zastosujesz <xref:System.CLSCompliantAttribute> do elementu, jest on uznawany za niezgodny.

 Domyślnie ten komunikat jest ostrzeżeniem. Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identyfikator błędu:** BC40028

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Jeśli procedura musi przyjmować parametr tego określonego typu, Usuń <xref:System.CLSCompliantAttribute> . Procedura nie może być zgodna ze specyfikacją CLS.

- Jeśli procedura musi być zgodna ze specyfikacją CLS, Zmień typ tego parametru na najbliższy typ zgodny ze specyfikacją CLS. Na przykład, zamiast `UInteger` można użyć, `Integer` Jeśli nie potrzebujesz zakresu wartości powyżej 2 147 483 647. Jeśli potrzebujesz rozszerzonego zakresu, możesz zamienić `UInteger` na `Long` .

- Jeśli masz połączenie z obiektami automatyzacji lub COM, pamiętaj, że niektóre typy mają różne szerokości danych niż w .NET Framework. Na przykład `int` często jest 16 bitów w innych środowiskach. Jeśli zaakceptujesz 16-bitową liczbę całkowitą z tego składnika, zadeklaruj ją jako `Short` zamiast `Integer` w kodzie zarządzanym Visual Basic.
