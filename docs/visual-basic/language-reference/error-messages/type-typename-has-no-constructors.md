---
title: Typ „<typename>” nie ma konstruktorów
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 249bcb7020f26c7c43d560e91ef7a34e4dc64470
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161182"
---
# <a name="bc30251-type-typename-has-no-constructors"></a>BC30251: typ " \<typename> " nie ma konstruktorów

Typ nie obsługuje wywołania do `Sub New()` . Jedną z możliwych przyczyn jest uszkodzony kompilator lub plik binarny.

 **Identyfikator błędu:** BC30251

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Jeśli typ znajduje się w innym projekcie lub w pliku, do którego istnieje odwołanie, zainstaluj ponownie projekt lub plik.

2. Jeśli typ znajduje się w tym samym projekcie, Skompiluj ponownie zestaw zawierający typ.

3. Jeśli błąd powtarza się, zainstaluj ponownie kompilator Visual Basic.

4. Jeśli błąd będzie się powtarzać, Zbierz informacje o okolicznościach i powiadom usługi pomocy technicznej firmy Microsoft.

## <a name="see-also"></a>Zobacz też

- [Obiekty i klasy](../../programming-guide/language-features/objects-and-classes/index.md)
- [Porozmawiaj z nami](/visualstudio/ide/feedback-options)
