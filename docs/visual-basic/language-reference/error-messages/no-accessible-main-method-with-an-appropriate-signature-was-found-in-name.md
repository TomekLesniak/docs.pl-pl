---
title: W elemencie „<name>” nie odnaleziono dostępnej metody „Main” z odpowiednim podpisem.
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6958e778701066760aa74e3b4d566800b7527b76
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871487"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>W elemencie „\<name>” nie odnaleziono dostępnej metody „Main” z odpowiednim podpisem.

Aplikacje wiersza polecenia muszą mieć `Sub Main` zdefiniowany. `Main` musi być zadeklarowany tak, jakby `Public Shared` jest zdefiniowana w klasie lub tak, jakby została `Public` zdefiniowana w module.  
  
 **Identyfikator błędu:** BC30737  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Zdefiniuj `Public Sub Main` procedurę dla projektu. Zadeklaruj go jako `Shared` if i tylko wtedy, gdy zdefiniujesz go wewnątrz klasy.  
  
## <a name="see-also"></a>Zobacz też

- [Struktura programu Visual Basic](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Procedury](../../programming-guide/language-features/procedures/index.md)
