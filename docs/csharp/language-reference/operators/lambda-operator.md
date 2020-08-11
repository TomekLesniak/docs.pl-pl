---
title: Operator> — odwołanie w C#
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 30e1a3546f83a0a1ba5b1363238878868e94ab93
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063136"
---
# <a name="-operator-c-reference"></a>=> — operator (odwołanie w C#)

`=>`Token jest obsługiwany w dwóch formach: jako [operator lambda](#lambda-operator) oraz jako separator nazwy elementu członkowskiego i implementacji elementu członkowskiego w [definicji treści wyrażenia](#expression-body-definition).

## <a name="lambda-operator"></a>Operator lambda

W [wyrażeniach lambda](lambda-expressions.md)operator lambda `=>` oddziela parametry wejściowe po lewej stronie od treści lambda po prawej stronie.

W poniższym przykładzie użyto funkcji [LINQ](../../programming-guide/concepts/linq/index.md) z składnią metody, aby pokazać użycie wyrażeń lambda:

[!code-csharp-interactive[infer types of input variables](snippets/shared/LambdaOperator.cs#InferredTypes)]

Parametry wejściowe wyrażenia lambda są silnie wpisywane w czasie kompilacji. Gdy kompilator może wywnioskować typy parametrów wejściowych, jak w poprzednim przykładzie, można pominąć deklaracje typu. Jeśli musisz określić typ parametrów wejściowych, należy to zrobić dla każdego parametru, jak pokazano w poniższym przykładzie:

[!code-csharp-interactive[specify types of input variables](snippets/shared/LambdaOperator.cs#ExplicitTypes)]

Poniższy przykład pokazuje, jak zdefiniować wyrażenie lambda bez parametrów wejściowych:

[!code-csharp-interactive[without input variables](snippets/shared/LambdaOperator.cs#WithoutInput)]

Aby uzyskać więcej informacji, zobacz [wyrażenia lambda](lambda-expressions.md).

## <a name="expression-body-definition"></a>Definicja treści wyrażenia

Definicja treści wyrażenia ma następującą składnię ogólną:

```csharp
member => expression;
```

gdzie `expression` jest prawidłowym wyrażeniem. Zwracany typ elementu `expression` musi być niejawnie konwertowany na typ zwracany elementu członkowskiego. Jeśli typem zwracanym elementu członkowskiego jest `void` lub, jeśli element członkowski jest konstruktorem, finalizatorem lub właściwością, lub typem `set` dostępu indeksatora, `expression` musi być [*wyrażeniem instrukcji*](~/_csharplang/spec/statements.md#expression-statements). Ze względu na to, że wynik wyrażenia jest odrzucany, zwracany typ wyrażenia może być dowolnym typem.

W poniższym przykładzie przedstawiono definicję treści wyrażenia dla `Person.ToString` metody:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

Jest to skrócona wersja następującej definicji metody:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

Definicje treści wyrażenia dla metod, operatorów i właściwości tylko do odczytu są obsługiwane począwszy od języka C# 6. Definicje treści wyrażenia dla konstruktorów, finalizatorów i metod dostępu właściwości i indeksatora są obsługiwane począwszy od języka C# 7,0.

Aby uzyskać więcej informacji, zobacz [elementy członkowskie z wyrażeniami](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Przeciążanie operatora

`=>`Operator nie może być przeciążony.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji na temat operatora lambda, zobacz sekcję [wyrażenia funkcji anonimowej](~/_csharplang/spec/expressions.md#anonymous-function-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
