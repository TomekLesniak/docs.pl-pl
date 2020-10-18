---
title: Instrukcja „Class” musi być zakończona odpowiadającą jej instrukcją „End Class”
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 6889e97aad913f6911ce438892752542de0d10f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163197"
---
# <a name="bc30481-class-statement-must-end-with-a-matching-end-class"></a>BC30481: Instrukcja "Class" musi być zakończona odpowiadającą jej instrukcją "End Class"

`Class` służy do inicjowania `Class` bloku; w związku z tym może wystąpić tylko na początku bloku, z odpowiadającą instrukcją `End Class` kończącą blok. Istnieje instrukcja nadmiarowa `Class` lub nie zakończono `Class` blokady przy użyciu `End Class` .

 **Identyfikator błędu:** BC30481

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Znajdź i Usuń niezbędną `Class` instrukcję.

- Zakończ `Class` blok ze zgodnym elementem `End Class` .

## <a name="see-also"></a>Zobacz też

- [End — \<keyword> instrukcja](../statements/end-keyword-statement.md)
- [Class, instrukcja](../statements/class-statement.md)
