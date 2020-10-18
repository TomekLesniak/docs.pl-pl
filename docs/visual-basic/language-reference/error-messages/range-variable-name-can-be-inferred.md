---
title: Nazwę zmiennej zakresu można wywnioskować tylko na podstawie prostej lub kwalifikowanej nazwy bez argumentów
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: 63990b7d37388057ff2cdb430d29878a1c7b39ba
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162365"
---
# <a name="bc36599-range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>BC36599: nazwę zmiennej zakresu można wywnioskować tylko na podstawie prostej lub kwalifikowanej nazwy bez argumentów

Element programistyczny, który ma co najmniej jeden argument jest dołączony do zapytania LINQ. Kompilator nie może wywnioskować zmiennej zakresu z tego elementu programowania.

**Identyfikator błędu:** BC36599

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

Podaj jawną nazwę zmiennej dla elementu programistycznego, jak pokazano w poniższym kodzie:

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a>Zobacz też

- [Wprowadzenie do LINQ w Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [SELECT — klauzula](../queries/select-clause.md)
