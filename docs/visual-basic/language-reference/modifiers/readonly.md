---
title: ReadOnly
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 3ca322da4e5f0edcbe12bf29bded863daabffe3d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867703"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)

Określa, że zmienna lub właściwość może być odczytana, ale nie zapisywana.

## <a name="remarks"></a>Uwagi

## <a name="rules"></a>Reguły

- **Kontekst deklaracji.** Można używać `ReadOnly` tylko na poziomie modułu. Oznacza to, że kontekst deklaracji dla `ReadOnly` elementu musi być klasą, strukturą lub modułem, i nie może być plikiem źródłowym, przestrzenią nazw ani procedurą.

- **Połączone modyfikatory.** Nie można określić `ReadOnly` razem z `Static` w tej samej deklaracji.

- **Przypisywanie wartości.** Kod zużywający `ReadOnly` Właściwość nie może mieć ustawionej wartości. Jednak kod, który ma dostęp do magazynu bazowego, może przypisywać lub zmieniać wartość w dowolnym momencie.

     Można przypisać wartość do `ReadOnly` zmiennej tylko w swojej deklaracji lub w konstruktorze klasy lub struktury, w której jest zdefiniowana.

## <a name="when-to-use-a-readonly-variable"></a>Kiedy używać zmiennej tylko do odczytu

Istnieją sytuacje, w których nie można użyć [instrukcji const](../statements/const-statement.md) do zadeklarowania i przypisania wartości stałej. Na przykład `Const` instrukcja może nie akceptować typu danych, który chcesz przypisać, lub nie można obliczyć wartości w czasie kompilacji przy użyciu wyrażenia stałej. Wartość w czasie kompilacji może nie być jeszcze znana. W takich przypadkach można użyć `ReadOnly` zmiennej do przechowywania wartości stałej.

> [!IMPORTANT]
> Jeśli typ danych zmiennej jest typem referencyjnym, takim jak tablica lub wystąpienie klasy, jego elementy członkowskie można zmienić, nawet jeśli sama zmienna jest `ReadOnly` . Ilustruje to poniższy przykład.

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

Po zainicjowaniu tablica wskazywana przez `characterArray()` zawiera wartości "x", "y" i "z". Ponieważ zmienna `characterArray` to `ReadOnly` , nie można zmienić jej wartości, gdy jest ona zainicjowana; oznacza to, że nie można przypisać do niej nowej tablicy. Można jednak zmienić wartości co najmniej jednego elementu członkowskiego tablicy. Po wywołaniu procedury `ChangeArrayElement` Tablica wskazywana przez `characterArray()` posiada "x", "M" i "z".

Należy zauważyć, że jest to podobne do deklarowania parametru procedury jako [ByVal](byval.md), co uniemożliwia procedury zmiany argumentu wywołującego, ale pozwala na zmianę jego elementów członkowskich.

## <a name="example"></a>Przykład

W poniższym przykładzie zdefiniowano `ReadOnly` Właściwość dla daty zatrudnienia pracownika. Klasa przechowuje wartość właściwości wewnętrznie jako `Private` zmienną i tylko kod wewnątrz klasy może zmienić tę wartość. Jednak właściwość jest `Public` , a każdy kod, który może uzyskać dostęp do klasy, może odczytać właściwość.

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

`ReadOnly`Modyfikator może być używany w tych kontekstach:

- [Dim, instrukcja](../statements/dim-statement.md)
- [Property — Instrukcja](../statements/property-statement.md)

## <a name="see-also"></a>Zobacz też

- [WriteOnly](writeonly.md)
- [Słowa kluczowe](../keywords/index.md)
