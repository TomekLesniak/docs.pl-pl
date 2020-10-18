---
title: Instrukcja nie może kończyć bloku poza instrukcją „If” wiersza
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 4fd7577accd0b312ee1e3d2d990d256514d5f5f6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161338"
---
# <a name="bc32005-statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>BC32005: instrukcja nie może kończyć bloku poza instrukcją "If" wiersza

Jednowierszowa `If` instrukcja zawiera kilka instrukcji rozdzielonych średnikami (:), z których jedna jest `End` instrukcją dla bloku sterowania poza linią jednowierszową `If` . Instrukcje jednowierszowe `If` nie używają `End If` instrukcji.

 **Identyfikator błędu:** BC32005

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Przenieś instrukcję jednowierszową `If` poza blok sterowania, który zawiera `End If` instrukcję.

## <a name="see-also"></a>Zobacz też

- [If...Then...Else, instrukcja](../statements/if-then-else-statement.md)
