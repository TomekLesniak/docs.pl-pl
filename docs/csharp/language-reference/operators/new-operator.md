---
description: New — odwołanie w C#
title: New — odwołanie w C#
ms.date: 10/02/2020
f1_keywords:
- new_CSharpKeyword
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 3125f3d2c694dcfc5682ee482f3f76072ac3726d
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609385"
---
# <a name="new-operator-c-reference"></a>New — Operator (odwołanie w C#)

`new`Operator tworzy nowe wystąpienie typu.

Można również użyć `new` słowa kluczowego jako [modyfikatora deklaracji składowej](../keywords/new-modifier.md) lub [ograniczenia typu ogólnego](../keywords/new-constraint.md).

## <a name="constructor-invocation"></a>Wywołanie konstruktora

Aby utworzyć nowe wystąpienie typu, zazwyczaj wywoływany jest jeden z [konstruktorów](../../programming-guide/classes-and-structs/constructors.md) tego typu przy użyciu `new` operatora:

[!code-csharp-interactive[invoke constructor](snippets/shared/NewOperator.cs#Constructor)]

Można użyć [inicjatora obiektu lub kolekcji](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) z `new` operatorem, aby utworzyć wystąpienie i zainicjować obiekt w jednej instrukcji, jak pokazano w poniższym przykładzie:

[!code-csharp-interactive[constructor with initializer](snippets/shared/NewOperator.cs#ConstructorWithInitializer)]

Począwszy od języka C# 9,0, wyrażenia wywołania konstruktora mają typ docelowy. Oznacza to, że jeśli jest znany typ docelowy wyrażenia, można pominąć nazwę typu, jak pokazano na poniższym przykładzie:

:::code language="csharp" source="snippets/shared/NewOperator.cs" id="SnippetTargetTyped":::

Jak pokazano w powyższym przykładzie, zawsze używaj nawiasów w wyrażeniu z typem docelowym `new` .

Jeśli typ docelowy `new` wyrażenia jest nieznany (na przykład w przypadku użycia [`var`](../keywords/var.md) słowa kluczowego), należy określić nazwę typu.

## <a name="array-creation"></a>Tworzenie tablicy

Możesz również użyć `new` operatora, aby utworzyć wystąpienie tablicy, jak pokazano w poniższym przykładzie:

[!code-csharp-interactive[create array](snippets/shared/NewOperator.cs#Array)]

Użyj składni inicjowania tablicy, aby utworzyć wystąpienie tablicy i wypełnić je elementami w jednej instrukcji. W poniższym przykładzie pokazano różne sposoby wykonywania następujących czynności:

[!code-csharp-interactive[initialize array](snippets/shared/NewOperator.cs#ArrayInitialization)]

Aby uzyskać więcej informacji na temat tablic, zobacz [tablice](../../programming-guide/arrays/index.md).

## <a name="instantiation-of-anonymous-types"></a>Tworzenie wystąpienia typów anonimowych

Aby utworzyć wystąpienie [typu anonimowego](../../programming-guide/classes-and-structs/anonymous-types.md), użyj `new` składni operatora i inicjatora obiektów:

[!code-csharp-interactive[anonymous type](snippets/shared/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a>Niszczenie wystąpień typu

Nie trzeba zniszczyć wcześniej utworzonych wystąpień typu. Wystąpienia obu typów odwołań i wartości są niszczone automatycznie. Wystąpienia typów wartości są niszczone, gdy tylko kontekst, który zawiera te elementy, zostanie zniszczony. Wystąpienia typów odwołań są niszczone przez [Moduł wyrzucania elementów bezużytecznych](../../../standard/garbage-collection/index.md) w nieokreślonym czasie po usunięciu ostatniego odwołania do nich.

Dla wystąpień typu, które zawierają niezarządzane zasoby, na przykład dojście do pliku, zaleca się zapełnienie deterministycznym czyszczeniem, aby upewnić się, że zasoby, które zawierają, są wystawione tak szybko, jak to możliwe. Aby uzyskać więcej informacji, zobacz <xref:System.IDisposable?displayProperty=nameWithType> Dokumentacja interfejsu API i artykuł [using instrukcji](../keywords/using-statement.md) .

## <a name="operator-overloadability"></a>Przeciążanie operatora

Typ zdefiniowany przez użytkownika nie może przeciążać `new` operatora.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [New Operator](~/_csharplang/spec/expressions.md#the-new-operator) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

Aby uzyskać więcej informacji na temat wyrażenia z określonym typem docelowym `new` , zobacz [Uwaga dotycząca oferty funkcji](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [Inicjatory obiektów i kolekcji](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
