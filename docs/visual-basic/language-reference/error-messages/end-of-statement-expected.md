---
title: Oczekiwano końca instrukcji
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 36883989fe5aa0b5c70aa9ab1f7c991fab99e778
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163132"
---
# <a name="bc30205-end-of-statement-expected"></a>BC30205: oczekiwano końca instrukcji

Instrukcja ma składnię kompletną, ale dodatkowy element programistyczny następuje po elemencie, który uzupełnia instrukcję. Terminator wiersza jest wymagany na końcu każdej instrukcji.

 Terminator wiersza dzieli znaki pliku źródłowego Visual Basic na wiersze. Przykłady terminatorów wiersza to znak powrotu karetki Unicode (&HD), znak wysuwu wiersza Unicode (&HA) i znak powrotu karetki Unicode, po którym następuje znak wysuwu wiersza w formacie Unicode. Aby uzyskać więcej informacji na temat terminatorów wierszy, zobacz [Specyfikacja języka Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).

 **Identyfikator błędu:** BC30205

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Sprawdź, czy dwie różne instrukcje zostały przypadkowo umieszczone w tym samym wierszu.

2. Wstaw terminator wiersza po elemencie, który uzupełnia instrukcję.

## <a name="see-also"></a>Zobacz też

- [Instrukcje: Przerywanie i łączenie instrukcji w kodzie](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Instrukcje](../../programming-guide/language-features/statements.md)
