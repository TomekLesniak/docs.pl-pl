---
title: Instrukcje „#Region” i „#End Region” nie są prawidłowe w treści metod/wielowierszowych wyrażeń lambda
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: e3147b6192f54ce85d0fecd6b67f7d80f6281b54
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870878"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Instrukcje „#Region” i „#End Region” nie są prawidłowe w treści metod/wielowierszowych wyrażeń lambda

`#Region`Blok musi być zadeklarowany na poziomie klasy, modułu lub przestrzeni nazw. Region zwijany może zawierać jedną lub więcej procedur, ale nie może zaczynać się ani kończyć wewnątrz procedury.  
  
 **Identyfikator błędu:** BC32025  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Upewnij się, że poprzednia procedura została prawidłowo `End Function` zakończona `End Sub` instrukcją or.  
  
2. Upewnij się, `#Region` że `#End Region` dyrektywy i znajdują się w tym samym bloku kodu.  
  
## <a name="see-also"></a>Zobacz też

- [#Region — dyrektywa](../directives/region-directive.md)
