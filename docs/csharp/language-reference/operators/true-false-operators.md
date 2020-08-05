---
title: Operatory true i false — odwołanie w C#
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: efba2c1c921d867725db90a1879cc9dee1a22b4e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555524"
---
# <a name="true-and-false-operators-c-reference"></a>Operatory true i false (odwołanie w C#)

`true`Operator zwraca wartość [logiczną](../builtin-types/bool.md) , `true` Aby wskazać, że jej operand ma wartość true. `false`Operator zwraca `bool` wartość `true` , aby wskazać, że jej argument operacji ma co najsamym wartość false. `true`Operatory i `false` nie są gwarantowane do uzupełniania siebie nawzajem. Oznacza to, że `true` operator i `false` może zwracać `bool` wartość dla tego `false` samego operandu. Jeśli typ definiuje jeden z dwóch operatorów, musi także definiować innego operatora.

> [!TIP]
> Użyj tego `bool?` typu, jeśli musisz obsługiwać logikę o trzech wartościach (na przykład podczas pracy z bazami danych, które obsługują wartość typu Boolean o wartości 3). Język C# zawiera `&` `|` Operatory i, które obsługują logikę trzykrotną z `bool?` argumentami operacji. Aby uzyskać więcej informacji, zobacz sekcję [Operatory logiczne wartości null](boolean-logical-operators.md#nullable-boolean-logical-operators) w artykule [Operatory logiczne Boolean](boolean-logical-operators.md) .

## <a name="boolean-expressions"></a>Wyrażenia logiczne

Typ ze zdefiniowanym `true` operatorem może być typem wyniku kontrolnego wyrażenia warunkowego w instrukcji [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md)i [for](../keywords/for.md) , a w [operatorze `?:` warunkowym ](conditional-operator.md). Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia logiczne](~/_csharplang/spec/expressions.md#boolean-expressions) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="user-defined-conditional-logical-operators"></a>Operatory logiczne warunkowe zdefiniowane przez użytkownika

Jeśli typ ze zdefiniowanymi `true` `false` operatorami i operatory [przeciążą](operator-overloading.md) [operatora logicznego](boolean-logical-operators.md#logical-or-operator-) or `|` lub [operatora logicznego and](boolean-logical-operators.md#logical-and-operator-) `&` w określony sposób, [warunkowego operatora logicznego](boolean-logical-operators.md#conditional-logical-or-operator-) or lub warunkowego operatora logicznego OR `||` [conditional logical AND operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` , można obliczyć odpowiednio dla operandów tego typu. Aby uzyskać więcej informacji, zapoznaj się z sekcją wyrażenia [warunkowe operatory logiczne zdefiniowane przez użytkownika](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="example"></a>Przykład

Poniższy przykład przedstawia typ, który definiuje `true` `false` Operatory i. Typ również przeciąża operatora logicznego i `&` w taki sposób, że `&&` operator może również być obliczany dla operandów tego typu.

[!code-csharp[true and false operators example](snippets/TrueFalseOperators.cs)]

Zwróć uwagę na zachowanie w krótkim obwodzie `&&` operatora. Gdy `GetFuelLaunchStatus` Metoda zwraca `LaunchStatus.Red` , `&&` nie jest oceniane prawo operandu operatora. Oznacza to, że `LaunchStatus.Red` jest to wartość false. Następnie wynik logiczny i nie zależy od wartości operandu po prawej stronie. Dane wyjściowe przykładu są następujące:

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
