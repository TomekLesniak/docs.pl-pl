---
title: Element „<elementname>" jest przestarzały (ostrzeżenie w języku Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: 555030d97434852eab64cc8b4bda2e901649d17d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163145"
---
# <a name="bc40008-elementname-is-obsolete-visual-basic-warning"></a>BC40008: element " \<elementname> " jest przestarzały (Visual Basic ostrzeżenie)

Instrukcja próbuje uzyskać dostęp do elementu programistycznego, który został oznaczony <xref:System.ObsoleteAttribute> atrybutem i dyrektywą, aby traktować go jako ostrzeżenie.

 Można oznaczyć dowolny element programistyczny jako nieużywany przez zastosowanie <xref:System.ObsoleteAttribute> do niego. W takim przypadku można ustawić <xref:System.ObsoleteAttribute.IsError%2A> właściwość atrybutu na `True` lub `False` . Jeśli ustawisz ją na `True` , kompilator traktuje próbę użycia elementu jako błąd. Jeśli ustawisz ją na `False` lub Zezwól na ustawienie domyślne `False` , kompilator generuje ostrzeżenie w przypadku próby użycia elementu.

 Domyślnie ten komunikat jest ostrzeżeniem, ponieważ <xref:System.ObsoleteAttribute.IsError%2A> Właściwość <xref:System.ObsoleteAttribute> jest `False` . Aby uzyskać więcej informacji na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędów, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identyfikator błędu:** BC40008

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Upewnij się, że odwołanie do kodu źródłowego jest poprawnie sprawdzane jako nazwa elementu.

## <a name="see-also"></a>Zobacz też

- [Przegląd atrybutów](../../programming-guide/concepts/attributes/index.md)
