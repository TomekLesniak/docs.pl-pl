---
title: wyrażenia wartości domyślnych — odwołanie w C#
description: Użyj wyrażeń wartości domyślnych, aby uzyskać wartość domyślną typu
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: c07eb8e50dc2ec3413882fa841d2f896b28d2e8d
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556712"
---
# <a name="default-value-expressions-c-reference"></a>wyrażenia wartości domyślnych (odwołanie w C#)

Domyślne wyrażenie wartości generuje [wartość domyślną](../builtin-types/default-values.md) typu. Istnieją dwa rodzaje wyrażeń wartości domyślnych: [domyślnego wywołania operatora](#default-operator) i [domyślnego literału](#default-literal).

Możesz również użyć `default` słowa kluczowego jako domyślnej etykiety case w [ `switch` instrukcji](../keywords/switch.md).

## <a name="default-operator"></a>default, operator

Argument `default` operatora musi być nazwą typu lub parametrem typu, jak pokazano w poniższym przykładzie:

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a>domyślny literał

Począwszy od języka C# 7,1, można użyć `default` literału, aby utworzyć wartość domyślną typu, gdy kompilator może wywnioskować typ wyrażenia. `default`Wyrażenie literału zwraca tę samą wartość, co `default(T)` wyrażenie, gdzie `T` jest typem wywnioskowanym. Literału można użyć `default` w dowolnym z następujących przypadków:

- W przypisaniu lub inicjacji zmiennej.
- W deklaracji wartości domyślnej dla [opcjonalnego parametru metody](../../methods.md#optional-parameters-and-arguments).
- W wywołaniu metody, aby podać wartość argumentu.
- W [ `return` instrukcji](../keywords/return.md) lub jako wyrażenie w [składowej](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)zawierającej wyrażenie.

W poniższym przykładzie pokazano użycie `default` literału:

[!code-csharp-interactive[default literal](snippets/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia wartości domyślnej](~/_csharplang/spec/expressions.md#default-value-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

Aby uzyskać więcej informacji na temat `default` literału, zapoznaj się z [uwagami](~/_csharplang/proposals/csharp-7.1/target-typed-default.md)dotyczącymi funkcji.

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [Wartości domyślne typów C#](../builtin-types/default-values.md)
- [Typy ogólne w .NET](../../../standard/generics/index.md)
