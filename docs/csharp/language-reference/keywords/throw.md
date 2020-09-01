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
# <a name="throw-c-reference"></a><span data-ttu-id="9b348-103">throw (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="9b348-103">throw (C# Reference)</span></span>

<span data-ttu-id="9b348-104">Sygnalizuje wystąpienie wyjątku podczas wykonywania programu.</span><span class="sxs-lookup"><span data-stu-id="9b348-104">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b348-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9b348-105">Remarks</span></span>

<span data-ttu-id="9b348-106">Składnia `throw` :</span><span class="sxs-lookup"><span data-stu-id="9b348-106">The syntax of `throw` is:</span></span>

```csharp
throw [e];
```

<span data-ttu-id="9b348-107">gdzie `e` to wystąpienie klasy pochodnej <xref:System.Exception?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9b348-107">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9b348-108">Poniższy przykład używa instrukcji, `throw` Aby zgłosić, <xref:System.IndexOutOfRangeException> czy argument przesłany do metody o nazwie nie `GetNumber` odpowiada prawidłowemu indeksowi tablicy wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="9b348-108">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]

<span data-ttu-id="9b348-109">Metody wywołujące używają następnie `try-catch` bloku lub `try-catch-finally` do obsługi zgłoszonego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="9b348-109">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="9b348-110">Poniższy przykład obsługuje wyjątek zgłoszony przez `GetNumber` metodę.</span><span class="sxs-lookup"><span data-stu-id="9b348-110">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]

## <a name="re-throwing-an-exception"></a><span data-ttu-id="9b348-111">Ponowne zgłaszanie wyjątku</span><span class="sxs-lookup"><span data-stu-id="9b348-111">Re-throwing an exception</span></span>

<span data-ttu-id="9b348-112">`throw` można go również użyć w `catch` bloku, aby ponownie zgłosić wyjątek obsłużony w `catch` bloku.</span><span class="sxs-lookup"><span data-stu-id="9b348-112">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="9b348-113">W tym przypadku nie `throw` przyjmuje operandu wyjątku.</span><span class="sxs-lookup"><span data-stu-id="9b348-113">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="9b348-114">Jest to najbardziej przydatne, gdy metoda przekazuje argument od wywołującego do innej metody biblioteki, a metoda Library zgłasza wyjątek, który musi zostać przekazana do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="9b348-114">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="9b348-115">Na przykład poniższy przykład generuje ponownie zdarzenie <xref:System.NullReferenceException> , które jest zgłaszane podczas próby pobrania pierwszego znaku niezainicjowanego ciągu.</span><span class="sxs-lookup"><span data-stu-id="9b348-115">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span>

[!code-csharp[csrefKeyword#3](~/samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]

> [!IMPORTANT]
> <span data-ttu-id="9b348-116">Możesz również użyć `throw e` składni w `catch` bloku, aby utworzyć wystąpienie nowego wyjątku przekazywanego do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="9b348-116">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="9b348-117">W takim przypadku śledzenie stosu oryginalnego wyjątku, który jest dostępny we <xref:System.Exception.StackTrace> właściwości, nie jest zachowywane.</span><span class="sxs-lookup"><span data-stu-id="9b348-117">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>

## <a name="the-throw-expression"></a><span data-ttu-id="9b348-118">`throw`Wyrażenie</span><span class="sxs-lookup"><span data-stu-id="9b348-118">The `throw` expression</span></span>

<span data-ttu-id="9b348-119">Począwszy od języka C# 7,0, `throw` można użyć jako wyrażenia, a także instrukcji.</span><span class="sxs-lookup"><span data-stu-id="9b348-119">Starting with C# 7.0, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="9b348-120">Pozwala to na wyrzucanie wyjątku w kontekstach, które były wcześniej nieobsługiwane.</span><span class="sxs-lookup"><span data-stu-id="9b348-120">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="9b348-121">Należą do nich następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="9b348-121">These include:</span></span>

- <span data-ttu-id="9b348-122">[operator warunkowy](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9b348-122">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="9b348-123">Poniższy przykład używa wyrażenia, `throw` Aby zgłosić, <xref:System.ArgumentException> czy metoda jest przenoszona pustą tablicę ciągów.</span><span class="sxs-lookup"><span data-stu-id="9b348-123">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="9b348-124">Przed C# 7,0, ta logika musi pojawić się w `if` / `else` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="9b348-124">Before C# 7.0, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](~/samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]

- <span data-ttu-id="9b348-125">[operator łączenia wartości null](../operators/null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9b348-125">[the null-coalescing operator](../operators/null-coalescing-operator.md).</span></span> <span data-ttu-id="9b348-126">W poniższym przykładzie `throw` wyrażenie jest używane z operatorem łączenia wartości null, aby zgłosić wyjątek, jeśli ciąg przypisany do `Name` właściwości jest `null` .</span><span class="sxs-lookup"><span data-stu-id="9b348-126">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>

   [!code-csharp[csrefKeyword#5](~/samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]

- <span data-ttu-id="9b348-127">wyrażenie wyrażenia [lambda](../operators/lambda-expressions.md) lub metody.</span><span class="sxs-lookup"><span data-stu-id="9b348-127">an expression-bodied [lambda](../operators/lambda-expressions.md) or method.</span></span> <span data-ttu-id="9b348-128">Poniższy przykład ilustruje metodę zanikającą z wyrażenia, która zgłasza, <xref:System.InvalidCastException> ponieważ konwersja do <xref:System.DateTime> wartości nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="9b348-128">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>

   [!code-csharp[csrefKeyword#6](~/samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="9b348-129">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="9b348-129">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9b348-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9b348-130">See also</span></span>

- [<span data-ttu-id="9b348-131">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="9b348-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9b348-132">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="9b348-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9b348-133">try-catch</span><span class="sxs-lookup"><span data-stu-id="9b348-133">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="9b348-134">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="9b348-134">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9b348-135">Instrukcje: Jawne zgłaszanie wyjątków</span><span class="sxs-lookup"><span data-stu-id="9b348-135">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
