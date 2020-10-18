---
title: Wyrażenie zawiera typ „<typename>”, który jest typem ograniczonym i nie można go używać do uzyskiwania dostępu do członków dziedziczonych po elemencie „Object” lub „ValueType”.
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 3e19c0d71ee47ac61e9704f0fcd2637f01aa0896
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163054"
---
# <a name="bc31393-expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a>BC31393: wyrażenie ma typ " \<typename> ", który jest typem ograniczonym i nie można go użyć w celu uzyskania dostępu do składowych dziedziczonych po elemencie "Object" lub "ValueType"

Wyrażenie daje w wyniku typ, który nie może być opakowany przez środowisko uruchomieniowe języka wspólnego (CLR), ale uzyskuje dostęp do elementu członkowskiego, który wymaga opakowania.

 *Opakowanie* odnosi się do przetwarzania niezbędnego do wykonania konwersji typu do `Object` lub, w przypadku, do <xref:System.ValueType> . Środowisko uruchomieniowe języka wspólnego nie może mieć pola niektórych typów struktur, na przykład, <xref:System.ArgIterator> <xref:System.RuntimeArgumentHandle> i <xref:System.TypedReference> .

 To wyrażenie próbuje użyć typu ograniczonego do wywołania metody dziedziczonej z <xref:System.Object> lub <xref:System.ValueType> , takich jak <xref:System.Object.GetHashCode%2A> lub <xref:System.Object.ToString%2A> . Aby uzyskać dostęp do tej metody, Visual Basic próbowała niejawną konwersję opakowania powodującą ten błąd.

 **Identyfikator błędu:** BC31393

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Znajdź wyrażenie, którego wynikiem jest typ cytowany.

2. Znajdź część instrukcji, która próbuje wywołać metodę dziedziczoną z <xref:System.Object> lub <xref:System.ValueType> .

3. Napisz ponownie instrukcję, aby uniknąć wywołania metody.

## <a name="see-also"></a>Zobacz też

- [Konwersje jawne i niejawne](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
