---
title: Nie można wykonać operacji, ponieważ katalog docelowy znajduje się w katalogu źródłowym
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: d159b9bb3a765a2fefe99fa15dff42e979fda9e3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079142"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>Nie można wykonać operacji, ponieważ katalog docelowy znajduje się w katalogu źródłowym

Operacja cykliczna zakończyła się niepowodzeniem. Cykliczny cykl operacji i w związku z tym nie można ukończyć. Na przykład obiekt A może próbować dziedziczyć z obiektu B, który z kolei dziedziczy z obiektu A.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Podczas dziedziczenia upewnij się, że nie ma odwołań cyklicznych.  
  
## <a name="see-also"></a>Zobacz także

- [Typy błędów](../programming-guide/language-features/error-types.md)
- [Używanie punktów przerwania w debugerze programu Visual Studio](/visualstudio/debugger/using-breakpoints)
