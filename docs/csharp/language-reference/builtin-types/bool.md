---
title: Typ bool — odwołanie w C#
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
- "true"
- "false"
- true_CSharpKeyword
- false_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 4623dc7d6c8c6c437c78aee45f0eeee8a92e3200
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854883"
---
# <a name="bool-c-reference"></a>bool (odwołanie w C#)

`bool`Słowo kluczowe type jest aliasem dla <xref:System.Boolean?displayProperty=nameWithType> typu struktury .NET, który reprezentuje wartość logiczną, która może być albo `true` `false` .

Aby wykonać operacje logiczne z wartościami `bool` typu, użyj logicznych operatorów [logicznych](../operators/boolean-logical-operators.md) . `bool`Typ jest typem wyniku [porównania](../operators/comparison-operators.md) i operatory [równości](../operators/equality-operators.md) . `bool`Wyrażenie może być wyrażeniem warunkowym sterującym w instrukcjach [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md)i [for](../keywords/for.md) oraz w [operatorze `?:` warunkowym ](../operators/conditional-operator.md).

Wartość domyślna `bool` typu to `false` .

## <a name="literals"></a>Literały

Można użyć `true` `false` literałów i, aby zainicjować `bool` zmienną lub przekazać `bool` wartość:

[!code-csharp-interactive[bool literals](snippets/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a>Logika logiczna z trzema wartościami

Użyj typu dopuszczającego wartość null `bool?` , jeśli potrzebujesz obsługi logiki trójwarstwowej, na przykład podczas pracy z bazami danych, które obsługują typ Boolean o wartości 3. W przypadku `bool?` operandów wstępnie zdefiniowane `&` Operatory i `|` obsługują logikę z trzema wartościami. Aby uzyskać więcej informacji, zobacz sekcję [Operatory logiczne wartości null](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) w artykule [Operatory logiczne Boolean](../operators/boolean-logical-operators.md) .

Aby uzyskać więcej informacji na temat typów wartości null, zobacz [dopuszczanie typów wartości null](nullable-value-types.md).

## <a name="conversions"></a>Konwersje

Język C# zawiera tylko dwie konwersje, które obejmują `bool` Typ. Są to niejawne konwersje do odpowiedniego typu dopuszczającego wartość null `bool?` i jawnej konwersji z `bool?` typu. Jednak platforma .NET udostępnia dodatkowe metody, których można użyć do przekonwertowania na typ lub z tego `bool` typu. Aby uzyskać więcej informacji, zobacz sekcję [konwertowanie do i z wartości logicznych](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) na <xref:System.Boolean?displayProperty=nameWithType> stronie Dokumentacja interfejsu API.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [Typ bool](~/_csharplang/spec/types.md#the-bool-type) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Typy wartości](value-types.md)
- [true i false, operatory](../operators/true-false-operators.md)
