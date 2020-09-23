---
title: 'Porady: określanie, czy dwa obiekty są powiązane'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b33815d58b0ef40f7f75a6a41bb4b1eeef591859
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072226"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Porady: określanie, czy dwa obiekty są powiązane (Visual Basic)

Można porównać dwa obiekty, aby określić relację, jeśli istnieje, między klasami, z których zostały utworzone. <xref:System.Type.IsInstanceOfType%2A>Metoda <xref:System.Type?displayProperty=nameWithType> klasy zwraca `True` , jeśli określona klasa dziedziczy z bieżącej klasy lub jeśli bieżący typ jest interfejsem obsługiwanym przez określoną klasę.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Aby określić, czy jeden obiekt dziedziczy z klasy lub interfejsu innego obiektu

1. Na obiekcie, który sądzisz, może być typu podstawowego, wywołaj <xref:System.Object.GetType%2A> metodę.

2. Dla <xref:System.Type?displayProperty=nameWithType> obiektu zwróconego przez <xref:System.Object.GetType%2A> , wywołaj <xref:System.Type.IsInstanceOfType%2A> metodę.

3. Na liście argumentów dla <xref:System.Type.IsInstanceOfType%2A> Określ obiekt, który może być typem pochodnym.

    <xref:System.Type.IsInstanceOfType%2A> Zwraca wartość, `True` Jeśli jej typ argumentu dziedziczy z <xref:System.Type?displayProperty=nameWithType> typu obiektu.

## <a name="example"></a>Przykład

 Poniższy przykład określa, czy jeden obiekt reprezentuje klasę pochodzącą od klasy innego obiektu.

```vb
Public Class baseClass
End Class
Public Class derivedClass : Inherits baseClass
End Class
Public Class testTheseClasses
    Public Sub seeIfRelated()
        Dim baseObj As Object = New baseClass()
        Dim derivedObj As Object = New derivedClass()
        Dim related As Boolean
        related = baseObj.GetType().IsInstanceOfType(derivedObj)
        MsgBox(CStr(related))
    End Sub
End Class
```

Zwróć uwagę na nieoczekiwane rozmieszczenie dwóch zmiennych obiektów w wywołaniu <xref:System.Type.IsInstanceOfType%2A> . Przypuszczalny typ podstawowy jest używany do generowania <xref:System.Type?displayProperty=nameWithType> klasy, a typ pochodny jest przenoszona jako argument do <xref:System.Type.IsInstanceOfType%2A> metody.

## <a name="see-also"></a>Zobacz także

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object — typ danych](../../../language-reference/data-types/object-data-type.md)
- [Zmienne obiektów](object-variables.md)
- [Wartości zmiennej obiektu](object-variable-values.md)
- [Porady: określanie, czy dwa obiekty są jednakowe](how-to-determine-whether-two-objects-are-identical.md)
