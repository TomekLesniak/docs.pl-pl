---
title: Instrukcja „#ElseIf” musi być poprzedzona odpowiadającą jej instrukcją „#If” lub „#ElseIf”
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 06af269508db6a2b258251272fdc18ef20eb1c0f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874446"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>Instrukcja „#ElseIf” musi być poprzedzona odpowiadającą jej instrukcją „#If” lub „#ElseIf”

`#ElseIf` jest dyrektywy kompilacji warunkowej. `#ElseIf`Klauzula musi być poprzedzona odpowiadającą jej `#If` `#ElseIf` klauzulą or.  
  
 **Identyfikator błędu:** BC30014  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Sprawdź, czy poprzedni `#If` lub `#ElseIf` nie został oddzielony od tego `#ElseIf` przez inicjowany przez Ciebie blok kompilacji warunkowej lub nieprawidłowo umieszczony `#End If` .  
  
2. Jeśli `#ElseIf` jest poprzedzona przez `#Else` dyrektywę, Usuń `#Else` lub Zmień ją na `#ElseIf` .  
  
3. Jeśli wszystko inne jest w porządku, Dodaj `#If` dyrektywę na początku bloku kompilacji warunkowej.  
  
## <a name="see-also"></a>Zobacz też

- [#If... Then... #Else — dyrektywy](../directives/if-then-else-directives.md)
