---
title: Operand 'IsNot' typu „typename” można porównać tylko z elementem „Nothing”, ponieważ typ „typename” jest typem zerowalnym
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 084978c1e047eebd60149af63c0ec9a1135225be
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163340"
---
# <a name="bc32128-isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a>BC32128: argument operacji "IsNot" typu "typename" można porównać tylko z elementem "Nothing", ponieważ typ "typename" jest typem dopuszczającym wartość null

Zmienna zadeklarowana jako typ wartości null została porównana z wyrażeniem innym niż `Nothing` użycie `IsNot` operatora.

**Identyfikator błędu:** BC32128

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

Aby porównać typ dopuszczający wartość null z wyrażeniem innym niż `Nothing` przy użyciu `IsNot` operatora, należy wywołać `GetType` metodę na typie dopuszczającym wartość null i porównać wynik z wyrażeniem, jak pokazano w poniższym przykładzie.

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a>Zobacz też

- [Typy wartości null](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [IsNot, operator](../operators/isnot-operator.md)
