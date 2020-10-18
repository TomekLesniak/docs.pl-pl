---
title: Oczekiwano deklaracji
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 2755f5afcb96ca7a6c4d140908649390dd66d571
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162703"
---
# <a name="bc30188-declaration-expected"></a>BC30188: oczekiwano deklaracji

Niedeklaratywna instrukcja, taka jak Instrukcja przypisania lub pętla, występuje poza żadną procedurą. Tylko deklaracje są dozwolone poza procedurami.

 Alternatywnie, element programowania jest zadeklarowany bez słowa kluczowego deklaracji, takiego jak `Dim` lub `Const` .

 **Identyfikator błędu:** BC30188

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Przenieś niedeklaracyjne instrukcje do treści procedury.

- Rozpocznij deklarację z odpowiednimi słowami kluczowymi deklaracji.

- Upewnij się, że słowo kluczowe deklaracji nie jest błędnie napisane.

## <a name="see-also"></a>Zobacz też

- [Procedury](../../programming-guide/language-features/procedures/index.md)
- [Dim, instrukcja](../statements/dim-statement.md)
