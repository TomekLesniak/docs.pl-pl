---
title: W elemencie „<name>” nie odnaleziono dostępnej metody „Main” z odpowiednim podpisem.
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: e1f95484a153bdcac9543508b7f2708dc6b7d942
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160044"
---
# <a name="bc30737-no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>BC30737: w elemencie "" nie znaleziono dostępnej metody "Main" z odpowiednim podpisem. \<name>

Aplikacje wiersza polecenia muszą mieć `Sub Main` zdefiniowany. `Main` musi być zadeklarowany tak, jakby `Public Shared` jest zdefiniowana w klasie lub tak, jakby została `Public` zdefiniowana w module.

 **Identyfikator błędu:** BC30737

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Zdefiniuj `Public Sub Main` procedurę dla projektu. Zadeklaruj go jako `Shared` if i tylko wtedy, gdy zdefiniujesz go wewnątrz klasy.

## <a name="see-also"></a>Zobacz też

- [Struktura programu Visual Basic](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Procedury](../../programming-guide/language-features/procedures/index.md)
