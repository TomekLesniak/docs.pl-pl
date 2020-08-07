---
title: Operatory powiązane ze wskaźnikiem — odwołanie w C#
description: Dowiedz się więcej na temat operatorów języka C#, których można używać podczas pracy ze wskaźnikami.
ms.date: 05/20/2019
author: pkulikov
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- pointer related operators [C#]
- address-of operator [C#]
- '& operator [C#]'
- pointer indirection operator [C#]
- dereference operator [C#]
- '* operator [C#]'
- pointer member access operator [C#]
- -> operator [C#]
- pointer element access [C#]
- '[] operator [C#]'
- pointer arithmetic [C#]
- pointer increment [C#]
- pointer decrement [C#]
- pointer comparison [C#]
ms.openlocfilehash: 3728778b31a4b4adc51933e8fdc6287f28e03d83
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916715"
---
# <a name="pointer-related-operators-c-reference"></a>Operatory pokrewne wskaźnika (odwołanie w C#)

Można użyć następujących operatorów do pracy ze wskaźnikami:

- Operator jednoargumentowy [ `&` (Address-of)](#address-of-operator-) : Aby uzyskać adres zmiennej
- Operator jednoargumentowy [ `*` (pośredni wskaźnik)](#pointer-indirection-operator-) : Aby uzyskać zmienną wskazywaną przez wskaźnik
- Operatory [ `->` (dostęp do elementów członkowskich)](#pointer-member-access-operator--) i [ `[]` (dostęp do elementów)](#pointer-element-access-operator-)
- Operatory arytmetyczne [ `+` , `-` , `++` i `--` ](#pointer-arithmetic-operators)
- Operatory porównania,,,, [ `==` `!=` `<` `>` `<=` i `>=` ](#pointer-comparison-operators)

Aby uzyskać informacje na temat typów wskaźnikowych, zobacz [typy wskaźnika](../../programming-guide/unsafe-code-pointers/pointer-types.md).

> [!NOTE]
> Wszystkie operacje ze wskaźnikami wymagają [niebezpiecznego](../keywords/unsafe.md) kontekstu. Kod, który zawiera niebezpieczne bloki, musi być skompilowany przy użyciu [`-unsafe`](../compiler-options/unsafe-compiler-option.md) opcji kompilatora.

## <a name="address-of-operator-amp"></a><a name="address-of-operator-"></a>Operator address-of&amp;

Operator jednoargumentowy `&` zwraca adres tego operandu:

[!code-csharp[address of local](snippets/shared/PointerOperators.cs#AddressOf)]

Operand `&` operatora musi być zmienną stałą. Zmienne *stałe* są zmiennymi, które znajdują się w lokalizacjach magazynu, które nie mają wpływ na działanie [modułu wyrzucania elementów bezużytecznych](../../../standard/garbage-collection/index.md). W poprzednim przykładzie zmienna lokalna `number` to stała zmienna, ponieważ znajduje się ona na stosie. Zmienne, które znajdują się w lokalizacjach magazynu, na które może mieć wpływ Moduł wyrzucania elementów bezużytecznych (na przykład rezlokalizowane), *są nazywane* zmiennymi zmiennych. Pola obiektów i elementy tablicy to przykłady ruchomych zmiennych. Adres ruchomej zmiennej można pobrać, jeśli "Napraw" lub "PIN", za pomocą [ `fixed` instrukcji](../keywords/fixed-statement.md). Uzyskany adres jest prawidłowy tylko wewnątrz bloku `fixed` instrukcji. Poniższy przykład pokazuje, jak używać `fixed` instrukcji i `&` operatora:

[!code-csharp[address of fixed](snippets/shared/PointerOperators.cs#AddressOfFixed)]

Nie można uzyskać adresu stałej ani wartości.

Aby uzyskać więcej informacji na temat zmiennych stałych i przenośnych, zobacz sekcję [zmienne stałe i ruchome](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

Operator binarny `&` oblicza wartość [logiczną i](boolean-logical-operators.md#logical-and-operator-) jej operandy logiczne oraz [koniunkcję bitową i](bitwise-and-shift-operators.md#logical-and-operator-) jej całkowite argumenty operacji.

## <a name="pointer-indirection-operator-"></a>Operator pośredni wskaźnika *

Operator operatora bezoperatorowego pośredni `*` uzyskuje zmienną, do której odwołuje się argument operacji. Jest on również znany jako operator dereferencji. Operand `*` operatora musi być typu wskaźnika.

[!code-csharp[pointer indirection](snippets/shared/PointerOperators.cs#PointerIndirection)]

Nie można zastosować `*` operatora do wyrażenia typu `void*` .

Operator binarny `*` oblicza [iloczyn](arithmetic-operators.md#multiplication-operator-) argumentów liczbowych.

## <a name="pointer-member-access-operator--"></a>Operator dostępu do elementów członkowskich wskaźnika — >

`->`Operator łączy [pośredni wskaźnik](#pointer-indirection-operator-) i [dostęp do elementów członkowskich](member-access-operators.md#member-access-expression-). Oznacza to, że jeśli `x` jest wskaźnikiem typu `T*` i `y` jest dostępnym elementem członkowskim typu `T` , wyrażenie formularza

```csharp
x->y
```

jest równoważny

```csharp
(*x).y
```

Poniższy przykład ilustruje użycie `->` operatora:

[!code-csharp[pointer member access](snippets/shared/PointerOperators.cs#MemberAccess)]

Nie można zastosować `->` operatora do wyrażenia typu `void*` .

## <a name="pointer-element-access-operator-"></a>Operator dostępu do elementów wskaźnika []

Dla wyrażenia `p` typu wskaźnika dostęp do elementu wskaźnika `p[n]` jest oceniany jako `*(p + n)` , gdzie `n` musi być typem niejawnie konwertowanym na `int` , `uint` , `long` , lub `ulong` . Aby uzyskać informacje o zachowaniu `+` operatora ze wskaźnikami, zobacz [Dodawanie lub odejmowanie wartości całkowitej do lub z sekcji wskaźnika](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) .

W poniższym przykładzie pokazano, jak uzyskać dostęp do elementów tablicy za pomocą wskaźnika i `[]` operatora:

[!code-csharp[pointer element access](snippets/shared/PointerOperators.cs#ElementAccess)]

W poprzednim przykładzie [ `stackalloc` wyrażenie](stackalloc.md) przydziela blok pamięci na stosie.

> [!NOTE]
> Operator dostępu do elementów wskaźnika nie sprawdza występowania błędów poza granicami.

Nie można użyć `[]` do uzyskania dostępu do elementu wskaźnika z wyrażeniem typu `void*` .

Można również użyć `[]` operatora dla [elementu tablicy lub dostępu indeksatora](member-access-operators.md#indexer-operator-).

## <a name="pointer-arithmetic-operators"></a>Operatory arytmetyczne wskaźnika

Za pomocą wskaźników można wykonywać następujące operacje arytmetyczne:

- Dodaj lub Odejmij wartość całkowitą do lub ze wskaźnika
- Odejmij dwa wskaźniki
- Zwiększ lub Zmniejsz wskaźnik

Nie można wykonać tych operacji ze wskaźnikami typu `void*` .

Aby uzyskać informacje o obsługiwanych operacjach arytmetycznych o typach liczbowych, zobacz [Operatory arytmetyczne](arithmetic-operators.md).

### <a name="addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer"></a>Dodanie lub odjęcie wartości całkowitej do lub ze wskaźnika

Dla wskaźnika `p` typu `T*` i wyrażenia `n` typu niejawnie konwertowany na `int` , `uint` , `long` , lub `ulong` , Dodawanie i odejmowanie są zdefiniowane w następujący sposób:

- Oba `p + n` i `n + p` wyrażenia tworzą wskaźnik typu `T*` , który wynika z dodania `n * sizeof(T)` do adresu podanego przez `p` .
- `p - n`Wyrażenie generuje wskaźnik typu `T*` , który wynika z odejmowania `n * sizeof(T)` od adresu podanych przez `p` .

[ `sizeof` Operator](sizeof.md) uzyskuje rozmiar typu w bajtach.

Poniższy przykład ilustruje użycie `+` operatora ze wskaźnikiem:

[!code-csharp[pointer addition](snippets/shared/PointerOperators.cs#AddNumber)]

### <a name="pointer-subtraction"></a>Odejmowanie wskaźnika

W przypadku dwóch wskaźników `p1` i `p2` typu `T*` wyrażenie `p1 - p2` tworzy różnicę między adresami podaną przez `p1` i `p2` podzieloną przez `sizeof(T)` . Typ wyniku to `long` . Oznacza to, że `p1 - p2` jest obliczana jako `((long)(p1) - (long)(p2)) / sizeof(T)` .

Poniższy przykład ilustruje odejmowanie wskaźnika:

[!code-csharp[pointer subtraction](snippets/shared/PointerOperators.cs#SubtractPointers)]

### <a name="pointer-increment-and-decrement"></a>Zwiększenie i zmniejszenie wskaźnika

`++`Operator przyrostu [dodaje](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 do jego operandu wskaźnika. `--`Operator zmniejszania [odejmuje](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 od jego operandu wskaźnika.

Oba operatory są obsługiwane w dwóch formach: przyrostka ( `p++` i `p--` ) oraz prefiks ( `++p` i `--p` ). Wynik `p++` i `p--` jest wartością `p` *przed* operacją. Wynik `++p` i `--p` jest wartością `p` *po* operacji.

W poniższym przykładzie przedstawiono zachowanie operatorów przyrostu przyrostkowego i powiększania:

[!code-csharp[pointer increment](snippets/shared/PointerOperators.cs#Increment)]

## <a name="pointer-comparison-operators"></a>Operatory porównania wskaźnika

`==` `!=` Operatory,,,, i służą `<` `>` `<=` `>=` do porównywania operandów dowolnego typu wskaźnika, w tym `void*` . Te operatory porównują adresy podane przez dwa operandy, tak jakby były to liczby całkowite bez znaku.

Aby uzyskać informacje o zachowaniu tych operatorów dla operandów innych typów, zobacz artykuły [Operatory równości](equality-operators.md) i [Operatory porównania](comparison-operators.md) .

## <a name="operator-precedence"></a>Pierwszeństwo operatorów

Poniższa lista kolejności pokrewnych operatorów, rozpoczynając od najwyższego priorytetu do najniższego:

- Operatory przyrostka i zmniejszanie przyrostkowe oraz `x++` `x--` `->` `[]` Operatory i
- Operatory przyrostu `++x` i zmniejszania prefiksu oraz `--x` `&` `*` Operatory i
- Dodatek `+` i `-` Operatory
- Porównanie `<` , `>` , `<=` i `>=` Operatory
- Równość `==` i `!=` Operatory

Użyj nawiasów, `()` , aby zmienić kolejność oceny nałożona przez pierwszeństwo operatorów.

Aby uzyskać pełną listę operatorów języka C# uporządkowanych według poziomu pierwszeństwa, zobacz sekcję [pierwszeństwo](index.md#operator-precedence) operatorów w artykule [operatory języka c#](index.md) .

## <a name="operator-overloadability"></a>Przeciążanie operatora

Typ zdefiniowany przez użytkownika nie może przeciążać operatorów powiązanych ze wskaźnikiem, `&` `*` , `->` i `[]` .

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):

- [Zmienne stałe i ruchome](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)
- [Operator address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)
- [Pośredni wskaźnik](~/_csharplang/spec/unsafe-code.md#pointer-indirection)
- [Dostęp do elementu członkowskiego wskaźnika](~/_csharplang/spec/unsafe-code.md#pointer-member-access)
- [Dostęp do elementu wskaźnika](~/_csharplang/spec/unsafe-code.md#pointer-element-access)
- [Arytmetyczny wskaźnik](~/_csharplang/spec/unsafe-code.md#pointer-arithmetic)
- [Zwiększenie i zmniejszenie wskaźnika](~/_csharplang/spec/unsafe-code.md#pointer-increment-and-decrement)
- [Porównanie wskaźników](~/_csharplang/spec/unsafe-code.md#pointer-comparison)

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [Typy wskaźnika](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [unsafe — słowo kluczowe](../keywords/unsafe.md)
- [FIXED — słowo kluczowe](../keywords/fixed-statement.md)
- [stackalloc](stackalloc.md)
- [sizeof — Operator](sizeof.md)
