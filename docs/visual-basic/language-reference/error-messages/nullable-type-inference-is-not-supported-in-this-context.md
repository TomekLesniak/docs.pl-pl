---
title: Wnioskowanie typu zerowalnego nie jest obsługiwane w tym kontekście
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 610d2dc427d882c412b87eb67f021a8a86025f25
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159930"
---
# <a name="bc36629-nullable-type-inference-is-not-supported-in-this-context"></a>BC36629: wnioskowanie o typie dopuszczające wartość null nie jest obsługiwane w tym kontekście

Typy wartości i struktury mogą być deklarowane jako dopuszczające wartość null.

```vb
Dim a? As Integer
Dim b As Integer?
```

 Nie można jednak używać deklaracji wartości null w połączeniu z wnioskami o typie. Poniższe przykłady powodują wystąpienie tego błędu.

```vb
' Not valid.
' Dim c? = 10
' Dim d? = a
```

 **Identyfikator błędu:** BC36629

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Użyj `As` klauzuli, aby zadeklarować zmienną jako typ wartości null.

## <a name="see-also"></a>Zobacz też

- [Typy wartości null](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Wnioskowanie o typie lokalnym](../../programming-guide/language-features/variables/local-type-inference.md)
