---
description: operator delegata — odwołanie w C#
title: operator delegata — odwołanie w C#
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dfaaf40c0f5a19534adef3be7e3c917bc95c4a8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122254"
---
# <a name="delegate-operator-c-reference"></a>Delegate — operator (odwołanie w C#)

`delegate`Operator tworzy anonimową metodę, która może zostać przekonwertowana na typ delegata:

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> Począwszy od języka C# 3 wyrażenia lambda zapewniają bardziej zwięzły i jednoznaczny sposób tworzenia anonimowej funkcji. Użyj [operatora =>](lambda-operator.md) , aby utworzyć wyrażenie lambda:
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> Aby uzyskać więcej informacji na temat funkcji wyrażeń lambda, na przykład przechwytywania zmiennych zewnętrznych, zobacz [lambda Expressions](lambda-expressions.md).

Gdy używasz `delegate` operatora, możesz pominąć listę parametrów. W takim przypadku utworzona Metoda anonimowa może zostać przekonwertowana na typ delegata z dowolną listą parametrów, co ilustruje poniższy przykład:

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

Jest to jedyna funkcja metod anonimowych, które nie są obsługiwane przez wyrażenia lambda. We wszystkich innych przypadkach wyrażenie lambda jest preferowanym sposobem pisania kodu śródwierszowego.

Możesz również użyć `delegate` słowa kluczowego, aby zadeklarować [typ delegata](../builtin-types/reference-types.md#the-delegate-type).

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia funkcji anonimowej](~/_csharplang/spec/expressions.md#anonymous-function-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [=> — operator](lambda-operator.md)
