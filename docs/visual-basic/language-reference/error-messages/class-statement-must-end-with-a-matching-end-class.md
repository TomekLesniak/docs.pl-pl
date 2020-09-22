---
title: Instrukcja „Class” musi być zakończona odpowiadającą jej instrukcją „End Class”
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: d67f0e71dbdbf97420ec5b5ba4b6f06acfba1bd9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874617"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a>Instrukcja „Class” musi być zakończona odpowiadającą jej instrukcją „End Class”

`Class` służy do inicjowania `Class` bloku; w związku z tym może wystąpić tylko na początku bloku, z odpowiadającą instrukcją `End Class` kończącą blok. Istnieje instrukcja nadmiarowa `Class` lub nie zakończono `Class` blokady przy użyciu `End Class` .  
  
 **Identyfikator błędu:** BC30481  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Znajdź i Usuń niezbędną `Class` instrukcję.  
  
- Zakończ `Class` blok ze zgodnym elementem `End Class` .  
  
## <a name="see-also"></a>Zobacz też

- [End — \<keyword> instrukcja](../statements/end-keyword-statement.md)
- [Class, instrukcja](../statements/class-statement.md)
