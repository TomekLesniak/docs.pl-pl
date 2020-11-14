---
title: Interfejsy
description: 'Dowiedz się, jak interfejsy języka F # określają zestawy powiązanych elementów członkowskich, które są implementowane przez inne klasy.'
ms.date: 08/15/2020
ms.openlocfilehash: 0cef2932045dae401f5aa069107815543457ca4a
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557054"
---
# <a name="interfaces"></a>Interfejsy

*Interfejsy* określają zestawy powiązanych członków, które są implementowane przez inne klasy.

## <a name="syntax"></a>Składnia

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a>Uwagi

Deklaracje interfejsów przypominają deklaracje klas, z tą różnicą, że żaden element członkowski nie jest zaimplementowany. Zamiast tego wszystkie elementy członkowskie są abstrakcyjne, zgodnie ze wskazaniem słowa kluczowego `abstract` . Nie udostępniamy treści metody dla metod abstrakcyjnych. Można jednak podać domyślną implementację, uwzględniając także odrębną definicję elementu członkowskiego jako metodę razem ze `default` słowem kluczowym. Jest to równoznaczne z tworzeniem metody wirtualnej w klasie bazowej w innych językach .NET. Taka metoda wirtualna może zostać przesłonięta w klasach, które implementują interfejs.

Domyślnymi ułatwieniami dostępu dla interfejsów są `public` .

Opcjonalnie możesz nadać każdemu parametrowi metody nazwę przy użyciu standardowej składni F #:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

W powyższym `ISprintable` przykładzie `Print` Metoda ma jeden parametr typu `string` o nazwie `format` .

Istnieją dwa sposoby implementacji interfejsów: przy użyciu wyrażeń obiektów i typów klas. W obu przypadkach typ klasy lub wyrażenie obiektu zawiera treść metody dla abstrakcyjnych metod interfejsu. Implementacje są specyficzne dla każdego typu, który implementuje interfejs. W związku z tym metody interfejsu dla różnych typów mogą się różnić od siebie.

Słowa kluczowe `interface` i `end` , które oznaczają początek i koniec definicji, są opcjonalne w przypadku używania lekkiej składni. Jeśli nie używasz tych słów kluczowych, kompilator próbuje określić, czy typ jest klasą, czy interfejsem, analizując używane konstrukcje. Jeśli zdefiniujesz element członkowski lub użyjesz innej składni klasy, typ jest interpretowany jako Klasa.

Styl kodowania .NET polega na rozpoczęciu wszystkich interfejsów z stolicą `I` .

Można określić wiele parametrów na dwa sposoby: F #-styl i. Styl sieci. Oba te wersje zostaną skompilowane w taki sam sposób dla użytkowników platformy .NET, ale styl F # spowoduje wymuszenie wywoływania przez program F # aplikacji parametrów języka F # i. Styl sieci spowoduje wymuszenie wywoływania przez program F # wywołań aplikacji argumentu z krotką.

```fsharp
type INumeric1 =
    abstract Add: x: int -> y: int -> int

type INumeric2 =
    abstract Add: x: int * y: int -> int
```

## <a name="implementing-interfaces-by-using-class-types"></a>Implementowanie interfejsów przy użyciu typów klas

Można zaimplementować jeden lub więcej interfejsów w typie klasy za pomocą `interface` słowa kluczowego, nazwy interfejsu i `with` słowa kluczowego, a następnie definicji elementu członkowskiego interfejsu, jak pokazano w poniższym kodzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Implementacje interfejsu są dziedziczone, więc wszystkie klasy pochodne nie muszą ponownie wdrażać.

## <a name="calling-interface-methods"></a>Wywoływanie metod interfejsu

Metody interfejsu można wywoływać tylko za pomocą interfejsu, a nie za pomocą dowolnego obiektu typu, który implementuje interfejs. W ten sposób może być konieczne przerzutowanie na typ interfejsu za pomocą `:>` operatora lub `upcast` operatora w celu wywołania tych metod.

Aby wywołać metodę interfejsu, gdy masz obiekt typu `SomeClass` , należy przerzutować obiekt na typ interfejsu, jak pokazano w poniższym kodzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Alternatywą jest zadeklarowanie metody na obiekcie, który rzutuje i wywołuje metodę interfejsu, jak w poniższym przykładzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a>Implementowanie interfejsów przy użyciu wyrażeń obiektów

Wyrażenia obiektów zapewniają krótki sposób implementacji interfejsu. Są one przydatne, gdy nie trzeba tworzyć nazwanego typu, a ty chcesz tylko obiekt obsługujący metody interfejsu, bez żadnych dodatkowych metod. Wyrażenie obiektu jest zilustrowane w poniższym kodzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a>Dziedziczenie interfejsu

Interfejsy mogą dziedziczyć z jednego lub kilku interfejsów podstawowych.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="implementing-interfaces-with-default-implementations"></a>Implementowanie interfejsów z domyślnymi implementacjami

Język C# obsługuje definiowanie interfejsów z domyślnymi implementacjami, takich jak:

```csharp
using System;

namespace CSharp
{
    public interface MyDim
    {
        public int Z => 0;
    }
}
```

Są one bezpośrednio konsumowane w języku F #:

```fsharp
open CSharp

// You can implement the interface via a class
type MyType() =
    member _.M() = ()

    interface MyDim

let md = MyType() :> MyDim
printfn $"DIM from C#: %d{md.Z}"

// You can also implement it via an object expression
let md' = { new MyDim }
printfn $"DIM from C# but via Object Expression: %d{md'.Z}"
```

Można zastąpić domyślną implementację, na `override` przykład zastępując dowolny wirtualny element członkowski.

Wszystkie elementy członkowskie w interfejsie, które nie mają implementacji domyślnej, muszą być nadal jawnie zaimplementowane.

## <a name="implementing-the-same-interface-at-different-generic-instantiations"></a>Implementowanie tego samego interfejsu w różnych wystąpieniach ogólnych

Język F # obsługuje implementowanie tego samego interfejsu w różnych wystąpieniach ogólnych, takich jak:

```fsharp
type IA<'T> =
    abstract member Get : unit -> 'T

type MyClass() =
    interface IA<int> with
        member x.Get() = 1
    interface IA<string> with
        member x.Get() = "hello"

let mc = MyClass()
let iaInt = mc :> IA<int>
let iaString = mc :> IA<string>

iaInt.Get() // 1
iaString.Get() // "hello"
```

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
- [Wyrażenia obiektów](object-expressions.md)
- [Klasy](classes.md)
