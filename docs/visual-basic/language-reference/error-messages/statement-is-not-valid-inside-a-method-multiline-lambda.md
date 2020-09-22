---
title: Instrukcja nie jest prawidłowa wewnątrz metody/wielowierszowego wyrażenia lambda
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: d5d756f1772b9519613e163119b88a3057d36cf3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870628"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Instrukcja nie jest prawidłowa wewnątrz metody/wielowierszowego wyrażenia lambda

Instrukcja nie jest prawidłowa w ramach `Sub` procedury, `Function` , właściwości `Get` lub właściwości `Set` . Niektóre instrukcje mogą być umieszczane na poziomie modułu lub klasy. Inne, takie jak `Option Strict` , muszą znajdować się na poziomie przestrzeni nazw i poprzedzać wszystkie inne deklaracje.  
  
 **Identyfikator błędu:** BC30024  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Usuń instrukcję z procedury.  
  
## <a name="see-also"></a>Zobacz też

- [Sub, instrukcja](../statements/sub-statement.md)
- [Function, instrukcja](../statements/function-statement.md)
- [Get — Instrukcja](../statements/get-statement.md)
- [Set — Instrukcja](../statements/set-statement.md)
