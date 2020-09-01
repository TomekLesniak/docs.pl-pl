---
description: Ograniczenia dotyczące używania poziomów ułatwień dostępu — Dokumentacja języka C#
title: Ograniczenia dotyczące używania poziomów ułatwień dostępu — Dokumentacja języka C#
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 542e463e41c70f2e8aed5c20dc1294e296a88518
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137004"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a>Ograniczenia dotyczące używania poziomów ułatwień dostępu (odwołanie w C#)

Po określeniu typu w deklaracji Sprawdź, czy poziom dostępności tego typu jest zależny od poziomu dostępności elementu członkowskiego lub innego typu. Na przykład bezpośrednia klasa bazowa musi być co najmniej równa dostępności jako Klasa pochodna. Następujące deklaracje powodują wystąpienie błędu kompilatora, ponieważ klasa bazowa `BaseClass` jest mniej dostępna niż `MyClass` :

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

Poniższa tabela zawiera podsumowanie ograniczeń dotyczących deklarowanych poziomów dostępności.

|Kontekst|Uwagi|
|-------------|-------------|
|[Klasy](../../programming-guide/classes-and-structs/classes.md)|Bezpośrednia klasa bazowa typu klasy musi być co najmniej równa dostępności jako samego typu klasy.|
|[Interfejsy](../../programming-guide/interfaces/index.md)|Jawne interfejsy podstawowe typu interfejsu muszą być co najmniej takie same jak typ interfejsu.|
|[Delegaci](../../programming-guide/delegates/index.md)|Typ zwracany i typy parametrów typu delegata muszą być co najmniej tak samo jak typ delegata.|
|[Stałe](../../programming-guide/classes-and-structs/constants.md)|Typ stałej musi być co najmniej tak samo jak jako stała.|
|[Pola](../../programming-guide/classes-and-structs/fields.md)|Typ pola musi być co najmniej tak samo jak w przypadku samego pola.|
|[Metody](../../programming-guide/classes-and-structs/methods.md)|Typ zwracany i typy parametrów metody muszą być co najmniej tak samo samo jak metoda.|
|[Właściwości](../../programming-guide/classes-and-structs/properties.md)|Typ właściwości musi być co najmniej taki sam jak wartość właściwości.|
|[Zdarzenia](../../programming-guide/events/index.md)|Typ zdarzenia musi być co najmniej tak samo jak w przypadku samego zdarzenia.|
|[Indeksatory](../../programming-guide/indexers/index.md)|Typ i typy parametrów indeksatora muszą być co najmniej tak samo dostępne jak indeksator.|
|[Operatory](../operators/index.md)|Typ zwracany i typy parametrów operatora muszą być co najmniej takie same jak dla samego operatora.|
|[Konstruktory](../../programming-guide/classes-and-structs/constructors.md)|Typy parametrów konstruktora muszą być co najmniej tak samo samo jak Konstruktor.|

## <a name="example"></a>Przykład

Poniższy przykład zawiera błędne deklaracje różnych typów. Komentarz po każdej deklaracji wskazuje oczekiwany błąd kompilatora.

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error:
    // "The parameter B.MyPrivateMethod is not accessible due to
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Modyfikatory dostępu](access-modifiers.md)
- [Domena ułatwień dostępu](accessibility-domain.md)
- [Poziomy ułatwień dostępu](accessibility-levels.md)
- [Modyfikatory dostępu](../../programming-guide/classes-and-structs/access-modifiers.md)
- [public](public.md)
- [private](private.md)
- [protected](protected.md)
- [internal](internal.md)
