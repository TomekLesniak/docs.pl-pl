---
title: Instrukcja nie może kończyć bloku poza instrukcją „If” wiersza
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 5e75c29e57a9c04c66e6bca79d99bb18c513f667
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870743"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>Instrukcja nie może kończyć bloku poza instrukcją „If” wiersza

Jednowierszowa `If` instrukcja zawiera kilka instrukcji rozdzielonych średnikami (:), z których jedna jest `End` instrukcją dla bloku sterowania poza linią jednowierszową `If` . Instrukcje jednowierszowe `If` nie używają `End If` instrukcji.  
  
 **Identyfikator błędu:** BC32005  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Przenieś instrukcję jednowierszową `If` poza blok sterowania, który zawiera `End If` instrukcję.  
  
## <a name="see-also"></a>Zobacz też

- [If...Then...Else, instrukcja](../statements/if-then-else-statement.md)
