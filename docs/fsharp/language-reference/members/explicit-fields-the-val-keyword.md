---
title: 'Pola jawne: val — Słowo kluczowe'
description: 'Dowiedz się więcej o słowie kluczowym F # "Val", które jest używane do deklarowania lokalizacji do przechowywania wartości w typie klasy lub struktury bez inicjalizacji typu.'
ms.date: 08/15/2020
ms.openlocfilehash: 9f5599a241f27b234eeacf48327b4ccbc46ed38c
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811785"
---
# <a name="explicit-fields-the-val-keyword"></a>Pola jawne: val — Słowo kluczowe

`val`Słowo kluczowe jest używane do deklarowania lokalizacji do przechowywania wartości w typie klasy lub struktury, bez jej inicjalizacji. Lokalizacje magazynu zadeklarowane w ten sposób są nazywane *jawnymi polami*. Inne użycie `val` słowa kluczowego jest w połączeniu ze `member` słowem kluczowym w celu zadeklarować właściwości, która jest implementowana. Aby uzyskać więcej informacji na temat właściwości, które są implementowane, zobacz [Właściwości](properties.md).

## <a name="syntax"></a>Składnia

```fsharp
val [ mutable ] [ access-modifier ] field-name : type-name
```

## <a name="remarks"></a>Uwagi

Typowym sposobem definiowania pól w klasie lub typie struktury jest użycie `let` powiązania. Jednakże `let` powiązania muszą być zainicjowane jako część konstruktora klasy, co nie zawsze jest możliwe, konieczne lub pożądane. Możesz użyć `val` słowa kluczowego, gdy chcesz, aby pole, które jest niezainicjowane.

Jawne pola mogą być statyczne lub niestatyczne. *Modyfikatorem dostępu* może być `public` , `private` , lub `internal` . Domyślnie jawne pola są publiczne. Różni się to od `let` powiązań w klasach, które są zawsze prywatne.

Atrybut [DefaultValue](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-defaultvalueattribute.html) jest wymagany w jawnych polach w typach klas, które mają Konstruktor podstawowy. Ten atrybut określa, że pole jest inicjowane na wartość zero. Typ pola musi obsługiwać inicjowanie o wartości zero. Typ obsługuje Inicjowanie zero, jeśli jest jedną z następujących:

- Typ pierwotny, który ma wartość zerową.
- Typ, który obsługuje wartość null, jako wartość normalną, jako wartość nietypową lub jako reprezentację wartości. Obejmuje to klasy, krotki, rekordy, funkcje, interfejsy, typy odwołań platformy .NET, `unit` Typ i typy Unii rozłącznych.
- Typ wartości .NET.
- Struktura, której pola wszystkie obsługują domyślną wartość zerową.

Na przykład niezmienne pole o nazwie `someField` ma pole zapasowe w skompilowanej reprezentacji .NET o nazwie `someField@` i uzyskuje dostęp do przechowywanej wartości przy użyciu właściwości o nazwie `someField` .

W przypadku pola modyfikowalnego skompilowana reprezentacja .NET jest polem platformy .NET.

> [!WARNING]
> Przestrzeń nazw .NET Framework `System.ComponentModel` zawiera atrybut, który ma taką samą nazwę. Informacje o tym atrybucie można znaleźć w temacie <xref:System.ComponentModel.DefaultValueAttribute> .

Poniższy kod przedstawia użycie jawnych pól i, w przypadku porównania, `let` powiązanie w klasie, która ma Konstruktor podstawowy. Zwróć uwagę, że `let` pole-powiązane `myInt1` jest prywatne. Gdy `let` odwołanie do pola `myInt1` jest powiązane z metody składowej, jego identyfikator samodzielny `this` nie jest wymagany. Ale w przypadku odwoływania się do jawnych pól `myInt2` i `myString` , wymagany jest sam identyfikator.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6701.fs)]

Wynik jest następujący:

```console
11 12 abc
30 def
```

Poniższy kod przedstawia użycie jawnych pól w klasie, która nie ma konstruktora podstawowego. W tym przypadku `DefaultValue` atrybut nie jest wymagany, ale wszystkie pola muszą być zainicjowane w konstruktorach, które są zdefiniowane dla tego typu.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6702.fs)]

Wynik to `35 22`.

Poniższy kod przedstawia użycie jawnych pól w strukturze. Ponieważ struktura jest typem wartości, automatycznie ma Konstruktor bez parametrów, który ustawia wartości pól na zero. W związku z tym `DefaultValue` atrybut nie jest wymagany.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6703.fs)]

Wynik to `11 xyz`.

**Uważaj**, jeśli zamierzasz zainicjować strukturę przy użyciu `mutable` pól bez `mutable` słowa kluczowego, przypisania będą działać na kopii struktury, która zostanie odrzucona po przypisaniu. W związku z tym struktura nie ulegnie zmianie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6704.fs)]

Jawne pola nie są przeznaczone do rutynowego użycia. Ogólnie rzecz biorąc, gdy jest to możliwe, należy użyć `let` powiązania w klasie zamiast pola jawnego. Jawne pola są przydatne w niektórych scenariuszach współdziałania, na przykład w sytuacji, gdy trzeba zdefiniować strukturę, która będzie używana w wywołaniu wywołania platformy do natywnego interfejsu API lub w scenariuszach międzyoperacyjnych modelu COM. Aby uzyskać więcej informacji, zobacz [funkcje zewnętrzne](../functions/external-functions.md). Inną sytuacją, w której jawne pole może być konieczne, jest to, że podczas pracy z generatorem kodu języka F #, który emituje klasy bez konstruktora podstawowego. Jawne pola są również przydatne w przypadku zmiennych statycznych wątków lub podobnych konstrukcji. Aby uzyskać więcej informacji, zobacz `System.ThreadStaticAttribute`.

Gdy słowa kluczowe `member val` są wyświetlane razem w definicji typu, jest to definicja automatycznie implementowanej właściwości. Aby uzyskać więcej informacji, zobacz [Właściwości](properties.md).

## <a name="see-also"></a>Zobacz też

- [Właściwości](properties.md)
- [Elementy członkowskie](index.md)
- [`let` Powiązania w klasach](let-bindings-in-classes.md)
