---
description: throw — odwołanie w C#
title: throw — odwołanie w C#
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
ms.openlocfilehash: 4cad4810b89f976f92ce576917feb2398acce636
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142040"
---
# <a name="throw-c-reference"></a>throw (odwołanie w C#)

Sygnalizuje wystąpienie wyjątku podczas wykonywania programu.  
  
## <a name="remarks"></a>Uwagi

Składnia `throw` :

```csharp
throw [e];
```

gdzie `e` to wystąpienie klasy pochodnej <xref:System.Exception?displayProperty=nameWithType> . Poniższy przykład używa instrukcji, `throw` Aby zgłosić, <xref:System.IndexOutOfRangeException> czy argument przesłany do metody o nazwie nie `GetNumber` odpowiada prawidłowemu indeksowi tablicy wewnętrznej.

[!code-csharp[csrefKeyword#1](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]

Metody wywołujące używają następnie `try-catch` bloku lub `try-catch-finally` do obsługi zgłoszonego wyjątku. Poniższy przykład obsługuje wyjątek zgłoszony przez `GetNumber` metodę.

[!code-csharp[csrefKeyword#2](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]

## <a name="re-throwing-an-exception"></a>Ponowne zgłaszanie wyjątku

`throw` można go również użyć w `catch` bloku, aby ponownie zgłosić wyjątek obsłużony w `catch` bloku.  W tym przypadku nie `throw` przyjmuje operandu wyjątku. Jest to najbardziej przydatne, gdy metoda przekazuje argument od wywołującego do innej metody biblioteki, a metoda Library zgłasza wyjątek, który musi zostać przekazana do obiektu wywołującego. Na przykład poniższy przykład generuje ponownie zdarzenie <xref:System.NullReferenceException> , które jest zgłaszane podczas próby pobrania pierwszego znaku niezainicjowanego ciągu.

[!code-csharp[csrefKeyword#3](~/samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]

> [!IMPORTANT]
> Możesz również użyć `throw e` składni w `catch` bloku, aby utworzyć wystąpienie nowego wyjątku przekazywanego do obiektu wywołującego. W takim przypadku śledzenie stosu oryginalnego wyjątku, który jest dostępny we <xref:System.Exception.StackTrace> właściwości, nie jest zachowywane.

## <a name="the-throw-expression"></a>`throw`Wyrażenie

Począwszy od języka C# 7,0, `throw` można użyć jako wyrażenia, a także instrukcji. Pozwala to na wyrzucanie wyjątku w kontekstach, które były wcześniej nieobsługiwane. Należą do nich następujące elementy:

- [operator warunkowy](../operators/conditional-operator.md). Poniższy przykład używa wyrażenia, `throw` Aby zgłosić, <xref:System.ArgumentException> czy metoda jest przenoszona pustą tablicę ciągów. Przed C# 7,0, ta logika musi pojawić się w `if` / `else` instrukcji.

   [!code-csharp[csrefKeyword#4](~/samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]

- [operator łączenia wartości null](../operators/null-coalescing-operator.md). W poniższym przykładzie `throw` wyrażenie jest używane z operatorem łączenia wartości null, aby zgłosić wyjątek, jeśli ciąg przypisany do `Name` właściwości jest `null` .

   [!code-csharp[csrefKeyword#5](~/samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]

- wyrażenie wyrażenia [lambda](../operators/lambda-expressions.md) lub metody. Poniższy przykład ilustruje metodę zanikającą z wyrażenia, która zgłasza, <xref:System.InvalidCastException> ponieważ konwersja do <xref:System.DateTime> wartości nie jest obsługiwana.

   [!code-csharp[csrefKeyword#6](~/samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [try-catch](try-catch.md)
- [Słowa kluczowe języka C#](index.md)
- [Instrukcje: Jawne zgłaszanie wyjątków](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
