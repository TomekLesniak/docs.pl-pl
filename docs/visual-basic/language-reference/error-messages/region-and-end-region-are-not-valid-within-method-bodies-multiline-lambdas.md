---
title: Instrukcje „#Region” i „#End Region” nie są prawidłowe w treści metod/wielowierszowych wyrażeń lambda
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c792fa1a42bde22959ae21439cb2a0a1e4be343f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162287"
---
# <a name="bc32025-region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>BC32025: instrukcje "#Region" i "#End Region" nie są prawidłowe w treści metod/wielowierszowych wyrażeń lambda

`#Region`Blok musi być zadeklarowany na poziomie klasy, modułu lub przestrzeni nazw. Region zwijany może zawierać jedną lub więcej procedur, ale nie może zaczynać się ani kończyć wewnątrz procedury.

 **Identyfikator błędu:** BC32025

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Upewnij się, że poprzednia procedura została prawidłowo `End Function` zakończona `End Sub` instrukcją or.

2. Upewnij się, `#Region` że `#End Region` dyrektywy i znajdują się w tym samym bloku kodu.

## <a name="see-also"></a>Zobacz też

- [#Region — dyrektywa](../directives/region-directive.md)
